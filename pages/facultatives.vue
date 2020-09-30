<template>
    <div class="facultatives">
        <img class="left-blot" src="/img/ui/blots/blot_left_2.svg">
        <img class="right-blot" src="/img/ui/blots/blot_right_2.svg">
        <div class="header" align="left">
            <span class="facname_transparent">Список факультативов</span>
            <span class="facname_transparent">Список факультативов</span>
            <span class="facname">Список факультативов</span>
        </div>
        <div class="main-table">
            <div class="select">
                <select class="selector">
                    <option>По кафедрам</option>
                    <option>По зданиям</option>
                </select>
            </div>
            <div class="facult_table">
                <table align="center" class="fac_table" cellpadding="30em" width="75%">
                    <tr class="table_head">
                        <th>Название факультатива</th>
                        <th>Время</th>
                        <th>Преподаватель</th>
                    </tr>
                    <tbody>
                        <tr>
                            <td>
                                <h4>Facultative name</h4>
                                <p>Facultative brief description</p>
                            </td>
                            <td>
                                Date and time
                            </td>
                            <td>
                                Name of the teacher
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<script lang="ts">

import Vue from 'vue'
import TrackHeadMenu from '~/components/track/TrackHeadMenu.vue'

export default {
    
}
</script>

<style scoped lang="scss">
    .facultatives {
        position: relative;
        padding: 0;
        .header {
            position: relative;
            width: 80%;
            margin: 0 auto;
            padding-top: 32px;
            padding-bottom: 16px;
        }
        .facname_transparent, .facname {
            width: fit-content;
            display: block;
            font-size: 44px;
            font-weight: 700;
            font-family: 'IBM Plex Sans';
            margin-top: -12px;
            -webkit-text-stroke: 1px $header-color;
            @media (max-width: $large) {
                font-size: 24px;
                font-weight: 200;
                -webkit-text-stroke: 1px $header-color;
            } 
        }
        .facname_transparent {
            color: transparent;
            @media (max-width: $large) {
                display: none;
            }
        }
        .facname {
            color: $header-color;
        }
    }
    .fac_table, .selector{
        font-family: Montserrat;
        font-size: 18px;
        @media (max-width: $large) {
            font-size: 14px;
        }
    }
    .main-table {
        padding-top: 20px;
    }
    .select { //div
        padding-bottom: 25px;
        margin-left: 20em;
        margin-right: auto;
    }
    .selector { //select
        border: 1.5px solid rgb(156, 187, 114);
        position: absolute;
    }
    table {
        border: rgba(83, 74, 74, 0.5) 1px solid;
        border-collapse: collapse;
        box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    }

    th {
        border-right: 1px rgba(83, 74, 74, 0.5) solid;
        color: white;
        background-color: rgb(154, 198, 147);
        font-weight: normal;
        text-align: center;
    }

    td {
        border-right: 1px rgba(83, 74, 74, 0.5) solid;
        font-weight: normal;
        text-align: center;
    }

    h4 {
        text-decoration: underline rgba(6, 6, 6, 0.13);
        font-weight: normal;
        margin-bottom: 0;
        text-align: center;
    }

    p {
        color: rgb(81, 65, 65);
        text-align: center;
    }
    .table_head {
        height: 80px;
    }
    .left-blot {
      position: absolute;
      height: 60%;
      width: auto;
      margin-bottom: 40px;
      margin-top: -20px;
      @media (max-width: $large) {
          display: none;
      } 
      
    }
    .right-blot {
      position: absolute;
      height: 60%;
      width: auto;
      left: auto;
      
      right: 0;
      top: 0;
      @media (max-width: $large) {
          display: none;
      } 
    }

</style>