using System;

namespace jogo
{
    class program
    {
        static void Main(string[] args)
        {
            Batalha jogo = new Batalha();
            jogo.IniciarCombate();
        }
    }

    class Batalha
    {
        int HPHero = 100;
        int HPMaxHero = 130;
        int ArmaduraHero = 10;
        int HPMonster = 120;
        int HPMaxMonster = 150;
        int ATAKHero = 20;
        int ATAKMonster = 30;

        int HPMonsterGnomo = 180;
        int ATAKMonsterGnomo = 40;


        int HPMonsterDino = 200;
        int ATAKMonsterDino = 45;

        int HPMonsterGaviao = 220;
        int ATAKMonsterGaviao = 50;

        int HPMonsterChefao = 350;
        int ATAKMonsterChefao = 70;

        int nivelAtualHeroi = 1;
        float expAtualHeroi = 0;
        float expAlvoHeroi = 200;
        float multiplicadorExpHeroi = 1.2f;

        int OuroAtualDoHeroi = 0;

        bool Combate = true;
        bool Loja = false;

        string escolha;
        string escolhaHeroiAtak;
        string classe;

        string escolhaBoss;

        string EscolhaLojaItem;

        Random chanceAtaque = new Random();
        int chanceAtaque2;


        public void IniciarCombate()
        {

            EscolherClasse();

            Turno();

            Console.Read();

        }

        //----------primeira_loja----------------------------------------

        public void LojaLoja()
        {
            if (Loja == true)
            {
                Console.WriteLine("Armadura 1 - Custa 20 - (Para comprar escreva 1)");
                Console.WriteLine("Poder de Ataque 1 - Custa 20 - (Para comprar escreva 2)");
                Console.WriteLine("Vida Maxima 1 - Custa 20 - (Para comprar escreva 3)");

                EscolhaLojaItem = Console.ReadLine();

                if (OuroAtualDoHeroi <= 0)
                {
                    Console.WriteLine("Heroi não tem dinheiro para comprar itens");
                }

                if (EscolhaLojaItem == "1" && OuroAtualDoHeroi >= 20)
                {
                    ArmaduraHero = ArmaduraHero + 10;
                    OuroAtualDoHeroi = OuroAtualDoHeroi - 20;
                    Console.WriteLine(" Herói ganhou mais 10 de armadura ");
                    Console.WriteLine(" Herói está com " + OuroAtualDoHeroi + " de ouro");
                }

                if (EscolhaLojaItem == "2" && OuroAtualDoHeroi >= 20)
                {
                    ATAKHero = ATAKHero + 15;
                    OuroAtualDoHeroi = OuroAtualDoHeroi - 20;
                    Console.WriteLine(" Herói ganhou mais 15 de ataque ");
                    Console.WriteLine(" Herói está com " + OuroAtualDoHeroi + " de ouro");
                }

                if (EscolhaLojaItem == "3" && OuroAtualDoHeroi >= 20)
                {
                    HPHero = HPHero + 30;
                    OuroAtualDoHeroi = OuroAtualDoHeroi - 20;
                    Console.WriteLine(" Herói ganhou mais 30 de vida ");
                    Console.WriteLine(" Herói está com " + OuroAtualDoHeroi + " de ouro");
                }

                Console.WriteLine("Pronto para o proximo round? sim ou não");
                string resposta = Console.ReadLine();
                if (resposta == "sim")
                {
                    Combate = true;
                    Console.WriteLine("Você vai lutar com o Mega Gnomo!");
                    TurnoGnomo();
                }

                if (resposta == "não")
                {
                    LojaLoja();
                }

            }
        }

