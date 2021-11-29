<template>
	<div id="app" class="home">
		<div class="wrap">
			<div class="header">
				<div class="header__img">
					<img src="./assets/pic1.jpg" alt="" />
				</div>
				<div class="header__txt">
					<h3>醫療好評網</h3>
					<h4>
						給您安心有保障的醫療評價資訊，<br />簡單明瞭、操作方便
					</h4>
				</div>
			</div>
			<div class="feature1">
        <h1 class="feature1__number">01</h1>
				<div class="avaster">
					<div class="avaster__img">
						<img src="./assets/pic3.jpg" alt="" />
					</div>
					<div class="avaster__txt">
						<h3>學歷</h3>
						<ul>
							<li>德國慕尼黑科技大學醫學研究所博士</li>
							<li>台灣大學醫學院醫學系 學士</li>
						</ul>
						<h3>現職</h3>
						<ul>
							<li>輔仁大學校長</li>
							<li>
								台大醫學院、台北醫學大學醫學院、輔仁大學醫學院教授
							</li>
							<li>
								台北醫學大學附設醫院、耕莘醫院泌尿科、新光醫院主治醫師
							</li>
							<li>中華民國大專體育總會會長</li>
						</ul>
						<a
              class="more_btn"
							href="https://www.hospital.fju.edu.tw/#gsc.tab=0"
							target="_blank">了解更多</a>
					</div>
				</div>
				<div class="feature1__img">
					<img src="./assets//pic2.jpg" />
				</div>
			</div>
			<div class="feature2">
        <div class="feature2__header">
          <h1 class="feature2__number">02</h1>
          <div class="feature2__title">好評推薦</div>
        </div>
				<VueSlickCarousel v-bind="settings">
					<div v-for="item in list" :key="item.id">
						<div class="item" @click="toWebsite(item)">
							<div class="item__img">
								<img
									:src="require(`./assets/${item.imgsrc}.jpg`)"/>
							</div>
							<div class="item__txt">
								<h3>院名 : {{ item.name }}</h3>
								<p>院址 : {{ item.address }}</p>
								<p>{{ item.detail }}</p>
								<a 
                  :href="item.website" 
                  target="_blank" 
                  class="more_btn">
                  詳細介紹
                </a>
							</div>
						</div>
					</div>
				</VueSlickCarousel>
			</div>
      <div class="feature3">
        <div class="feature3__header">
          <h1 class="feature3__number">03</h1>
          <h1 class="feature3__title">良醫推薦</h1>          
					<a 
            class="more_btn"
            target="_blank">
            查看全部
          </a>          
        </div>
        <div class="feature3__content">
          <div class="feature3__item item1">
            <div class="img">
              <img :src="require(`./assets/${doctor_1.imgsrc}.jpg`)"/>
            </div>
            <div class="txt">
              <h4>{{ doctor_1.specialty }}</h4>            
              <h1>{{ doctor_1.name }} 醫師</h1>     
              <a :href="doctor_1.website" class="more_btn" target="_blank">VIEW</a>         
            </div>
          </div>
          <div class="feature3__item item2">
            <div class="img">
              <img :src="require(`./assets/${doctor_2.imgsrc}.jpg`)"/>
            </div>
            <div class="txt">
              <h4>{{ doctor_2.specialty }}</h4>            
              <h1>{{ doctor_2.name }} 醫師</h1>     
              <a :href="doctor_2.website" class="more_btn" target="_blank">VIEW</a>         
            </div>
          </div>          
        </div>
      </div>
			<div class="footer">
				<div class="title">
					<h1>醫療好評網</h1>
          
				</div>
				<div class="detail">
					<h3>網站地圖</h3>
					<h4>
						粉絲專頁 &nbsp;&nbsp; <a href="">醫療好評網@Facebook</a>
					</h4>
					<h4>客服專線 &nbsp;&nbsp;(02) 2905-2000</h4>
					<h4><a href="">工作團隊</a></h4>
				</div>
				<div class="copyright">
					<h4>&copy; 2021 醫療好評網</h4>
					<h4><a href="">隱私政策</a></h4>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";

