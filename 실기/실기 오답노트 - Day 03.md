```c
#include ＜stdio.h＞
int isPrime(int number) { 
  int i; 
  for (i=2; i＜number; i++) { 
    if (number % i == 0) return 0; 
  } 
  return 1; 
} 
 
int main(void) { 
  int number = 13195, max_div=0, i; 
  for (i=2; i＜number; i++) 2639
  if (isPrime(i) == 1 && number % i == 0) max_div = i; 
  printf("%d", max_div); 
  return 0; 
}
```

### 관계 데이터 모델

대절해비

- 관계 대수 - 절차적 어쩌구
- 관계 해석 - 비절차적 어쩌구

### 대칭 키 알고리즘

- IDEA : 국제 데이터 암호화 알고리즘
- SKIPJACK : 미국의 NSA에서 개발 블록 알고리즘

### SOLID

- SRP 단일 책임 원칙 : 소프트웨어의 컴포넌트는 단 하나의 책임만을 가져야 한다.
- OCP 개방 폐쇄 원칙 : 확장에 대해선 열려 있어야 하고 수정에 대해선 닫혀 있어야한다.
- LISP 리츠코프 치환 원칙 : 자식 클래스는 부모클래스에서 가능한 행위를 수행할 수 있어야 한다.
- ISP 인터페이스 분리의 원칙 : 하나의 일반적인 인터페이스 보단 여러 개의 구체적인 인터페이스가 낫다.
- DIP 의존관계 역전 원칙 : 의존 관계를 맺을 때, 변화하기 쉬운것 보단 별화하기 어려운 것에 의존

### 점진적 통합 방식

- 회귀 테스트
  - 이미 테스트된 프로그램의 테스팅을 반복

- 상드하스
- 상향식 테스트 드라이버, 클러스터
- 하향식 테스트 스텁

### 순수 관계 연산자

- 순수관계 연산자 (Select)
  - 연산자의 기호는 그리스 문자 시그마를 사용
  - 조건을 만족하는 튜플의 부분집합을 구하여 새로운 릴레이션을 만든다 수평연산
- Project
  - 릴레이션에서 속성에 제시된 Attribute만을 추출하는 연산, 수직연산
  - 파이를 사용
- joini
  - 공통 속성 합침
  - 화살표 기호
- Division
  - 나누기를 사용
  - 제외한 속성만을 구하는 연산

### 프로토콜

- 내부 라우팅 프로토콜(IGP)
  - OSPF : 최단경로를 찾는 라우팅 프로토콜
- 외부 라우팅 프로토콜(EGP)
  - BGP : AS상호간에 경로 정보를 교환하기 위한 라우팅

### 함수 종속성

- 완전 종속 : 둘다 잇어야
- 부분 종속 : 둘중 하나만 있다면
- 이행적 함수 종속 : 얽혀있는 관계

