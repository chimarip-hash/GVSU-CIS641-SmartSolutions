# Smart Solutions — Final Software Requirements Specification

# Overview

This document describes the requirements for the Smart Solutions Life Counter Website for Magic: The Gathering. The website helps two players track their life totals. Each player starts with 20 life points. Users can enter player names, add or subtract life points, and reset the game.

The current version runs in a web browser. Game data is not saved after the page is refreshed or closed. Commander mode is a future feature and is outside the current scope.

# Software Requirements

The functional requirements describe what the website shall do. The non-functional requirements describe how well it shall work.

## Functional Requirements

### 1. Player Setup

| ID | Requirement |
| --- | --- |
| FR1 | The website shall provide life counters for exactly two players. |
| FR2 | The website shall provide a separate name input field for each player. |
| FR3 | The website shall limit each player name to 40 characters. |
| FR4 | The website shall allow users to change either player's name during a game. |
| FR5 | The website shall keep both life totals unchanged when a player name is edited. |
### 2. Life Total Display

| ID | Requirement |
| --- | --- |
| FR6 | The website shall set both players' life totals to 20 when the page first loads. |
| FR7 | The website shall display each player's life total in that player's section. |
| FR8 | The website shall update the displayed life total after a valid addition or subtraction. |
| FR9 | The website shall keep the other player's life total unchanged when one player's total is adjusted. |
| FR10 | The website shall display life totals of zero or less without changing them to a different value. |

### 3. Adding and Subtracting Life

| ID | Requirement |
| --- | --- |
| FR11 | The website shall provide a separate life adjustment amount field for each player. |
| FR12 | The website shall set both adjustment amount fields to 1 when the page first loads. |
| FR13 | The website shall allow users to change either player's adjustment amount. |
| FR14 | The website shall add the entered valid amount to the selected player's life total when Add is clicked. |
| FR15 | The website shall subtract the entered valid amount from the selected player's life total when Subtract is clicked. |
### 4. Input Validation

| ID | Requirement |
| --- | --- |
| FR16 | The website shall reject a life adjustment when the amount field is empty. |
| FR17 | The website shall reject adjustment amounts of zero or less. |
| FR18 | The website shall reject adjustment amounts that are not whole numbers. |
| FR19 | The website shall display an error message when an adjustment amount is rejected. |
| FR20 | The website shall keep both life totals unchanged when an adjustment is rejected. |

### 5. Resetting the Game

| ID | Requirement |
| --- | --- |
| FR21 | The website shall provide a Reset button that resets both players in one action. |
| FR22 | The website shall return both players' life totals to 20 when Reset is clicked. |
| FR23 | The website shall keep both player names unchanged when Reset is clicked. |
| FR24 | The website shall return both adjustment amount fields to 1 when Reset is clicked. |
| FR25 | The website shall clear all displayed input error messages when Reset is clicked. |
## Non-Functional Requirements

### 1. Ease of Use

| ID | Requirement |
| --- | --- |
| NFR1 | The website shall label each addition button "Add" and each subtraction button "Subtract." |
| NFR2 | The website shall label the game reset button "Reset." |
| NFR3 | The website shall display a visible label for every player name and adjustment amount field. |
| NFR4 | The website shall display each input error message within the affected player's section. |
| NFR5 | The website shall explain in the invalid amount message that users must enter a positive whole number. |

### 2. Accessibility

| ID | Requirement |
| --- | --- |
| NFR6 | The website shall allow users to reach every input field, button, and link using the Tab key. |
| NFR7 | The website shall display a visible focus indicator on the field, button, or link selected using the keyboard. |
| NFR8 | The website shall allow users to activate every button using the keyboard. |
| NFR9 | The website shall provide programmatically associated labels so a screen reader can identify each input field. |
| NFR10 | The website shall announce updated life totals to screen readers without requiring users to move focus to the total. |
### 3. Response Time

The following response times apply after the page has fully loaded.

| ID | Requirement |
| --- | --- |
| NFR11 | The website shall display the updated life total within one second after Add is activated with a valid amount. |
| NFR12 | The website shall display the updated life total within one second after Subtract is activated with a valid amount. |
| NFR13 | The website shall display both reset life totals within one second after Reset is activated. |
| NFR14 | The website shall display an error message within one second after an invalid adjustment is attempted. |
| NFR15 | The website shall complete life adjustments and resets without reloading the page or waiting for a server response. |

### 4. Browser and Screen Compatibility

Browser checks shall use the latest stable browser versions available at the time of final testing. The tested versions shall be recorded.

