# Feature

Controls all modules in game_run_page module
It loads layout file in display

## Acceptance criteria

### Scenario: User has not done login

given game is working and system has internet access
when user starts game and user has not login
Then transfer control to login/signup module

### Scenario: user press in app purchase icon

given game is working and system has internet access
when user press in app purchase icon
then transfer control to in_app_purchase module

### Scenario: user press settings icon

given game is working
when user press settings icon
then transfer control to settings module

### Scenario: user press play icon

given game is working
when user press play icon
then transfer control to game_setup_page module and also transfer user details
like in app purchase details to game_setup_page module

### Scenario: user press exit

given game is working
when user press exit icon
then close game and transfer control to system
