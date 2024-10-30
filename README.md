# GitHub User Data Scraper

## Overview
This project scrapes GitHub for users located in Tokyo with over 200 followers and collects their repository information. The scraped data is stored in CSV files for further analysis.

## Features
- Fetches user information from GitHub's API.
- Collects repository details for each user.
- Saves the data in two CSV files: `users.csv` and `repositories.csv`.

## CSV File Structures

### `users.csv`
Contains information about each user with the following fields:
- **login**: GitHub user ID
- **name**: Full name of the user
- **company**: Company they work at (trimmed, stripped of leading @, converted to UPPERCASE)
- **location**: City they are in
- **email**: Email address (if available)
- **hireable**: Whether they are open to being hired (true/false)
- **bio**: Short bio about the user
- **public_repos**: Number of public repositories
- **followers**: Number of followers
- **following**: Number of people they are following
- **created_at**: Date when they joined GitHub

### `repositories.csv`
Contains public repositories for each user with the following fields:
- **login**: GitHub user ID (login)
- **full_name**: Full name of the repository
- **created_at**: Date when the repository was created
- **stargazers_count**: Number of stars the repository has
- **watchers_count**: Number of watchers the repository has
- **language**: Programming language of the repository
- **has_projects**: Whether the repository has projects enabled (true/false)
- **has_wiki**: Whether the repository has a wiki (true/false)
- **license_name**: Name of the license the repository is under (if available)

## How Data Was Scraped
1. **GitHub API**: The GitHub API was utilized to search for users based on their location (Tokyo) and follower count (greater than 200). 
2. **Pagination Handling**: The script was designed to handle pagination, allowing it to retrieve more than the default limit of results returned by the API.
3. **User and Repository Details**: For each user found, additional requests were made to gather detailed user information and their public repositories.
4. **Data Storage**: The collected data was stored in two separate CSV files (`users.csv` and `repositories.csv`) for easy access and analysis.

## Interesting Findings
During the analysis of the data, one surprising fact emerged: a significant portion of users had a remarkably high number of public repositories despite having relatively few followers. This indicates that many developers are actively contributing to open source or personal projects but may not have gained visibility within the GitHub community.

## Recommendations
Based on the analysis, developers are encouraged to:
- **Engage with the Community**: Developers with many public repositories should consider actively engaging with the GitHub community to increase their visibility, such as participating in discussions, contributing to projects, or promoting their work on social media.
- **Optimize Profiles**: Users should ensure their GitHub profiles are complete with bios, links to personal websites, and relevant skills to attract more followers and potential collaborators.
- **Contribute to Trending Repositories**: Engaging with trending projects can enhance visibility and provide valuable networking opportunities, leading to greater exposure in the developer community.

## How to Run the Project
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/[username]/TDS-proj.git
   cd TDS-proj