        public void LojaLojaDino()
        {
            if (Loja == true)
            {
                Console.WriteLine("Armadura 2 - Custa 20 - (Para comprar escreva 1)");
                Console.WriteLine("Poder de Ataque 2 - Custa 20 - (Para comprar escreva 2)");
                Console.WriteLine("Vida Maxima 2 - Custa 20 - (Para comprar escreva 3)");

                EscolhaLojaItem = Console.ReadLine();

                if (OuroAtualDoHeroi <= 0)
                {
                    Console.WriteLine("Heroi não tem dinheiro para comprar itens");
                }

                if (EscolhaLojaItem == "1" && OuroAtualDoHeroi >= 20)
                {
                    ArmaduraHero = ArmaduraHero + 20;
                    OuroAtualDoHeroi = OuroAtualDoHeroi - 20;
                    Console.WriteLine(" Herói ganhou mais 20 de armadura ");
                    Console.WriteLine(" Herói está com " + OuroAtualDoHeroi + " de ouro");
                }

                if (EscolhaLojaItem == "2" && OuroAtualDoHeroi >= 20)
                {
                    ATAKHero = ATAKHero + 25;
                    OuroAtualDoHeroi = OuroAtualDoHeroi - 20;
                    Console.WriteLine(" Herói ganhou mais 25 de ataque ");
                    Console.WriteLine(" Herói está com " + OuroAtualDoHeroi + " de ouro");
                }

                if (EscolhaLojaItem == "3" && OuroAtualDoHeroi >= 20)
                {
                    HPHero = HPHero + 40;
                    OuroAtualDoHeroi = OuroAtualDoHeroi - 20;
                    Console.WriteLine(" Herói ganhou mais 40 de vida ");
                    Console.WriteLine(" Herói está com " + OuroAtualDoHeroi + "  de ouro");
                }

                Console.WriteLine("Pronto para o proximo round? sim ou não");
                string resposta = Console.ReadLine();
                if (resposta == "sim")
                {
                    Combate = true;
                    Console.WriteLine("Você vai lutar com o Mega Dinossauro!");
                    TurnoDino();
                }

                if (resposta == "não")
                {
                    LojaLojaDino();
                }

            }
        }

        public void LojaLojaGaviao()
        {
            if (Loja == true)
            {
                Console.WriteLine("Armadura 3 - Custa 20 - (Para comprar escreva 1)");
                Console.WriteLine("Poder de Ataque 3 - Custa 20 - (Para comprar escreva 2)");
                Console.WriteLine("Vida Maxima 3 - Custa 20 - (Para comprar escreva 3)");

                EscolhaLojaItem = Console.ReadLine();

                if (OuroAtualDoHeroi <= 0)
                {
                    Console.WriteLine("Herói não tem dinheiro para comprar itens");
                }

                if (EscolhaLojaItem == "1" && OuroAtualDoHeroi >= 20)
                {
                    ArmaduraHero = ArmaduraHero + 30;
                    OuroAtualDoHeroi = OuroAtualDoHeroi - 20;
                    Console.WriteLine(" Herói ganhou mais 30 de armadura ");
                    Console.WriteLine(" Herói está com " + OuroAtualDoHeroi + " de ouro");
                }

                if (EscolhaLojaItem == "2" && OuroAtualDoHeroi >= 20)
                {
                    ATAKHero = ATAKHero + 35;
                    OuroAtualDoHeroi = OuroAtualDoHeroi - 20;
                    Console.WriteLine(" Herói ganhou mais 35 de ataque ");
                    Console.WriteLine(" Herói está com " + OuroAtualDoHeroi + " de ouro");
                }

                if (EscolhaLojaItem == "3" && OuroAtualDoHeroi >= 20)
                {
                    HPHero = HPHero + 50;
                    OuroAtualDoHeroi = OuroAtualDoHeroi - 20;
                    Console.WriteLine(" Herói ganhou mais 50 de vida ");
                    Console.WriteLine(" Herói está com " + OuroAtualDoHeroi + " de ouro");
                }

                Console.WriteLine("Pronto para o proximo round? sim ou não");
                string resposta = Console.ReadLine();
                if (resposta == "sim")
                {
                    Combate = true;
                    Console.WriteLine("Você vai lutar com o Mega Gavião!");
                    TurnoGaviao();
                }

                if (resposta == "não")
                {
                    LojaLojaGaviao();
                }

            }
        }

