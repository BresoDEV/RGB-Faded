
<h1>RGB Faded Void</h1><br >
<p>Importante:
Para sistemas que estouram valores maiores que 255, nao usar velocidade acima de 15. Para isso, precisa mudar os valores dos limites tbm
Para modmenus, esse limite pode ultrapassar sem crashar</p>


<br >




```C#
 private void timer1_Tick(object sender, EventArgs e)
        {
            this.Text = pt.ToString();
            
            if (pt >= r.Count -1)
                pt= 0;
            else
            {
                this.BackColor = Color.FromArgb(255, r[pt], g[pt], b[pt]);
                pt += Convert.ToInt32(numericUpDown1.Value);
            }
           
        }




List<int> r = new List<int>();
        List<int> g = new List<int>();
        List<int> b = new List<int>();
        public static int pt = 0;
        private void button5_Click(object sender, EventArgs e)
        {
            for (int x = 0; x != 256; x++) r.Add(x);
            for (int x = 0; x != 256; x++) g.Add(0);
            for (int x = 0; x != 256; x++) b.Add(0);

            for (int x = 0; x != 256; x++) r.Add(255);
            for (int x = 0; x != 256; x++) g.Add(x);
            for (int x = 0; x != 256; x++) b.Add(0);

            for (int x = 255; x >= 0; x--) r.Add(x);
            for (int x = 0; x != 256; x++) g.Add(255);
            for (int x = 0; x != 256; x++) b.Add(0);

            for (int x = 0; x != 256; x++) r.Add(0);
            for (int x = 0; x != 256; x++) g.Add(255);
            for (int x = 0; x != 256; x++) b.Add(x);

            for (int x = 0; x != 256; x++) r.Add(0);
            for (int x = 255; x >= 0; x--) g.Add(x);
            for (int x = 0; x != 256; x++) b.Add(255);

            for (int x = 0; x != 256; x++) r.Add(x);
            for (int x = 0; x != 256; x++) g.Add(0);
            for (int x = 0; x != 256; x++) b.Add(255);

            for (int x = 0; x != 256; x++) r.Add(255);
            for (int x = 0; x != 256; x++) g.Add(x);
            for (int x = 0; x != 256; x++) b.Add(255);



            for (int x = 255; x >= 0; x--) r.Add(x);
            for (int x = 255; x >= 0; x--) g.Add(x);
            for (int x = 255; x >= 0; x--) b.Add(x);


            timer1.Enabled = true;

        }
```




