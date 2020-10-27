# Using the repo
Clone repo (and submodules): git clone --recurse-submodules https://github.com/guilleatm/love2d-utils.git
Update repo (and submodules): git submodule update --remote
Push repo (and submodules): git push --recurse-submodules=on-demand

# Useful code for making games with Löve2D

[Löve2D web](https://love2d.org/wiki/Main_Page)

## Animations

Download Animation.lua for making this work (and the .png)

```lua
-- main.lua

require 'Animation'


function love.load()
	love.graphics.setDefaultFilter("nearest", "nearest") -- Not necessary, it is for loading correctly pixelart images.

	local img = love.graphics.newImage("oldHero.png") -- Sprite size --> 16 x 18
	myAnimation = Animation:new(img, 16, 18, 0.5, true) -- The animation takes 0.5 seconds and loops until myAnimation:stop()
	myAnimation:setScale(8) -- The drawn image is 8 times bigger than the real size.
	myAnimation:addCallback(5, function() print("I am called in the frame 5!!") end) -- Each time the animation reaches the 5 frame, this function is called.
	myAnimation:start() -- Starts the animation.
end



function love.update(dt)
	myAnimation:update(dt) -- Remember the update and the draw!!
end


function love.draw()
	myAnimation:draw(200, 200) -- Remember the update and the draw!!
end
```

## Tilemaps

Create your own tilemaps with this library!!

## Utils

Useful functions for your games (a bit random)

## Camera

Simple and useful camera (not mine)

## Pathfinding (A*)

[Pathfinding Algorithm A*](https://github.com/lattejed/a-star-lua) (not mine)
