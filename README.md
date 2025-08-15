# Aninda News Processor

Private GitHub Actions-based news processing system for aninda.org

## Overview

This repository processes RSS feeds from 40+ international news sources, performs intelligent clustering, and generates AI-powered summaries using Google Gemini API. The processed data is stored as JSON files and served via Cloudflare Workers.

## Architecture

- **GitHub Actions**: Processes RSS feeds every 4 hours
- **Google Gemini API**: Generates 5-bullet point summaries using Gemini 1.5 Flash
- **JSON Storage**: Processed data stored in `/data` directory
- **Cloudflare Workers**: Lightweight API to serve processed data

## Sections

- **Global**: 23 international news sources
- **Australia**: 8 Australian news sources  
- **Technology**: 10 technology news sources
- **Medical**: 3 medical/health news sources

## Processing Features

- **Multi-source clustering**: Groups related articles from different sources
- **Popularity scoring**: Ranks stories by significance and coverage
- **AI summaries**: 5-bullet point summaries with proper attribution
- **Trusted sources**: Single-source articles from verified outlets
- **Web scraping**: Supplements RSS with popular article sections

## Setup

1. Set repository secrets:
   - `GEMINI_API_KEY`: Your Google Gemini API key (get from https://aistudio.google.com/app/apikey)

2. GitHub Actions will automatically:
   - Run every 4 hours
   - Process all RSS feeds  
   - Generate AI summaries using Gemini 1.5 Flash
   - Commit updated JSON files

## Manual Trigger

To manually trigger processing:
1. Go to Actions tab
2. Select "Process News Feeds"
3. Click "Run workflow"

## Data Files

- `data/global.json`: Global news clusters
- `data/australia.json`: Australian news clusters  
- `data/technology.json`: Technology news clusters
- `data/medical.json`: Medical news data (4 subsections)