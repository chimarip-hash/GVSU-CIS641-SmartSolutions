# Overview

This document describes the requirements for the Smart Solutions Life Counter Website for Magic: The Gathering. The current version will help two players track their life totals, add or subtract life points, and reset the totals for a new game.

# Functional Requirements

## Player Setup

- FR1: The website shall allow users to enter a name for each of the two players.
- FR2: The website shall display both players' names and life totals at the same time.

## Starting Life Total

- FR3: The website shall set each player's starting life total to 20 points.

## Adding and Subtracting Life

- FR4: The website shall allow users to enter a positive whole-number amount to add to a selected player's life total.
- FR5: The website shall allow users to enter a positive whole-number amount to subtract from a selected player's life total.

## Resetting the Game

- FR6: The website shall provide a Reset button that returns both players' life totals to 20 points.

# Non-Functional Requirements

## Response Time

- NFR1: The website shall display the updated life total within one second after the user adds or subtracts life points.

## Browser Compatibility

- NFR2: The website shall support player setup, adding life, subtracting life, and resetting in Chrome, Firefox, Edge, and Safari.

## Screen Layout

- NFR3: The website shall display player names, life totals, input fields, and buttons without overlapping at screen widths of 375 pixels and 1280 pixels.

## Clear Labels

- NFR4: The website shall label the life adjustment buttons "Add" and "Subtract" and the game reset button "Reset."

## Calculation Accuracy

- NFR5: The website shall produce the correct whole-number life total after each addition or subtraction, including a test of 20 consecutive life adjustments.

# Future Enhancement

Commander mode may be added in a future version with a starting life total of 40 points. Commander mode is outside the scope of the current version.
