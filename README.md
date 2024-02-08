# creaci-n-de-un-navegador-de-internet
creación de un navegador de internet
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Security.Policy;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace pagina_web
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            //webBrowser1.Navigate(new Uri(comboBox1.SelectedItem.ToString()));
            string url = comboBox1.Text.ToString();
            string cod = comboBox1.Text.ToString();
            if (!(url.Contains("http")))
            {
                url = "http://" + url;  
            }
            webBrowser1.Navigate(new Uri(url));

            if (!(cod.Contains("-")))
            {
                cod = "http://www.google.com/search?q=" + cod;
            }
            webBrowser1.Navigate(new Uri(cod));
        }

        private void navegarToolStripMenuItem_Click(object sender, EventArgs e)
        {

        }

        private void inicioToolStripMenuItem_Click(object sender, EventArgs e)
        {
            webBrowser1.GoHome();
        }

        private void haciaAtrasToolStripMenuItem_Click(object sender, EventArgs e)
        {
            webBrowser1.GoBack();
        }

        private void haciaAdelanteToolStripMenuItem_Click(object sender, EventArgs e)
        {
            webBrowser1.GoForward();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            comboBox1.SelectedIndex = 0;
            webBrowser1.GoHome();
        }
    }
}
