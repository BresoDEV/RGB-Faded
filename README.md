
<h1>RGB Faded Void</h1><br >
<p>Importante:
Para sistemas que estouram valores maiores que 255, nao usar velocidade acima de 15. Para isso, precisa mudar os valores dos limites tbm
Para modmenus, esse limite pode ultrapassar sem crashar</p>


<br >


```C++
int R = 0, G = 0, B = 0;
int Ponto = 0;
int Ve = 23;

void RGB_fade(int velocidade = 1, int limiteMaior = 245, int limiteMenor = 5)
{ 
	if (Ponto == 0) { if (R <= limiteMaior) R += velocidade; else Ponto = 1; }
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




