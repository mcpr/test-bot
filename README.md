# MCPR-Test-Bot Server
This is the future home of the `MCPR-Test-Bot` Server component!

The `MCPR-Test-Bot` runs some basic tests on Minecraft plugins uploaded to [MCPR](https://mcpr.io).


## Test Flow
1. Plugin is uploaded to MCPR
2. MCPR sends a webhook to `MCPR-Test-Bot` Server with the plugin ID and version
3. `MCPR-Test-Bot` provisions an ACI container with [`MCPR-Test-Bot` Worker](https://github.com/mcpr/test-bot-worker) on it
4. The ACI container runs `MCPR-Test-Bot` Worker on the plugin version (`test-bot-worker test [pluginID] [version]`)
5. `MCPR-Test-Bot` Worker reports back to `MCPR-Test-Bot` Server with the test results
6. `MCPR-Test-Bot` Server makes note of the results and sends them to MCPR
