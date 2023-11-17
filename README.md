import logging

class Sim:
    def __init__(self, name):
        self.name = name
        self.energy = 100

    def sleep(self, hours):
        self.energy += hours * 10
        logging.info(f"{self.name} is sleeping. Energy is now {self.energy}.")

    def play(self, hours):
        if self.energy >= hours * 5:
            self.energy -= hours * 5
            logging.info(f"{self.name} is playing. Energy is now {self.energy}.")
        else:
            logging.warning(f"{self.name} is too tired to play.")
            

logging.basicConfig(level=logging.INFO, format='%(asctime)s - %(levelname)s - %(message)s')


sim = Sim("Sim1")
sim.sleep(3)
sim.play(2)