        public void LojaLojaChefao()
        {
            if (Loja == true)
            {
                Console.WriteLine("Armadura 4 - Custa 20 - (Para comprar escreva 1)");
                Console.WriteLine("Poder de Ataque 4 - Custa 20 - (Para comprar escreva 2)");
                Console.WriteLine("Vida Maxima 4 - Custa 20 - (Para comprar escreva 3)");

                EscolhaLojaItem = Console.ReadLine();

                if (OuroAtualDoHeroi <= 0)
                {
                    Console.WriteLine("Herói não tem dinheiro para comprar itens");
                }

                if (EscolhaLojaItem == "1" && OuroAtualDoHeroi >= 20)
                {
                    ArmaduraHero = ArmaduraHero + 30;
                    OuroAtualDoHeroi = OuroAtualDoHeroi - 20;
                    Console.WriteLine(" Herói ganhou mais 50 de armadura ");
                    Console.WriteLine(" Herói está com " + OuroAtualDoHeroi + " de ouro");
                }

                if (EscolhaLojaItem == "2" && OuroAtualDoHeroi >= 20)
                {
                    ATAKHero = ATAKHero + 35;
                    OuroAtualDoHeroi = OuroAtualDoHeroi - 20;
                    Console.WriteLine(" Herói ganhou mais 55 de ataque ");
                    Console.WriteLine(" Herói está com " + OuroAtualDoHeroi + " de ouro");
                }

                if (EscolhaLojaItem == "3" && OuroAtualDoHeroi >= 20)
                {
                    HPHero = HPHero + 50;
                    OuroAtualDoHeroi = OuroAtualDoHeroi - 20;
                    Console.WriteLine(" Herói ganhou mais 70 de vida ");
                    Console.WriteLine(" Herói está com " + OuroAtualDoHeroi + " de ouro");
                }

                Console.WriteLine("Pronto para o enfrentar o chefão? sim ou não (Se quiser ir para o round anterior digite não.)");
                string resposta = Console.ReadLine();
                if (resposta == "sim")
                {
                    Combate = true;
                    Console.WriteLine("Você vai lutar com o Chefão!");
                    TurnoChefao();
                }

                if (resposta == "não")
                {
                    LojaLojaGaviao();
                }

            }
        }

        //---------------------------------------------------------------

        public void HeroATKMonsterGaviao()
        {
            chanceAtaque2 = chanceAtaque.Next(0, 101);

            if (chanceAtaque2 <= 75)
            {
                HPMonsterGaviao = HPMonsterGaviao - ATAKHero;
                Console.WriteLine("Herói causou " + ATAKHero + " de dano no Mega Gavião");

                if (HPMonsterGaviao <= 0)
                {
                    HPMonsterGaviao = 0;

                    Console.WriteLine("Mega Gavião Morreu");

                    ATAKMonsterGaviao = 0;

                    OuroAtualDoHeroi = OuroAtualDoHeroi + 20;
                    Console.WriteLine("Herói ganhou 20 de ouro ao matar o Mega Gavião");

                    AlterarExperiencia(50);
                    Console.WriteLine("Herói ganhou 50 de experiencia");

                    Combate = false;
                    Loja = true;

                }
            }

            chanceAtaque2 = chanceAtaque.Next(0, 101);

            if (chanceAtaque2 > 80)
            {
                ATAKEspecial();
            }

        }

        public void HeroATKMonsterDino()
        {
            chanceAtaque2 = chanceAtaque.Next(0, 101);

            if (chanceAtaque2 <= 75)
            {
                HPMonsterDino = HPMonsterDino - ATAKHero;
                Console.WriteLine("Herói causou " + ATAKHero + " de dano no Mega Dinossauro");

                if (HPMonsterDino <= 0)
                {
                    HPMonsterDino = 0;

                    Console.WriteLine("Mega Dinossauro Morreu");

                    ATAKMonsterDino = 0;

                    OuroAtualDoHeroi = OuroAtualDoHeroi + 20;
                    Console.WriteLine("Herói ganhou 20 de ouro ao matar o Mega Dinossauro");

                    AlterarExperiencia(50);
                    Console.WriteLine("Herói ganhou 50 de experiencia");

                    Combate = false;
                    Loja = true;

                }
            }

            chanceAtaque2 = chanceAtaque.Next(0, 101);

            if (chanceAtaque2 > 80)
            {
                ATAKEspecial();
            }

        }