```javas
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<header class="header">		
	<div class="wrap">
	<script type="text/javascript">

	$(function(){
		$("#selectLang").change(function(){
			var selected = $("#selectLang option:selected");
			changeLocale(selected.data("language"), selected.data("country"));
		});
		
		var language = "[[${#messages.msg('label.common.language')}]]";
		if (language != "") {
			$("#selectLang option[data-language="+language+"]").attr("selected", "selected");
		}
		
		$('.btn').click(function(){
			header_searchList(1);
		});
	});

	function header_searchList(page) {
		var param = new Object();
		param.page = page;
		param.language = "[[${#messages.msg('label.common.language')}]]";
		param.searchType = 'N';
		param.searchTxt = $('#search_txt').val();
		$.ajax({
			url : "/th/front/product/listAction",
			type : "POST",
			data : param,
			success : function(data) {
				$("#listActionDiv").html(data);
			},
			error : function() {
				$.alertable.alert("[[${#messages.msg('label.common.fail.action')}]]");
			}
		});
	}
	
	function logout() {
		document.frmMenuHandle.action="<%=request.getContextPath()%>/login/logoutAction";
		document.frmMenuHandle.method="post";
		document.frmMenuHandle.submit();
	}
	
	/**
		카테고리별 리스트보기
	*/
	function goCategory(categoryId){
		var depth = $("*[id="+categoryId+"]").parent().parent().attr("class");
		var submenu = $(".depth_2[data-num=s0"+categoryId+"]").html();
		var existDepth = $("ul[data-num=s0"+categoryId+"]").last().html();
		
		var param = new Object();
		
		if(depth == "depth_1")	param.category1 =  categoryId;
		if(depth == "depth_2")	param.category2 =  categoryId;
		
		if(existDepth == "" || existDepth == null){
			movePage('/th/front/product/list', param);	
		}
		
	}
	
	/**
		언어 변경
	*/
	function changeLocale(locale, country) {
		var param = new Object();
		param.language = locale;
		param.country = country;
		var cate1 = "[[${productInfo?.category1}]]";
		var cate2 = "[[${productInfo?.category2}]]";
		var product_id = "[[${productInfo?.prodId}]]";
		
		// 리스트 view일 경우
		if(cate1 !=null || cate1 !="")		param.category1 = cate1;
		else if(cate2 !=null || cate2 !="")	param.category2 = cate2;
		
		// detail view일 경우
		if(product_id != null || product_id !="")	param.prodId = product_id;
			
			
		movePage("/th/front/product/list", param);
	}
	function goSignin_front() {
		movePage('/th/login/front/goSignInfront');
	}
	//쿠키 가져오기
	function getCookie(cookieName){
		console.log(cookieName);				
		cookieName = cookieName + '=';
		var cookieData = document.cookie;
		var start = cookieData.indexOf(cookieName);
		var cookieValue = '';
		  if(start != -1){
			start += cookieName.length;
			var end = cookieData.indexOf(';',start);
			if(end == -1) end = cookieData.length;
			cookieValue = cookieData.substring(start,end);
		} 
		return unescape(cookieValue);
	}
	$(document).ready(function() {      
		$("#header .subMenuIcon").click(function(){
			asideAction();
		})	
	});
</script>
		<div class="topLink">
			<span class="lang">
				<select class="inp">
					<th:block th:each="code : ${languageCodeList}">
						<option th:attr="data-language=${code.dtlCd}" data-country="KR" th:text="${code.dtlNm}"></option>
					</th:block>
				</select>
			</span>
			<div class="myInfo">
				<span class="unit"><a href="javascript:login();" th:text="${#messages.msg('label.btn.login.title')}">로그인</a></span>
				<span class="unit"><a href="javascript:goSignin_front();" th:text="${#messages.msg('label.btn.register.title')}">회원가입</a></span>
				<span class="unit"><a href="#">고객센터</a></span>
				<span class="unit"><a href="#">장바구니</a></span>
				<span class="unit dropMenu">
					<a href="#">마이메뉴</a>
					<ul class="dropMenuBox">
						<li class="listUnit"><a href="#">주문/배송조회</a></li>
						<li class="listUnit"><a href="#">마이프로필</a></li>
					</ul>
				</span>
			</div>
		</div>
	</div>
	<div class="wrap">
		<div class="topHeader">
			<div class="logo"><a href="javascript:movePage('/th/front/product/list');" title="logo"><span class="">NShop Mall</span></a></div>

			<div class="iconBtn">
				<button type="button" class="icobBtn searchIcon mobileOnly" title="검색"><span class="hiddenText">검색</span></button>
				<button type="button" class="icobBtn subMenuIcon" title="메뉴"><span class="hiddenText">메뉴</span></button>
			</div>
				
			<div class="totalSearchBox">
				<input type="search" class="inp totalSearch" th:placeholder="${#messages.msg('label.front.product.search')}" />
				<a href="#" class="btn" title="Search"><span class="hiddenText">Search</span></a>
			</div>				
		</div>
	</div>	
</header>
</html>
```

```html
<!DOCTYPE html>
<html
        lang="ko"
        xmlns:th="http://www.thymeleaf.org"
        xmlns:layout="http://www.ultraq.net.nz/thymeleaf/layout"
        xmlns="http://www.w3.org/1999/html">
<head>
<meta charset="utf-8">
<meta id="viewport" name="viewport">
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
<meta name="description" content="">
<meta name="keywords" content="">

<link rel="stylesheet" href="/css/front_import.css">
<link rel="stylesheet" href="/css/shop_layout_temp_test.css">

<script type="text/javascript" src="/js/jquery/jquery-3.4.1.min.js"></script>
<script type="text/javascript" src="/js/amb_ui_common_test.js"></script>	

<!-- //공통 부분 -->
<script type="text/javascript" src="/js/commonUtil.js"></script>

<!-- /////////// 사이트 특화부분 -->
<title>Ameoba UI shop Templete</title><!-- 해당 사이트의 타이틀 부분 -->
<script>

function refreshList() {
	$("#list").trigger("reloadGrid", [{ page: $(".ui-pager-control .ui-pg-input").val() }]);
}

</script>
</head>
<body>
	<div class="amb_layout_common">		
		<!--  default layout 구조 -->
		<div th:replace="fragments/front/inc_header :: header"></div>
		<div th:replace="fragments/front/inc_nav :: nav"></div>
		<div th:replace="fragments/front/inc_aside :: aside"></div>
		<!-- topVisual -->
		<section id="topVisual" class="topVisual">
			<ul class="bannerWrap">
				<li class="unit" style="background-color:#ffa2b7;">
					<a href="http://www.naver.com" target="_blank">
						<img src="/img/GNB_M_img_web.jpg" alt="해당 내용이 관한 텍스트가 들어갑니다.">
					</a>
				</li>
			</ul>
		</section>
		<th:block layout:fragment="content"></th:block>
		<div th:replace="fragments/front/inc_footer :: footer"></div>
	</div>
</body>
</html>
```

