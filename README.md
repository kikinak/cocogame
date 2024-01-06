Let's make a game!
	name:Coco Clicker
	by:Kikinak
	desc:Because why not
	created:1/5/2024
	updated:lmao
	version:1

Settings
	background:https://imgur.com/tAIrUEO.png
	building cost increase:105%
	building cost refund:75%
	spritesheet:icons, 48 by 48, stuff/bunnyIcons.png
	stylesheet:stuff/bigBlue.css

Layout
	use default
		
Buttons
	*cocoButton
		name:Pet the cat!
		desc:Click C'ocah to pet him and make him happy!
		on click:anim icon wobble
		on click:yield 1 happiness
		on click:if (have heavyPetting and chance(1%)) yield 1 milk
		on click:if (have heavyPetting and earScritches and chance(1%)) yield 1 milk
		on click:if (have heavyPetting and bellyRubs and chance(1%)) yield 1 milk
		on click:if (have heavyPetting and ppTouches and chance(1%)) yield 1 milk
		on click:if (have heavyPetting and tonguePets and chance(1%)) yield 1 milk
		on click:if (have heavyPetting and felatio and chance(1%)) yield 1 milk
		on click:if (have heavyPetting and buttStuff and chance(1%)) yield 1 milk
		on click:if (have heavyPetting and foreskinPlay and chance(1%)) yield 1 milk
		on click:if (have heavyPetting and cherry and chance(1%)) yield 1 milk
		on click:if (have heavyPetting and lood and chance(1%)) yield 1 milk
		icon:https://images2.imgbox.com/3f/9c/jzZdukBz_o.png
		no text
		class:bigButton hasFlares
		icon class:shadowed
		tooltip origin:bottom
		tooltip class:red
		
Resources
	*Happiness|happiness
		name:Happiness|Happiness
		desc:A representation of how happy you've made Coco! You want to make him as happy as possible, right?
		icon:icons[0,0]
		class:noBackground
		show earned
		
	*milk|milk
		name:milk|milk
		desc:When the cat gets REALLY happy he gives you some milk! A sign of a happy cat, and also a magical reagent!
		icon:icons[0,1]
		class:noBackground
		hidden when 0
		
Shinies
	*toy
		on click:log Woop
		movement:onRight moveLeft fade bounce:0.05
		frequency:60
		frequency variation:30
		icon:https://images2.imgbox.com/5d/ad/I0ZpVhfE_o.png
		class:bigButton
		on click:
				$amount=1
				toast You use the toy on C'ocah and get <//><b>[$amount] milk[s?$amount]</b>!
				yield $amount milk
			end
		end

Buildings
	*TEMPLATE
		on click:anim glow
		
	*plush|plushies
		name:Plush|Plushies
		desc:A cute stuff animal for C'ocah to snuggle.<//><b>Effect:</b><.>Produces 1 happiness every 10 seconds.
		icon:icons[3,0]
		cost:15 happiness
		on tick:yield 0.1 happiness
		unlocked
	
	*garden|gardens
		name:Garden|Gardens
		desc:A plot for C'ocah to plant st.<//><b>Effect:</b><.>Produces 1 happiness every 2 seconds.
		icon:icons[3,1]
		cost:100 happiness
		on tick:yield 0.5 happiness
		req:100 happiness:earned
	
	*friend|friends
		name:Friend|Friends
		desc:Somebody his age to play with<//><b>Effect:</b><.>Produces 5 happiness per second.
		icon:icons[3,2]
		cost:600 happiness
		on tick:yield 5 happiness
		req:600 happiness:earned
	
	*pet|pets
		name:Pet|Pets
		desc:A cute little animal friend to play and cuddle with<//><b>Effect:</b><.>Produces 12 happiness per second.
		icon:icons[3,3]
		cost:4000 happiness
		on tick:yield 12 happiness
		req:4000 happiness:earned
	
	*milf|milfs
		name:Milf|Milfs
		desc:His favorite type of person! The kid can't get enough of older women<//><b>Effect:</b><.>Produces 90 happiness per second.
		icon:icons[3,4]
		cost:20000 happiness
		on tick:yield 90 happiness
		req:20000 happiness:earned
	
	*smallGate|smallGates
		name:Small Gate|Small Gates
		desc:A rather small, rudimentary portal only capable of allowing bunny-size things through. Safe, if not particularly exciting<//><b>Effect:</b><.>Produces 300 happiness per second.
		icon:icons[3,5]
		cost:200000 happiness, 1 milk
		on tick:yield 300 happiness
		on tick:if (have lustBeacon) yield 0.01 milk
		req:200000 happiness:earned and bestialPlane

	*midGate|midGates
		name:Medium Gate|Medium Gates
		desc:Big enough for a person to walk through, though C'ocah's only allowed on our side for his safety<//><b>Effect:</b><.>Produces 1000 happiness per second.
		icon:icons[3,6]
		cost:3000000 happiness, 10 milk
		on tick:yield 1000 happiness
		on tick:if (have lustBeacon) yield 0.1 milk
		req:3000000 happiness:earned and bestialPlane
		
	*bigate|bigates
		name:Large Gate|Large Gates
		desc:Anything shy of a kaiju could come crawling out. Dangerous? Probably, but who cares, it's cool! And the boy always loved being with bigger partners<//><b>Effect:</b><.>Produces 4000 happiness per second.
		icon:icons[3,7]
		cost:70000000 happiness, 100 milk
		on tick:yield 4000 happiness
		on tick:if (have lustBeacon) yield 1 milk
		req:70000000 happiness:earned and bestialPlane
		
	*inverse
		name:Unlock Portal
		text:Unlock Portal ([this]%)
		desc:Allow the boy to enter the bestial plane. It'll be dangerous, but he'll be happy. And it's not like you're letting him go alone.<//><b>The portal is [this]% complete.</b>
		icon:icons[3,8]
		cost:300000000 happiness, 10000 milk
		req:70000000 happiness:earned and bestialPlane
		limit:100
		cost increase:105%
		
