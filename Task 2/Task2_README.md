# Task 2 -- GitHub Trending Repositories Digest

## Overview

Built an n8n workflow that retrieves JavaScript repositories from
GitHub, selects the five repositories with the highest star counts,
fetches the README of the top repository, and sends an email digest
using Gmail.

## APIs Used

**1. GitHub Search Repositories API**

Endpoint: `https://api.github.com/search/repositories`

-   Fetches JavaScript repositories.
-   Sorts results by stars in descending order.
-   Retrieves up to 10 repositories.

**2. GitHub Repository README API**

Endpoint: `https://api.github.com/repos/{owner}/{repo}/readme`

-   Fetches the README of the highest-ranked repository.
-   Provides additional information for the email digest.

## Data Transformation

The Code node: - Sorts repositories by star count in descending order. -
Selects the top five repositories. - Extracts repository details such as
owner, name, stars, URL, and description. - Identifies the
highest-ranked repository. - Prepares the digest text.

The README content is cleaned and formatted before being included in the
email.

## Conditional Logic

An IF node checks whether the top repository has more than 1,000 stars.

-   **True:** Sends the Popular Repositories digest email.
-   **False:** Sends the Low Stars digest email.

Both branches use Gmail to deliver notifications.

## Error Handling

Both HTTP Request nodes have error-output handling configured.

If an API request fails, the workflow routes the error to the Email
Error Alert node, which sends an email notification.

## Testing

-   Successfully executed the workflow manually.
-   Verified that the top five repositories were selected.
-   Tested both IF condition branches.
-   Tested a failed README API request and verified the error alert
    email.

**Note:** The hourly schedule is configured, but automatic hourly
execution has not yet been verified. The first GitHub API failure path
is configured but was not independently tested.

## Credentials

Gmail authentication is managed through n8n Credentials. No Gmail
password or OAuth secret is hard-coded in the workflow.
