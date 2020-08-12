# Image-to-Binary-
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
namespace conversion
{
 public partial class Form1 : Form
 {
 public Form1()
 {
 InitializeComponent();
 }
 private void button2_Click(object sender, EventArgs e)
 {
 openFileDialog1.FileName = ""; 
 openFileDialog1.Title = "Images"; 
 openFileDialog1.Filter = "task_image|*.jpg; *.bmp; *.png"; 
 openFileDialog1.ShowDialog(); 
 if (openFileDialog1.task_image.ToString() != "") 
 Image.Imagelocation= openFileDialog1.Filename.ToString(); 
 Bitmap img;
 img = new Bitmap(openFileDialog1.FileName.ToString()); 
 string texto = "";
 for (int i = 0; i < img.Height; i++) 
 { 
 for (int j = 0; j < img.Width; j++)
 { 
 if (img.GetPixel(j, i).A.ToString() == "255" && 
img.GetPixel(j, i).B.ToString() == "255" && img.GetPixel(j, i).G.ToString() 
== "255" && img.GetPixel(j, i).R.ToString() == "255") { 
 texto = texto + "0"; 
 } 
 else
 { 
 texto = texto + "1"; 
 } 
 } 
 texto = texto + "\r\n";
 } 
 
 txtArreglo.Text = texto; 
 }
}
