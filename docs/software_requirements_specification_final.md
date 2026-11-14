# Smart Solutions — Final Software Requirements Specification

# Overview

This document describes the requirements for the Smart Solutions Life Counter Website for Magic: The Gathering. The website allows two or more players to track their life totals, with no fixed maximum number of players. Each player starts with 20 life points. Users can enter player names, add or subtract life points, add new players, remove players, reset individual players, and reset all players for a new game.

The website runs in a web browser. It starts with two players and allows additional players to be added during a game. At least two players must remain. Game data is not saved after the page is refreshed or closed. Commander mode is a future enhancement and is outside the current scope.

# Software Requirements

The functional requirements describe what the website shall do. The non-functional requirements describe how well it shall work.

## Functional Requirements

### 1. Player Setup and Management

| ID | Requirement |
| --- | --- |
| FR1 | The website shall provide life counters for two or more players, with no fixed maximum number of players. |
| FR2 | The website shall provide a separate name input field for each player. |
| FR3 | The website shall limit each player name to 40 characters. |
| FR4 | The website shall allow users to change any player's name during a game. |
| FR5 | The website shall provide an Add Player button that creates a new player with a starting life total of 20. |

### 2. Life Total Display and Player Removal

| ID | Requirement |
| --- | --- |
| FR6 | The website shall initialize two players with 20 life points each when the page first loads. |
| FR7 | The website shall display each player's life total in that player's section. |
| FR8 | The website shall update the displayed life total after a valid addition or subtraction. |
| FR9 | The website shall keep all other players' life totals unchanged when one player's life total is adjusted. |
| FR10 | The website shall allow users to remove a player while preventing the number of players from dropping below two. |

### 3. Adding and Subtracting Life

| ID | Requirement |
| --- | --- |
| FR11 | The website shall provide a separate life adjustment amount field for each player. |
| FR12 | The website shall initialize each player's life adjustment amount field to 1. |
| FR13 | The website shall allow users to change any player's adjustment amount. |
| FR14 | The website shall add the entered valid amount to the selected player's life total when Add is clicked. |
| FR15 | The website shall subtract the entered valid amount from the selected player's life total when Subtract is clicked. |

### 4. Input Validation

| ID | Requirement |
| --- | --- |
| FR16 | The website shall reject a life adjustment when the amount field is empty. |
| FR17 | The website shall reject adjustment amounts of zero or less. |
| FR18 | The website shall reject adjustment amounts that are not whole numbers. |
| FR19 | The website shall display an error message when an adjustment amount is rejected. |
| FR20 | The website shall keep all players' life totals unchanged when an invalid life adjustment is rejected. |

### 5. Resetting the Game

| ID | Requirement |
| --- | --- |
| FR21 | The website shall provide a Reset All button that resets all current players' life totals in one action. |
| FR22 | The website shall return all current players' life totals to 20 when Reset All is clicked. |
| FR23 | The website shall keep all current players' names unchanged when Reset All is clicked. |
| FR24 | The website shall provide a Reset Player button that resets only the selected player's life total to 20 without changing other players' totals. |
| FR25 | The website shall preserve the current number of players when Reset All is clicked. |

## Non-Functional Requirements

### 1. Ease of Use

| ID | Requirement |
| --- | --- |
| NFR1 | The website shall clearly label the life adjustment buttons Add and Subtract. |
| NFR2 | The website shall clearly label the Add Player, Remove Player, Reset Player, and Reset All buttons. |
| NFR3 | The website shall display a visible label for every player name and adjustment amount field. |
| NFR4 | The website shall display each input error message within the affected player's section. |
| NFR5 | The website shall explain in the invalid amount message that users must enter a positive whole number. |

### 2. Accessibility

| ID | Requirement |
| --- | --- |
| NFR6 | The website shall allow users to reach every enabled input field, enabled button, and link using the Tab key. |
| NFR7 | The website shall display a visible focus indicator on the field, button, or link selected using the keyboard. |
| NFR8 | The website shall allow users to activate every enabled button using the keyboard. |
| NFR9 | The website shall provide programmatically associated labels so a screen reader can identify each input field. |
| NFR10 | The website shall visually distinguish disabled Remove Player buttons when only two players remain. |

### 3. Response Time

The following response times apply after the page has fully loaded.

| ID | Requirement |
| --- | --- |
| NFR11 | The website shall display the updated life total within one second after Add is activated with a valid amount. |
| NFR12 | The website shall display the updated life total within one second after Subtract is activated with a valid amount. |
| NFR13 | The website shall display updated life totals within one second after Reset Player or Reset All is activated. |
| NFR14 | The website shall display an error message within one second after an invalid adjustment is attempted. |
| NFR15 | The website shall complete player management, life adjustments, and resets without reloading the page or waiting for a server response. |

### 4. Browser and Screen Compatibility

Browser checks shall use the latest stable browser versions available at the time of final testing. The tested versions shall be recorded.

