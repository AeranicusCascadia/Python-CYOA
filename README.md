# Python-CYOA
interactive fiction/CYOA game
# CYOA adventure

import textwrap

class Game:
	def __init__(self):
		self.running = True
		self.won = False
		self.lost = False

class Player:
	def __init__(self):
		self.name = "player"
		self.health = 100
		self.strength = 10
		self.agility = 10
		self.constitution = 10
		self.perception = 10
		self.mindpower = 10
		self.willpower = 10
		
	def display_stats(self):
		print("")
		print(self.name)
		print("-"*len(self.name))
	
		self.stat_titles = ["Health: ", "Strength: ", "Agility: ", "Constitution: ", "Perception: "\
		, "Mindpower: ", "Willpower: "]
		self.stats = [self.health, self.strength, self.agility, self.constitution\
		, self.perception, self.mindpower, self.willpower]
		stat_lines = zip(self.stat_titles, self.stats)
		
		for line in stat_lines:
			cat_line = ""
			for item in line:
				cat_line += str(item)
			print(cat_line)
				
class Scene:
	def __init__(self, id):
		self.id = id
		
		self.scene_text = """You awaken suddenly to the sounds of panic and combat. You bolt upright and stumble out of your simple stray bed.
Your heart is hammering as you look rapidly look around you, scanning for signs of immediate danger. 
The acrid odor of smoke tickles your nostrils. You realize that the village is burning.
		
		"""
	 
	
		
	def display_scene_text(self):
		wrapper = textwrap.TextWrapper(width=75)
		content = wrapper.wrap(text=self.scene_text)
		for element in content:
			print(element)
	
	
my_scene = Scene("01")
player = Player()

player.display_stats()
