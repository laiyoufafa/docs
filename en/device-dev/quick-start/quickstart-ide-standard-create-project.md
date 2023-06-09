# Creating a Source Code Project


After [setting up the Windows+Ubuntu hybrid development environment](../quick-start/quickstart-ide-standard-env-setup-win-ubuntu.md) and [obtaining source code](../quick-start/quickstart-ide-standard-sourcecode-acquire.md), perform the following steps to create a source code project in Windows:


1. Open DevEco Device Tool, go to the home page, and click **Import Project** to open your project or source code.

   ![en-us_image_0000001171426014](figures/en-us_image_0000001171426014.png)

2. Select the source code directory to be imported and click **Import**.

   > ![icon-note.gif](public_sys-resources/icon-note.gif) **NOTE**<br/>
   > Make sure the selected directory does not contain Chinese characters or spaces. Otherwise, the building may fail.

   ![en-us_image_0000001271562277](figures/en-us_image_0000001271562277.png)

3. If you select to open the OpenHarmony source code, a message will be displayed indicating that the project is not a DevEco Device Tool project. Click **Import** to continue.

   ![en-us_image_0000001135394334](figures/en-us_image_0000001135394334.png)

4. On the **Select Project type** page, select **Import from OpenHarmony Source**.

   ![en-us_image_0000001215743910](figures/en-us_image_0000001215743910.png)

5. On the **Import Project** page, select a product, and the MCU, board, company, and kernel fields will be automatically populated. Then, select the OpenHarmony source code version for **ohosVersion**. The following figure uses **Hi3516DV300** as an example.

   > ![icon-note.gif](public_sys-resources/icon-note.gif) **NOTE**<br/>
   > - Set **Product** to **Hi3516DV300** for the Hi3516D V300 development board.
   > 
   > - Set **Product** to **rk3568** for the RK3568 development board.

   ![en-us_image_0000001271448821](figures/en-us_image_0000001271448821.png)

6. Click **Open** to open the project or source code.
