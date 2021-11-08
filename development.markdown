---
layout: page
title: Development
permalink: /development/
---

The general instructions for development are:
1. Fork the code repository;
2. Clone your fork;
3. Work on a feature/bug on a new branch; and
4. When done, submit a push request for your code to be reviewed and merged.

# Testing the plugin

# QGIS testing
To test changes to the plugin within QGIS, best will be to install 'Plugin reloader':
- In QGIS, go to Plugins > Manage and install plugins;
- Click on the All tab;
- In the search bar, type 'plugin reloader'; and
- Click on the Install button.

![reloader_plugin](/images/ui/plugin_reloader.png)

This plugin allows the user to make changes to the plugin code without the need to close and reopen QGIS:
- Click on the 'Plugin reloader' button;
- Select Configure;

![reloader_button](/images/ui/reload_icon.png)

- Set it to the 'stream_feature_extractor' plugin.

![reloader_config](/images/ui/reloader_config.png)

Clicking on the button to reload a plugin if changes were made without the need to close and reopen QGIS. The plugins folder for QGIS can be found here:
- Windows: C:\Users\YOUR_USER_NAME\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins\
- Linux: Home\.local\share\QGIS\QGIS3\profiles\default\python\plugins\

## Automated testing
The plugin or changes to the plugin can be tested locally using shell scripts or remotely using Github Actions (https://github.com/kartoza/stream_feature_extractor/actions).
Tests will be performed on each of the methods (e.g. feature extraction) by comparing the result to existing data in the ‘/test’ folder. The following QGIS versions are tested:
1. 3.10;
2. 3.12;
3. 3.14;
4. 3.16 LTR;
5. 3.18;
6. 3.20;
7. 3.22; and
8. latest version.

### Local testing
To perform local testing the 'run-docker-tests.sh' can be used. The shell script can be used as follows:
1. Open your terminal/console;
2. Go to the root directory of the plugin;
3. Type "./run-docker-test.sh" and press enter;
4. The result should be similar to the figure which follows;
5. If there is any errors the user will need to investigate.

![segment_center](/images/testing/local_testing.png)

### Github actions
Tests will be performed when a PR is performed, but tests can also be performed manually if required. Here is the steps for manual execution:
1. On the repository click on the Actions tab, and select the ‘Test’ worksflow (will execute .github/workflows/test.yml);
2. Click on the Run workflow drop-down and select the Branch you want to perform the test on;
3. Click Run workflow;
4. Processing might take a while, especially if the docker images needs to be pulled; and
5. If processing is done, check if the one of the jobs succeeded or failed.

![actions](/images/testing/github_actions.png)

Failed:

![failed](/images/testing/failed.png)

Success:

![success](/images/testing/success.png)

#### Failed
If the testing failed, the user needs to investigate the cause of the error. Here is a quick guide on how to do this:
- Select the test which failed;
- Select the job which failed (e.g. ‘test (release-3_16)’);
- The user will be presented with the job steps. Select the job which failed (e.g. ‘Run test suite’);

![success](/images/testing/job_steps.png)

- A list of print lines will be shown, with the error at the end; and

![error](/images/testing/error_msg.png)

- Investigate the code to which the error relates to the method performed during that test. Having a look at the data used for the test may also be useful.

#### Success
There should be no issue if the tests does not fail. The jobs will be similar to the following:

![jobs_success](/images/testing/jobs_success.png)

The plugin and any updates to the plugin should work with no issue for each of the QGIS versions in the above list.

# Contributing

If you would like to contribute an enhancement, bug fix, translation etc. to
this plugin, please make a fork of the repository on Github at:

https://github.com/kartoza/stream_feature_extractor

Then make your improvements and make a Github pull request. Please follow
the existing coding conventions if you want us to include your changes.
