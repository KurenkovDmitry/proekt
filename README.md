# proekt
def helper() :
        print("В любой момент вы можете набрать комманду 'help' и он откроет лист с объяснением пользования коммандой.")
        print("! ВНИМАНИЕ Во время ввода самого коэффициента нельзя вводить посторонние комманды, это может привести к ошибке программы!")
        print()
        print()
        print("При отправки вашего уравнения, напишите сначала режим ввода:")
        print("1: Отправьте 1, если желаете ввести коэффициент в виде целого числа или представленным в виде десятичной дроби. (Пример десятичной дроби: 1.076)")
        print("2: Отправьте 2, если желаете ввести коэффициент в виде дроби. Через прбел введите сначала чеслитель, а потом знамнатель.")    
        print("Пример ввода:")
        print()
        print("---------------------------------------------")
        print()
        print("        Введите коэффициент А:")
        print("        1")
        print("        117")
        print("        Введите коэффициент В:")
        print("        2")
        print("        17 168")
        print("        Введите коэффициент С:")
        print("        2")
        print("        13 174")
        print()
        print("---------------------------    ------------------")
        print()
        print("Если вы ошиблись при введении числа, напишите комманду 'error' и напишите коэффициент снова.")
        print("! ВНИМАНИЕ перед повторной задачей числа всё равно нужно ввести режим ввода!")
        print()
        print("Если вы хотите вернуться к вводу преведущего коэффициента, напишите комманду 'back'")
        print("! ВНИМАНИЕ при переходе на ввод предыдущего коэффициента, последующие придется вводить заново!")
        print()
        print()

