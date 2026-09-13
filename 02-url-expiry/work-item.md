# URL Expiry

## User Story

As a visitor, I want to optionally set an expiry when creating a short URL so that I can limit how long the link is available.

## Acceptance Criteria

- **Given** a visitor is on the URL creation form, **when** they view the page, **then** they can see an optional expiry selector with **Never**, **In 24 hours**, **In 7 days**, and **On a specific date** options.
- **Given** a visitor selects an expiry option, **when** they choose **Shorten URL**, **then** the short URL is created with the selected expiry.
- **Given** a visitor leaves the expiry set to **Never**, **when** they choose **Shorten URL**, **then** the short URL is created without an expiry.
- **Given** a short URL is created with or without an expiry, **when** URL creation completes, **then** the visitor can see the generated short URL in a result area.
