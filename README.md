name: Update TryHackMe Badge
on:
  schedule:
    - cron: '0 0 * * *' # Runs daily at midnight UTC
  workflow_dispatch: # Allows manual triggering

jobs:
  update-badge:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Fetch TryHackMe Badge
        uses: p4p1/tryhackme-badge-workflow@main
        with:
          username: "Eseosa20" # Replace with your TryHackMe username
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }} # Automatically uses your GitHub token
