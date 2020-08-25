# Feature

Controls movement of ball and slider according to user input
Counts result or score of gameplay

## Acceptance Criteria

### Scenario: Game is completed or game is over

  Given game run page is active and game is working

  When Game is completed

  Then module gives control to game_result_page module
sequenceDiagram
  
  
# Sequence Flow

```mermaid
game_setup_page->>layout_updater: user press start game
layout_updater->>layout_updater: display layout in user interface
layout_updater->>ball_coordinates_updater_plus_score_counter: start
ball_coordinates_updater_plus_score_counter->>slider_coordinates_updater: start
  
par layout_updater
layout_updater->>layout_updater: display layout in user interface
and slider cordinates
slider_coordinates_updater->>slider_coordinates_updater:update slider coordinates
and count score and upate ball position
ball_coordinates_updater_plus_score_counter->>ball_coordinates_updater_plus_score_counter:upadte ball coordinates and count score
end
ball_coordinates_updater_plus_score_counter->>game_result_page:game over
```

_Diagram not visible? Use the
[Mermaid live viewer](https://mermaid-js.github.io/mermaid-live-editor)
or use a [VScode plug-in](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid)_
