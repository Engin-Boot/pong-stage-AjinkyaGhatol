
# Feature

Display game setup page and controls feature on setup page

## Acceptance Criteria

### Scenario: game setup page displays or game setup page loads
  
  Given setup page loaded successfully and game is working

  When game setup page loads

  Then display option to choose number of players

### Scenario: user press one for number of players

  Given setup page is active and game is working

  When user press one button

  Then display user vs bot and option to enter name of player and option
  to choose difficulty level

### Scenario: user selected one for number of players and entered all

### details in setup page

  Given setup page is active and game is working and user entered all
  details in setup page

  When user press start button

  Then transfer control to game_run_page module
  
### Scenario: user press two for number of players

  Given setup page is active and game is working

  When user press two button

  Then display player1 vs player2 and option to enter name of players

### Scenario: user selected two for number of players and entered all

### details in setup page

  Given setup page is active and game is working and user entered all
  details in setup page

  When user press start button

  Then transfer control to game_run_page module
