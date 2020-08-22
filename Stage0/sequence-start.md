# Interaction Sequences

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

## Movement Initiation

-describe-how-modules-interact-to-make-the-ball-move

## One score

-describe-how-the-modules-interact-to-record-scores