| ID | Requirement |
| --- | --- |
| NFR16 | The website shall support player management, life adjustments, and resetting in Chrome, Firefox, Edge, and Safari. |
| NFR17 | The website shall display player cards vertically on narrow mobile screens without overlapping controls. |
| NFR18 | The website shall display player cards in a responsive layout at desktop screen widths. |
| NFR19 | The website shall allow users to access all controls without horizontal scrolling at viewport widths from 375 to 1280 pixels. |
| NFR20 | The website shall keep all fields and buttons usable at 200% browser zoom on a desktop screen. |

### 5. Reliability and Calculation Accuracy

| ID | Requirement |
| --- | --- |
| NFR21 | The website shall produce the expected life total after each step in a test of 20 consecutive valid additions and subtractions. |
| NFR22 | The website shall keep all other players' life totals unchanged when adjustments are made to one player. |
| NFR23 | The website shall keep all life totals unchanged when tested with empty, zero, negative, and decimal adjustment amounts. |
| NFR24 | The website shall maintain the correct player count and corresponding life totals when players are added or removed. |
| NFR25 | The website shall reject an adjustment that would produce a total outside JavaScript's safe integer range, from -9007199254740991 to 9007199254740991, without changing any player's life total. |

# Change Management Plan

This plan describes how the Smart Solutions team will introduce the Life Counter website to staff who organize Magic: The Gathering games at a local game store. The game store is an assumed customer for this plan.

## 1. Introduce the Website

The team will meet with the store organizer to explain the website's purpose and demonstrate its main functions. We will explain that the website starts with two players, supports additional players without a fixed maximum, and allows users to remove players while keeping at least two. Each player starts with 20 life points. Commander mode is not included. We will ask staff about their current life tracking method and any concerns about using the website.

## 2. Train Users

The team will provide a short demonstration and written instructions. Staff will practice entering player names, adding players, removing players, adding and subtracting life, resetting individual players, and resetting all players.

They will also try an invalid adjustment amount to learn how to correct an input error. We will explain that resetting life totals preserves player names, while refreshing or closing the page clears the current game.

## 3. Fit the Website into Existing Work

Staff will open the website in a browser on a phone, tablet, or computer. No account, software installation, or database connection is required.

Before use, we will check that the store's devices and network can access the website. The organizer can bookmark the link or add it to the store's existing event instructions. No connection to payment or customer record systems is planned.

## 4. Run a Small Trial

Before wider use, a small group of players will try the website during a practice game. The trial will include games with two players and more than two players.

A staff member will also record life totals on paper to check the results. The team will collect feedback about adding and removing players, life adjustments, reset functions, screen layout, and instructions.

Any issue that causes incorrect totals or prevents a main function from working will be fixed and tested before wider use.

## 5. Report and Resolve Problems

Users will report problems to the store organizer, who will share them with the project team.

Each report will include the device, browser, steps taken, expected result, and actual result. The team will record the issue in GitHub Issues and assign an owner.

Problems involving incorrect totals or unusable controls will be handled before minor appearance issues. After a fix, the team will repeat the reported steps and check the main functions before closing the issue.

## 6. Review and Release Changes

Puja and Bryan will review proposed changes together. They will consider the benefit, effort, and effect on the agreed requirements.

Approved changes will be recorded in GitHub and tested before release. The team will update the SRS, diagrams, and user instructions when behavior changes.

If a release causes a serious problem, the team will restore the last working version while preparing a fix. Staff will be advised to use paper tracking until the website works correctly again.

# Traceability Links

These tables connect the multiplayer Life Counter Website diagrams to the requirements they represent.

## Class Diagram Traceability

| Artifact Name | Requirement ID | Connection |
| --- | --- | --- |
| Website UI | FR2, FR7, FR8, FR19 | Displays player information, life totals, and input error messages. |
| Player Management | FR1, FR5, FR6, FR10 | Manages multiple players and maintains a minimum of two players. |
| Player | FR3, FR4, FR7, FR14, FR15 | Represents individual player information and life adjustments. |
| Reset Player | FR24 | Resets the selected player's life total to 20. |
| Reset All | FR21, FR22, FR23, FR25 | Resets all life totals while preserving player names and player count. |

## Sequence Diagram Traceability

| Artifact ID | Artifact Name | Requirement ID |
| --- | --- | --- |
| SEQ1 | Add a new player | FR1, FR5 |
| SEQ1 | Subtract life points from the selected player | FR8, FR9, FR15 |
| SEQ1 | Reset an individual player | FR24 |
| SEQ1 | Remove a player while maintaining a minimum of two players | FR10 |
| SEQ1 | Reset all players | FR21, FR22, FR23, FR25 |
## State Machine Diagram Traceability

| Artifact ID | Artifact Name | Requirement ID |
| --- | --- | --- |
| STATE1 | Initialize a player with 20 life points | FR5, FR6 |
| STATE1 | Track life additions and subtractions | FR14, FR15 |
| STATE1 | Reject invalid life adjustments | FR16, FR17, FR18, FR19, FR20 |
| STATE1 | Reset life totals to 20 | FR22, FR24 |
| STATE1 | Remove a player while maintaining a minimum of two players | FR10 |

The updated class, sequence, and state machine diagrams are included in [Multiplayer Life Counter Diagrams](../artifacts/Multiplayer_Life_Counter_Diagrams.pdf).
