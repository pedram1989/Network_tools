using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
using System.Net.NetworkInformation;
using System.Net;
using System.Diagnostics;

namespace Cafe_IT___fanap_infra
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }


        private string GetIP()
        {
            string HostName = "";
            HostName = Dns.GetHostName();
            IPHostEntry ipEntry = Dns.GetHostEntry(HostName);
            IPAddress[] addr = ipEntry.AddressList;
            return addr[addr.Length - 1].ToString();
        }

        

        private void Form1_Load(object sender, EventArgs e)
        {
            label_name.Text = (Dns.GetHostName());
            label_ip.Text = (GetIP());
        }
