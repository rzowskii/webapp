<script>
  import { accounts, account, mode } from './stores.js';
  import Modal from './Modal.svelte';
  let showsubjects = false;
  let requestquota = false;
  let review = false;
  let learning = false;
  let timetable = false;
</script>

<div style="overflow-x:auto;"> 
<div class="header">
  <img src="head.png"height="350" width ="1503.1">
</div>
</div>

<div class="bg">
  <center>
    <br><br>
    <h1>USER MANUAL</h1>
    <button class="decshowsub" on:click="{() => showsubjects = true}">
	   รายวิชา
    </button>
    {#if showsubjects}
	  <Modal on:close="{() => showsubjects = false}">
		<h2 slot="header">
			👩🏻‍💻 HOW TO 
		<small>ดูรายละเอียดแต่ละวิชา </small>
		</h2>
		<ol class="definition">
			<li>ด้านซ้ายจะมีให้เลือกรายวิชาทั้งหมด และวิชาโควตาจำกัด </li>
			<li>เมื่อกดเลือกวิชา จะแสดงรายละเอียดวิชานั้นๆ เช่น วิชาบังคับก่อนหน้า รายละเอียดเนื้อหาการเรียน เป็นต้น เพื่อใช้ในการตัดสินใจลงทะเบียนเรียน </li>
		</ol>
  	</Modal>
    {/if}
    
    <button class="decqt" on:click="{() => requestquota = true}">
	 จดทะเบียนและขอโควต้า
</button>
{#if requestquota}
	<Modal on:close="{() => requestquota = false}">
		<h2 slot="header">
			👩🏻‍💻 HOW TO 
			<small>ทำการขอหรือยกเลิกรายวิชาทั่วไปและรายวิชาโควตาจำกัด</small>
		</h2>
		<ol class="definition">
			<li>เมื่อเข้ามายังหน้าจดทะเบียนเรียนแล้ว ให้พิมพ์รหัสวิชาที่จะขอจดทะเบียน </li>
			<li>เมื่อกดค้นหาแล้วจะขึ้นรหัสวิชา ชื่อรายวิชา ประเภทรายวิชาที่จดทะเบียน จำนวนที่นั่งของวิชานั้นๆ</li>
			<li>หากต้องการจดทะเบียนเรียนให้คลิกที่เครื่องหมายบวกด้านหลัง</li>
			<li>วิชานั้นจะมาแสดงอยู่ที่ด้านล่างในหัวข้อผลการจดทะเบียน</li>
			<li>หากต้องการยกเลิกสามารถค้นหาเหมือนข้างต้นและคลิกที่เครื่องหมายลบซึ่งการขอยกเลิกรายวิชานั้นก็จะเสร็จสิ้น</li>
      <li>โดยระบบจะทำการบันทึกและเก็บข้อมูลผลการจดทะเบียนโดยอัตโนมัติทุกครั้งที่มีการจดทะเบียนหรือยกเลิกรายวิชาอยู่แล้ว แต่เพื่อความมั่นใจสามารถคลิกที่ปุ่มยืนยันการจดทะเบียนและขอโควตาได้เช่นกัน</li>
		</ol>
	</Modal>
{/if}

<button class="decqt" on:click="{() => timetable = true}">
	ตารางเรียนและตารางสอบ
</button>
{#if timetable}
	<Modal on:close="{() => timetable = false}">
		<h2 slot="header">
			👩🏻‍💻 HOW TO 
			<small>ดูข้อมูลตารางเรียนและตารางสอบ</small>
		</h2>
		<ol class="definition">
			<li>หน้าจอจะแสดงตารางเรียนของวิชาทั้งหมดในภาคเรียนนั้นๆ  </li>
			<li>ส่วนด้านล่างถัดลงมาจะแสดงวันเวลาที่สอบกลางภาค และปลายภาคในเทอมนั้น</li>
		</ol>
	</Modal>
{/if}
    
</center>

<center>
<button class="decrv"on:click="{() => review = true}">
	รีวิวรายวิชา
</button>
{#if review}
	<Modal on:close="{() => review = false}">
		<h2 slot="header">
			👩🏻‍💻 HOW TO 
			<small>ดูการรีวิววิชาต่างๆ</small>
		</h2>
		<ol class="definition">
			<li>หน้ารีวิวจะมีแสดงรายวิชาต่างๆ เพื่อประกอบการตัดสินใจลงเรียนและการเตรียมตัวในการเรียนวิชานั้นๆ </li>
			<li>เมื่อคลิกที่วิชานั้นๆจะมีคำรีวิวจากผู้ที่เคยลงเรียน และบางวิชาจะมีลิงค์ส่งไปยังเว็บที่มีคนเข้าไปรีวิว</li>
		</ol>
	</Modal>
{/if}
<button on:click="{() => learning = true}">
	สื่อการเรียนเพิ่มเติม
</button>
{#if learning}
	<Modal on:close="{() => learning = false}">
		<h2 slot="header">
			👩🏻‍💻 HOW TO 
			<small>ดูสื่อประกอบการเรียนเพื่อประกอบการตัดสินใจในการขอโควตาวิชานั้นๆ</small>
		</h2>
		<ol class="definition">
			<li>เมื่อเข้ามาหน้าสื่อการเรียนรู้ มีการแบ่งเป็นหมวดวิชาต่างๆ เพื่อใช้เป็นแนวทาง และศึกษาเบื้องต้นก่อนเรียน </li>
			<li>เมื่อคลิกแล้วจะมีลิงค์ไปยังเว็บต่างๆ ซึ่งจะเป็นเนื้อหาที่คล้ายกับหัวข้อที่ต้องเรียน</li>
      <li>หากต้องการดูว่าแต่ละวิชาเรียนอะไรทางด้านซ้ายจะมีให้คลิกไปยังรายวิชาได้</li>
		</ol>
	</Modal>
{/if}
  </center>
  <center>
<button class="back"on:click={()=>$mode='menu'}>Back to Menu</button>
  </center>
<div class="footer"> 
  <p>----- THAMMASAT SCHOOL OF ENGINEERING -----</p>
</div></div>

<style>

button{
    padding-top: 50px;
    padding-bottom: 50px;
    padding-left: 50px;
    padding-right: 50px;
    border-radius: 1em;
    margin-bottom: 1.5em;
    margin-right: 1.5em;
    background-color: #787878;
    border-style: ridge;
    border-width: 6px;
    border-color: #f3f6f6;
    color: #ffffff;
    font-size: 15px;
  }
button:hover {
  background-color: #04aa6d; 
  color: white;
  box-shadow: 0px 10px 14px 0px rgba(0,0,0,0.26), 0 17px 50px 0
  rgba(0,0,0,0.19);
  }
li {
    padding-bottom: 4px;
  }
.definition{
    text-align: left;
  }
 .decshowsub {
    margin-top: 6.5em;
    padding-left: 80px;
    padding-right: 80px;
  }
.decrv {
    padding-left: 80px;
    padding-right: 80px;
  }
.decqt {
    padding-left: 51px;
    padding-right: 51px;
  }
h4 {
    text-align: center;
    margin-top: 9em;
    padding-bottom: 2.3em;
    margin-bottom: -1em;
    color: #97938a;
  }
.bg {
    background-color: #fefafa;
    margin-left: -1em;
    margin-right: -1.3em;
  }
h1{
    margin-top:1.5em;
    color: #04aa6d
  }
.back{
  margin-top: 5em;
  padding-top: 10px;
  padding-bottom: 10px;
  padding-left: 10px;
  padding-right:10px;
  margin-bottom:2em;
  background-color: #04aa6d;
}

/* Footer */
.footer {
  color: white;
  padding-top: 1.2em;
  padding-bottom: 1.2em;
  text-align: center;
  background: #222222;
  margin-bottom: -10px;
}
</style>