        public void HeroATKMonsterGnomo()
        {
            chanceAtaque2 = chanceAtaque.Next(0, 101);

            if (chanceAtaque2 <= 75)
            {
                HPMonsterGnomo = HPMonsterGnomo - ATAKHero;
                Console.WriteLine("Herói causou " + ATAKHero + " de dano no Mega Gnomo");

                if (HPMonsterGnomo <= 0)
                {
                    HPMonsterGnomo = 0;

                    Console.WriteLine("Mega Gnomo Morreu");

                    ATAKMonsterGnomo = 0;

                    OuroAtualDoHeroi = OuroAtualDoHeroi + 20;
                    Console.WriteLine("Herói ganhou 20 de ouro ao matar o Mega Gnomo");

                    AlterarExperiencia(50);
                    Console.WriteLine("Herói ganhou 50 de experiencia");

                    Combate = false;
                    Loja = true;

                }
            }

            chanceAtaque2 = chanceAtaque.Next(0, 101);

            if (chanceAtaque2 > 80)
            {
                ATAKEspecial();
            }

        }

        public void HeroATKMonster()
        {
            chanceAtaque2 = chanceAtaque.Next(0, 101);

            if (chanceAtaque2 <= 75)
            {
                HPMonster = HPMonster - ATAKHero;
                Console.WriteLine("Herói causou " + ATAKHero + " de dano no Monstro");

                if (HPMonster <= 0)
                {
                    HPMonster = 0;

                    Console.WriteLine("Monstro Morreu");

                    ATAKMonster = 0;

                    OuroAtualDoHeroi = OuroAtualDoHeroi + 20;
                    Console.WriteLine("Heroi ganhou 20 de ouro ao matar o monstro");

                    AlterarExperiencia(50);
                    Console.WriteLine("Herói ganhou 50 de experiencia");

                    Combate = false;
                    Loja = true;

                }
            }
            chanceAtaque2 = chanceAtaque.Next(0, 101);

            if (chanceAtaque2 > 80)
            {
                ATAKEspecial();
            }

        }

        public void HeroATKMonsterChefao()
        {
            chanceAtaque2 = chanceAtaque.Next(0, 101);

            if (chanceAtaque2 <= 75)
            {
                HPMonsterChefao = HPMonsterChefao - ATAKHero;
                Console.WriteLine("Herói causou " + ATAKHero + " de dano no Chefão");

                if (HPMonsterChefao <= 0)
                {
                    HPMonsterChefao = 0;

                    Console.WriteLine("Chefão Morreu");

                    ATAKMonsterChefao = 0;

                    OuroAtualDoHeroi = OuroAtualDoHeroi + 20;
                    Console.WriteLine("Heroi ganhou 20 de ouro ao matar o monstro");

                    AlterarExperiencia(50);
                    Console.WriteLine("Herói ganhou 50 de experiencia");

                    Combate = false;
                    Loja = true;

                }
            }
            chanceAtaque2 = chanceAtaque.Next(0, 101);

            if (chanceAtaque2 > 80)
            {
                ATAKEspecial();
            }

        }

        //---------------------------------------------------------------

        public void MonsterATKHero()
        {
            HPHero = HPHero - ATAKMonster;
            Console.WriteLine("Monstro causou " + ATAKMonster + " de dano no Herói");

            if (HPHero < 0)
            {
                HPHero = 0;

                ATAKHero = 0;

                Console.WriteLine("Herói Morreu");
            }
        }

