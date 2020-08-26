# Feature

Controls movement of ball and slider according to user input
Counts result or score of gameplay

## Sequence Flow

```mermaid
sequenceDiagram
  game_setup_page->>run_page_controller: user press start game
  run_page_controller->>layout_updater:start thread1
  run_page_controller->>ball_plus_score:start thread2
  run_page_controller->>slider_coordinates_updater:start thread3
  layout_updater->>layout_updater: display layout in user interface

  
  par layout update
    loop every fps
    layout_updater-->>layout_updater: display layout in user interface
    end
  and update slider coordinates
    loop every 10ms
    slider_coordinates_updater-->>slider_coordinates_updater:update slider coordinates
    end
  and count score and upate ball position
    loop every 10ms
ball_plus_score-->>ball_plus_score:upadte ball coordinates and count score
    end
  end
ball_plus_score->>run_page_controller:game over(one of player reach score of 10)
  run_page_controller->>layout_updater:end thread1
  run_page_controller->>ball_plus_score:end thread2
  run_page_controller->>slider_coordinates_updater:end thread3
  run_page_controller->>game_result_page:show result

```

_Diagram not visible? Use the
[Mermaid live viewer](https://mermaid-js.github.io/mermaid-live-editor)
or use a [VScode plug-in](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid)_

## Acceptance Criteria

### Scenario: Game is completed or game is over

  Given game run page is active and game is working

  When Game is completed

  Then module gives control to game_result_page module