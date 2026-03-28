# Bot de Aparcamiento PMR (Disabled Parking Bot)

A Telegram bot that helps users find reserved parking spaces for people with reduced mobility (PMR/Discapacitados) using real-time data from OpenStreetMap via the Overpass API.

## Stack

- **Language:** Python 3.12
- **Bot Framework:** python-telegram-bot 20.7 (async)
- **Web Server:** Flask 3.0.0 (keep-alive server on port 5000)
- **Data Source:** Overpass API (OpenStreetMap)
- **HTTP Client:** requests 2.31.0

## Project Structure

- `main.py` — Entry point: starts Flask keep-alive server + Telegram bot
- `bot.py` — Bot logic: command handlers, location handling, Overpass API integration
- `keep_alive.py` — Flask server (port 5000) + self-ping thread to prevent sleep
- `requirements.txt` — Python dependencies

## Features

- Users send their location and the bot finds up to 8 disabled parking spaces within 800m
- Uses the Haversine formula for distance calculations
- Provides Google Maps links for navigation
- Self-ping mechanism keeps the bot alive on Replit

## Environment Variables / Secrets

- `TELEGRAM_TOKEN` — Telegram Bot API token (from @BotFather)

## Running

The workflow `Start application` runs `python main.py`, which:
1. Starts the Flask server on `0.0.0.0:5000`
2. Starts the Telegram bot polling loop
