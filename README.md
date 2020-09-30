# Ssangyong_OracleProject

## PC방 이용 및 관리 시스템(오라클 연습프로젝트)
  - 주제 : 실제 피시방 시스템과 유사하게 오라클로 만든 프로젝트
  
  - 적용 기술 : 다른 컴퓨터로 IP를 입력해 주문이 가능하게 하였고(네트워킹), 자바 스트림 사용,
                Thread(쓰레드), 예외처리, 컬렉션(List,Map) 등을 사용하고 기초적인 자바를 연습
                하는 용도로 회원가입, 로그인, 메뉴선택, 주문 등 기초적인 기능을 모두 추가한 
                프로젝트이다.
  
  - 방법 :  손님이 피시방을 실제이용하는 행동을 오라클 프로세스에 비교하여 
            --1. 손님은 사용 가능한 좌석을 조회 할 수 있다.(좌석 확인)
            execute can_seat;

            --2. 손님은 좌석을 선택하고 로그인을 할 수 있다.(좌석 선택 및 로그인)
            execute p_seat('a1','&id','&password');
            select * from login;

            --3. 손님은 회원가입을 할 수 있다.(회원가입)
            execute p_member_join('park', 123, 123, '박현', '910725-1000000', '010-8939-8888');
            select * from member;

            --4. 손님은 피시방 요금제를 확인 할 수 있다.(요금제 확인)
            execute check_ki;

            --5. 손님은 피시방 시간을 충전 할 수 있다.(충전하기)
            execute ki_charge('gwang8', '4시간', 10000);

            --6. 직원은 회원정보를 조회 할 수 있다.(회원정보 확인)
            execute ch_member('gwang8');

            --7. 손님은 자신의 남은 시간을 확인 할 수 있다.(남은 시간 확인)
            execute ch_extratime('gwang8');

            --8. 손님은 직원에게 문의사항을 보낼 수 있다.(문의)
            execute p_c_query('자리좀 치워주세요', 'a1');

            --9. 직원은 손님이 보낸 문의를 확인 할 수 있다.(문의 확인)
            execute p_query;

            --10. 손님은 주문 전 제품을 확인 할 수 있다.(제품 확인)
            execute ch_c_goods;

            --11. 직원은 제품의 재고를 확인 할 수 있고, 발주 해야할 제품을 확인 할 수 있다.(제품 재고 확인)
            execute ch_goods;

            --12. 손님은 음식을 주문 할 수 있다.(주문하기)
            execute p_c_order('a1', '사이다', 1, 5000);

            --13. 직원은 손님이 주문한 내역을 확인 할 수 있다.(주문 확인)
            execute p_p_order;

            --14. 직원은 매출을 확인 할 수 있다.(매출 확인)
            execute sales;

            --15. 손님은 로그아웃을 할 수 있다.(로그아웃)
            execute p_logout('gwang8');
            select * from login;

            --16. 직원은 손님들의 로그인, 로그아웃 로그내역을 확인 할 수 있다.(로그 확인)
            execute ch_log('gwang8');

            --17. 직원은 마감을 할 수 있다.(마감)
            execute p_off(sysdate);

            --18. 직원은 일자별 일일 매출내역을 확인 할 수 있다.(일일 매출액 확인)
            execute p_date_income;

           
