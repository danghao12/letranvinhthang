### Hi there 👋
hao dep trai
thang dep trai

<!--
**letranvinhthang/letranvinhthang** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->



using System;

namespace vinhthang
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
class GameModel
{
    private int[] table;
    private int width, height;

    public GameModel(int _width, int _height, int _numOfType)
    {
        width = _width;
        height = _height;

        table = new int[height, width];

        // su dung de luu cac o da sinh ra pokemon
        HashSet<int> cellIndex = new HashSet<int>();

        // su dung de sinh so ngau nhien
        Random random = new Random();

        for (int i = 0; i < width * height / 2; i++)
        {
            // sinh ngau nhien 1 loai pokemon, nam trong khoang tu 1 -> _numOfType
            int typeOfPokemon = random.Next(1, _numOfType + 1);
            Console.WriteLine(i);
            // sinh ra o thu 1 chua pokemon, yeu cau la khong dc nam trong cellIndex
            int cell1 = random.Next(random.Next(0, width * height + 1));
            while (cellIndex.Contains(cell1))
                cell1 = random.Next(random.Next(0, width * height + 1));
            table[cell1 / width, cell1 % width] = typeOfPokemon;
            cellIndex.Add(cell1);

            // sinh ra o thu 2 chua pokemon, yeu cau la khong dc nam trong cellIndex
            int cell2 = random.Next(random.Next(0, width * height + 1));
            while (cellIndex.Contains(cell2))
                cell2 = random.Next(random.Next(0, width * height + 1));
            table[cell2 / width, cell2 % width] = typeOfPokemon;
            cellIndex.Add(cell2);

            Console.WriteLine(i);
        }
    }
}

public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        GameModel gameModel = new GameModel(20, 10, 10);
        for (int i = 0; i < gameModel.Height; i++)
            for (int j = 0; j < gameModel.Width; j++)
            {
                PictureBox px = new PictureBox();
                px.Width = 40;
                px.Height = 50;
                px.Top = 10 + i * 50;
                px.Left = 10 + j * 40;

                string name = "pieces" + gameModel.getCell(i, j).ToString() + ".png";
                px.Image = Image.FromFile(name);
                this.Controls.Add(px);
            }
        int i;
        print("Nhập i:");
        scanf("%d",&i);
        switch(i)
        {
            case 01: print("KQ: %d", i);
                       break;

    }
}
