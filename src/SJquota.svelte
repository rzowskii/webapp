<script>
  import { accounts, account, mode } from './stores.js';
</script>

<div style="overflow-x:auto;"> 
  <div class="header">
    <img src="head.png"height="350" width ="1503.1">
  </div>
</div>

<div class="row">
  <div class="side">
    <div class="nav"> 
      <button on:click={()=>$mode='SJall'}>รายวิชาทั้งหมด</button>
      <hr>
      <button on:click={()=>$mode='SJquota'}>รายวิชาโควต้าจำกัด</button>
      <hr>
      <button on:click={()=>$mode='menu'}>Back to Menu</button>
    </div>
  </div>
  
  <div class="main">
    <h2>รายวิชาโควต้าจำกัด</h2>
    <button class="collapsible">SF210 PROGRAMMING SKILL DEVELOPMENT 1</button>
    <div class="content">
      <p>วิชาบังคับก่อน: สอบได้CN101</p>
      <p>การเขียนโปรแกรมและการแก้ปัญหาด้วยภาษาไพธอน เน้นหลักการของการพัฒนาซอฟแวร์ รูปแบบการเขียนโค้ด และการทดสอบ หัวข้อประกอบด้วย กระบวนคำสั่งและฟังก์ชั่น การวนซ้ำ การเรียกซ้ำ อาร์เรย์และเวกเตอร์ สตริง รูปแบบการดำเนินงานของการเรียกใช้กระบวนคำสั่งและฟังก์ชั่น ขั้นตอนวิธี ความผิดปกติ</p>
    </div>
    
    <button class="collapsible">TU050 ENGLISH SKILL DEVELOPMENT</button>
    <div class="content">
      <p>รายวิชาต่อเนื่อง:	TU105</p>
      <p>ฝึกทักษะภาษาอังกฤษในระดับเบื้องต้น ได้แก่ การพูด การอ่าน การเขียน เชิงบูรณาการ เพื่อเป็นพื้นฐานในการพัฒนาทักษะภาษาอังกฤษระดับต่อไป</p>
    </div>

    <button class="collapsible">TU105 COMMUNICATION SKILLS IN ENGLISH</button>
    <div class="content">
      <p>วิชาบังคับก่อน: ต้องมีผลการศึกษาในระดับผ่าน(s)วิชาTU050ก่อนการจดทะเบียนเรียนวิชาTU105</p>
      <p>พัฒนาทักษะการฟัง พูด อ่าน และเขียนภาษาอังกฤษโดยมุ่งเน้นความสามารถในการสนทนาเพื่อแลกเปลี่ยนความคิดเห็น และการอ่าน เพื่อทำความเข้าใจเนื้อหาวิชาการในศาสตร์ต่างๆ ที่เกี่ยวข้องกับวิชาชีพของนักศึกษา</p>
    </div>
    
    <script>
      var coll = document.getElementsByClassName("collapsible");
      var i;

      for (i = 0; i < coll.length; i++) {coll[i].addEventListener("click", function() {
        this.classList.toggle("active");
        var content = this.nextElementSibling;
        if (content.style.maxHeight){
          content.style.maxHeight = null;
        } else {
          content.style.maxHeight = content.scrollHeight + "px";
          } 
        });
      }
    </script>    
  </div>
</div>

<div class="footer"> 
  <p>----- THAMMASAT SCHOOL OF ENGINEERING ----- </p>
</div>

<style>
  * {
    box-sizing: border-box;
  }

  .row {  
    display: -ms-flexbox; 
    display: flex;
    -ms-flex-wrap: wrap; 
    flex-wrap: wrap;
  }

  .side {
    -ms-flex: 30%; 
    flex: 10%;
    background-color: #787878;
    padding: 10px;
    padding-bottom: 50px;
    margin-top: -4px;
  }

  .main {   
    -ms-flex: 70%; 
    flex: 70%;
    background-color: #FEFAFA;
    padding: 20px;
  }

  .nav {
    width: 100%;
    padding: 20px;
    margin: center;
  }

  button {
    background-color: #04AA6D;
    color: white;
    padding: 14px 20px;
    margin: auto;
    border: none;
    cursor: pointer;
    width: 100%;
  }
  
  @media screen and (max-width: 700px) {
    .row {   
      flex-direction: column;
    }
  }

  .collapsible {
    background-color: #777;
    color: white;
    cursor: pointer;
    padding: 18px;
    width: 100%;
    border: none;
    text-align: left;
    outline: none;
    font-size: 15px;
  }

  .collapsible:hover {
    background-color: #04aa6d;
  }

  .collapsible:after {
    content: '\002B';
    color: white;
    font-weight: bold;
    float: right;
    margin-left: 5px;
  }

  .content {
    padding: 0 18px;
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.2s ease-out;
    background-color: #f1f1f1;
  }

  .footer {
    color: white;
    padding: 20px;
    text-align: center;
    background: #222222;
  }
</style>