**Changing bounce angle based on how you hit something**

To make something move at an angle depending on how it hits something, you'll probably want to use the map() function.  This will let you calculate a value based on a variable, its current possible range, and the range you want it to have.

**Syntax for map function**

	map(variable, min of current range, max of current range, min of desired range, max of desired range)
	
often used as:
	variable = map(insert the above stuff)

**Example**

In this example, I have a ball whose coordinates are based on x,y, and r (for radius) bouncing off of a raft whose coordinates are based on raft.x, raft.y, and raft.w (for the width of the rectangle).  When the ball hits the top of the raft, the yspeed changes to a negative value.  The xspeed is assigned a value based on mapping x from the range of values where the raft is located to a range between the minimum and maximum speeds I want.

    if (x>=raft.x && x<= raft.x+raft.w && y+r>=raft.y) {      //bounce ball off raft
      yspeed=-abs(yspeed);
      xspeed=map(x, raft.x, raft.x+raft.w, -2, 2);
    }
