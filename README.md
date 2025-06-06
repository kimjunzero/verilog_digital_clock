베릴로그를 활용한 디지털 시계 프로젝트

module p1_DigitClock(
   input clk, 
   n_reset,   // button F
   mode,      // button A 
   inc,       // button B
   alrm_off,  // button C
   stopw,     // button D
   display,   // button E
   output [7:0] seg_data,
   output [7:0] seg_com,
   output led1_am, led2_pm, led3_rm, led4_s, led_5, led_6, led_7 // 오전, 오후, 알람ON, stopw모드표시, 저장시간 1, 2, 3
   output piezo // 알람소리
);

MODE(A)     : 시계(알람전용) - 스톱워치 - 시간(H) - 시간(M) - 시간(S) - 알람(H) - 알람(M) - 알람(S)

inc(B)      : 시계, 알람 시간 - H,M,S 시간 증가
              STOPWATCH - record(시간기록)

alrm_off(C) : 알람 끄기 
              STOPWATCH - 스톱워치 초기화

stopw(D)    : STOPWATCH - 시작, 정지

display(E)  : STOPWACH - 저장시간 보기(1, 2, 3)

reset(F)    : 전체 reset

시계 : Am 12:00으로 시작. Am/Pm 오전오후 표시. 시간 설정 가능(blink).
스탑워치 : 시작, 정지. 3개의 시간 저장 가능. 저장된 3개의 시간 보여줌(led5, led6, led7 on), led4번on
알람 : Am/Pm 오전오후 표시. 시간 설정 가능(blink). 시간과 맞을시에 led3과 동시에 알람이 울림. 