        public void MonsterDinoATKHero()
        {
            HPHero = HPHero - ATAKMonsterDino;
            Console.WriteLine("Mega Dinossauro causou " + ATAKMonsterDino + " de dano no Herói");

            if (HPHero < 0)
            {
                HPHero = 0;

                ATAKHero = 0;

                Console.WriteLine("Herói Morreu");
            }
        }

        public void MonsterGnomoATKHero()
        {
            HPHero = HPHero - ATAKMonsterGnomo;
            Console.WriteLine("Mega Gnomo causou " + ATAKMonsterGnomo + " de dano no Herói");

            if (HPHero < 0)
            {
                HPHero = 0;

                ATAKHero = 0;

                Console.WriteLine("Herói Morreu");
            }
        }

        public void MonsterGaviaoATKHero()
        {
            HPHero = HPHero - ATAKMonsterGaviao;
            Console.WriteLine("Mega Gavião causou " + ATAKMonsterGaviao + " de dano no Herói");

            if (HPHero < 0)
            {
                HPHero = 0;

                ATAKHero = 0;

                Console.WriteLine("Herói Morreu");
            }
        }

        public void MonsterChefaoATKHero()
        {
            HPHero = HPHero - ATAKMonsterChefao;
            Console.WriteLine("O Chefão causou " + ATAKMonsterChefao + " de dano no Herói");

            if (HPHero < 0)
            {
                HPHero = 0;

                ATAKHero = 0;

                Console.WriteLine("Herói Morreu");
            }
        }

        //---------------------------------------------------------------

        public void MonsterCura()
        {
            if (HPMonster > 0)
            {
                HPMonster = HPMonster + 5;

                Console.WriteLine("Monstro curou + 5 HP");

                if (HPMonster > HPMaxMonster)
                {
                    HPMonster = HPMaxMonster;

                    Console.WriteLine("O Monstro está full life");
                }
            }

        }

        public void HeroCura()
        {
            if (HPHero > 0)
            {
                HPHero = HPHero + 30;

                Console.WriteLine("Herói curou + 5 HP");

                if (HPHero > HPMaxHero)
                {
                    HPHero = HPMaxHero;

                    Console.WriteLine("O Herói está full life");
                }
            }
        }

        public void Notificar()
        {
            Console.WriteLine(" A vida do Herói " + HPHero + " / " + HPMaxHero);

            Console.WriteLine(" O ataque do Herói é " + ATAKHero);

            Console.WriteLine(" A experiencia do Herói é " + expAtualHeroi);

            Console.WriteLine(" O nivel atual do Herói é " + nivelAtualHeroi);

            Console.WriteLine(" ----------------------- ");

            Console.WriteLine(" A vida do Monstro " + HPMonster + " / " + HPMaxMonster);

            Console.WriteLine(" O ataque do Monstro é " + ATAKMonster);

            Console.WriteLine(" ----------------------- ");
        }

        public void NotificarGnomo()
        {
            Console.WriteLine(" A vida do Herói " + HPHero + " / " + HPMaxHero);

            Console.WriteLine(" O ataque do Herói é " + ATAKHero);

            Console.WriteLine(" A experiencia do Herói é " + expAtualHeroi);

            Console.WriteLine(" O nivel atual do Herói é " + nivelAtualHeroi);

            Console.WriteLine(" ----------------------- ");

            Console.WriteLine(" A vida do Monstro " + HPMonsterGnomo);

            Console.WriteLine(" O ataque do Monstro é " + ATAKMonsterGnomo);

            Console.WriteLine(" ----------------------- ");
        }

        public void NotificarDino()
        {
            Console.WriteLine(" A vida do Herói " + HPHero + " / " + HPMaxHero);

            Console.WriteLine(" O ataque do Herói é " + ATAKHero);

            Console.WriteLine(" A experiencia do Herói é " + expAtualHeroi);

            Console.WriteLine(" O nivel atual do Herói é " + nivelAtualHeroi);

            Console.WriteLine(" ----------------------- ");

            Console.WriteLine(" A vida do Monstro " + HPMonsterDino);

            Console.WriteLine(" O ataque do Monstro é " + ATAKMonsterDino);

            Console.WriteLine(" ----------------------- ");
        }

