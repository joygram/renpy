# renpy
```rpy
image eileen happy = "eileen_happy.png"

# 게임에서 사용할 캐릭터를 변수를
define e = Character('린', color="#c8ffc8")
define s = Character('선생님', color="#c8ffc8")
define score = 0

# 점수 화면 
screen score: 
    frame:
        text '점수: %d' % score  

label start:
    $ score = 0
    show screen score

    "운명의 날 ... 두둥"   
    
    s "면접까지 오느라 고생이 많았어요. 몇가지 질문을 해볼께요."
    s "디지텍 고에 지원하신 동기는?"

    e "게임프로그래밍을 배우기 위해 여러학교를 찾아 보았고 "
    e "기초가 없는 제가 가장 체계적으로 배울 수 있다고 생각해서 지원했어요."
    $ score = score + 50


    s "다음중 변수의 개념으로 맞는 것은?"
    e "답을 말해볼까..."
    menu:
        "변....":
            "머리가 백지 상태가 되고 말았다."
            $ score = score - 30
        
        "변수의 정의를 말해보자":
            e "어떤 것을 담아 두었다가 필요할 때 사용할 수 있게"
            e "만들어둔 그릇같은 거라고 생각해요."
            $ score = score + 30 


    if score >= 80:
        "축하 합니다."
        "왔싸 새로운 미래를 개척해볼까~~~"
    else:
        "으으.. 점수가... ㅠ..ㅠ"
        "면접에 실패하고 말았다."
        
        menu: 
            "다시 시도해본다":
                jump start 
            "그만 종료한다":
                "한번 만 더 해보... ㅠ..ㅠ"
                return 
return

```
