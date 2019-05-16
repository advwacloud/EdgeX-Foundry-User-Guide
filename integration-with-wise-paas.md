# Integration with WISE-PaaS

---

以下步驟會說明如何透過設定將EdgeX設備的數據上傳到WISE-PaaS/APM。

1. 請用瀏覽器開啟EdgeX Foundry Console網頁，網址為http://{IP}:4000，{IP}為Docker Containers所運行的電腦IP，Name和Password都是admin，登入畫面如下。

![](/assets/login.png)

1. 第一次登入時，並沒有Gateway存在，請先新增一個Gateway，Address請填入Docker Containers所運行的電腦IP，並選擇剛剛新增的Gateway。

![](/assets/gateway1.png)  
![](/assets/gateway2.png)

1. 點擊左側的WISE-PaaS Setting進行連線和白名單設定
   * Connection Setting：要在master node的portal做WISE-PaaS Setting, 多gateway的機制才可以正常運作，WISE-PaaS相關的連線資訊各屬性描述如下
     * Launch：是否啟動資料上傳功能。
     * Master Address：選定一台gateway address去接收所有gateway的export data。
     * SRP Type：支援的WISE-PaaS SRP類型，目前支援WISE-PaaaS/APM和SCADA。
     * APM ID：WISE-PaaS/APM的識別碼，從APM Portal建立Gateway時取得。
     * IoT Key：與WISE-PaaS IotHub連線所需的資訊，從APM Portal建立Gateway時取得。
     * Credential Url：與WISE-PaaS IotHub連線所需的資訊，從APM Portal建立Gateway時取得。
     * Publish Interval：資料上傳頻率。\(若為0則是設備資料有變化才上傳\)
   * Whitelist Setting：設定設備資料上傳的白名單，下拉選擇Gateway和該Gateway下的設備之後，會列出該設備下的測點清單，勾選並設定好Deadband範圍即可，。
2. 設定完後，按下Save即開始傳送資料到WISE-PaaS。

![](/assets/complete1.png)