        public void NotificarGaviao()
        {
            Console.WriteLine(" A vida do Herói " + HPHero + " / " + HPMaxHero);

            Console.WriteLine(" O ataque do Herói é " + ATAKHero);

            Console.WriteLine(" A experiencia do Herói é " + expAtualHeroi);

            Console.WriteLine(" O nivel atual do Herói é " + nivelAtualHeroi);

            Console.WriteLine(" ----------------------- ");

            Console.WriteLine(" A vida do Monstro " + HPMonsterGaviao);

            Console.WriteLine(" O ataque do Monstro é " + ATAKMonsterGaviao);

            Console.WriteLine(" ----------------------- ");
        }

        public void NotificarChefao()
        {
            Console.WriteLine(" A vida do Herói " + HPHero + " / " + HPMaxHero);

            Console.WriteLine(" O ataque do Herói é " + ATAKHero);

            Console.WriteLine(" A experiencia do Herói é " + expAtualHeroi);

            Console.WriteLine(" O nivel atual do Herói é " + nivelAtualHeroi);

            Console.WriteLine(" ----------------------- ");

            Console.WriteLine(" A vida do Monstro " + HPMonsterChefao);

            Console.WriteLine(" O ataque do Monstro é " + ATAKMonsterChefao);

            Console.WriteLine(" ----------------------- ");
        }

        //----------primeiro_Turno---------------------------------------

        public void Turno()
        {
            if (Combate == true)
            {
                while (HPHero > 0 && HPMonster > 0)
                {
                    Console.WriteLine(" O Herói quer atacar(1) ou se curar(2)! ");
                    escolhaHeroiAtak = Console.ReadLine();
                    if (escolhaHeroiAtak == "1")
                    {
                        HeroATKMonster();
                    }
                    if (escolhaHeroiAtak == "2")
                    {
                        HeroCura();
                    }
                    MonsterATKHero();
                    Notificar();

                }
            }

            if (Combate == false && Loja == true)
            {
                LojaLoja();
            }

        }

        //----------segundo_Turno----------------------------------------

        public void TurnoGnomo()
        {
            HPHero = HPHero + 100;
            Console.WriteLine("Heroi curou 200 de vida");

            while (HPHero > 0 && HPMonsterGnomo > 0)
            {
                Console.WriteLine(" O Herói quer atacar(1) ou se curar(2)! ");
                escolhaHeroiAtak = Console.ReadLine();
                if (escolhaHeroiAtak == "1")
                {
                    HeroATKMonsterGnomo();
                }
                if (escolhaHeroiAtak == "2")
                {
                    HeroCura();
                }
                MonsterGnomoATKHero();
                NotificarGnomo();
            }

            if (Combate == false && Loja == true)
            {
                LojaLojaDino();
            }

        }

        //----------terceiro_Turno---------------------------------------

        public void TurnoDino()
        {
            HPHero = HPHero + 50;
            Console.WriteLine("Heroi curou 100 de vida");

            while (HPHero > 0 && HPMonsterDino > 0)
            {
                Console.WriteLine(" O Herói quer atacar(1) ou se curar(2)! ");
                escolhaHeroiAtak = Console.ReadLine();
                if (escolhaHeroiAtak == "1")
                {
                    HeroATKMonsterDino();
                }
                if (escolhaHeroiAtak == "2")
                {
                    HeroCura();
                }
                MonsterDinoATKHero();
                NotificarDino();
            }

            if (Combate == false && Loja == true)
            {
                LojaLojaGaviao();
            }

        }

        //----------Quarto_Turno-----------------------------------------

        public void TurnoGaviao()
        {
            HPHero = HPHero + 50;
            Console.WriteLine("Heroi curou 100 de vida");

            while (HPHero > 0 && HPMonsterGaviao > 0)
            {
                Console.WriteLine(" O Herói quer atacar(1) ou se curar(2)! ");
                escolhaHeroiAtak = Console.ReadLine();
                if (escolhaHeroiAtak == "1")
                {
                    HeroATKMonsterGaviao();
                }
                if (escolhaHeroiAtak == "2")
                {
                    HeroCura();
                }
                MonsterGaviaoATKHero();
                NotificarGaviao();
            }

            if (Combate == false && Loja == true)
            {
                LojaLojaChefao();
            }

        }

