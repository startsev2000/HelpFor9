<template>
    <div class="facultatives">
        <!--<img class="left-blot" src="/img/ui/blots/blot_left_2.svg">
        <img class="right-blot" src="/img/ui/blots/blot_right_2.svg">-->
        <div class="header">
            <span class="facname">Список факультативов</span>
            <span class="facname">Список факультативов</span>
            <span class="facname">Список факультативов</span>
        </div>
        <div class="main-table">
            <div class="selector">
                <select class="select">
                    <option id="1">По зданиям</option>
                    <option id="2">По кафедрам</option>
                </select>
            </div>
            <div class="facult_table">
                <table class="fac_table">
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
        width: 90%;
        margin: 0 auto;
        padding-top: 32px;
        }
        .facname {
            color: transparent;
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
                color: $header-color;
                font-family: 'IBM Plex Sans';
                -webkit-text-stroke: 1px $header-color;
            } 
            span:first-child {
                margin-top: 0;
                @media (max-width: $large) {
                    display: none;
                } 
            }
            span:last-child {
                color: $header-color;
                -webkit-text-stroke-width: 0;
                @media (max-width: $large) {
                    display: none;
                }
            }
        }
    }
    .fac_table, .select{
        font-family: Montserrat;
        font-size: 18px;
        @media (max-width: $large) {
            font-size: 14px;
        }
    }
    .selector {
        border: 1.5px solid rgb(156, 187, 114);
        position: absolute;
        margin-left: 50em;
        margin-right: auto;
        margin-bottom: 20em;
    }
    table {
        border: rgba(83, 74, 74, 0.5) 1px solid;
        border-collapse: collapse;
        box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
        width: 1500px;
        margin: auto;
        @media (max-width: $large) {
            width: 360px;
        }
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

</style>