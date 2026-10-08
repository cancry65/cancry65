name: GitHub Metrics
on:
  schedule:
    - cron: "0 0 * * *" # Diperbarui setiap hari pada jam 00:00 UTC
  workflow_dispatch:

jobs:
  github-metrics:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: lowlighter/metrics@latest
        with:
          token: ${{ secrets.METRICS_TOKEN }}
          user: Cancry
          template: classic
          base: header, activity, community, repositories, metadata
          plugin_isocalendar: yes
          plugin_isocalendar_duration: full-year
          plugin_streaks: yes
          config_timezone: Asia/Jakarta
