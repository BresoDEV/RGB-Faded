
<h1>RGB Faded Void</h1><br >
<p>Importante:
Para sistemas que estouram valores maiores que 255, nao usar velocidade acima de 15. Para isso, precisa mudar os valores dos limites tbm
Para modmenus, esse limite pode ultrapassar sem crashar</p>


<br >


```C++
struct Fade
{
	int R;
	int G; 
	int B;
};

Fade RGB_fade(int velocidade = 1, int limiteMaior = 245, int limiteMenor = 5)
{
	static int RGB_fadeR,RGB_fadeG,RGB_fadeB;
	static int Ponto;
	if (Ponto == 0) { if (RGB_fadeR <= limiteMaior) RGB_fadeR += velocidade; else Ponto = 1; }
	if (Ponto == 1) { if (RGB_fadeG <= limiteMaior) RGB_fadeG += velocidade; else Ponto = 2; }
	if (Ponto == 2) { if (RGB_fadeB <= limiteMaior) RGB_fadeB += velocidade; else Ponto = 3; }
	if (Ponto == 3) { if (RGB_fadeG >= limiteMenor) RGB_fadeG -= velocidade; else Ponto = 4; }
	if (Ponto == 4) { if (RGB_fadeR >= limiteMenor) { RGB_fadeR -= velocidade; RGB_fadeG += velocidade; } else Ponto = 5; }
	if (Ponto == 5) { if (RGB_fadeG >= limiteMenor) { RGB_fadeG -= velocidade; } else Ponto = 6; }
	if (Ponto == 6) { if (RGB_fadeB >= limiteMenor) { RGB_fadeG += velocidade; RGB_fadeB -= velocidade; } else Ponto = 7; }
	if (Ponto == 7) { if (RGB_fadeR <= limiteMaior && RGB_fadeB <= limiteMaior) { RGB_fadeR += velocidade; RGB_fadeB += velocidade; } else Ponto = 8; }
	if (Ponto == 8) { if (RGB_fadeR >= limiteMenor) { RGB_fadeR -= velocidade; RGB_fadeG -= velocidade; RGB_fadeB -= velocidade; } else { Ponto = 0; RGB_fadeR = 0; RGB_fadeG = 0; RGB_fadeB = 0; } }
	return { RGB_fadeR,RGB_fadeG,RGB_fadeB };
}
```






```C#
public int R = 0, G = 0, B = 0;
        public int Ponto = 0;
        public int Ve = 23;


        void RGB(int velocidade = 1, int limiteMaior = 245, int limiteMenor = 5)
        {  if (Ponto == 0) { if (R <= limiteMaior) R += velocidade; else Ponto = 1; }
            if (Ponto == 1) { if (G <= limiteMaior) G += velocidade; else Ponto = 2; }
            if (Ponto == 2) { if (B <= limiteMaior) B += velocidade; else Ponto = 3; }
            if (Ponto == 3) { if (G >= limiteMenor) G -= velocidade; else Ponto = 4; }
            if (Ponto == 4) { if (R >= limiteMenor) { R -= velocidade; G += velocidade; } else Ponto = 5; }
            if (Ponto == 5) { if (G >= limiteMenor) { G -= velocidade; } else Ponto = 6; }
            if (Ponto == 6) { if (B >= limiteMenor) { G += velocidade; B -= velocidade; } else Ponto = 7; }
            if (Ponto == 7) { if (R <= limiteMaior && B <= limiteMaior) { R += velocidade; B += velocidade; } else Ponto = 8; }
            if (Ponto == 8) { if (R >= limiteMenor) { R -= velocidade; G -= velocidade; B -= velocidade; } else { Ponto = 0; R = 0; G = 0; B = 0; } }

        }
```




