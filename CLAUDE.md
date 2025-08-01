# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Missile Command game implementation with eye-tracking capabilities. The game is a self-contained HTML5 application that runs entirely in the browser.

## Architecture

The application consists of a single `index.html` file containing:
- HTML structure with canvas element for game rendering
- CSS styling for game interface and UI elements
- JavaScript game logic implementing:
  - Player missile bases (3 bases controlled by keyboard)
  - Cities to defend (6 cities)
  - Enemy missiles spawning from top of screen
  - Player missiles fired from bases to intercept
  - Eye tracking crosshair (currently using mouse as fallback)
  - Collision detection and explosion effects
  - Score tracking and game over states

## Key Game Mechanics

1. **Controls**: 
   - B, N, M keys fire missiles from left, middle, and right bases respectively
   - Mouse movement controls crosshair (eye tracking simulation)
   - R key restarts the game after game over

2. **Game Objects**:
   - `PlayerMissile`: Fires from bases toward eye/mouse position
   - `EnemyMissile`: Falls from top targeting cities/bases
   - `Explosion`: Created when missiles explode, can destroy enemy missiles
   - Bases and Cities: Destructible targets

3. **Eye Tracking Integration**:
   - Currently uses mouse movement as fallback
   - Ready for eye tracker API integration (see lines 336-339)
   - Uses eyeX/eyeY coordinates for targeting

## Development Notes

Since this is a single-file HTML application:
- No build process required
- No dependencies or package management
- Can be opened directly in a browser
- All modifications are made to the single `index.html` file

## Running the Game

Simply open `index.html` in a web browser. The game starts automatically and uses the full browser window.

## Eye Tracker Integration

To integrate with a real eye tracker, replace the mouse event listener (lines 330-333) with an eye tracking event listener that updates `eyeX` and `eyeY` coordinates with the eye tracker's gaze position.