<template>
    <div>
        <AppHeader />
        <div id="wrap">
            <div id="container" class="clearfix">
                <!-- aside 없음 -->
                <div id="full-content">
                    <!-- content-head 없음 -->

                    <div id="index">
                        <div id="greetings">



                            <!-- <h1>상품 관리 (등록/삭제/수정)</h1> -->

                            <div id="productFormGroup">

                                <!--
                                <ul>
                                    <li><img id="clothesImage" src="https://www.fashionn.com/files/board/2018/image/p1cforbgmvcok1ii51o8c1tecoc11.jpg"></li>
                                    <li>영수 스페셜 원피스</li>
                                    <li><strong>10,000원</strong></li>
                                    <li><router-link to="">수정</router-link></li>
                                    <li><router-link to="">삭제</router-link></li>
                                </ul>

                                <ul>
                                    <li><img id="clothesImage" src="https://www.fashionn.com/files/board/2018/image/p1cforbgmvcok1ii51o8c1tecoc11.jpg"></li>
                                    <li>영수 스페셜 진</li>
                                    <li><strong>8,000원</strong></li>
                                    <li><router-link to="">수정</router-link></li>
                                    <li><router-link to="">삭제</router-link></li>
                                </ul>

                                <ul>
                                    <li><img id="clothesImage" src="https://www.fashionn.com/files/board/2018/image/p1cforbgmvcok1ii51o8c1tecoc11.jpg"></li>
                                    <li>에스파 닝수 착용!!! 프린세스 원피스</li>
                                    <li><strong>1,000,000원</strong></li>
                                    <li><router-link to="">수정</router-link></li>
                                    <li><router-link to="">삭제</router-link></li>
                                </ul>
                                -->

                                <table>
                                    <thead>
                                        <tr>
                                            <th id="firstTh"></th>
                                            <th id="secondTh">상품명</th>
                                            <th id="thirdTh">가격</th>
                                            <th id="fourthTh"></th>
                                        </tr>
                                    </thead>

                                    <!--<tbody>
                                        <tr>
                                            <td><img id="clothesImage"
                                                    src="https://www.fashionn.com/files/board/2018/image/p1cforbgmvcok1ii51o8c1tecoc11.jpg">
                                            </td>
                                            <td>영수 스페셜 티셔츠</td>
                                            <td>10,000원</td>
                                            <td><router-link id="btnDelete" to="">삭제</router-link></td>
                                        </tr>

                                        <tr>
                                            <td><img id="clothesImage"
                                                    src="https://www.fashionn.com/files/board/2018/image/p1cforbgmvcok1ii51o8c1tecoc11.jpg">
                                            </td>
                                            <td>영수 스페셜 진</td>
                                            <td>8,000원</td>
                                            <td><router-link id="btnDelete" to="">삭제</router-link></td>
                                        </tr>

                                        <tr>
                                            <td><img id="clothesImage"
                                                    src="https://www.fashionn.com/files/board/2018/image/p1cforbgmvcok1ii51o8c1tecoc11.jpg">
                                            </td>
                                            <td>에스파 닝수 착용!!! 프린세스 원피스</td>
                                            <td>1,000,000원</td>
                                            <td><router-link id="btnDelete" to="">삭제</router-link></td>
                                        </tr>

                                        <tr>
                                            <td><img id="clothesImage"
                                                    src="https://www.fashionn.com/files/board/2018/image/p1cforbgmvcok1ii51o8c1tecoc11.jpg">
                                            </td>
                                            <td>영수 스페셜 티셔츠</td>
                                            <td>10,000원</td>
                                            <td><router-link id="btnDelete" to="">삭제</router-link></td>
                                        </tr>

                                        <tr>
                                            <td><img id="clothesImage"
                                                    src="https://www.fashionn.com/files/board/2018/image/p1cforbgmvcok1ii51o8c1tecoc11.jpg">
                                            </td>
                                            <td>영수 스페셜 진</td>
                                            <td>8,000원</td>
                                            <td><router-link id="btnDelete" to="">삭제</router-link></td>
                                        </tr>

                                        <tr>
                                            <td><img id="clothesImage"
                                                    src="https://www.fashionn.com/files/board/2018/image/p1cforbgmvcok1ii51o8c1tecoc11.jpg">
                                            </td>
                                            <td>에스파 닝수 착용!!! 프린세스 원피스</td>
                                            <td>1,000,000원</td>
                                            <td><router-link id="btnDelete" to="">삭제</router-link></td>
                                        </tr>
                                    </tbody>-->

                                    <tbody v-bind:key="i" v-for="(pVo, i) in pList">
                                        <!-- if(i%2==0){
                                            background-color: red
                                        } -->
                                        <tr v-if="i%2==0" id="v-ifIsTrue">
                                            <td>
                                                <img id="clothesImage"
                                                    src="https://www.fashionn.com/files/board/2018/image/p1cforbgmvcok1ii51o8c1tecoc11.jpg">
                                            </td>
                                            <td>{{ pVo.p_name }}</td>
                                            <td>{{ pVo.p_price }}원</td>
                                            <!--<td><router-link id="btnDelete" to="">삭제</router-link></td>-->
                                            <!--<td><button id="btnDelete" type="submit"
                                                    v-on:click="delete (pVo.p_no)">삭제</button>
                                            </td>-->
                                            <td>
                                                <button v-on:click="remove(pVo.p_no)">삭제</button>
                                            </td>
                                        </tr>

                                        <tr v-else id="v-ifIsFalse">
                                            <td>
                                                <img id="clothesImage"
                                                    src="https://www.fashionn.com/files/board/2018/image/p1cforbgmvcok1ii51o8c1tecoc11.jpg">
                                            </td>
                                            <td>{{ pVo.p_name }}</td>
                                            <td>{{ pVo.p_price }}원</td>
                                            <!--<td><router-link id="btnDelete" to="">삭제</router-link></td>-->
                                            <!--<td><button id="btnDelete" type="submit"
                                                    v-on:click="delete (pVo.p_no)">삭제</button>
                                            </td>-->
                                            <td>
                                                <button v-on:click="remove(pVo.p_no)">삭제</button>
                                            </td>
                                        </tr>
                                    </tbody>
                                </table>

                                <router-link id="addBtn" to="">등록</router-link>

                            </div>



                        </div>
                        <!-- //greetings -->
                        <div class="clear"></div>
                    </div>
                    <!-- //index -->
                </div>
                <!-- //full-content -->
            </div>
            <!-- //container -->

            <!-- //footer -->
        </div>
        <!-- //wrap -->
        <AppFooter />
    </div>
