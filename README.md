# knowledge-base

我的知识库

# 预览

```shell
.venv\\Scripts\\mkdocs serve --dirtyreload
```

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Chrome",
      "type": "chrome",
      "request": "launch",
      "runtimeArgs": [
        "--disable-features=Translate",
        "--incognito"
      ],
      "preLaunchTask": "Start and watch for changes",
      "url": "http://localhost:8000/",
      "webRoot": "${workspaceFolder}",
      "sourceMaps": true,
      "sourceMapPathOverrides": {
        "*": "${workspaceFolder}/*"
      },
      "smartStep": true
    },
    {
      "name": "MkDocs",
      "type": "debugpy",
      "request": "launch",
      "program": ".venv\\Scripts\\mkdocs",
      "args": [
        "build"
      ],
      "env": {
        "PYTHONPATH": "."
      }
    },
    {
      "name": "MkDocs server",
      "type": "debugpy",
      "request": "launch",
      "preLaunchTask": "Start and watch for changes",
      "program": ".venv\\Scripts\\mkdocs",
      "args": [
        "serve",
        "--watch-theme"
      ],
      "env": {
        "PYTHONPATH": "."
      }
    },
    {
      "name": "MkDocs server (dirty)",
      "type": "debugpy",
      "request": "launch",
      "preLaunchTask": "Start and watch for changes",
      "program": ".venv\\Scripts\\mkdocs",
      "args": [
        "serve",
        "--watch-theme",
        "--dirtyreload"
      ],
      "env": {
        "PYTHONPATH": "."
      }
    }
  ],
  "compounds": [
    {
      "name": "Chrome + MkDocs server",
      "configurations": [
        "Chrome",
        "MkDocs server"
      ]
    },
    {
      "name": "Chrome + MkDocs server (dirty)",
      "configurations": [
        "Chrome",
        "MkDocs server (dirty)"
      ]
    }
  ]
}
```