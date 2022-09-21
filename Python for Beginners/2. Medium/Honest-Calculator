import operator
ops = {"+": operator.add, "-": operator.sub, "*": operator.mul, "/": operator.truediv}
msg = ("Enter an equation\n", "Do you even know what numbers are? Stay focused!",
        "Yes ... an interesting math operation. You've slept through all classes, haven't you?",
       "Yeah... division by zero. Smart move...", "Do you want to store the result? (y / n):\n",
       "Do you want to continue calculations? (y / n):\n",
       " ... lazy", " ... very lazy", " ... very, very lazy", "You are",
       "Are you sure? It is only one digit! (y / n)\n",
       "Don't be silly! It's just one number! Add to the memory? (y / n)\n",
       "Last chance! Do you really want to embarrass yourself? (y / n)\n")
memory = 0

def is_one_digit(v):
    return v > -10 and v < 10 and v.is_integer()

def check(v1, v2, v3):
    msg = ""

    if is_one_digit(v1) and is_one_digit(v2):
        msg = msg + " ... lazy"
    if (v1 == 1 or v2 == 1) and v3 == "*":
        msg = msg + " ... very lazy"
    if (v1 == 0 or v2 == 0) and (v3 == "*" or v3 == "+" or v3 == "-"):
        msg = msg + " ... very, very lazy"
    if msg != "":
        msg = "You are" + msg
    print(msg)

def memory_one_digit(message):
    while True:
        answer = input(message)
        if answer == "y":
            return True
        elif answer == "n":
            return False


while True:
    try:
        calc = input(msg[0]).split()
        calc = [i if i != "M" else memory for i in calc]
        x, oper, y = float(calc[0]), calc[1], float(calc[2])
        check(x, y, oper)
        result = ops[oper](x, y)
        print(result)

        if memory_one_digit(msg[4]):
            if is_one_digit(result):
                msg_index = 10
                while memory_one_digit(msg[msg_index]):
                    if msg_index < 12:
                        msg_index += 1
                    else:
                        memory = result
                        break
            else:
                memory = result

        if not memory_one_digit(msg[5]):
            break

    except ValueError:
        print(msg[1])
    except KeyError:
        print(msg[2])
    except ZeroDivisionError:
        print(msg[3])