</template>

<script>
import axios from 'axios';
import "@/assets/css/admin/ProductAdminView.css";
import AppFooter from "@/components/customer/AppFooter.vue";
import AppHeader from "@/components/customer/AppHeader.vue";

export default {
    name: "ProductAdminView",
    components: {
        AppHeader,
        AppFooter,
    },
    data() {
        return {
            pList: [],
            pVo: {
                p_no: "",
                p_name: "",
                p_price: ""
            },
        };
    },
    methods: {
        getList() {
            console.log("리스트 가져오기");

            axios({
                method: "get", // put, post, delete
                url: "http://localhost:9000/api/admin/productlist",
                headers: { "Content-Type": "application/json; charset=utf-8" }, //전송타입
                //params: guestbookVo, //get방식 파라미터로 값이 전달
                //data: guestbookVo, //put, post, de    lete 방식 자동으로 JSON으로 변환 전달

                responseType: "json", //수신타입
            })
                .then((response) => {
                    //console.log(response.data.apiData); //수신데이타
                    this.pList = response.data.apiData;
                })
                .catch((error) => {
                    console.log(error);
                });

        },
        remove(p_no){
            console.log("클릭클릭");
            console.log(p_no);

            axios({
                method: 'delete', // put, post, delete                   
                url: 'http://localhost:9000/api/admin/delete/' + p_no,
                headers: { "Content-Type": "application/json; charset=utf-8" }, //전송타입
                //params: guestbookVo, //get방식 파라미터로 값이 전달
                data: { p_no }, //put, post, delete 방식 자동으로 JSON으로 변환 전달

                responseType: 'json' //수신타입
            }).then(response => {
                console.log(response.data); //수신데이타

                if (response.data.count > 0) {
                    this.pList.splice(response.data, 1);
                } else {
                    alert("삭제에 실패했습니다");
                }

            }).catch(error => {
                console.log(error);
            });
        }
    },
    created() {
        this.getList();
    },
};
</script>

<style></style>