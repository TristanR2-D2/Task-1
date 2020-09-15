# Task-1

abstract class Tile
        {
            public enum TileType
            { HERO, ENEMY, GOLD, WEAPON }

           
        private int posX;
        private int posY;
        private TileType type;

            public virtual void TypePosition( int xpos, int ypos)
            {
                posX = xpos;
                posY = ypos;
            }
            public abstract bool IsValidMove(int xpos, int ypos);
           
        }
        class EmptyTile : Tile
    {
        public override bool IsValidMove(int xpos, int ypos)
        {
            throw new NotImplementedException();
        }
        public virtual void EmptyTilePos(int xpos, int ypos)
        { TypePosition(xpos, ypos); }
    }


    abstract class Character: Tile
    {
        public override bool IsValidMove(int xpos, int ypos)
        {
            throw new NotImplementedException();
        }
        public enum Movement
        { NoMovement, Up, Down,Left,Right}

        private int HP;
        private int MaxHp;
        private int Damage;
        private int[][] TileArray;

        public virtual void CharPosition(int xpos, int ypos, char symbol)
        {
            
        }
        
 public virtual void Attack()
        { int enemyHp=0;
           enemyHp = enemyHp - Damage; }
        public bool IsDead()
        {
            if( HP == 0)
            { return true; }
        else
            { return false; }    
               }
                public virtual bool CheckRange()
            {if (DistanceTo() > 1)
            { return false; }
            else { return true; }    
                    }
        private int DistanceTo()
        { }
        
         public void Move(MovementEnum move)
            { if (Movement == 1)
                { ypos = ypos + 1; }
                else if (Movement == 2)
                { ypos = ypos - 1; }
                else if (Movement == 3)
                { xpos = xpos - 1; }
                else if (Movement == 1)
                { xpos = xpos + 1; }
            }

    }
