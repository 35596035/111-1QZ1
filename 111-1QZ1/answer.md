# 第1次隨堂-隨堂-QZ1
>
>學號：109111101 
><br />
>姓名：邱韋翔
><br />
>作業撰寫時間：15 (mins，包含程式撰寫時間)
><br />
>最後撰寫文件日期：2022/10/01
>

本份文件包含以下主題：(至少需下面兩項，若是有多者可以自行新增)
- [x]說明內容
- [x]個人認為完成作業須具備觀念

## 說明程式與內容

先建立一個陣列，專門用來儲存炸彈位置的，因為等等會用到`for`迴圈的特性所以是建立`int`的陣列，在建立一個用來存放字元的二維陣列的掃雷邊界大小10*10=100，
建立完用`for`迴圈訪問全部的二維陣列讓所有二維陣列為字元`o`，在來再給個迴圈訪問存放炸彈的陣列，
並將炸彈原有的位置進行替換，也就是把字元`o`給替換掉換字元`*`，最後再利用`for`迴圈列印出全部的二維陣列
就得到和原題目一樣的結果，下段程式碼為使用後結果：

```csharp
    public partial class Bomb : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            int[] ia_Mlndex = new int[10] { 0, 7, 13, 28, 44, 62, 74, 75, 87, 90 };
            char[,] ia_Map = new char[10, 10];
            //先訪問全部的二維陣列
            for (int i_Row = 0; i_Row < 10; i_Row++)
            {
                for (int i_Col = 0; i_Col < 10; i_Col++)
                {
                    ia_Map[i_Row, i_Col] = 'o';
                }
            }
            //塞入炸彈位置
            for (int i_Ct = 0; i_Ct < 10; i_Ct++)
            {
                int i_Row = ia_Mlndex[i_Ct] / 10;
                int i_Col = ia_Mlndex[i_Ct] % 10;
                ia_Map[i_Row, i_Col] = '*';
            }
            //列印全部的二維陣列
            for (int i_Row = 0; i_Row < 10; i_Row++)
            {
                for (int i_Col = 0; i_Col < 10; i_Col++)
                {
                    Response.Write(ia_Map[i_Row,i_Col]);
                }
                Response.Write("<br />");
            }
        }
    }
}
```

## 個人認為完成作業須具備觀念

首先必須先了解建立陣列的語法和特性，例如想要一個陣列存放數字就必須使用`int`，要字元則使用`char`
，另外還須了解`for`迴圈的語法，其中`for`迴圈也包含一些邏輯運算子的應用
，了解完以上觀念變可完成此次作業。
