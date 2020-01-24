# Changing Your Site's Theme

Themes are used to set the overall look and feel for your Site. A Site's Pages can be configured to use any theme that has been deployed to your DXP instance.

The DXP Docker image has the _Classic_ theme available by default. In this example, we will deploy a new simple theme and then show you how to switch from one theme to another.

![Out-of-the-box themes](./changing-your-sites-theme/images/01.png)

## Deploy a New Theme

1. Start up the Liferay DXP Docker image:

    ```bash
    docker run -it -p 8080:8080 liferay/dxp:7.2.10.1-sp1
    ```

1. Download the WAR containing the [Acme Sample Theme](./liferay-5b2v-theme.war):

    ```bash
    curl https://learn.liferay.com/dxp/7.x/en/getting-started/changing-your-sites-theme/liferay-5b2v-theme.war -O
    ```

1. Deploy the WAR containing the theme:

    ```bash
    docker cp liferay-5b2v-theme.war docker-container:path-to-deploy-folder
    ```

This will load the sample theme into your DXP instance. You can check your console for the following message to confirm that the theme successfully deployed:

```
020-01-23 00:04:32.824 INFO  [fileinstall-/home/liferay/deploy/7.2-test/osgi/war][BundleStartStopLogger:39] STARTED liferay-5b2v-theme_1.0.0 [934]
```

## Change Your Site's Theme

Next, configure the Public Pages for your Site to use the deployed theme:

1. Open your browser to `https://localhost:8080` and [login as an administrator](./introduction-to-the-admin-account.md).

1. Navigate to the Product Menu → _Site Administration_ → _Site Builder_ → _Pages_.

1. Click the gear icon ![Gear icon](../images/icon-control-menu-gear.png) next to _Public Pages_ to configure them:

    ![Open the Pages screen to configure your Public Pages.](./changing-your-sites-theme/images/02.png)

1. Scroll down and click the _Change Current Theme_ button:

    ![Click Change Current Theme to select a new theme for your Public Pages.](./changing-your-sites-theme/images/03.png)

1. Select the deployed sample theme, _Classic with Blue Background._

1. Navigate back to the home page for your Site to confirm that the theme has changed. The background for your Site is now blue.

    ![The home page has a different color background after changing the theme.](./changing-your-sites-theme/images/04.png)

Your site's theme has been updated.

## Additional Information

There are many themes available on the [Liferay Marketplace](../advanced-installation-and-upgrades/01-installing-liferay-dxp/10-setting-up-marketplace.md) that can be used to quickly achieve a professional look and feel.

You can also learn how to [create your own theme](../site-building/README.md).