Upgrades
	*TEMPLATE
		on click:anim glow
	
	//action upgrades
	
	*headPats
		name:Headpats
		desc:Patting his head lets him know he's a good boy!<//><b>Effect:</b><.>+1 happiness/click
		icon:icons[1,1]
		cost:100 happiness
		passive:increase happiness yield of cocoButton by 1
		req:10 happiness:earned
		
	*earScritches
		name:Ear Scritches
		desc:The weakspot of many a cat, Coco being no exception<//><b>Effect:</b><.>+1 happiness/click
		icon:icons[1,2]
		cost:200 happiness
		passive:increase happiness yield of cocoButton by 1
		req:50 happiness:earned
		
	*bellyRubs
		name:Belly Rubs
		desc:Going further south seems to have better results. Could going further be better? Warrants further study.<//><b>Effect:</b><.>+1 happiness/click
		icon:icons[1,3]
		cost:400 happiness
		passive:increase happiness yield of cocoButton by 1
		req:200 happiness:earned
		
	*ppTouches
		name:ppTouches
		desc:We've officially found the best place to pet the cat! Where do we go from here?<//><b>Effect:</b><.>happiness/click x2<.>happiness production +5%
		icon:icons[1,4]
		cost:3000 happiness
		passive:multiply happiness yield of cocoButton by 2
		passive:multiply yield of happiness by 1.05
		req:1000 happiness:earned
		
	*tonguePets
		name:Tongue Pets
		desc:That is to say, using your tongue to pet him, not petting his tongue.<//><b>Effect:</b><.>happiness/click x1.5<.>happiness production +5%
		icon:icons[1,5]
		cost:10000 happiness
		passive:multiply happiness yield of cocoButton by 1.5
		passive:multiply yield of happiness by 1.05
		req:1000 happiness:earned
		
	*felatio
		name:Felatio
		desc:Why stop at just the tongue? Put the entire mouth to work! See if you can get the balls in there too!<//><b>Effect:</b><.>happiness/click x1.5<.>happiness production +5%
		icon:icons[1,6]
		cost:50000 happiness
		passive:multiply happiness yield of cocoButton by 1.5
		passive:multiply yield of happiness by 1.05
		req:10000 happiness:earned
		
	*buttStuff
		name:Butt Stuff
		desc:Are you touching his butt? Is HE touching YOUR butt? Who knows? Both, probably.<//><b>Effect:</b><.>happiness/click x1.5<.>happiness production +5%
		icon:icons[1,7]
		cost:100000 happiness
		passive:multiply happiness yield of cocoButton by 1.5
		passive:multiply yield of happiness by 1.05
		req:50000 happiness:earned
		
	*foreskinPlay
		name:Foreskin Play
		desc:All this time we thought he just didn't have a head down there, but we finally found it! And that means we can pet it, we just have to dig a little.<//><b>Effect:</b><.>happiness/click x1.5<.>happiness production +5%
		icon:icons[1,8]
		cost:500000 happiness
		passive:multiply happiness yield of cocoButton by 1.5
		passive:multiply yield of happiness by 1.05
		req:100000 happiness:earned
		
	*cherry
		name:Cherry
		desc:The time has come to properly take the cat's virginity<//><b>Effect:</b><.>happiness/click x2<.>happiness production +5%, instant bonus
		icon:icons[1,9]
		cost:1000000 happiness
		yield:2000000 happiness
		yield:10 milk
		passive:multiply happiness yield of cocoButton by 2
		passive:multiply yield of happiness by 1.05
		req:500000 happiness:earned
		
	*lood
		name:lood
		desc:Actual, proper sex. Mating press, amazon position, cowgirl, everything.<//><b>Effect:</b><.>happiness/click x3<.>happiness production +10%
		icon:icons[1,0]
		cost:100000000 happiness
		passive:multiply happiness yield of cocoButton by 3
		passive:multiply yield of happiness by 1.1
		req:1000000 happiness:earned
	
	//building upgrades
	
	*buildingUpgrade1
		name:FC House
		desc:A place to call home, keep his stuff, and play with friends!<//><b>Effect:</b><.>plush, garden, and friend production x2
		icon:icons[2,0] icons[3,0]
		cost:1000 happiness
		passive:multiply yield of plush by 2
		passive:multiply yield of garden by 2
		passive:multiply yield of friend by 2
		req:(plush>=10 or garden>=10 or friend>=10)
		
	*buildingUpgrade2
		name:Quicksands
		desc:The place, not the thing! A great place to find cuddle partners!<//><b>Effect:</b><.>pet, friend, and milf production x2
		icon:icons[2,0] icons[3,1]
		cost:100000 happiness
		passive:multiply yield of pet by 2
		passive:multiply yield of friend by 2
		passive:multiply yield of milf by 2
		req:(pet>=10 or friend>=50 or milf>=10)
		
	*buildingUpgrade3
		name:Events
		desc:Starlight, all saints wake, all sorts of opportunities to get free stuff and meet cool npcs!<//><b>Effect:</b><.>plush, garden, and friend production x2
		icon:icons[2,0] icons[3,2]
		cost:5000000 happiness
		passive:multiply yield of plush by 2
		passive:multiply yield of garden by 2
		passive:multiply yield of friend by 2
		req:(plush>=50 or garden>=50 or friend>=50)
		
	*buildingUpgrade4
		name:Private Bedroom
		desc:Sharing with the captain is great, but some partners prefer a bit more privacy<//><b>Effect:</b><.>pet and milf x2
		icon:icons[2,0] icons[3,3]
		cost:50000 happiness
		passive:multiply yield of pet by 2
		passive:multiply yield of milf by 2
		req:(pets>=50 or milfs>=50)
		
	*buildingUpgrade5
		name:Discord Server
		desc:Reach beyond the limits of the game, find even more friends!<//><b>Effect:</b><.>friend and milf production x2
		icon:icons[2,0] icons[3,4]
		cost:10000000 happiness
		passive:multiply yield of friend by 2
		passive:multiply yield of milf by 2
		req:(friend>=50 or milf>=50)
		
	*buildingUpgrade6
		name:Glams
		desc:Showing off cool glams will attract more attention, and by extension: New friends!.<//><b>Effect:</b><.>friend and milf x2
		icon:icons[2,0] icons[3,5]
		cost:500000 happiness
		passive:multiply yield of friend by 2
		passive:multiply yield of milf by 2
		req:(milf>=10 or friend>=10)
		
	*buildingUpgrade7
		name:Outside Profiles
		desc:Market your more intimate goods to let others find what they're looking for (you)<//><b>Effect:</b><.>milf production x4
		icon:icons[2,0] icons[3,6]
		cost:500000000 happiness
		passive:multiply yield of milf by 4
		req:50 milfs
		
	*buildingUpgrade8
		name:Dawntrail
		desc:The new expansion is sure to bring in more of, well, everything!<//><b>Effect:</b><.>everything brings in x2 happiness!
		icon:icons[2,0] icons[3,7]
		cost:1000000000 happiness
		passive:multiply yield of citadel by 2
		req: buildingUpgrade7
		
	//golden carrot upgrades
	
	*heavyPetting
		name:Heavy Petting
		desc:Knowing where to pet can make your cat more than just happy.<//><b>Effect:</b><.>1% chance per pet upgrade of gaining 1 milk per pet.
		icon:icons[2,5]
		cost:1 milk
		req:1 milk:earned
		
	*marketboard
		name:Marketboard
		desc:By playing the market you can earn more gil to buy more toys!<//><b>Effect:</b><.>toys appear 30% more often
		icon:icons[2,6]
		passive:multiply frequency of toys by 0.7
		cost:5 milk
		req:1 milk:earned
	
	*bestialPlane
		name:Bestial Plane
		desc:A gateway to another dimension full of beasts and monsters. Should be able to find Coco some new friends here!<//><b>Effect:</b><.>unlocks new buildings
		icon:icons[2,7]
		cost:10 milk
		req:5 milk:earned
		
	*aphrodisiac
		name:Aphrodisiac
		desc:a pink liquid that makes orgasms easier and bigger.<//><b>Effect:</b><.>multiply milk gains by 4
		icon:icons[2,8]
		cost:100 milk
		req:50 milk:earned

	*pheromones
		name:Pheromones
		desc: A sweet smelling gas that helps soothe, relax, and more.<//><b>Effect:</b><.>double happiness gains
		icon:icons[2,8]
		cost:100 milk
		req:50 milk:earned
		
	*lustBeacon
		name:Lust Beacon
		desc:A beacon for the far side of your portals that attracts monsters that are bit more friendly than usual<//><b>Effect:</b><.>Gates now slowly give milk!
		icon:icons[2,9]
		cost:100 milk
		req:50 milk:earned
		