export default {
	components: {
		VueSlickCarousel,
	},
	data() {
		return {
			settings: {
				infinite: true,
				initialSlide: 0,
				speed: 500,
				slidesToShow: 3,
				slidesToScroll: 1,
				swipeToSlide: true,
				autoplay: false,
				autoplaySpeed: 5000,
				cssEase: "linear",
				variableWidth: true,
			},
			list: [
				{
					id: 1,
					name: "天主教輔仁大學附屬醫院",
					address: "新北市泰山區貴子路69號",
					detail: "近捷運信義安和站，步行至此院約10分鐘",
					imgsrc: "pic4",
					website: "https://www.hospital.fju.edu.tw/#gsc.tab=0",
				},
				{
					id: 2,
					name: "新光吳火獅紀念醫院",
					address: "台北市士林區文昌路95-1號",
					detail: "近捷運士林站，步行至此院約10-15分鐘",
					imgsrc: "pic5",
					website: "https://www.skh.org.tw/skh/index.html",
				},
				{
					id: 3,
					name: "國泰綜合醫院",
					address: "臺北市仁愛路四段280號",
					detail: "近捷運信義安和站，步行至此院約10分鐘",
					imgsrc: "pic6",
					website: "https://www.cgh.org.tw/",
				},
				{
					id: 4,
					name: "臺北市立聯合醫院",
					address: "臺北市鄭州路145號",
					detail: "近捷運北門站，步行至此院約6分鐘",
					imgsrc: "pic7",
					website: "https://tpech.gov.taipei//",
				},
				{
					id: 5,
					name: "恩主公醫院",
					address: "新北市三峽區復興路399號",
					detail: "近鶯歌火車站，步行至此院約30分鐘以上",
					imgsrc: "pic8",
					website: "https://www.eck.org.tw/",
				},
				{
					id: 6,
					name: "天主教耕莘醫院",
					address: "新北市新店區中正路362號",
					detail: "近捷運大坪林站，步行至此院約20分鐘",
					imgsrc: "pic9",
					website: "https://www.cth.org.tw/",
				},
			],
      doctor_1: {},
      doctor_2: {}
		};
	},
  created() {
    this.doctorRandom()
  },
  methods: {
    toWebsite(item){
      window.open(item.website, '_blank')
    },
    doctorRandom(){
      const min_val = 0
      const max_val = 10
      const random1 = Math.floor(Math.random() * (max_val - min_val))
      const random2 = Math.floor(Math.random() * (max_val - min_val))
      const doctor_1 = [
        {
          id: 1,
					name: "江福田",
					imgsrc: "doctor1_1",
					specialty: "心臟內科",  
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00115"        
        },
        {
          id: 2,
					name: "張吉仰",
					imgsrc: "doctor1_2",
					specialty: "胃腸肝膽內科", 
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00110" 
        },      
        {
          id: 3,
					name: "朱培倫",
					imgsrc: "doctor1_3",
					specialty: "腎臟內科", 
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00117" 
        },  
        {
          id: 4,
					name: "李麗娜",
					imgsrc: "doctor1_4",
					specialty: "胸腔內科", 
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00131" 
        },   
        {
          id: 5,
					name: "羅若玲",
					imgsrc: "doctor1_5",
					specialty: "血液腫瘤科", 
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00169" 
        },     
        {
          id: 6,
					name: "裴馰",
					imgsrc: "doctor1_6",
					specialty: "新陳代謝科", 
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00119" 
        },                                          
        {
          id: 7,
					name: "黃德豐",
					imgsrc: "doctor1_7",
					specialty: "風濕免疫科", 
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=02161" 
        },      
        {
          id: 8,
					name: "李宜謙",
					imgsrc: "doctor1_8",
					specialty: "感染科", 
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00421" 
        },         
        {
          id: 9,
					name: "吳義勇",
					imgsrc: "doctor1_9",
					specialty: "腎臟內科", 
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00200" 
        }, 
        {
          id: 10,
					name: "李啟明",
					imgsrc: "doctor1_10",
					specialty: "心臟內科", 
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=03174" 
        }
      ]
      const doctor_2 = [
        {
          id: 1,
					name: "王水深",
					imgsrc: "doctor2_1",
					specialty: "心臟血管外科",    
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00002"          
        },   
        {
          id: 2,
					name: "王瑋",
					imgsrc: "doctor2_2",
					specialty: "一般外科",   
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00406"           
        },     
        {
          id: 3,
					name: "張景年",
					imgsrc: "doctor2_3",
					specialty: "一般外科",    
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00121"          
        },     
        {
          id: 4,
					name: "陳賢典",
					imgsrc: "doctor2_4",
					specialty: "乳房外科",    
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=02026"          
        },     
        {
          id: 5,
					name: "廖守富",
					imgsrc: "doctor2_5",
					specialty: "大腸直腸外科",    
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=02784"          
        },     
        {
          id: 6,
					name: "張晃宙",
					imgsrc: "doctor2_6",
					specialty: "胸腔外科",      
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00419"        
        },     
        {
          id: 7,
					name: "江漢聲",
					imgsrc: "doctor2_7",
					specialty: "泌尿科",        
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00001"      
        },     
        {
          id: 8,
					name: "林子淦",
					imgsrc: "doctor2_8",
					specialty: "神經外科",      
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00880"        
        },     
        {
          id: 9,
					name: "張士人",
					imgsrc: "doctor2_9",
					specialty: "整形外科",      
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=00427"        
        },     
        {
          id: 10,
					name: "楊惠馨",
					imgsrc: "doctor2_10",
					specialty: "小兒外科",     
          website: "https://www.hospital.fju.edu.tw/DoctorCond?STAMPID=02335"         
        }        
      ]
      this.doctor_1 = doctor_1[random1]
      this.doctor_2 = doctor_2[random2]
    }
  }
};
</script>

<style type="text/css" src="@/assets/style.css"></style>
