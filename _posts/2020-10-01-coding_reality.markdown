---
layout: post
title:      "Coding Reality"
date:       2020-10-01 08:06:52 +0000
permalink:  coding_reality
---


   It is not amongst the most popular of opinions to think of code as being "realistic", what does that even mean, and what would its purpose even be? I wouldn't consider myself to be clever or the sherlock holms type, I don't seek to fill unanswered questions, at least not usually. Though In the last project I was working on, "JS and Rails API", I did so often chase what seemed too pointless questions, ones that, beyond my immediate desire, were far from relative to the task at hand. Though I found one thing particularly interesting, and for me at least, thought-provoking. I wondered if simulating code to behave like the natural world, is useful or just plain dumb.
	 
	 Now, for some, it may seem like an utterly stupid Idea, or relatively naive, and it may be. But, I digress. Let's start from The beginning, shall we? My project started off as what I thought to be a relatively simple and smooth sailing Idea, and for most, it would have been. I wanted to create a BlackJack game, How exciting right. It would have been so simple a game as simple as, and please mind my pseudocode, " if playing cards are more than house cards, the player loses else player wins", seems simple enough. Well, the truth of the matter is that it is. Then why I am I writing this then, well I've had a little motto since I started my venture into code "it's more important to understand why something works than why it does". Bare with me if you will. What I'm saying is that just because something can be simple does not necessarily mean that is it is or that it should. for example, I was working on a function for shuffling and I did some digging and I found this nifty little trick
	 
	`function shuffle (array) {
  let i = 0
    , j = 0
    , tmp = null

  for (i = array.length - 1; i > 0; i -= 1) {
    j = Math.floor(Math.random() * (i + 1))
    temp = array[i]
    array[i] = array[j]
    array[j] = temp
  }
}`
This is simply just taking one element and swapping it with a random element and then replacing its index with the swapped element. By the way, this is really good, casinos would love it if they could adopt a shuffling machine or dealer who could shuffle this well, but that's it isn't it. In reality, we don't have objects like Math.random.

  Now as I'm sure your aware, incomplete truth or as fare as my knowledge leads me to believe there are no random occurrences, everything can be calculated down and repeated if one had the 100% precision and info. What some might perceive to be "random" is just a group of events to large and too complicated for someone to keep track of. That is where I come in "dud, da du daaa", I thought it might be a nice idea to try and replicate how a deck of cards is shuffle or at leat to as much as possible. Professionals Use a method called Riffle, Riffle, Box, Riffle
	Step 1.) 
	Wash the Cards- washing the cards just means to put all 52 cards on the table and mix them up.
	`
	onst wash = (a) => {
	let shuffledDeck = r2b(a),
		ran = +Math.floor(Math.random() * 52),
		i = 0;
	while (i++ < ran) {
		shuffledDeck = r2b(shuffledDeck);
	}
	return shuffledDeck;
};
	`
	r2b is just  the method of riffle, riffle, box riffle. 
	Step 2.)
	Riffle- riffling is where you split a deck of cards and then send them layer one on top of the other than push them all together again
	`
	const riffle = (deck) => {
	let halfDeck = deck,
		tmp = [],
		half = Math.floor(halfDeck.length / 2),
		h1 = halfDeck.slice(0, half),
		h2 = halfDeck.slice(half, halfDeck.length);

	for (let i = 0; i < half; i++) {
		if (i % 2 == 1 || i == 0) {
			tmp.push(h1[i]);
			tmp.push(h2[i]);
		} else {
			tmp.push(h2[i]);
			tmp.push(h1[i]);
		}
	}
	return tmp;
};
	`
	Here I riffle the Deck one on top of the other before I box lt. 
	Now, this may not seem like much, and in the world, at large it really isn't but thoughts have a way of snowballing into something bigger. so do what you will with this information.
