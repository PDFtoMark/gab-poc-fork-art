name: PR Workflow
on:
  pull_request:
    branches: [main]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: emit artifact
        run: |
          mkdir -p out
          echo "head_repo=${{ github.event.pull_request.head.repo.full_name }} head_sha=${{ github.event.pull_request.head.sha }} marker=${MARKER:-base-default}" > out/payload.txt
          cat out/payload.txt
      - uses: actions/upload-artifact@v4
        with:
          name: dependency-graph_probe
          path: out/
