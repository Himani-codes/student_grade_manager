import json
class Student_grade:
    def __init__(self):
        self.id = []
    def add_std(self,a,b):
        if b<0 or b>100:
            raise InvalidMarksError()
        n = {"name":a,"marks":b}
        self.id.append(n)
    def cal_mark(self):
        for i in self.id:
            if i["marks"]>=90 and i["marks"]<=100:
                print(i["name"],":","A")
            elif i["marks"]>=70 and i["marks"]<90:
                print(i["name"],":"," B")
            elif i["marks"]>=60 and i["marks"]<70:
                print(i["name"],":"," C")
            elif i["marks"]>=40 and i["marks"]<60:
                print(i["name"],":","D")
            else:
                print( i["name"],"Fail!")
    def topper(self):
        mm = 0
        for i in self.id:
            if i["marks"]>mm:
                mm = i["marks"]
        for i in self.id:
            if i["marks"] == mm:
                print("topper:",i["name"])
    def save_file(self,filename):
        with open(filename,"w") as f:
            json.dump(self.id,f)
    def load_file(self,filename):
        with open(filename,"r") as f:
            self.id = json.load(f)
            return self.id
class InvalidMarksError(Exception):
    def __init__(self,msg="marks should be between 0 to 100"):
        self.msg = msg
        super().__init__(self.msg)
def Menu():
    c1 = Student_grade()
    while True:
        try:
         i = int(input("enter choice from 1 to 6 if want to quit press 6: "))
         match i:
          case 1:
            a = input("a is :")
            b =  int(input("b is : "))
            c1.add_std(a,b)
            print(c1.id)
          case 2:
            c1.cal_mark()
          case 3:
            c1.topper()
          case 4:
            c1.save_file("him.txt")
            print("saved")
          case 5:
            print(c1.load_file("him.txt"))
          case 6:
            break
        except ValueError:
          print("error enter the numbers not string")
        except FileNotFoundError:
          print("no such file exist")
        except InvalidMarksError as e:
            print(e)
Menu()




