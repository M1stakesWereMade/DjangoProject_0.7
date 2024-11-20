from task1.models import Buyer
from task1.models import Game
Buyer.objects.create(name='pavel88', balance=150.75, age='16')
Buyer.objects.create(name='dima78', balance=1763, age='28')
Buyer.objects.create(name='iliya', balance=9999.99, age='31')
Game.objects.create(title='Metro 2033', cost=79.99, size=56, description='', age_limited=True)
Game.objects.create(title='God of War', cost=89.99, size=120, description='', age_limited=True)
Game.objects.create(title='Dune 2000', cost=59.99, size=25, description='')
fst_buyer = Buyer.objects.get(age__lt=18)
sec_buyer, thrd_buyer = Buyer.objects.filter(age__gt=18)
Game.objects.get(id=3).buyer.set((fist_buyer, second_buyer, thrd_buyer))
Game.objects.get(id=1).buyer.set((second_buyer, thrd_buyer))
Game.objects.get(id=2).buyer.set([thrd_buyer])