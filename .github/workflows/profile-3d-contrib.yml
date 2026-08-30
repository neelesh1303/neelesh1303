name: 3D Profile Contribution Graph

on:
  schedule:
    # runs once a day at 00:00 UTC — adjust as you like
    - cron: "0 0 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: actions/checkout@v4

      - name: Generate 3D contribution graph
        uses: yoshi389111/github-profile-3d-contrib@0.7.1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          username: neelesh1303

      - name: Commit and push the generated images
        run: |
          git config user.name  github-actions
          git config user.email github-actions@github.com
          git add -A profile-3d-contrib
          git commit -m "docs: update 3D contribution graph" || echo "No changes to commit"
          git push
