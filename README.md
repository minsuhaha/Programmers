# Programmers
프로그래머스 level1 ~ level2

# 프로그래머스 문제풀이

[일정표](https://www.notion.so/71f5d2bc1db040b6bba02e6ebf8ced46)

- 1월 1주차
    - 1/3(화)
        
        [1. 짝수와 홀수](https://www.notion.so/1-9369977b9fcf47d6bc981f85d9e6d5af)
        
        [2. 약수의 합](https://www.notion.so/2-ee51888c571c4032993dd6777a36f15f)
        
        [3. 평균 구하기](https://www.notion.so/3-4529d5496c4a4a359cfd34877fdb7a00)
        
        [4. 자릿수 더하기](https://www.notion.so/4-b083149aea2a45d1b16c80e196783211)
        
        [5. 자연수 뒤집어 배열로 만들기](https://www.notion.so/5-2ce3d821601441bf8652eb30b1cc78ee)
        
    - 1/4(수)
        
        ### 1. 정수 제곱근 판별
        
        ```python
        from math import sqrt
        def solution(n):
            return (sqrt(n)+1)**2 if sqrt(n) == int(sqrt(n)) else -1
        ```
        
        - math 패키지에서 sqrt 함수를 불러왔다
        - 만약 sqrt(n) 값이 양의정수라면 n값이이 양의 정수의 제곱임이 성립되는 것을 이용하여 풀이함
        
        ### 2. 문자열 내 p와 y의 개수
        
        ```python
        def solution(s):
            new_s = s.lower()
            if new_s.count('p') == new_s.count('y'):
                return True
            elif new_s.count('p') == 0 and new_s.count('y') == 0:
                return True
            else:
                return False
        ```
        
        - 대문자 소문자가 같이 있는 경우 ‘p’ 와 ‘y’ 의 개수를 파악하는데 번거로움이 있기 때문에 lower() 함수를 통해 새로운 변수 new_s 에 문자열 s를 소문자들로 바꿔서 넣어줌
        - 이후 문자열.count() 함수를 통해 개수 파악
        - 민수하이 ㅋㅋㅋ화이팅^____^땜
        - zzzzzzzzzzzㅋㅋㅋㅋㅋㅋ 하이 갑자기 뭐라쓸라했는데 까먹었
        
        ### 3. x만큼 간격이 있는 n개의 숫자
        
        ```python
        def solution(x, n):
            answer = []
            for i in range(1,n+1):
                answer.append(x*i)
            return answer
        ```
        
        - for문을 돌려 1~n까지의 숫자를 반복해주고 하나씩 i와 곱해서 answer 배열에 넣어줌
        
        ### 4. 문자열을 정수로 바꾸기
        
        ```python
        def solution(s):
            return int(s)
        ```
        
        - ? 답은 맞다는데 이렇게 구현해도 되는건가 ?
        
        ### 5. 하샤드 수
        
        ```python
        def solution(x):
            lst_x = [int(x) for x in str(x)]
            sum_x = sum(lst_x)
            if x % sum_x == 0:
                return True
            else:
                return False
        ```
        
        - 주어진 x가 숫자형이기에 for문을 돌리기 위해서 문자열로 바꿔준 후 list comprehension을 사용하여 lst_x 배열에 담아줌
        - lst_x 타입이 배열이기 때문에 sum() 함수 사용가능 → sum_x 에 lst_x 합을 담아줌
        - x 와 sum_x 가 나누어 떨어지면 True!
            
            
    - 1/5(목)
        
        ### 1. 정수 내림차순으로 배치하기
        
        ```python
        def solution(n):
            sort_n = sorted(str(n), reverse=True)
            return int(''.join(sort_n))
        ```
        
        - sort_n 변수에 sorted 함수를 사용하여 내림차순 문자열을 넣어줌
            
            중요 : 문자열.sort() 함수를 사용하면 이후에도 정렬된 상태로 사용할수 있는데 sorted(문자열) 함수는 변수에 담아서 사용해야함.  
            
        - ‘ ‘.join() 을 사용하여 sort_n 배열을 문자열로 만들어주고 int 함수를 통해 정수로 바꿔줌
        
        ### 2. 나머지가 1이 되는 수 찾기
        
        ```python
        def solution(n):
            for i in range(1, n+1):
                if n % i == 1:
                    return i
        ```
        
        - for문으로 1~n까지의 i를 돌리고 n % i == 1 if문을  이용하여 해당되는 가장 작은 i값을 return 해줌
        
        ### 3. 두 정수 사이의 합
        
        ```python
        def solution(a, b):
            if a <= b:
                return sum(range(a,b+1))
            else:
                return sum(range(b,a+1))
        ```
        
        - range 함수를 이용해 a ~ b or b ~ a 까지의 합을 구해주기
        
        ### 4. 콜라츠 추측
        
        ```python
        def solution(num):
            count = 0
            while(num != 1):
                if num % 2 == 0:
                    num = num / 2
                else:
                    num = num * 3 + 1
                count+=1
            return -1 if count >= 500 else count
        ```
        
        - while 문을 돌려서 num이 1이 아닐때 무한반복
        - num이 짝수이면 num/2  홀수이면 num*3+1 해주고 어찌됐든 count는 while문이 돌아갈때마다 +1 해줌
        - count 값이 500보다 크거나 같을경우 -1 아니면 count 값을 return 해줌
        
        ### 5. 서울에서 김서방 찾기
        
        ```python
        def solution(seoul):
            s = seoul.index("Kim")
            return f'김서방은 {s}에 있다'
        ```
        
        - 문자열에서 index 값 찾는 함수는 index()함수!
        - 값을 찾고 나서 f-string을 사용하여 출력
        
    - 1/6(금)
        
        ### 1. 핸드폰 번호 가리기
        
        ```python
        def solution(phone_number):
            star = len(phone_number) - 4  
            return '*'*star+phone_number[-4:]
        ```
        
        - 뒷자리 4개를 제외하고 전부 별모양으로 바꿔주기 위해 phone_number개수 - 4 를 해줌
        - * 를 star 개수만큼 나타내주고 나머지 뒷자리4개는 뒤에 붙여줌
        
        ### 2. 나누어 떨어지는 숫자 배열
        
        ```python
        def solution(arr, divisor):
            result = [a for a in arr if a % divisor == 0]
            result.sort()
            return [-1] if len(result) == 0 else result
        ```
        
        - result 변수에 listcomprehension을 사용하여 arr 배열안에 있는 숫자중 divisor 숫자에 나누어떨어지는 숫자만 넣어줌
        - 오름차순을 해주고 만약 result 배열에 아무것도 없는 -1, 1개이상있다면 result 반환
        
        ### 3. 제일 작은 수 제거하기
        
        ```python
        def solution(arr):
            arr.remove(min(arr))   
            return arr if len(arr) >= 1 else [-1]
        ```
        
        - arr 배열에서 가장 작은 arr원소를 제거해주기
        - 남아있는 arr 개수가 1개이상이면 arr 반환 아무것도 없다면  -1반환
        
        ### 4. 음양 더하기
        
        ```python
        def solution(absolutes, signs):
            lst = []
            for i in range(len(signs)):
                if signs[i] == True:
                    lst.append(absolutes[i])
                else:
                    lst.append(-absolutes[i])
            return sum(lst)
        ```
        
        - signs 개수만큼 for문을 돌려주고 signs[i] 가 True이면 양의 absolutes 원소로 lst 배열에 넣어주고 False 이면 음의 absolutes 원소 형태로 lst 배열에 넣어줌
        
        ### 5. 없는 숫자 더하기
        
        ```python
        def solution(numbers):
            lst = [number for number in range(10) if number not in numbers]
            return sum(lst)
        ```
        
        - lst 변수에 numbers 배열에 없는 원소를 넣어준뒤 합을 구해줌
    - 1/7(토)
        
        ```python
        def solution(array):
            count = {arr:array.count(arr) for arr in set(array)}
            max_key = [key for key, value in count.items() if max(count.values()) == value]
            return -1 if len(max_key) != 1 else max_key[0] # or max_key.pop()
        ```
        
        - for문과 dict을 활용하여 arr 키 값과 array.coun(arr) value 값을 뽑아서 count 변수에 넣음
        - count.items()를 하면 key값과 대응되는 value 값이 나온다는 성질을 이용하여 count dict에서 가장 큰 value값이 지금 value과 같을 때의 key을 max_key에 넣어줌 (둘다 해봤는데 max_key[0]가 속도가 더 빨라서 max_key[0]를 사용함)
        - 만약 max_key에 원소가 1개이상 있다면 -1을 반환 1개만 있다면 max_key[0] or max_key.pop()으로 값 반환
        
        처음에 딕셔너리를 이용하지 않다보니 코드가 길어지고 런타임 에러가 났다. 이 후에 딕셔너리를 이용하여 푸니 코드가 짧아지고 간단하게 구현할수 있었다.. 딕셔너리 더 공부해야될거같다...
        
- 1월 2주차
    - 1/9(월)
        
        ### 1. 가운데 글자 가져오기
        
        ```python
        def solution(s):
            length = len(s)//2
            return s[length-1:length+1] if len(s) % 2 == 0 else s[length]
        ```
        
        - 문자열 슬라이싱 이용
        - 만약 문자열 s의 길이가 짝수이면 s[length-1:length+1] 로 중간 두글자를 뽑아내고 홀수이면 s[length]로 중간 한글자를 뽑아내줌
        
        ### 2. 수박수박수박수박수박수?
        
        ```python
        def solution(n):
            str_n = ''
            for i in range(1, n+1): 
                if i % 2 == 1:
                    str_n = str_n + '수'
                else:
                    str_n = str_n + '박'
            return str_n
        ```
        
        - 결과값을 받을 str_n 문자열을 만들어줌
        - for 문을 돌려 i가 홀수일때 ‘수’ , 짝수일땐 ‘박’을 문자열에 추가
        
        ### 3. 내적
        
        ```python
        def solution(a, b):
            result = 0
            for i, j in zip(a,b):
                result += i*j
            return result
        ```
        
        - zip 함수를 사용하여 zip 안에 a,b를 넣어줌으로써 i, j 두개의 값을 동시에 for문에서 돌릴 수 있게 됨
        - 받은 i, j 값을 차례대로 곱해주고 result 변수에 차곡차곡 플러스 해줌
        
        ### 4. 문자열 내림차순으로 배치하기
        
        ```python
        def solution(s):
            upper = []
            lower = []
            for i in s:
                if i.isupper():
                    upper.append(i)
                else:
                    lower.append(i)
            upper.sort(reverse=True)
            lower.sort(reverse=True)
            return ''.join(lower) + ''.join(upper)
        ```
        
        - 문자열 s에서 대문자는 upper 리스트에 소문자는 lower 리스트에 넣어줌
        - upper, lower 둘다 내림차순으로 정렬
        - 문자열로 만들어주고 lower, upper 순으로 출력
        
        ```python
        def solution(s):
            return ''.join(sorted(s,reverse=True))
        ```
        
        - 어떤식으로 풀면 코드를 줄일수 있을까 했는데 이렇게도 되네..
        
        ### 5. 약수의 개수와 덧셈
        
        ```python
        from math import sqrt
        def solution(left, right):
            result = 0
            count = 0
            for num in range(left, right+1):
                for i in range(1, int(sqrt(num))+1): #for문 돌아가는 시간을 줄이기 위해 for 절반
                    if num % i == 0:
                        if i == sqrt(num): # sqrt(n)이 정수일시
                            count+=1
                        else:
                            count+=2
                if count % 2 == 0:
                    result+=num
                else:
                    result-=num
                count = 0
            return result
        ```
        
        - left ~ right 까지 for문을 통해 차례대로 num이라는 변수에 담아 돌려줌
        - sqrt(num)을 쓴 이유를 설명하면
        
        예를들어, 16의 약수를 구하기 위해 1부터 16까지 16과 나눗셈을 통해 한번씩 나누어떨어지는지 여부를 파악해서 구할수 있겠지만, 숫자가 1000이상으로가면 1000번을 비교해야돼서 시간이 오래걸릴거 같다는 생각을 하게 됨. sqrt(num)을 통해 만약 16의 약수를 구하고 싶다면 어차피 약수는 짝이 있는거기 때문에 1~4까지만 돌리면 될거같다는 생각을 하게 됨. 
        
        그래서 16의 약수를 구하기 위해서는 1~4까지만 돌려서 sqrt(16) == 4 가 같을 경우만 짝이 없는 약수니깐 count 에 +1 해주고 나머지는 다 짝이 있기에 count +2 를 해줌
        
        - 이후 약수의 개수가 짝수인 경우 result에 더해주고 홀수인경우 result 에서 빼줌
        
    - 1/10(화)
        
        ### 1. 문자열 다루기 기본 (10점)
        
        ```python
        def solution(s):
            return True if (len(s) == 4 or len(s) == 6 ) and s.isdigit() else False
        ```
        
        - 정해진 s문자열 길이와 s 문자열이 숫자인지 파악한 후 True, False 출력
        
        ### 2. 부족한 금액 계산하기 (9점)
        
        ```python
        def solution(price, money, count):
            total = 0
            for i in range(1,count+1):
                total += price*i
            return total - money if total > money else 0
        ```
        
        - total 값에 price*i를 통해 배수값으로 된 total을 넣어둠
        - total이 가지고 있는 money 보다 크다면 total-money 같거나 money가 더 크다면 0 반환
        
        ### 3. 행렬의 덧셈 (2점)
        
        ```python
        def solution(arr1, arr2):
            sum_result = []
            for i in range(len(arr1)):
                result = []
                for j in range(len(arr1[i])):
                    result.append(arr1[i][j] + arr2[i][j])
                sum_result.append(result)
            return sum_result
        ```
        
        - 이중리스트의 덧셈 문제
        - result 리스트에 먼저 더한 값을 받은 작은 행렬들을 넣어주고 sum_result 리스트에 result를 append 해줌
        
        ```python
        def solution(arr1, arr2):
            answer = [[i+j for i,j in zip(a,b)]for a,b in zip(arr1,arr2)]
            return answer
        ```
        
        이중 zip 함수 사용 zip 함수 공부하자..
        
    - 1/11(수)
        
        ### 1. 직사각형 별찍기
        
        ```python
        a, b = map(int, input().strip().split(' '))
        for i in range(1,b+1):
            for j in range(1,a+1):
                print('*',end='')
            print()
        ```
        
        - j 반복횟수 만큼 ‘*’을 찍어주고 j만큼 다 돌았으면 한칸 뛰어서 반복하여 값 출력
        
        ### 2. 최대공약수와 최소공배수
        
        ```python
        def gcd(a,b): # 유클리드 호제법 사용하여 최대공약수 구하기
            while (b > 0):
                a, b = b, a%b
            return a
        
        def solution(n, m):
            lcm = n*m / gcd(n,m)  # 최소공배수는 두수곱하기 최대공약수로 나눠준 값
            return [gcd(n,m),lcm]
        ```
        
        - 유클리드 호제법을 사용하여 최대공약수를 구함
        - 최소공배수는 주어진 두수를 곱한 뒤 최대공약수로 나눠주면 됨
        
        ### 3. 같은 숫자는 싫어
        
        ```python
        def solution(arr):
            lst = []
            answer = [arr[0]]
            for a in arr:
                if lst: # lst가 비어있지 않으면 if문 실행
                    ans = lst.pop() # lst에 끝값 꺼내주기
                    if ans != a:
                        answer.append(a)
                lst.append(a)  # lst는 모든 a값을 append해서 비교를 해줄거임
            return answer
        ```
        
        - answer 리스트에 미리 arr[0] 을 담아주고 시작
        - for문과 stack 성질을 이용하여 품
        
    - 1/12(목)
        
        ### 1. 이상한 문자 만들기 (11점)
        
        ```python
        def solution(s):
            lst = s.split(' ') # 공백을 기준으로 한단어씩 나눠서 lst에 저장
            string = ''
            for i in range(len(lst)):
                for j in range(len(lst[i])):
                    if j % 2 != 0:  # j가 홀수일때 짝수일때 구분해서
                        string += lst[i][j].lower()
                    else:
                        string += lst[i][j].upper()
                string+=' '
            return string[:-1] # 마지막 빈칸 제거
        ```
        
        ### 2. 3진법 뒤집기 (3점)
        
        ```python
        def change(a):  # 10진법을 입력받고 3진법으로 바꿔주는 함수
            string = ''
            while (a > 0):
                a, y = divmod(a,3) 
                string = str(y) + string
            return string
            
        def solution(n):
            res = list(change(n))
            res.reverse()
            return int(''.join(res),3)  # int(str, base(몇진수인지 작성) -> 10진수로 변환
        ```
        
        ### 3. 예산 (점수 까먹 ㅋ)
        
        ```python
        def solution(d, budget):
            d.sort() # 먼저 오름차순으로 정렬해주기
            count = 0 
            for i in d :
                budget -= i   #budget 에서 i 빼주기
                if budget >= 0:  
                    count+=1  # budget이 0보다 크거나 같다면 count +1
            return count
        ```
        
    - 1/13(금)
        
        ### 1. 시저암호 (9점)
        
        ```python
        from string import ascii_lowercase, ascii_uppercase # 알파벳 함수
        
        def solution(s, n):
            low = list(ascii_lowercase) # 소문자 알파벳 리스트
            up = list(ascii_uppercase) # 대문자 알파벳 리스트
            result = '' # 빈 문자열 생성 
            for i in s:
                if i.isupper(): 
                    a = (up.index(i)+n) % 26 # 알파벳 개수가 26개니깐 %26을 이용하여 구현
                    result += up[a]   
                elif i.islower():
                    b = (low.index(i)+n) % 26
                    result += low[b]
                else:
                    result += ' ' # 빈공간일때는 똑같이 빈공간으로 만들어줌
            return result
        ```
        
        ### 2. 최소직사각형 (1점 주네..)
        
        ```python
        def solution(sizes):
            big = [] 
            small = []
            for i in range(len(sizes)):
                big.append(max(sizes[i][0], sizes[i][1])) # 가로,세로 상관없이 둘중 큰 숫자담기
                small.append(min(sizes[i][0],sizes[i][1])) # 둘중 작은 숫자담기 -> 결국 회전 원리랑 똑같음
            return max(big)*max(small) # 고정
        ```
        
        ### 3. 비밀지도 (4점)
        
        ```python
        def solution(n, arr1, arr2):
            lst = []
            new_lst = []
            for a1, a2 in zip(arr1, arr2): 
                lst.append(bin(a1|a2)[2:]) # a1, a2 둘이 함께 2진법으로 바꾸기 bin 함수이용
            for i in lst:                 
                while len(i) != n: # 만약 len(i) 가 n과 다르다면 앞에 '0' 추가
                    i = '0' + i
                new_lst.append(i.replace('1', '#').replace('0',' ')) # 1 -> #,  0 -> ' '
            return new_lst
        
        ```
        
    - 1/14(토)
        
        ### 1. 옹알이(1) (4점)
        
        ```python
        def solution(babbling):
            speaks = ['aya', 'ye', 'woo', 'ma']
            count = 0
            for bab in babbling:
                for speak in speaks:
                    if speak*2 not in bab:  # 한 speak이 연속되지않다면
                        bab = bab.replace(speak,' ')
                if bab.strip() == '':
                    count+=1
            return count
        ```
        
        - speak라는 새로운 리스트를 만들어줌
        - babbling과 speaks를 중첩 for문을 돌려준 후 만들어질수 있는 문자열은 문제에서 ‘각 문자열의 가능한 모든 부분 문자열중에서 한번씩만 등장한다’ 라는 조건에 따라 같은 speak가 연속되어지면 안되기에 if문으로 조건을 설정해주었다
        - 이후 같은 speak가 연속되지 않을때 bad에 speak가 있다면 공백으로 만들어준다
        - 이 과정을 반복한 뒤 bab에 strip()을 통해 양쪽 문자열 공백을 없애주고 bab 그때에 아무것도 남지 않았다면 count +1
    
- 1월 3주차
    - 1/16(월)
        
        ### 1. 삼총사 (2점)
        
        ```python
        from itertools import combinations # 조합인데 중복 제거된
        def solution(number):
            count = 0 
            nums = combinations(number,3) # 3개로 이뤄진 조합
            for num in nums:
                if sum(num) == 0:
                    count+=1
            return count
        ```
        
        - combination 조합을 사용하여 3개로 이뤄진 조합들 찾아주기
        - 3개로 이뤄진 조합들 sum이 0이면 count+1
        
        ### 2. 문자열 내 마음대로 정렬하기 (4점)
        
        ```python
        def solution(strings, n):
            strings.sort() # 인덱스 값이 같을 수 있으므로 사전순으로 먼저 정렬
            strings.sort(key = lambda x : x[n]) # n번째 인덱스 값을 기준으로 정렬
            return strings
        ```
        
        - 인덱스 값이 같을 수 있으므로 사전순으로 먼저 정렬
        - key = lambda를 사용하여 n번째 인덱스 값을 기준으로 정렬
        
        ### 3. k번째수 (2점인가 3점인가 무튼)
        
        ```python
        def solution(array, commands):
            result = []
            for i in range(len(commands)):
                lst = sorted(array[commands[i][0]-1:commands[i][1]])
                result.append(lst[commands[i][2]-1])
            return result
        ```
        
        - 슬라이싱을 이용하여 lst 변수에 조건대로 담아주고 오름차순으로 정렬해준 뒤 n번째 수를 뽑기
    - 1/17(화)
        
        ### 1. 숫자 문자열과 영단어 (2점)
        
        ```python
        def solution(s):
            nums = ['zero','one','two','three','four','five','six','seven','eight','nine']
            for i, j in enumerate(nums): # enumerate 인덱스값과 value가 같이 나옴
                s = s.replace(j,str(i)) # replace 함수는 str 에서만 사용이 가능함
            return int(s)
        ```
        
        - nums 숫자문자열을 담은 배열을 만들어줌
        - enumerate 함수를 통해 인덱스와 value값을 동시에 받기
        - nums에 있는 숫자문자가 s 문자열에 있으면 해당되는 숫자로 바꿔주기
        
        ### 2. 두 개 뽑아서 더하기(6점)
        
        ```python
        from itertools import combinations
        def solution(numbers):
            result = []
            for number in combinations(numbers,2):
                result.append(sum(number))
            return sorted(list(set(result)))
        ```
        
        - combination 을 이용하여 numbers 배열 조합을 만들어준다 (원소가 2개씩 포함되도록)
        - for문을 돌려 각 조합마다 sum을 구해주기
        - 이후에 중복되는 sum 값을 제거해주고 오름차순으로 정렬
        
        ### 3. 2016년 (8점)
        
        ```python
        def solution(a, b):
            months = [31,29,31,30,31,30,31,31,30,31,30,31]
            days = ['THU', 'FRI', 'SAT', 'SUN', 'MON', 'TUE', 'WED']
            day = 0
            for i in range(a-1):
                day+=months[i]
            return days[(day+b) % 7]
        ```
        
        - 매월 날짜를 넣은 months 배열을 만든다 (윤년도 조건 부합하게)
        - days에 1월1일은 금요일이니 인덱스 1에 금요일이 올수있도록 맞춰서 값 넣어주기
        - for 문으로 day변수에 a달전까지 months 배열에 있는 값 할당해주기
        - 총일수 % 7 을 통해 요일 구해주기
        
    - 1/18(수)
        
        ### 1.  폰켓몬 (합..1점)
        
        ```python
        def solution(nums):
            if len(set(nums)) < len(nums)/2:
                return len(set(nums))
            else:
                return len(nums)/2
        ```
        
        - 이렇게 푸는게 아닌가? 다른 풀이 봐야겠다
        - nums 배열을 set로 담아서 중복되는 값들 제거해주고 len(nums)/2 와 비교해줌
        
        ### 2. 콜라 문제 (10점)
        
        ```python
        def solution(a, b, n):
            result = 0
            left = 0
            while (n >= a):
                left = n % a
                n = (n // a) * b
                result += n   # 순수 n만 더해져야함
                n+=left
            return result
        ```
        
        - n이 a보다 크거나 같을때까지 while문을 실행 시켜줌
        - left에 n 나누기 a의 나머지를 넣어줌
        - 나머지는 조건에 부합하게 설정 (산수문제같음)
        
        ### 3. 소수 찾기  (11점)
        
        ```python
        # 에라토스테네스의 체 이용
        def solution(n):
            nums = set(range(2,n+1)) # 1을 제외한 n까지의 모든 수
            for num in range(2,n+1):
                if num in nums:   # num이 아직 nums 안에 있다면  
                    nums -= set(range(num*2, n+1, num))
            return len(nums)
        ```
        
        - 1을 제외한 n까지의 수 nums 배열 만들기
        - for 문을 돌린 후 num이 nums 안에 있다면 set차집합 성질을 이용하여 num*2 부터 num씩 증가하여 nums에서 빼주기
    - 1/19(목)
        
        ### 1. 크기가 작은 부분문자열(6점)
        
        ```python
        def solution(t, p):
            count = 0
            for i in range(len(t)-len(p)+1):
                if int(t[i:len(p)+i]) <= int(p):
                    count+=1
            return count
        ```
        
        - t의 길이에서 p의 길이를 빼고 +1  만큼 for문을 돌려주기
        - slice를 이용하여 p의 길이와 같이 만들어주고 정수형으로 바꿔주고 비교해서 같거나 작으면 count +1
        
        ### 2. 소수 만들기 (5점)
        
        ```python
        from itertools import combinations
        
        def check(num): # 소수가 맞는지 확인해주는 함수
            for i in range(2, num): # 1과 자기자신을 제외해서 나누어지는 수가 있으면 소수가 아님!
                if num % i == 0:
                    return False
            return True        
        
        def solution(nums):
            count = 0
            sum_lst = [sum(num) for num in list(combinations(nums,3))]
            for num in sum_lst:
                if check(num): # check(num) 값이 True 이면 count +1
                    count+=1
            return count
        ```
        
        - run time 아슬아슬하다… 다들 어떻게 풀었을지..
        - check 함수를 만들어 소수 확인 작업해주기 check 함수내에서 for문을 (2, num) 까지 1과 자기자신을 제외한 숫자를 돌려줄 경우 num % i == 0 에서 하나라도 해당하는 값이 나올경우 소수가 아니다 라는 방법을 사용
        - def solution 함수로 돌아가서 sum_lst 에 3가지 숫자를 조합하여 합한 값들을 넣어주고 for문을 돌려 그 합한 num들을 check 함수를 이용해 소수가 맞는지 확인해주는 작업을 함
        
        ### 3. 모의고사 (6점)
        
        ```python
        def solution(answers):
            math1 = [1, 2, 3, 4, 5]
            math2 = [2, 1, 2, 3, 2, 4, 2, 5]
            math3 = [3, 3, 1, 1, 2, 2, 4, 4, 5, 5]
            count = [0, 0, 0] 
            result = []
            for i, v in enumerate(answers): # enumerate 함수는 index와 value 둘다 나옴
                if v == math1[i % len(math1)]:
                    count[0] += 1
                if v == math2[i % len(math2)]:
                    count[1] += 1
                if v == math3[i % len(math3)]:
                    count[2] += 1
            for i, v in enumerate(count):
                if v == max(count):
                    result.append(i+1)
            return result
        ```
        
        - 수포자들의 각 math 배열들과, 맞은 개수를 담을 count 배열 생성
        - enumerate 함수를 이용해 index와 value 동시에 가져와줌
        - answer의 value 값과 각 수포자들의 math 배열에서 value 에 상응하는 answer의 index값을 math[i%len(math1)] 을 해줌으로써 비교가능 % len(math1) 을 해주는 이유는 answer 값이 math1 의 값보다 많을 경우를 대비하여서
        - 이후 값을 비교해주고 count 배열에 각 수포자들이 정답을 맞춘 개수를 담아줌
        - enumerate 함수를 한번 더 사용해서 max(count) 값과 해당 value 값이 같으면 result 배열에 담아줌
        
    - 1/20(금)
        
        ### 1. 푸드 파이트 대회 (1점)
        
        ```python
        def solution(food):
            result = ''
            for i in range(1, len(food)): # 한쪽 참가자가 먹는 순서
                result += str(i)*(food[i]//2)
            return result + '0' + result[::-1]
        ```
        
        - 이렇게 푸는게 아닌가보다 ㅋ
        - 한쪽 참가자가 먹는 순서를 먼저 구해준 후, 물은 항상 가운데 있으니 가운데 ‘0’으로 고정, 마지막으로 한쪽 참가자가 먹는 순서인 result의 reverse로 다른 참가자가 먹는 순서 만들어주고 합치기
        - slice[시작:끝:규칙] ! → result[::-1] : 문자열 거꾸로 뒤집어서 보여주기
        
        ### 2. 실패율 (9점)
        
        ```python
        def solution(N, stages):
            stage = len(stages)
            result = {}
            for n in range(1,N+1):
                if stage != 0:
                    result[n] = stages.count(n)/stage
                    stage-=stages.count(n)
                else:
                    result[n] = 0
                    
            return sorted(result.keys(), key = lambda x : result[x], reverse=True)
        ```
        
        - 내가 못하는건가 어렵다.. 30분이 훌쩍 넘게 걸린다…하
        - stage에 stages길이를 담고, result dict을 만들어줌
        - for문을 스테이지만큼 돌려주고 stage가 0이 아닐때 실패율을 반복해서 구해줌
        - 만약 초반에 실패율이 높아서 stage가 주어진 스테이지를 다 돌지 못했는데 0이 되버리면 이후 실패율을 다 0이 됨
        - lambda를 이용하여 result[x] 즉 value의 크기에 따라 내림차순으로 정렬하고 각 value 상응하는 result안의 key 값들만 sort해서 반환
        - dict 이용법 : dict[key] = value 으로 담아주기
        - dict에서 value 값에 따른 sort 이용법 : key = lambda x : result[x] 해줌으로써 value 값에 대해서 sort 할수있도록 만들어줌
        
    - 1/21(토)
        
        ### 1. 평행 (11점)
        
        ```python
        # 기울기가 같은지 판단해주는 함수를 작성
        from itertools import combinations
        def inclination(dot2, dot1):
            return (dot2[1] - dot1[1]) / (dot2[0]- dot1[0])   # 기울기 : (y2-y1)/(x2-x1)        
        def solution(dots):
            lst = []
            com = combinations(dots,2)
            for c in com:
                lst.append(inclination(c[1], c[0]))
            return 0 if len(lst) == len(list(set(lst))) else 1
        ```
        
        - 임의의 두점을 이은 직선이 평행하기 위해서는 기울기 값이 같아야한다
        - 그리하여 두개의 인자를 받는 (기울기를 판단해주는) inclination 함수 생성.
        - 이후 combination 을 통해 점 두개씩 조합을 만들어줌
        - 만든 조합들을 inclination 함수에 넣어 lst에 각 기울기들을 담아주고 lst에서 같은 값이 있으면 같은 기울기를 가진 직선이 존재한다고 판단
    
- 1월 4주차
    - 1/25(수)
        
        ### 1. 가장 가까운 같은 글자 (2점)
        
        ```python
        def solution(s):
            dic = dict()
            result = []
            for i in range(len(s)):
                if s[i] not in dic:
                    result.append(-1)
                else:
                    result.append(i - dic[s[i]])
                dic[s[i]] = i
            return result
        ```
        
        - dic 변수에 dict() 을 해줌으로써 dictionary 생성
        - for 문을 s의 길이만큼 돌려서 한번 돌릴때마다 dic[s[i]] = i 해줌으로써 최근의 s[i] 값이 몇번째에 나왔는지 표시
        - s[i] 과 dic에 없으면 처음나온 값이기 때문에 result.append(-1)
        - s[i] dic에 있으면 result.append(i - dic[s[i]]) 해줌으로써 최근나온값과 몇번째 차이가 나오는지 파악가능
        
        ### 2. 다트게임 (3점)
        
        ```python
        def solution(dartResult):
            stack = [] # pop을 사용할것이기때문에 stack으로 변수이름 지정
            answer = [] # 다트 연산값을 담을 배열
            dartResult = dartResult.replace('10','?') # 두자리수는 하나하나 따로 수가 나오기때문에 replace 이용하여 한글자로 만들어줌
            for dart in dartResult:
                if dart.isnumeric(): # dart가 숫자이면
                    stack.append(int(dart))
                elif dart == '?': # dart 10인 경우
                    stack.append(10)
                #stack.pop()해서 사용할수 있는 이유는 숫자와문자는 항상 붙어있는 상황이기때문에 이런식으로 사용이가능
                elif dart == 'S': # single일시
                    answer.append(stack.pop()**1) 
                elif dart == 'D': # double일시
                    answer.append(stack.pop()**2)
                elif dart == 'T': # triple일시
                    answer.append(stack.pop()**3)
                elif dart == '*': # 스타상일시
                    if len(answer) <= 1: # 첫번째 기회에서 나올시
                        answer[-1] *= 2
                    else: # 첫번째 기회가 아닐시
                        answer[-2] *= 2 # 바로 전 점수
                        answer[-1] *= 2 # 해당 점수
                
                elif dart == '#': # 아차상일시
                    answer[-1] = (-1)*answer[-1]
                
            return sum(answer)
        ```
        
        - 이게 맞나 싶다 설명은 코드내에 작성하였다
        
    - 1/26(목)
        
        ### 1. 로또의 최고 순위와 최저 순위 (7점)
        
        ```python
        def rank(count):
            if count == 0:
                return 6
            else:
                return 7 - count 
        def solution(lottos, win_nums):
            max_count = 0
            min_count = 0
            for lotto in lottos:
                if lotto != 0:
                    if lotto in win_nums:
                        min_count+=1
                        max_count+=1
                else:
                    max_count+=1
            return [rank(max_count), rank(min_count)]
        ```
        
        - 맞춘 개수에 따라 rank를 매겨주는 rank함수 만들어줌
        - lottos에 원소를 하나씩 lotto로 받아 0이 아니면 min_count, max_count 둘다 +1 씩 해주고 lotto가 0일시 로또 당첨번호로 바꿀수 있기때문에 max_count에만 +1 해주고 return 값으로 rank 함수에 min_count와 max_count를 넣어 반환
        
        ### 2. 과일 장수 (3점)
        
        ```python
        def solution(k, m, score):
            result = 0
            lst = []
            score.sort(reverse=True)
            for i in range((len(score))):
                lst.append(score[i])
                if len(lst) == m:
                    result += lst.pop()*m
                    lst.clear()
            return result
        ```
        
        - score를 오름차순으로 배열해줌으로써 최대이익을 구하기 쉽게 만들어주기
        - score의 길이만큼 for을 돌려 lst에 담아주고 lst길이가 m과 같아지면 result에 이익계산하고 다시 lst를 비워주기
        
    - 1/27(금)
        
        ### 1. 체육복
        
        ```python
        def solution(n, lost, reserve): 
            new_lost = set(lost) - set(reserve) #체육복을 도난 당한 학생중에 여벌 체육복이 있는 학생제외
            new_reserve = set(reserve) - set(lost) # 중복 값 제거
            for res in new_reserve: 
                if res-1 in new_lost:
                    new_lost.remove(res-1)
                elif res+1 in new_lost:
                    new_lost.remove(res+1)
                    
            return n - len(new_lost)
        ```
        
        *+9*
        
        ### 2. 명예의 전당
        
        ```python
        def solution(k, score):
            lst = []
            result = []
            for s in score:
                lst.append(s)
                lst.sort(reverse=True)
                if len(lst) <= k:
                    result.append(lst[-1])
                else: 
                    lst.pop()
                    result.append(lst[-1])
            return result
        ```
        
        *+2 or +3*
        
        - for문을 돌려서 score원소 하나씩 s로 받아 lst에 담아주고 바로 sort로 내림차순 작업을 해줌
        - lst의 길이가 k보다 작거나 같으면 기존 lst 배열의 최솟값만 result에 담아주고 lst의 길이가 k보다 크면 lst 중 가장 작은 값을 제거하고 난 lst 배열의 최솟값을 result에 담아줌
    - 1/28(토)
        
        ### 1. 분수의 덧셈
        
        ```python
        def gcd(a,b): # 최대공약수 구하는 함수 (유클리드 호제법)
            while b > 0:
                a, b = b, a%b
            return a
          
        def solution(numer1, denom1, numer2, denom2):
            numer = numer1*denom2 + numer2*denom1 # 분모를 같게 만들어주고 분자 더하기
            denom = denom1*denom2
            n = gcd(numer,denom) # 분자 분모의 최대공약수 구해주기
            return [numer/n, denom/n]
        ```
        
        *+4*
        
        - 자주 나오는 최대공약수 구하는 법 : 유클리드 호제법 이용
        - 유클리드 호제법을 이용하여 최대공약수 구하는 함수를 만들어줌
        - numer 라는 변수에 분모를 값을 같게 만들어준후 분자에 값을 곱해줘서 분자 합을 구해줌
        - denom 변수에 분모의 최소공배수를 담아줌
        - 이후 numer과 denom의 gcd 함수를 통해 최대공약수를 구해주고 return 때 numer과 denom 각각 최대공약수로 나눠주기
- 1월 5주차
    - 1/30(월)
        
        ### 1. 완주하신 못한 선수
        
        ```python
        def solution(participant, completion):
            participant.sort()
            completion.sort()
            for p, c in zip(participant,completion): # zip 함수는 적은 경우에 대해서 맞춰줌
                if p != c: 
                    return p
            return participant.pop()
        ```
        
        +5
        
        - 짝을 맞춰주기 위해 participant와 completion을 먼저 오름차순으로 정렬해주기
        - zip 함수를 이용 → zip 함수는 받은 list인자중 더 길이가 작은 list 인자에 맞춰 zip해줌
        - p≠c 즉 짝이 맞지 않을경우 해당 particpant 완주를 못한것으로 간주하여 return p
        - zip을 통해서 비교한 p와 c가 다 같았을 경우 완주하지 못한 사람은 항상 1명있기 때문에 오름차순으로 정렬한 participant의 가장 끝에 있는 사람이 완주하지 못한 것!
        
        ### 2. 숫자짝궁
        
        ```python
        def solution(X, Y):
            lst = []
            lst_Y = list(Y)
            for x in X:
                if x in lst_Y:
                    lst.append(x)
                    lst_Y.remove(x) # 삭제되는 순서는 상관없으니 remove로 맨앞 공통숫자 삭제하기
            lst.sort(reverse=True)
            if len(lst) == 0:
                return '-1'
            elif lst[0] == '0':
                return '0'
            else:
                return ''.join(lst)
        ```
        
        - 이렇게 하니깐 런타임 에러 뜨네..
        - 중복을 더 효율적으로 제거해야되나보다
        
        ```python
        def solution(X, Y):
            lst = []
            for same in (set(X)&set(Y)):
                for i in range(min(X.count(same),Y.count(same))):
                     lst.append(same)           
            lst.sort(reverse=True)
            if len(lst) == 0:
                return '-1'
            elif lst[0] == '0':
                return '0'
            else:
                return ''.join(lst)
        ```
        
        +11
        
        어렵네
        
        - set(X)&set(Y)를 통해 X, Y의 중복값을 찾아주고 for문을 돌림
        - X와 Y 문자열에서 count함수를 통해 중복된 값 same의 개수를 파악해주고 더 작은 수를 min 함수를 사용하여 구해 for문을 돌려서 그 수 만큼 lst에 append 해줌
        - 중복된 값들중 가장 큰 수를 구하는거기에 내림차순으로 정렬
        - lst가 빈 리스트이면 return -1, 정렬한 lst 맨앞자리가 0이라면 return ‘0’, 이 두경우에 해당 안되는 경우 리스트로 문자열로 변환하여 값 반환
    - 2/2(목)
        
        ### 1. 기사단원의 무기
        
        ```python
        from math import sqrt
        def count(n): # 약수의 개수를 구해주는 함수
            count = 0
            for i in range(1,int(sqrt(n))+1):
                if n % i == 0:
                    if sqrt(n) == i:
                        count+=1
                    else: count+=2
            return count
                
        def solution(number, limit, power):
            result = 0
            for num in range(1,number+1):
                if count(num) > limit:
                    result+=power
                else: result+=count(num)
            return result
        ```
        
        +5
        
        - 약수의 개수를 구해주는 함수 count를 정의해줌
        - 그리고 본 solution 함수로 돌아와서 1~number까지 각각 하나씩 num으로 받아주고 count(num)이 limit 를 초과한다면 result에 power를 더해줌
        - count(num) 이 limit 이하라면  result에 count(num)을 합해줌
        
        ### 2. 키패드 누르기
        
        ```python
        def solution(numbers, hand):
            result = ''
            keypad = {1:(0,3), 2:(1,3), 3:(2,3),
                      4:(0,2), 5:(1,2), 6:(2,2),
                      7:(0,1), 8:(1,1), 9:(2,1),
                      '*':(0,0), 0:(1,0), '#':(2,0)}
            left = '*' # left 시작점
            right = '#' # right 시작점
            for number in numbers:
                if number in [1, 4, 7]: #왼쪽 1,4,7 라인은 왼손 엄지손가락으로만!
                    left = number
                    result +='L'
                elif number in [3, 6, 9]: #오른쪽 3,6,9 라인은 오른손 엄지손가락으로만!
                    right = number
                    result +='R'
                else: # 2,5,8,0 라인일 경우 현재 왼쪽손 오른쪽손 거리 비교 |x1-x2| + |y1-y2|
                    n_left = abs(keypad[left][0] - keypad[number][0])+abs(keypad[left][1] - keypad[number][1])
                    n_right = abs(keypad[right][0] - keypad[number][0])+abs(keypad[right][1] - keypad[number][1])
                    if n_left > n_right:
                        result +='R'
                        right = number
                    elif n_left < n_right:
                        result +='L'
                        left = number
                    else: # 2,5,8,0 라인에서 왼손과 오른쪽 거리가 같을 경우 왼손,오른손 잡이 비교
                        if hand =="left":
                            result+='L'
                            left = number
                        else: 
                            result+='R'
                            right = number
            return result
        ```
        
        +3
        
        - 후에 거리 계산을 위해 keypad 딕셔너리를 만들어줌
        - left, right 시작점으로 초기화 해주기
        - numbers 배열에서 하나씩 number을 꺼내서 [1,4,7] 이면 무조건 왼손으로, [3,6,9] 이면 무조건 오른손으로 누르기!
        - [2,5,8,0] 이면 현재 왼쪽 엄지손가락의 위치와 오른쪽 엄지손가락의 위치를 비교해주기
        - |x1-x2| + |y1-y2| 이용! → 수가 더 크면 거리가 더 멂
        - 현재 number의 거리와 왼쪽,오른쪽 엄지손가락 거리를 구해준 n_left, n_right를 비교해서 n_left 값이 더 크면 오른쪽 엄지로 눌러줘야하고, n_right 값이 더 크면 왼쪽 엄지손가락으로 눌러주기
        - [2,5,8,0] 에서 현재 왼쪽 엄지손가락과 오른쪽 엄지손가락 거리가 동일하면 왼손잡이는 왼쪽 엄지손가락으로 오른손잡이는 오른손 엄지손가락으로 누르기
    - 2/3(금)
        
        ### 1. 크레인 인형뽑기
        
        ```python
        def solution(board, moves):
            stack = []
            answer = 0
            for move in moves: 
                for i in range(len(board)): 
                    if board[i][move-1] != 0: # 배열임을 고려하여 move-1 으로 바꿔줌
                        stack.append(board[i][move-1]) 해당되는 값을 stack에 넣어줌
                        board[i][move-1] = 0 해당되는 값을 0으로 변경(빈값)
                        if (len(stack)) >= 2 and (stack[-1] == stack[-2]): 
        								# stack 길이가 2 이상이고, stack끝과 stack끝 바로앞 숫자가 같을시
                                stack.pop()
                                stack.pop()
                                answer += 2
                        break # for문을 나가게 해줌    
            return answer
        ```
        
        +7
        
        break 문의 중요성!
        
        - for문 바로 하위에 있는 if문에서 조건에 부합할시 break를 걸어줌으로서 for문을 나와버리게 만들어줌.
        
        ### 2. 옹알이 (2)
        
        ```python
        from itertools import combinations
        def solution(babbling):
            result = 0
            say = ['aya', 'ye', 'woo', 'ma']
            for bab in babbling:
                for s in say:
                    if s*2 not in bab: # 같은 발음이 연속이 아닐때
                        bab = bab.replace(s,' ')
                if bab.strip()== '':
                    result+=1
            return result
        ```
        
        +8
        
        - 발음할수있는 say 배열을 만들어줌
        - 주어진 babbling을 하나씩 bab으로 꺼내 s와 비교
        - s*2 가 bab에 없으면 같은 발음이 연속되는것이 아니므로 bab에 s가 있으면 공백으로 바꿔줌
        - 이후  strip() 함수를 사용해 bab이 공백이면 result+1
    - 2/4(토)
        
        ### 1. 신규 아이디 추천
        
        ```python
        def solution(new_id):
            result = ''
            new_id = new_id.lower() # 1단계
            for i in new_id:
                if i.islower() or i.isdigit() or i in ['-', '_', '.']: # 2단계
                    result += i
            
        	  while '..' in result: # 3단계  '..' 이 사라질때까지
        			  result = result.replace('..','.')  # '..' -> '.'
            
            result = result.strip('.') # 4단계 양쪽에 있는 '.' 제거
                
            # if result[0] == '.': # 4단계
            #     result = result[1:]
            # elif result[-1] == '.':
            #     result = result[:-1]
            
            result = 'a' if len(result) == 0 else result # 5단계
            
            if len(result) >= 16: # 6단계
                result = result[:15]
                if result[-1] == '.':
                    result = result[:-1]
            
            if len(result) <= 2:
                while len(result) < 3:
                    result = result + result[-1]
            return result
        ```
        
        +6
        
        strip() 함수
        
        - strip(제거할 문자) 작성하면 양쪽 끝에 있는 해당 문자를 제거해줌 다른문자가 나올때까지!
        
        ### 2. 문자열 나누기
        
        ```python
        def solution(s):
            result = 0
            count = 0
            while s: # s를 계속 slice 하며 자를거기에
                start = s[0]
                for i in range(len(s)):
                    if s[i] == start: # start랑 같을시
                        count+=1
                    else:
                        count-=1
                    if count == 0 or i == len(s)-1: # count가 0이거나 i가 끝까지 다 돌았을때
                        result+=1
                        s = s[i+1:] # s에서 분리할 문자열 빼주기
                        break
            return result
        ```
        
        +4 어떻게 문제 이해하는데 시간이 더 걸리냐….
        
        - while문을 돌려 s가 빈 문자열이 아닐경우 계속 돌려주기
        - 문자열 s의 첫 글자를 start 변수에 담아줌
        - s[i] 가 start와 같을 경우 count+1 다를 경우 count -1
        - count = 0 되거나 i가 끝까지 돌았을 경우 result+=1, s에서 이전 문자열 분리해주기 그리고 break로 for문 빠져나가기
- 2월 1주차
    - 2/6(월)
        
        ### 1. 성격 유형 검사하기
        
        ```python
        def solution(survey, choices):
            result = ''
            dic = {'R':0, 'T':0, 'C':0, 'F':0, 'J':0, 'M':0, 'A':0, 'N':0}
            for i in range(len(survey)):
                if choices[i] < 4:
                    if choices[i] == 1:
                        dic[survey[i][0]] += 3
                    elif choices[i] == 2:
                        dic[survey[i][0]] += 2
                    elif choices[i] == 3:
                        dic[survey[i][0]] += 1
                elif choices[i] > 4:
                    if choices[i] == 5:
                        dic[survey[i][1]] += 1
                    elif choices[i] == 6:
                        dic[survey[i][1]] += 2
                    elif choices[i] == 7:
                        dic[survey[i][1]] += 3
            # 1번지표부터 차례대로 result에 넣기
            result += 'R' if dic['R'] >= dic['T'] else 'T' # 같을경우는 사전상으로 빠른 R이 결과로 나옴
            result += 'C' if dic['C'] >= dic['F'] else 'F'
            result += 'J' if dic['J'] >= dic['M'] else 'M'
            result += 'A' if dic['A'] >= dic['N'] else 'N'
            return result
        ```
        
        +2
        
        - 값을 넣어줄 dictionary인 dic를 초기화해준다.
        
        dic = dict() 로만 만들어주고 dic[survey[i][0]] += 숫자 형태로 대입하려니깐 안되고 dic 안에 미리 key값이랑 value값들이 짝지어져 존재해야 이후 연산이나 값 대입이 가능한걸 깨달았다..’
        
        - 이후 survey len만큼 for문을 돌려 survey의 길이와 choices의 길이가 같다는 점을 이용해 i를 활용한다!
        - 문제 조건에 나온 것을 따라 차례대로 if문을 사용하여 dic에 값을 대입해줌
        - 마지막으로 지표마다 value값을 비교해서 큰값 or value값이 같을경우 사전상빠른값을 result에 1지표부터 차례대로 대입해주기!
        
        ### 2. 최댓값과 최솟값
        
        +1
        
        ```python
        def solution(s):
            lst = list(map(int, s.split(' ')))
            return str(min(lst))+' '+str(max(lst))
        ```
        
        - for문을 돌리지말고 map() 함수를 사용도 간편한거 같다.
        
        **map(적용할 함수, 적용할 값(list,tuple) → list or tuple로 감싸서 변수에 담아줘야함.**
        
        - s.split(’ ‘) 을 사용하여 공백을 기준으로 list로 만들어주기!
        
        “1, 2, 3, 4”  → [1,2,3,4]  /  “-1, -2, -3, -4” → [-1, -2, -3, -4]
        
    - 2/7(화)
        
        ### 1. 햄버거 만들기
        
        ```python
        def solution(ingredient):
            lst = []
            result = 0
            for i in ingredient:
                lst.append(i)
                if lst[-4:] == [1,2,3,1]: # 끝 기준 4번째부터 끝까지
                    result+=1
                    lst.pop()
                    lst.pop()
                    lst.pop()
                    lst.pop()
            return result
        ```
        
        +7
        
        - ingredient의 원소들은 하나씩 lst에 append 해줌
        - 만일 lst[-4:] → (맨 끝기준으로 끝에서 4번째부터 끝까지) == [1,2,3,1] 과 같다면 result +1
        - [1,2,3,1]를 삭제해주기 pop()사용  / lst = lst[:-4] 를 사용하여 삭제하려고 했는데 런타임 에러가 걸리네..
        
        ### 2. JadenCase 문자열 만들기
        
        ```python
        def solution(s):
            lst = s.lower().split(' ')
            result = ''
            for i in range(len(lst)):
                if lst[i][0].isdigit():
                    result+=lst[i]
                else:
                    new_lst = lst[i].replace(lst[i][0],lst[i][0].upper())
                    result+=new_lst
                result+=' '
            return result[:-1]
        ```
        
        런타임 에러 실패…
        
        ```python
        def solution(s):
            lst = s.split(' ')
            result = ''
            for i in range(len(lst)):
                result += lst[i].capitalize() #첫글자만 대문자로
                result+=' '
            return result[:-1]
        ```
        
        +6
        
        - capitalize() / title()  함수를 사용하면 편리하다!
        - **capitalize()** 함수는 단어의 첫글자만 대문자로 변환시켜줌
        - **title()** 함수는 알파벳 외의 문자로(숫자, 특수기호, 띄어쓰기 등) 나눠져 있는 단어들의 첫글자를 모두 대문자로 변환시켜줌\
        - 문자열.split(’ ’) 을 통해 공백을 기준으로 나눠 lst에 하나씩 담아줌
        - 하나씩 나눠진 lst의 단어의 첫글자만 대문자로 변환해줌, 이후 띄어쓰기를 위해 result+=’ ‘ 해줌
        - 마지막으로 result값에 하나의 띄어쓰기가 오바되어있으므로 result[:-1]를 통해 필요없는 띄어쓰기를 제하기
    - 2/8(수)
        
        ### 1. 둘만의 암호
        
        ```python
        from string import ascii_lowercase
        def solution(s, skip, index):
            result = ''
            alpha = str(ascii_lowercase)
            for sk in skip:
                alpha = alpha.replace(sk,'') #skip에 있는 원소들 다 제거해주기
            for i in s:
                result += alpha[(alpha.index(i)+index)% (26-len(skip))]
            return result
        ```
        
        +8
        
        - ascii_lowercase → 소문자 알파벳을 불러옴
        - 빈 result 문자열을 만들어주기
        - alpha 변수에 ascii_lowercase을 문자열로 만들어 담아줌
        - skip을 하나씩 꺼내 alpha에 skip들을 제거해주기
        - 이후 s문자열에서 하나씩 꺼내 alpha에서 각각의 index를 파악하고 + 주어진 index를 해준 뒤 알파벳 전체 수 26에서 skip된 길이를 제한 값을 나눠서 원하는 alpha 인덱스값을 만들어 값 구하기
        
        ### 2. 최솟값 만들기
        
        ```python
        def solution(A,B):
            A.sort()
            B.sort(reverse=True)
            result = 0
            for i in range(len(A)):
                result+=A[i]*B[i]
            return result
        ```
        
        +1
        
        ㅋ.. 1점주네
        
        - 두개의 원소를 곱해서 최솟값을 만들기 위해서는 AorB에서 가장 작은 원소 x BorA에서 가장 큰 원소를 곱한 값을 차례로 더해주면 됨.
    - 2/9(목)
        
        ### 1. 신고 결과 받기
        
        ```python
        def solution(id_list, report, k):
            report = set(report) # 한명이 똑같은 사람을 여러번 신고해도 신고횟수는 1번으로 인정되기에 중복 제거
            dic = {i:0 for i in id_list} # 신고당한 횟수를 세기 위해 dictionary
            result = [0]*len(id_list) # id_list에 길이만큼 result안에 0으로 초기화해줌
            for r in report: 
                a, b = r.split(' ') # 공백을 기준으로 두개의 단어로 나눠줌
                dic[b]+=1 # 신고당했을 때마다 +1
            
            for r in report:
                a, b = r.split(' ') # a : 신고한 사람, b : 신고당한사람
                if dic[b] >= k: # k번 이상 신고당한 사람들이면 a에게 신고결과메일이 날라감
                    result[id_list.index(a)]+=1 
            return result
        ```
        
        +3
        
        - 설명은 코드 작성하면서 적었음
        
        ### 2. 올바른 괄호
        
        ```python
        def solution(s):
            answer = 0
            for i in s:
                if i == '(':
                    answer+=1
                elif i == ')':
                    answer-=1
                    if answer == -1:
                        return False
            return True if answer == 0 else False
        ```
        
        +5 ? +6
        
        - 괄호가 들어있는 문자열 s에서 하나씩 꺼내줘서 ‘(’ 랑 같은지 비교해서 같으면 answer+1
        - ‘)’ 와 같으면 answer-1 해줌
        - ‘)’ 와 같을때 answer값이 음수가 될 경우( ’(’ 나오기전에 ‘)’먼저 나온 경우) False
        - for 문을 나온 뒤 answer = 0 이면 True 0이 아니고 0초과인 수라면 False처리
    - 2/10(금)
        
        ### 1. 개인정보 수집 유효기간
        
        ```python
        def solution(today, terms, privacies):
            i = 0
            result = []
            # terms 재정의! 공백을 기준으로 key(약관종류), value(유효기간 달) 값 나눠서 dictionary 만들기
            terms = {term.split(' ')[0]:term.split(' ')[1] for term in terms} 
            y,m,d = today.split('.') # '.'을 기준으로 년,월,일 나눠서 변수에 담아주기 (일수로 통합하기 위해)
            today = int(y)*(12*28) + int(m)*28 + int(d) # today 일수로 바꿔주기
            
            for p in privacies:
                p = p.split(' ')
                y,m,d = p[0].split('.')
                privaice = int(y)*(12*28) + int(m)*28 + int(d) # 각 개인정보 수집일자 일자로 바꿔주기
                i += 1
                if today > privaice + int(terms[p[1]])*28-1: #유효기간이 today보다 작다면 -> 유효기간 지남
                    result.append(i) # 해당되는 i값만 넣기
            return result
        ```
        
        +4
        
        i+=1 이 아니라 enumerate 함수를 써서 index랑 값이랑 한번에 받는 방법도 있었네…
        
        ### 2. 이진 변환 반복하기
        
        ```python
        def change2(a):
            result = ''
            while a >= 1: 
                a, b = divmod(a,2)
                result = str(b) + result
            return result
        
        def solution(s):
            zero = 0
            answer = 0
            result = s
            while result != '1':
                new_s = result.replace('0','')
                zero += len(result) - len(new_s)
                result = change2(len(new_s))
                answer += 1
            return [answer, zero]
        ```
        
    - 2/11(토)
        
        ### 1. 숫자의 표현
        
        ```python
        def solution(n):
            result = 0
            for i in range(1,n+1):
                sum = 0
                for j in range(i,n+1):
                    sum+=j
                    if sum == n:
                        result+=1
                        break
            return result
        ```
        
        효율성 테스트 런타임 시간초과…
        
        ```python
        def solution(n):
            result = 0
            for i in range(1,n+1): 
                sum = 0
                for j in range(i,n+1): # 연속되는 숫자들의 합을 구해줘야 하니 for문 시작범위는 i부터
                    sum+=j
                    if sum == n:
                        result+=1
                        break
                    elif sum > n: # sum > n을 넘어버리면 의미없는 코드가 돌아가기 때문에 조건 추가
                        break
            return result
        ```
        
        +5
        
        기존 코드에 elif sum > n 일때 break 추가해줬더니 런타임 에러 해결!