Achievements
	*TEMPLATE
		on click:anim glow
		
	*bunnyAchiev1
		name:Happy Cat
		desc:You have pet the cat and made him happy, likely making yourself happy in the process
		req:1 happiness 
		icon:icons[2,4] icons[0,2] icons[0,6]
	*bunnyAchiev2
		name:Happier Cat
		desc:Awarded for acquiring 1,000 units of happiness. How is this measured anyway?
		req:1000 happiness 
		icon:icons[2,4] icons[0,3] icons[0,6]
	*bunnyAchiev3
		name:Happiest Cat
		desc:No cat has ever reached a million happy. Not until now anyway
		req:10000000 happiness 
		icon:icons[2,4] icons[0,4] icons[0,6]
		
	*clickAchiev1
		name:That Tickles
		desc:Pet C'ocah <b>10</b> times.
		req:10 cocoButton clicks
		icon:icons[2,2] icons[0,2] icons[0,6]
	*clickAchiev2
		name:Really Feeling It
		desc:Pet C'ocah <b>100</b> times.
		req:100 cocoButton clicks
		icon:icons[2,2] icons[0,3] icons[0,6]
	*clickAchiev3
		name:Cat Addiction
		desc:Pet C'ocah <b>2000</b> times.
		req:2000 cocoButton clicks
		icon:icons[2,2] icons[0,4] icons[0,6]
		
	*bunnyPsAchiev1
		name:Contented
		desc:Give Coco enough stuff to be 10 happy per second
		req:10 happiness per second
		icon:icons[2,3] icons[0,2] icons[0,6]
	*bunnyPsAchiev2
		name:Enjoyed
		desc:Passively make a thousand happiness per second
		req:1000 happiness per second
		icon:icons[2,3] icons[0,3] icons[0,6]
	*bunnyPsAchiev3
		name:Overjoyed
		desc:Produce <b>100000</b> happiness per second.
		req:100000 happiness per second
		icon:icons[2,3] icons[0,4] icons[0,6]
		
	*carrotAchiev1
		name:Something Came Out!
		desc:Obtain your first milk! Hopefully of many~
		req:1 milk
		icon:icons[0,1] icons[0,2]
	*carrotAchiev2
		name:Could get used to this
		desc:Make the cat cum a hundred times
		req:100 milk
		icon:icons[0,1] icons[0,3]
	*carrotAchiev3
		name:Cat Milker
		desc:harvest a thousand units of kitty cum
		req:1000 milk
		icon:icons[0,1] icons[0,4]
	
	*fortressAchiev
		name:Freedom!
		desc:Completely unlock the <b>bestial plane</b>.<//>This is it. You beat the game!
		req:100 inverse
		icon:icons[3,8] icons[0,4]