end = 0
print("Здравствуйте! Вас приветствует онлайн решение уравнений вида Ax + By = C.")
print("Выберите режим работы:")
print("1: Отправьте 1, если желаете ознакомиться, как пользоваться программой. Если вы запускаете её в первый раз, убедительно прошу сначала выбрать этот пункт.")
print("2: Отправьте 2, если желаете узнать решение вашего линейного диофантового уравнения.")
command = str(input())
while end == 0 :
    while (command != "1") and (command != "2") and (command != 'help') :
        print("Извеняюсь, но вы совершили ошибку во время ввода, попробуйте ещё раз!")
        command = str(input())
    while command == 'help' :
        helper()
        print("Выберите режим работы:")
        print("1: Отправьте 1, если желаете ознакомиться, как пользоваться программой. Если вы запускаете её в первый раз, убедительно прошу сначала выбрать этот пункт.")
        print("2: Отправьте 2, если желаете узнать решение вашего линейного диофантового уравнения.")
        command = str(input())        
        
    if command == '1' :
        helper()
        command = 'go'
        
    print("Начнём работу:")
    print("Введите коэффициент А:")
    command = str(input())
    p = 1
    while command == 'help' :
        helper()
        print("Введите коэффициент А:")
        command = str(input())
    back = 0
    while command == 'back' or back == 0 :
        if p == 0 :
            print("Введите коэффициент А3:")
            command = str(input())
            while command == 'help' :
                helper()
                print("Введите коэффициент А:")
                command = str(input())
                while command == 'help' :
                    helper()
                    command = str(input())          
        else :
            p = 0
        prov = 0
        while prov == 0 :
            if command == '2' :
                a_ch, a_zn = map(float, input().split())
                while a_zn == 0 :
                    print("Знаменатель не может быть равным 0, введите другое число!")
                    a_zn = float(input())
                prov = 1
                back = 1
                if a_ch != 0 :
                    while (a_ch % 1 != 0) or (a_zn % 1 != 0) :
                        a_ch *= 10
                        a_zn *= 10
            elif command == '1' :
                a_ch = float(input())
                a_zn = 1
                prov = 1
                back = 1
                if a_ch != 0 :
                    while a_ch % 1 != 0 :
                        a_ch *= 10
                        a_zn *= 10
            elif command == 'back' :
                print("А - первый коэффициент!")
                print("Введите коэффициент А:")
                command = str(input())
                while command == 'help' :
                    helper()
                    print("Введите коэффициент А:")
                    command = str(input())
            elif command == 'error' :
                print("Введите заново: ")
                print("Введите коэффициент А:")
                command = str(input())
                while command == 'help' :
                    helper()
                    print("Введите коэффициент А:")
                    command = str(input())
            else :
                print("Извеняюсь, но вы совершили ошибку во время ввода, попробуйте ещё раз!")
                print("Введите коэффициент А:")
                command = str(input())
                while command == 'help' :
                    helper()
                    print("Введите коэффициент А:")
                    command = str(input())
            
        while back == 1 :
            print("Введите коэффициент В:")
            command = str(input())
            while command == 'help' :
                helper()
                print("Введите коэффициент В:")
                command = str(input())
            prov = int(0)
            while prov == 0 :
                if command == '2' :
                    b_ch, b_zn = map(float, input().split())
                    while b_zn == 0 :
                        print("Знаменатель не может быть равным 0, введите другое число!")
                        b_zn = float(input())
                    prov = 1
                    back = 2
                    if b_ch != 0 :
                        while (b_ch % 1 != 0) or (b_zn % 1 != 0) :
                            b_ch *= 10
                            b_zn *= 10
                elif command == '1' :
                    b_ch = float(input())
                    b_zn = 1
                    prov = 1
                    back = 2
                    if b_ch != 0 :
                        while b_ch % 1 != 0 :
                            b_ch *= 10
                            b_zn *= 10
                elif command == 'back' :
                    back = 0
                    prov = 1
                elif command == 'error' :
                    print("Введите заново: ")
                    back = 0
                    prov = 1
                else :
                    print("Извеняюсь, но вы совершили ошибку во время ввода, попробуйте ещё раз!")
                    print("Введите коэффициент В:")
                    command = str(input())
                    while command == 'help' :
                        helper()
                        print("Введите коэффициент В:")
                        command = str(input())
            
            
            while back == 2 :
                print("Введите коэффициент С:")
                command = str(input())
                while command == 'help' :
                    helper()
                    print("Введите коэффициент С:")
                    command = str(input())
                prov = 0
                while prov == 0 :
                    if command == '2' :
                        c_ch, c_zn = map(float, input().split())
                        while c_zn == 0 :
                            print("Знаменатель не может быть равным 0, введите другое число!")
                            c_zn = float(input())
                        prov = 1
                        back = 3
                        if c_ch != 0 :
                            while (c_ch % 1 != 0) or (c_zn % 1 != 0) :
                                c_ch *= 10
                                c_zn *= 10
                    elif command == '1' :
                        c_ch = float(input())
                        c_zn = 1
                        prov = 1
                        back = 3
                        if c_ch != 0 :
                            while c_ch % 1 != 0 :
                                c_ch *= 10
                                c_zn *= 10
                    elif command == 'back' :
                        back = 1
                        prov = 1
                    elif command == 'error' :
                        print("Введите заново: ")
                        back = 1
                        prov = 1
                    else :
                        print("Извеняюсь, но вы совершили ошибку во время ввода, попробуйте ещё раз!")
                        print("Введите коэффициент С:")
                        command = str(input())
                        while command == 'help' :
                            helper()
                            print("Введите коэффициент С:")
                            command = str(input())
                if back == 3 :
                    print()
                    print()
                    if a_zn != 1 :
                        if a_ch == 0:
                            print("A = 0")
                        elif (a_zn < 0 and a_ch > 0) or (a_zn > 0 and a_ch < 0) :
                            print("A = -", abs(int(a_ch)), "/", abs(int(a_zn)))
                        else :
                            print("A = ", abs(int(a_ch)), "/", abs(int(a_zn)))
                    else :
                        print("A =", int(a_ch))
                    if b_zn != 1 :
                        if b_ch == 0:
                            print("B = 0")
                        elif (b_zn < 0 and b_ch > 0) or (b_zn > 0 and b_ch < 0) :
                            print("B = -", abs(int(b_ch)), "/", abs(int(b_zn)))
                        else :
                            print("B = ", abs(int(b_ch)), "/", abs(int(b_zn)))
                    else :
                        print("B =", int(b_ch))
                    if c_zn != 1 :
                        if c_ch == 0:
                            print("C = 0")
                        elif (c_zn < 0 and c_ch > 0) or (c_zn > 0 and c_ch < 0) :
                            print("C = -", abs(int(c_ch)), "/", abs(int(c_zn)))
                        else :
                            print("C = ", abs(int(c_ch)), "/", abs(int(c_zn)))
                    else :
                        print("C =", int(c_ch))                    
                    print()
                    print()
                    print("Если устраивают введённые коэффициенты, то напишите 'yes', иначе для возвращения к вводу коэффициента С введите 'error'.")
                    command = str(input())
                    while command == 'help' :
                        helper()
                        print("Если устраивают введённые коэффициенты, то напишите 'yes', иначе для возвращения к вводу коэффициента С введите 'error'.")
                        command = str(input())
                    if command == 'error' :
                        back = 2
                            

    first_ch = int(c_ch * b_zn)
    first_zn = int(c_zn * b_ch)
    first_prov = 0
    first_znach = int()
            
    if first_ch % first_zn == 0 :
        first_prov = 1
        first_znach = int(first_ch // first_zn)
        first_ch = int(first_znach)
        first_zn = int(1)
    elif first_zn % first_ch == 0 :
        first_prov = 2
        first_znach = int(first_zn // first_ch)
        first_zn = int(first_znach)
        first_ch = int(1)                
    else :
        poisk = 0
        if first_ch > first_zn :
            i = int(2)
            while i <= first_zn // 2 and poisk == 0 :
                if first_ch % i == 0 and first_zn % i == 0 :
                    poisk = i      
                i += 1
        else :
            i = int(2)
            while i <= first_ch // 2 and poisk == 0 :
                if first_ch % i == 0 and first_zn % i == 0 :
                    poisk = i      
                i += 1
                
        while poisk != 0 :
            first_ch //= poisk
            first_zn //= poisk
            poisk = 0
            if first_ch > first_zn :
                i = int(2)
                while i <= first_zn // 2 and poisk == 0 :
                    if first_ch % i == 0 and first_zn % i == 0 :
                        poisk = i      
                    i += 1
            else :
                i = int(2)
                while i <= first_ch // 2 and poisk == 0 :
                    if first_ch % i == 0 and first_zn % i == 0 :
                        poisk = i      
                    i += 1
    
    second_ch = int(a_ch * b_zn)
    second_zn = int(a_zn * b_ch)
    second_prov = 0
    second_znach = int()
            
    if second_ch % second_zn == 0 :
        second_prov = 1
        second_znach = int(second_ch // second_zn)
        second_ch = int(second_znach)
        second_zn = int(1)                
    elif second_zn % second_ch == 0 :
        second_prov = 2
        second_znach = int(second_zn // second_ch)
        second_zn = int(second_znach)
        second_ch = int(1)               
    else :        
        poisk = 0
        if second_ch > second_zn :
            i = int(2)
            while i <= second_zn and poisk == 0 :
                if second_ch % i == 0 and second_zn % i == 0 :
                    poisk = i      
                i += 1
        else :
            i = int(2)
            while i <= second_ch and poisk == 0 :
                if second_ch % i == 0 and second_zn % i == 0 :
                    poisk = i      
                i += 1
            
        while poisk != 0 :
            second_ch //= poisk
            second_zn //= poisk
            poisk = 0
            if second_ch > second_zn :
                i = int(2)
                while i <= second_zn and poisk == 0 :
                    if second_ch % i == 0 and second_zn % i == 0 :
                        poisk = i      
                    i += 1
            else :
                i = int(2)
                while i <= second_ch and poisk == 0 :
                    if second_ch % i == 0 and second_zn % i == 0 :
                        poisk = i      
                    i += 1  
                
        
    print()
    print(first_ch, "/", first_zn)
    print(second_ch, "/", second_zn)
    print()
        
        
    print("Уравнение относительно y:")
    if (first_ch > 0 and first_zn > 0) or (first_ch < 0 and first_zn < 0) :
        if (second_ch > 0 and second_zn > 0) or (second_ch < 0 and second_zn < 0) :
            if first_prov == 0 :
                if second_prov == 0 :
                    print("y =", abs(int(first_ch)), "/", abs(int(first_zn)), "-", abs(int(second_ch)), "* x /", abs(int(second_zn)))
                elif second_prov == 1 :
                    print("y =", abs(int(first_ch)), "/", int(abs(first_zn)), "-", int(abs(second_znach)), "* x")
                else :
                    print("y =", abs(int(first_ch)), "/", int(abs(first_zn)), "- x /", int(abs(second_znach)))
            elif first_prov == 1 :
                if second_prov == 0 :
                    print("y =", int((first_znach)), "-", int(abs(second_ch)), "* x /", int(abs(second_znach)))
                elif second_prov == 1 :
                    print("y =", int((first_znach)), "-", int(abs(second_znach)), "* x")
                else :
                    print("y =", int((first_znach)), "- x /", int(abs(second_znach)))
            else :
                if second_prov == 0 :
                    print("y = 1 /", int(abs(first_znach)), "-", int(abs(second_ch)), "* x /", int(abs(second_zn)))
                elif second_prov == 1 :
                    print("y = 1 /", int(abs(first_znach)), "-", int(abs(second_znach)), "* x")
                else :
                    print("y = 1 /", int(abs(first_znach)), "- x /", int(abs(second_znach)))          
        else :
            if first_prov == 0 :
                if second_prov == 0 :
                    print("y =", int(abs(first_ch)), "/", int(abs(first_zn)), "+", int(abs(second_ch)), "* x /", int(abs(second_zn)))
                elif second_prov == 1 :
                    print("y =", int(abs(first_ch)), "/", int(abs(first_zn)), "+", int(abs(second_znach)), "* x")
                else :
                    print("y =", int(abs(first_ch)), "/", int(abs(first_zn)), "+ x /", int(abs(second_znach)))
            elif first_prov == 1 :
                if second_prov == 0 :
                    print("y =", int((first_znach)), "+", int(abs(second_ch)), "* x /", int(abs(second_znach)))
                elif second_prov == 1 :
                    print("y =", int((first_znach)), "+", int(abs(second_znach)), "* x")
                else :
                    print("y =", int((first_znach)), "+ x /", int(abs(second_znach)))
            else :
                if second_prov == 0 :
                    print("y = 1 /", int(abs(first_znach)), "+", int(abs(second_ch)), "* x /", int(abs(second_znach)))
                elif second_prov == 1 :
                    print("y = 1 /", int(abs(first_znach)), "+", int(abs(second_znach)), "* x")
                else :
                    print("y = 1 /", int(abs(first_znach)), "+ x /", int(abs(second_znach)))
    else :
        if (second_ch > 0 and second_zn > 0) or (second_ch < 0 and second_zn < 0) :
            if first_prov == 0 :
                if second_prov == 0 :
                    print("y = -", int(first_ch), "/", int(first_zn), "-", int(abs(second_ch)), "* x /", int(abs(second_znach)))
                elif second_prov == 1 :
                    print("y = -", int(first_ch), "/", int(first_zn), "-", int(second_znach), "* x")
                else :
                    print("y = -", int(first_ch), "/", int(first_zn), "- x /", int(second_znach))
            elif first_prov == 1 :
                if second_prov == 0 :
                    print("y = -", int(abs(first_znach)), "-", int(abs(second_ch)), "* x /", int(abs(second_zn)))
                elif second_prov == 1 :
                    print("y = -", int(abs(first_znach)), "-", int(abs(second_znach)), "* x")
                else :
                    print("y = -", int(abs(first_znach)), "- x /", int(abs(second_znach)))
            else :
                if second_prov == 0 :
                    print("y = - 1 /", int(abs(first_znach)), "-", int(abs(second_ch)), "* x /", int(abs(second_zn)))
                elif second_prov == 1 :
                    print("y = - 1 /", int(abs(first_znach)), "-", int(abs(second_znach)), "* x")
                else :
                    print("y = - 1 /", int(abs(first_znach)), "- x /", int(abs(second_znach)))          
        else :
            if first_prov == 0 :
                if second_prov == 0 :
                    print("y = -", int(abs(first_ch)), "/", int(abs(first_zn)), "+", int(abs(second_ch)), "* x /", int(abs(second_zn)))
                elif second_prov == 1 :
                    print("y = -", int(abs(first_ch)), "/", int(abs(first_zn)), "+", int(abs(second_znach)), "* x")
                else :
                    print("y = -", int(abs(first_ch)), "/", int(abs(first_zn)), "+ x /", int(abs(second_znach)))
            elif first_prov == 1 :
                if second_prov == 0 :
                    print("y = -", int(abs(first_znach)), "+", int(abs(second_ch)), "* x /", int(abs(second_zn)))
                elif second_prov == 1 :
                    print("y = -", int(abs(first_znach)), "+", int(abs(second_znach)), "* x")
                else :
                    print("y = -", int(abs(first_znach)), "+ x /", int(abs(second_znach)))
            else :
                if second_prov == 0 :
                    print("y = - 1 /", int(abs(first_znach)), "+", int(abs(second_ch)), "* x /", int(abs(second_zn)))
                elif second_prov == 1 :
                    print("y = - 1 /", int(abs(first_znach)), "+", int(abs(second_znach)), "* x")
                else :
                    print("y = - 1 /", int(abs(first_znach)), "+ x /", int(abs(second_znach)))        
            
    prov = 0
    while prov == 0 :
        print("Отправьте 1, если хотите получить получить решение уравнения при x = -1; x = 0; x = 1; x = 2; x = 3.")
        print("Отправьте 2, если хотите получить ответ, при своём х.")
        command = str(input())
        while command == 'help' :
            helper()
            command = str(input())
        if command == '1' :
            for x in range(-1, 4) :
                y_ch = int(first_ch * second_zn - second_ch * first_zn * x)
                y_zn = int(first_zn * second_zn)
                y_znach = int(0)
                y_prov = 0
                if y_ch % y_zn == 0 :
                    y_prov = 1
                    y_znach = int(y_ch // y_zn)
                    y_ch = int(y_znach)
                    y_zn = int(1)
                elif y_zn % y_ch == 0 :
                    y_prov = 2
                    y_znach = int(y_zn // y_ch)
                    y_zn = int(y_znach)
                    y_ch = int(1)                
                else :                    
                    poisk = 0
                    if y_ch > y_zn :
                        i = int(2)
                        while i <= y_zn // 2 and poisk == 0 :
                            if y_ch % i == 0 and y_zn % i == 0 :
                                poisk = i      
                            i += 1
                    else :
                        i = int(2)
                        while i <= y_ch // 2 and poisk == 0 :
                            if y_ch % i == 0 and y_zn % i == 0 :
                                poisk = i      
                            i += 1
                                
                    while poisk != 0 :
                        y_ch //= poisk
                        y_zn //= poisk
                        poisk = 0
                        if y_ch > y_zn :
                            i = int(2)
                            while i <= y_zn // 2 and poisk == 0 :
                                if y_ch % i == 0 and y_zn % i == 0 :
                                    poisk = i      
                                i += 1
                        else :
                            i = int(2)
                            while i <= y_ch // 2 and poisk == 0 :
                                if y_ch % i == 0 and y_zn % i == 0 :
                                    poisk = i      
                                i += 1    
                if (y_ch > 0 and y_zn > 0) or (y_ch < 0 and y_zn < 0) :
                    if y_prov == 0 :
                        print("(", x, "; ", abs(y_ch), " / ", abs(y_zn), ")", sep = "")
                    elif y_prov == 2 :
                        print("(", x, "; ", 1, " / ", abs(y_zn), ")", sep = "")
                    else :
                        print("(", x, "; ", abs(y_znach), ")", sep = "")
                else :
                    if y_prov == 0 :
                        print("(", x, "; - ", abs(y_ch), " / ", abs(y_zn), ")", sep = "")
                    elif y_prov == 2 :
                        print("(", x, "; - ", 1, " / ", abs(y_zn), ")", sep = "")
                    else :
                        print("(", x, "; - ", abs(y_znach), ")", sep = "")                    
                            
            prov = 1
        elif command == '2' :
            pr = 0
            while pr == 0 :
                prov = 1
                p = 0
                while p == 0 :
                    print("Введите 1, если хотите ввести x в виде целого числа или десятичной дроби. На следующей строчке введите само значение.")
                    print("Введите 2, если хотите ввести х в виде дроби. На следующей строчке через пробел введите сначала чеслитель, а потом знаменатель.")
                    command = str(input())
                    while command == 'help' :
                        helper()
                        print("Введите 1, если хотите ввести x в виде целого числа или десятичной дроби. На следующей строчке введите само значение.")
                        print("Введите 2, если хотите ввести х в виде дроби.                         На следующей строчке через пробел введите сначала чеслитель, а потом знаменатель.")
                        command = str(input())
                    if command == '1' :
                        p = 1
                        x = float(input())
                        x_zn = int(1)
                        while x % 1 != 0 :
                            x *= 10
                            x_zn *= 10
                        x_ch = int(x)
                    elif command == '2' :
                        p = 1
                        x_ch, x_zn = map(float, input().split())
                        while x_ch % 1 != 0 or x_zn % 1 != 0 :
                            x_ch *= 10
                            x_zn *= 10
                    else :
                        print("Вы ввели не верную комманду, попробуйте ещё раз.")
                
                    poisk = 0
                    if x_ch > x_zn :
                        i = int(2)
                        while i <= x_zn and poisk == 0 :
                            if x_ch % i == 0 and x_zn % i == 0 :
                                poisk = i      
                            i += 1
                    else :
                        i = int(2)
                        while i <= x_ch and poisk == 0 :
                            if x_ch % i == 0 and x_zn % i == 0 :
                                poisk = i      
                            i += 1
                                                
                    while poisk != 0 :
                        x_ch //= poisk
                        x_zn //= poisk
                        poisk = 0
                        if x_ch > x_zn :
                            i = int(2)
                            while i <= x_zn and poisk == 0 :
                                if x_ch % i == 0 and x_zn % i == 0 :
                                    poisk = i      
                                i += 1
                        else :
                            i = int(2)
                            while i <= x_ch and poisk == 0 :
                                if x_ch % i == 0 and x_zn % i == 0 :
                                    poisk = i      
                                i += 1                                    
                                        
                    y_ch = int(first_ch * second_zn * x_zn - second_ch * first_zn * x_ch)
                    y_zn = int(first_zn * second_zn * x_zn)
                    y_znach = int(0)
                    y_prov = 0
                    if y_ch % y_zn == 0 :
                        y_prov = 1
                        y_znach = int(y_ch // y_zn)
                        y_ch = int(y_znach)
                        y_zn = int(1)
                    elif y_zn % y_ch == 0 :
                        y_prov = 2
                        y_znach = int(y_zn // y_ch)
                        y_zn = int(y_znach)
                        y_ch = int(1)                
                    else :                    
                        poisk = 0
                        if y_ch > y_zn :
                            i = int(2)
                            while i <= y_zn and poisk == 0 :
                                if y_ch % i == 0 and y_zn % i == 0 :
                                    poisk = i      
                                i += 1
                        else :
                            i = int(2)
                            while i <= y_ch and poisk == 0 :
                                if y_ch % i == 0 and y_zn % i == 0 :
                                    poisk = i      
                                i += 1
                    
                        while poisk != 0 :
                            y_ch //= poisk
                            y_zn //= poisk
                            poisk = 0
                            if y_ch > y_zn :
                                i = int(2)
                                while i <= y_zn and poisk == 0 :
                                    if y_ch % i == 0 and y_zn % i == 0 :
                                        poisk = i      
                                    i += 1
                            else :
                                i = int(2)
                                while i <= y_ch and poisk == 0 :
                                    if y_ch % i == 0 and y_zn % i == 0 :
                                        poisk = i      
                                    i += 1    
                        if x_zn == 1 :
                            if y_prov == 0 :
                                print("(", x_ch, "; ", y_ch, " / ", y_zn, ")", sep = "")
                            elif y_prov == 2 :
                                print("(", x_ch, "; ", 1, " / ", y_zn, ")", sep = "")
                            else :
                                print("(", x_ch, "; ", y_znach, ")", sep = "")
                        else :
                            if y_prov == 0 :
                                print("(", x_ch, " / ", x_zn, "; ", y_ch, " / ", y_zn, ")", sep = "")
                            elif y_prov == 2 :
                                print("(", x_ch, " / ", x_zn, "; ", 1, " / ", y_zn, ")", sep = "")
                            else :
                                print("(", x_ch, " / ", x_zn, "; ", y_znach, ")", sep = "")                                
                
                print("Хотите ли ввести ещё одно число? yes/no")
                command = str(input())
                while command == 'help' :
                    helper()
                    print("Хотите ли ввести ещё одно число? yes/no")
                    command = str(input())
                if command == 'no' :
                    pr = 1
                elif command != 'yes' :
                    print("Вы ввели не верную комманду, попробуйте ещё раз.")
                    
                    
    
    while command == 'help' :
        helper()
    prov = 0
    while (prov == 0) and (command != 'help') :
        print()
        print("Хотите ввести ещё одно уравнение, тогда введите 'yes', иначе введите 'no'.")
        command = str(input())
        if command != help :
            if command == 'no' :
                end = 1
                prov = 1
            elif command == 'yes' :
                command = str(2)
                moment = 0
                prov = 1
            else :
                print("Вы ввели не верную комманду, попробуйте ещё раз.")
print("Досвидания.")
