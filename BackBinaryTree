#Author: Mikael Schirru
#Date 28/02/2018

class Node:
    def __init__(self, name, arc, value, children):
        self.name = name
        self.arc = arc 
        self.value = value
        self.children = children

class Message:
    def __init__(self, name, messageValue):
        self.name = name
        self.messageValue = messageValue

class Pilha(object):
    def __init__(self):
        self.dados = []

    def empilha(self, elemento):
        self.dados.append(elemento)

    def desempilha(self):
        if not self.vazia():
            return self.dados.pop(-1)
    
    def vazia(self):
        return len(self.dados) == 0


################# Iniciating objects ######################
no24 = Node("7.1", "none", None, [])
no23 = Node("7.2", "none", None, [])
no22 = Node("6.1", "or", None, [no23, no24])
no21 = Node("5.5", "none", None, [])
no20 = Node("5.4", "none", None, [])
no19 = Node("5.3", "none", None, [])
no18 = Node("5.2", "none", None, [])
no17 = Node("5.1", "and", None, [no22])

no16 = Node("4.9", "none", None, [])
no15 = Node("4.8", "and", None, [no21])
no14 = Node("4.7", "none", None, [])
no13 = Node("4.6", "none", None, [])
no12 = Node("4.5", "or", None, [no20])
no11 = Node("4.4", "or", None, [no18,no19])
no10 = Node("4.3", "none", None, [])
no9 = Node("4.2", "none", None, [])
no8 = Node("4.1", "or", None, [no17])

no7 = Node("3.4", "and", None, [no14,no15,no16])
no6 = Node("3.3", "or", None, [no12,no13])
no5 = Node("3.2", "and", None, [no11])
no4 = Node("3.1", "or", None, [no8, no9, no10])

no3 = Node("2.2", "and", None, [no7])
no2 = Node("2.1", "and", None, [no4, no5, no6])

no1 = Node("1", "or", None, [no2, no3])

message = Message("7.1", True)
message2 = Message("7.2", False)
message3 = Message("4.2", False)
message4 = Message("4.3", False)
message5 = Message("5.2", True)
message6 = Message("5.3", False)
message7 = Message("5.4", False)
message8 = Message("4.6", True)
message9 = Message("4.7", False)
message10 = Message("5.5", True)
message11 = Message("4.9", False)
#############################################################

node_list = [no1, no2, no3, no4, no5, no6, no8, no9, no10, no11, no12,no13,no14,no15,no16,no17,no18,no19,no20,no21,no22,no23,no24]
message_list = [message, message2, message3, message4,message5,message6,message7,message8,message9,message10,message11]
children_list = []
positives_list = []
leaf_list = []
listaTeste = []

############## METHODS ###############
def ExecMessage(message_list, leaf_list):
    for msg in message_list:
            for leaf in leaf_list:
                if msg.name == leaf.name:
                    leaf.value = msg.messageValue

def RemoveFromStack(_pilha, node):
    _pilha.desempilha()
    CheckLastInStack(node)


def CheckLastInStack(node):    
    listaTeste[:] = []    
    if node.value == None:
        for filho in node.children:
            if (filho.value != None):
                listaTeste.append("Ok")
                if (filho.value == True):
                    positives_list.append(filho)
            else:
                listaTeste.append("N")
                p.empilha(filho)
                CheckLastInStack(filho)
        
        if all(x == "Ok" for x in listaTeste):
            if node.arc == 'and':
                for x in node.children:
                    if x.value == False:
                        node.value = False
                        RemoveFromStack(p, node)
                        break
                else:
                    node.value = True
                    positives_list.append(node)
                    RemoveFromStack(p, node)

            if node.arc == 'or':
                for x in node.children:
                    if x.value == True:
                        node.value = True
                        positives_list.append(node)
                        RemoveFromStack(p, node)
                        break
                    else:
                        node.value = False
                        RemoveFromStack(p, node)

        

######################################

for node in node_list:
    if len(node.children) == 0:
        leaf_list.append(node)

ExecMessage(message_list, leaf_list)

p = Pilha()
for node in node_list:
    p.empilha(node)
    CheckLastInStack(node)
    break
    
print("Topo mais alto: ", node.name,node.value)
for x in positives_list:
    print("Lista de positivos: ", x.name)


        


    
  
      

        
        
        