        //---------------------------------------------------------------

        public void TurnoChefao()
        {
            HPHero = HPHero + 150;
            Console.WriteLine("Heroi curou 100 de vida");

            while (HPHero > 0 && HPMonsterChefao > 0)
            {
                Console.WriteLine(" O Heroi quer atacar(1) ou se curar(2) ");
                escolhaHeroiAtak = Console.ReadLine();
                if (escolhaHeroiAtak == "1")
                {
                    HeroATKMonsterChefao();
                }
                if (escolhaHeroiAtak == "2")
                {
                    HeroCura();
                }
                MonsterChefaoATKHero();
                NotificarChefao();
            }

            if (Combate == false && Loja == true)
            {
                Console.WriteLine("Você derrotou o chefão do jogo, por tanto é o herói mais forte de todos os tempos, parabéns!");
                Console.WriteLine("Você gostaria de reiniciar o jogo? se Sim(1), se Não(2).");
                escolha = Console.ReadLine();

                if (escolhaBoss == "1")
                {
                    LojaLoja();
                }

                if (escolhaBoss == "2")
                {
                    Console.WriteLine("Fim de Jogo. Você é o Herói mais forte!");
                }
            }

        }

        //---------------------------------------------------------------

        public void EscolherClasse()
        {
            Console.WriteLine(" Escolha sua classe ");
            Console.WriteLine(" Gigante de ferro - Mini Mago ");
            Console.WriteLine(" Para Gigante de ferro escreva 1 - Para Mini Mago escreva 2 ");
            escolha = Console.ReadLine();

            if (escolha == "1")
            {
                classe = "Gigante de ferro";
                HPHero = 300;
                HPMaxHero = 400;
                ATAKHero = 40;

            }

            if (escolha == "2")
            {
                classe = "Mini Mago";
                HPHero = 100;
                HPMaxHero = 150;
                ATAKHero = 60;

            }
        }

        public void ATAKEspecial()
        {
            if (classe == "Gigante de ferro")
            {
                Console.WriteLine(" Gigante de ferro atirou com sua arma de plasma contra o inimigo! ");
                ATAKHero = ATAKHero + 30;
            }

            if (classe == "Mini Mago")
            {
                Console.WriteLine(" Mini Mago pulou sobre o inimigo gerando uma enorme bola de fogo e atirando-a contra ele! ");
                ATAKHero = ATAKHero + 30;
            }
        }

        public void Evoluir()
        {

            nivelAtualHeroi++;
            expAlvoHeroi += multiplicadorExpHeroi;

        }

        public void AtributosNivel()
        {
            if (nivelAtualHeroi == 2)
            {
                Console.WriteLine("Herói subiu de nivel, por tanto ganhou mais 20 de cada atributo");
                HPHero = HPHero + 20;
                HPMaxHero = HPMaxHero +20;
                ATAKHero = ATAKHero + 20;
            }

            if (nivelAtualHeroi == 3)
            {
                Console.WriteLine("Herói subiu de nivel, por tanto ganhou mais 30 de cada atributo");
                HPHero = HPHero + 30;
                HPMaxHero = HPMaxHero + 30;
                ATAKHero = ATAKHero + 30;
            }

            if (nivelAtualHeroi == 4)
            {
                Console.WriteLine("Herói subiu de nivel, por tanto ganhou mais 40 de cada atributo");
                HPHero = HPHero + 40;
                HPMaxHero = HPMaxHero + 40;
                ATAKHero = ATAKHero + 40;
            }
        }

        public void AlterarExperiencia(float xp)
        {

            expAtualHeroi += xp;
            if (expAtualHeroi >= expAlvoHeroi)

            {

                Evoluir();

            }

        }


    }

}
