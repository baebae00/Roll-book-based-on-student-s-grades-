# Roll-book-based-on-student-s-grades-
### Enter the program's number from the user and run the program.  
### In the program, you can use the program.  
### First, enter student information and add it to the list (school number, name, test score and homework score)
### Second, enter your student number and remove it from the list.  
### Third, print out the list in order of student numbers.  
### Fourth, print the list in order of total score (test score + sum of two homework scores) (from information of students with large total score to low score) 
### Fifth, shut down the program.  

```python
def function1(ids, names, exams, hw1s, hw2s):
    return {x : [y,z,w,q] for x,y,z,w,q in zip(ids,names,exams,hw1s,hw2s)}
  #학번을 key로, 이름, 시험성적, 숙제1과 숙제2의 점수를 values로 갖는 딕셔너리를 선언
def function2(result):
    a=int(input("추가할 학번을 입력하세요: "))
    if a in result.keys(): #사용자로부터 입력받은 학번이 이미 명단에 존재한다면
        print("이미 등록된 학번입니다.")
        return result
    else: #사용자로부터 입력받은 학번이 명단에 존재하지않을 경우
        b=input("이름을 입력하세요: ")
        c=int(input("시험성적을 입력하세요: "))
        d=int(input("숙제 1 성적을 입력하세요: "))
        e=int(input("숙제 2 성적을 입력하세요: "))
        result[a]=[b,c,d,e] #입력받은 학번을 key로, 나머지를 values로 저장
        return result
        
def function3(result):
    f=int(input("삭제할 학번을 입력하세요: "))
    if f in result.keys(): #입력받은 학번이 명단에 존재한다면
        del result[f] #해당 학번의 딕셔너리 전체를 삭제
        return result
    else: #입력받은 학번이 명단에 존재하지않을 경우
        print("등록되지 않은 학생입니다.")
        return result
    
def function4(result):
    for k,v in sorted(result.items()):
        print(k,v[0])
        
    

def function5(result):
    for k,v in result.items(): #딕셔너리의 key와 values를 가져옴
        i=v[-3]+v[-2]+v[-1] #딕셔너리의 values가 리스트로 만들어진 v, 시험성적, 숙제1, 숙재2를 더한 값을 i에 할당함
        v.insert(0,i) #리스트 v의 가장 앞쪽에 i를 위치시킴
    p=sorted(result.items(),reverse=True,key=lambda item:item[1])
     #{학번 : 총점,학번,'''} 형태의 딕셔너리를 p에 할당함
    for k,v in p:
        print(v[0],k,v[1]) # 총점,학번,이름 형태로 출력됨
        del(v[0]) #프로그램을 종료하지않고 계속 실행했을 때의 오류발생을 방지하기위해 v[0]을 삭제해줌
        

#학번
ids = [20197492, 20195440, 20162383, 20196349,
       20189041, 20196787, 20078627, 20171338,
       20183410, 20176422, 20095244, 20151810,
       20071234, 20172167, 20005891, 20151379,
       20188170, 20195497, 20191857, 20196846] 

#이름
names = ['송산', '혁', '고운', '나연',
         '콘', '난새', '노아', '다슬',
         '다온', '든솔', '규우', '로와',
         '모듬', '바다', '보아', '세찬',
         '솔찬', '아란', '지니', '초롬',]

#시험 점수
exams = [46, 98, 96, 65,
         69, 60, 61, 35,
         26, 73, 52, 85,
         51, 66, 48, 54,
         65, 26, 59, 50] 

#숙제1번 점수
hw1s = [21, 4, 23, 2,
        1, 4, 27, 19,
        19, 23, 21, 20,
        30, 11, 21, 28,
        18, 4, 26, 22] 

#숙제2번 점수
hw2s = [28, 5, 20, 12,
        15, 30, 5, 23,
        18, 26, 19, 21,
        10, 30, 18, 19,
        2, 25, 10, 19]

result = function1(ids, names, exams, hw1s, hw2s)


while True:
    print("1. 학생 추가")
    print("2. 학생 삭제")
    print("3. 학번 순 학생 출력")
    print("4. 순위 출력")
    print("5. 프로그램 종료")
    print()
    user_input = input("실행하려는 기능의 번호를 입력하세요: ")

    if user_input == '1':
        result = function2(result)

    elif user_input == '2':
        result = function3(result)

    elif user_input == '3':
        function4(result)

    elif user_input == '4':
        function5(result)

    elif user_input == '5':
        print()
        print("프로그램을 종료합니다.")
        break

    else:
        print()
        print("잘못된 입력입니다.")
        print()

```
