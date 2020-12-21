#Испитна задача

Потребно е да развиете апликација за менаџирање на продукти која ќе овозможи прегледување, додавање, уредување и бришење 
на продукти. 

- **(10 поени)** Во пакетот `mk.ukim.finki.wp.exam.example.model` веќе се креирани класите кои го репрезентираат моделот. 
Потребно е да извршите нивно мапирање со соодветните JPA анотации за моделот успешно да се сними во базата на податоци. 
Притоа важат следните услови: 
  - Продуктите може да припаѓаат во повеќе категории, а во секоја категорија може да има повеќе продукти.
  - Еден корисник може да биде `creator` на повеќе продукти. 

- **(30 поени)** Во пакетот `mk.ukim.finki.wp.exam.example.service` се веќе дефинирани интерфејсите за сервисната логика. 
За секој од методите имате опис што треба да биде имплементирано. Потребно е да се имплементираат овие интерфејси во 
соодветните класи во пакетот `mk.ukim.finki.wp.exam.example.service.impl`. 

- **(20 поени)** Класите од пакетот `mk.ukim.finki.wp.exam.example.repository` треба да ги дополните со потребните методи 
кои ви се потребни за да ја овозможите функционалноста на имплементацијата на сервисниот слој.

- **(20 поени)** Во класата `mk.ukim.finki.wp.exam.example.web.ProductsController` се дефинирани сите методи кои се 
потребни за да се имплементира менаџирањето со продуктите. Потребно е овие handler методи да ги мапирате со користење 
само на HTTP GET и POST барања. Во продолжение е подетален опис за секој од методите:  
     - `showProducts` треба да го искористи `list.html` темплејтот за приказ на сите продукти. Овој handler метод треба да 
     се мапира на патеките `/` и `/products`. 
       - Аргументите на овој метод не се задолжителни и може да бидат `null`. 
       - Во случај кога не се испратени аргументите (кога се `null`) треба да се прикажат сите продукти од базата. 
       - Ако некој, или двата, од аргументите е различен од `null`, тогаш треба да се прикажат продуктите кои ги враќа 
       `ProductService.listProductsByNameAndCategory`.  
     - `showAdd` треба да го прикаже темплејтот `form.html`. Овој handler метод треба да се мапира на патеката `/products/add`. 
     - `showEdit` треба да го прикаже темплејтот `form.html`, меѓутоа во секој од `input` елементите треба да биде пополнета 
     соодветната вредност за продуктот кој се уредува. Овој handler метод треба да се мапира на патеката `/products/edit/[id]`
     - `create` треба да го креира продуктот според аргументите на методот. Потоа треба да се прикажат сите продукти.
     - `update` треба да се уреди продуктот според аргументите на методот. Потоа треба да се прикажат сите продукти.
     - `delete` треба да се избрише продуктот со дадениот идентификатор. Потоа треба да се прикажат сите продукти. 
     
 - **(10 поени)** Дополнете ги темплејтите со соодветните **Thymeleaf** атрибути за да се постигнат бараните функционалности. 
 Притоа, ако недостасуваат одредени елементи и атрибути, може да ги додадете, но **НЕ СМЕЕ** да ги менувата `id` и 
 `class` својствата на тековните елементи. Во коментари се дадени описи за елементите кои треба да се повторуваат, како 
 и кои методи од контролерот треба да се повикаат.   
 
 - **(10 поени)** Потребно е да конфигурирате најава на `/login` и одјава на `/logout` со Spring Security во класата 
 `mk.ukim.finki.wp.exam.example.config.SecurityConfig`. Притоа, јавна треба да биде само страницата `/`, додека сите 
 останати страници треба да се видливи само за `ROLE_ADMIN`. Дополнително, кај`list.html` копчињата **Edit**, **Delete** 
 и **Add** треба да се видливи само за `ROLE_ADMIN`.
 
- **(5 поени)** Сите исклучоци треба да ги прикажете како пораки во `<div id="errorMessage">` елементот.

- **(5 поени)** Потребно е да ја анотирате класата `mk.ukim.finki.wp.exam.example.config.DataInitializer` и нејзиниот 
метод `initData` така што при стартување на апликацијата ќе се изврши методот `initData`.
  
   
##Тестирање
Во `mk.ukim.finki.wp.exam.example.selenium.SeleniumScenarioTest` се имплементирани 2 теста: 
- `testScenarioNoSecurity` кое треба да го повиката доколку не го имплементирате барањето за Spring Security
- `testSecurityScenario` кое треба да го повикате доколку го имплементирате барањето за Spring Security

Тестовите мора задолжително да ги извршите пред да го поставите кодот на `ispiti.finki.ukim.mk`. Тие ќе ви помогнат да 
ја проверите точноста на вашата имплементација, но и ќе испратат информации до нашиот сервер за тоа до каде функционира 
вашата апликација. Ќе се гледа кодот само на студентите кај кои барем една проверка (`Assert`) ќе помине успешно. 

**НЕ Е ДОЗВОЛЕНО МЕНУВАЊЕ НА ТЕСТОВИТЕ**
   