| ID | Requirement |
| --- | --- |
| NFR16 | The website shall support player name entry, life adjustments, and reset in Chrome, Firefox, Edge, and Safari. |
| NFR17 | The website shall display all fields, buttons, and life totals without overlap at a viewport width of 375 pixels. |
| NFR18 | The website shall display all fields, buttons, and life totals without overlap at a viewport width of 1280 pixels. |
| NFR19 | The website shall allow users to access all controls without horizontal scrolling at viewport widths from 375 to 1280 pixels. |
| NFR20 | The website shall keep all fields and buttons usable at 200% browser zoom on a desktop screen. |

### 5. Reliability and Calculation Accuracy

| ID | Requirement |
| --- | --- |
| NFR21 | The website shall produce the expected life total after each step in a test of 20 consecutive valid additions and subtractions. |
| NFR22 | The website shall keep the other player's life total unchanged throughout a test of 20 adjustments to one player. |
| NFR23 | The website shall keep both life totals unchanged when tested with empty, zero, negative, and decimal adjustment amounts. |
| NFR24 | The website shall return both life totals to 20 after each of five consecutive Reset actions. |
| NFR25 | The website shall reject an adjustment that would produce a total outside JavaScript's safe integer range, from -9007199254740991 to 9007199254740991, without changing either life total. |
# Change Management Plan

This plan describes how we will introduce the Life Counter website to staff who organize Magic: The Gathering games at a local game store. The game store is an assumed customer for this plan.

## 1. Introduce the Website

The team will meet with the store organizer to explain the website's purpose and demonstrate its main functions. We will explain that the current version supports two players starting with 20 life points. Commander mode is not included. We will ask staff about their current life tracking method and any concerns about using the website.

## 2. Train Users

The team will provide a short demonstration and written instructions. Staff will practice entering player names, adding life, subtracting life, and resetting a game. They will also try an invalid amount to learn how to correct an input error. We will explain that Reset keeps player names, but refreshing or closing the page clears the game data.

## 3. Fit the Website into Existing Work

Staff will open the website in a browser on a phone, tablet, or computer. No account, software installation, or database connection is required. Before use, we will check that the store's devices and network can access the website. The organizer can bookmark the link or add it to the store's existing event instructions. No connection to payment or customer record systems is planned.

## 4. Run a Small Trial

Before wider use, two players will try the website during one practice game. A staff member will also record life totals on paper to check the results. The team will collect feedback about the controls, screen layout, and instructions. Any issue that causes incorrect totals or prevents a main function from working will be fixed and tested before wider use.

## 5. Report and Resolve Problems

Users will report problems to the store organizer, who will share them with the project team. Each report will include the device, browser, steps taken, expected result, and actual result. The team will record the issue in GitHub Issues and assign an owner. Problems involving incorrect totals or unusable controls will be handled before minor appearance issues. After a fix, the team will repeat the reported steps and check the main functions before closing the issue.

## 6. Review and Release Changes

Puja and Bryan will review proposed changes together. They will consider the benefit, effort, and effect on the agreed requirements. Approved changes will be recorded in GitHub and tested before release. The team will update the SRS and user instructions when behavior changes. If a release causes a serious problem, the team will restore the last working version while preparing a fix. Staff will be advised to use paper tracking until the website works correctly again.
# Traceability Links

These tables connect the project diagrams to the requirements they represent. The class names below match the labels in the previously submitted class diagram.

## Class Diagram Traceability

| Artifact Name | Requirement ID | Connection |
| --- | --- | --- |
| Life Counter | FR7, FR8 | Displays the player's life total and updates it after an adjustment. |
| Gain Life | FR14 | Adds the entered amount to the player's life total. |
| Lose Life | FR15 | Subtracts the entered amount from the player's life total. |
| Reset Button | FR22 | Returns the life total to 20 for a new game. |
## Sequence Diagram Traceability

| Artifact ID | Artifact Name | Requirement ID |
| --- | --- | --- |
| SEQ1 | Subtract 5 life points and display the updated total | FR15, FR8 |

## State Machine Diagram Traceability

| Artifact ID | Artifact Name | Requirement ID |
| --- | --- | --- |
| STATE1 | Initialize the LifeCounter with 20 life points | FR6 |
| STATE1 | Add or subtract life points while tracking life | FR14, FR15 |
| STATE1 | Reset the LifeCounter to 20 life points | FR22 |

Both diagrams are included in [Sequence and State Diagrams](../artifacts/Puja_Chimariya_Sequence_State_Diagrams.pdf).
