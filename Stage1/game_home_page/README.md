
# Feature

Display home page and controls feature on home page

## Sequence Flow

```mermaid
sequenceDiagram
system->>home_page_controller:user start game
  home_page_controller->>login/signup:crate account if not exist or login
  login/signup-->>home_page_controller:done
  home_page_controller->>in_app_purchase:user click on buy option
  in_app_purchase->>in_app_purchase:load buying options on screen
  in_app_purchase->>in_app_purchase:user press hard paddles option
  in_app_purchase->>in_app_purchase:load payment gateway site
  in_app_purchase-->>home_page_controller:successfull payment
  home_page_controller->>settings:user press settings
  settings->>settings:load setting options on screen
  settings->>graphic_settings:user press on graphics
  graphic_settings-->>settings:done changes
  settings->>sound_settings:user press on sound icon
  sound_settings-->>settings:done changes
  settings-->>home_page_controller:user press back button
  home_page_controller->>game_setup_page:user press play button
  home_page_controller-->>system:user press exit

```

_Diagram not visible? Use the
[Mermaid live viewer](https://mermaid-js.github.io/mermaid-live-editor)
or use a [VScode plug-in](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid)_

## Acceptance Criteria

### Scenario: user press play button

  Given home page is active and game is working

  When user press play button

  Then module gives control to game_setup_page module
  
### Scenario: user press exit button

  Given home page is active and game is working

  When user press exit button

  Then module gives control to system module
  