#Menu_item-----------------------------------------------
class MenuItem:
    def __init__ (self,name,price):
        self.name = name
        self.price = price

    
    def info (self):
        return (self.name + ': ¥' + str(self.price))
    def get_total_price(self,count):
        total_price = self.price * count
           
        if count >= 3:
            total_price *= 0.9 
            
        
   
        return round(total_price)



#pan-------------------------------------------------------
class Pan (MenuItem):
    def __init__ (self,name,price):
        super().__init__(name,price)
    def info (self):
        return self.name + ': ¥' + str(self.price)
#vege------------------------------------------------------
class Vege (MenuItem):
     def __init__ (self,name,price):
        super().__init__(name,price)
     def info (self):
        return self.name + ': ¥' + str(self.price)
#meat------------------------------------------------------
class Meat (MenuItem):
     def __init__ (self,name,price):
        super().__init__(name,price)
     def info (self):
        return self.name + ': ¥' + str(self.price)
#source-----------------------------------------------------
class Source (MenuItem):
     def __init__ (self,name,price):
        super().__init__(name,price)
     def info (self):
        return self.name + ': ¥' + str(self.price)
#script-----------------------------------------------------
pan1 = Pan('食パン ',100)
pan2 = Pan('ベーグル ',120)
pan3 = Pan('ライ麦パン ', 100)
pan４ = Pan('レーズンパン ', 110)

pans = [pan1, pan2, pan3,pan4]

vege1 = Vege('レタス ', 100)
vege2 = Vege('トマト ', 100)
vege3 = Vege('オニオン ',100)
vege4 = Vege('アボカド ',150)
vege5 = Vege('野菜全部盛り　',400)

veges = [vege1,vege2 ,vege3,vege4,vege5]

meat1 = Meat('ポーク ', 150)
meat2 = Meat('チキン ', 150)
meat3 = Meat('ビーフ ', 200)
meat4 = Meat('肉全部盛り ', 450)

meats = [meat1,meat2,meat3,meat4]

source1 = Source('ケチャップ ', 50)
source2 = Source('マヨネーズ ', 50)
source3 = Source('タルタル ', 50)
source4 = Source('チーズ ', 80)

sources = [source1, source2, source3,source4]

print('・パン　メニュー')

index = 0
for pan in pans:
    print(str(index) + '. ' + pan.info())
    index += 1
print('--------------------')

print('・野菜　メニュー')
index = 0
for vege in veges:
    print(str(index) + '. ' + vege.info())
    index += 1
print('--------------------')

print('・お肉　メニュー')
index = 0
for meat in meats:
    print(str(index) + '. ' + meat.info())
    index += 1
print('--------------------')
    
print('・ソース　メニュー')
index = 0
for source in sources:
    print(str(index) + '. ' + source.info())
    index += 1

print('--------------------')

pan_order = int(input('お好みの パン の番号を選択してください: '))
selected_pan = pans[pan_order]

vege_order = int(input('お好みの 野菜 の番号を選択してください: '))
selected_vege = veges[vege_order]

meat_order = int(input('お好みの お肉 の番号を選択してください: '))
selected_meat = meats[meat_order]

source_order = int(input('お好みの ソース の番号を選択してください: '))
selected_source = sources[source_order]

count = int(input('何セット買いますか？(3つ以上で1割引): '))

result = selected_pan.get_total_price(count) + selected_vege.get_total_price(count) + selected_meat.get_total_price(count) + selected_source.get_total_price(count)

print('Your Sandwitch' + '  :' + selected_vege.name + selected_meat.name + selected_source.name +  selected_pan.name)
print('合計は' + str(result) + '円です')



