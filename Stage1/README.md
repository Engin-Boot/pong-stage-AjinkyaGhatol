# The taste of success

Your game is trending! The installations are encouraging!

## In app purchase

option is in home page module

## Startup Sequence

```mermaid
sequenceDiagram
System->>game_home_page: user press game icon
game_home_page->>game_setup_page: user press play button
game_setup_page->>game_setup_page:choose number of players
alt selected one
        game_setup_page->>game_setup_page:user vs bot
        game_setup_page->>game_setup_page:enter player name
        game_setup_page->>game_setup_page:choose difficulty
        game_setup_page->>game_run_page:press start game
    else selected two
        game_setup_page->>game_setup_page:player1 vs player2
        game_setup_page->>game_setup_page:enter player1 name
        game_setup_page->>game_setup_page:enter player2 name
        game_setup_page->>game_run_page:press start game
end
game_run_page->>game_run_page:user playing game
game_run_page->>game_result_page:game over
game_result_page->>game_popup_page:after 10 seconds timeout
game_popup_page->>game_popup_page:display do you want to play again?
alt selected YES
        game_popup_page->>game_setup_page:selected yes
    else selected NO
        game_popup_page->>game_home_page:selected no
end
game_home_page-->>System: user press exit button
```

_Diagram not visible? Use the
[Mermaid live viewer](https://mermaid-js.github.io/mermaid-live-editor)
or use a [VScode plug-in](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid)_

## Activity flow

```mermaid
graph TD
  A[Start] -->|user started game or press game icon| B(Game home page)
  B -->|click play button| C{choose number of players one/two}
  C -->|One| D[user vs bot]
  C -->|Two| E[player1 vs player2]
  D -->|go to setup| F[enter player name and choose difficulty out of 10]
  F -->|start game| G[game started]

  E -->|go to setup| H[enter player1 name and player2 name]
  H -->|start game| G[game started]
  
  G -->|user playing game| I[game ended]
  I -->|showing result| J[result page]
  J -->|after 10 seconds timeout| K{display popup do you want to play again?}

  K -->|NO| B
  K -->|YES| C

  B -->|user press exit button| L[close game]
```

_Diagram not visible? Use the
[Mermaid live viewer](https://mermaid-js.github.io/mermaid-live-editor)
or use a [VScode plug-in](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid)_
