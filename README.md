# Selenium-Shadow-Root-Example-Code
Selenium-Shadow-Root-Example-Code

using OpenQA.Selenium.Chrome;
using System;
using System.Threading;
using System.Windows.Forms;

namespace shadowrootexample
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }
        string url = "https://book.olacabs.com/?utm_source=book_now_top_right";
        string EBSXpath = "document.querySelector(\"body > ola-app\").shadowRoot.querySelector(\"iron-pages > ola-home\").shadowRoot.querySelector(\"ola-loc-permission\").shadowRoot.querySelector(\"div > div > div.footer > button\").click();";
        ChromeDriver drv;
        private void button1_Click(object sender, EventArgs e)
        {
            drv = new ChromeDriver();
            drv.Navigate().GoToUrl(url);
            Thread.Sleep(3000);
            drv.ExecuteScript(EBSXpath);
        }
    }
}
