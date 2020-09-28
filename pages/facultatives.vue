<template>
    <div class="facultatives">
        <!--<img class="left-blot" src="/img/ui/blots/blot_left_2.svg">
        <img class="right-blot" src="/img/ui/blots/blot_right_2.svg">-->
        <span class="name1">⠀⠀⠀⠀Список факультативов</span>
        <span class="name1">⠀⠀⠀⠀Список факультативов</span>
        <span class="name2">⠀⠀⠀⠀Список факультативов</span>
        <div>
            <span class="bracket">[</span>
            <div class="quote_rext">
                Лучше не брать больше 1-2 факультативов для того, чтобы справляться с нагрузкой
            </div>
            <span class="bracket">]</span>
        </div>
        <div>
            <table class="lowerContent_table">
                <thead>
                    <tr>
                        <th class="th">Название факультатива</th>
                        <th class="th">Дата и время</th>
                        <th class="th">Преподаватель</th>
                    </tr>
                </thead>
                <tbody class="fac_body">
                    <tr>
                    <td>
                        <div class="fac-desc">
                            <div class="fac-desc_header">
                                Экспериментальная химия
                            </div>
                            <div class="fac-desc_body">
                                Взрывы, интересные эксперименты, ракеты - все это на экспериментальной химии. Вы научитесь вырабатывать алгоритм получения различных
                                веществ с заданными химическими и физическими свойствами и проводить их
                                идентификацию.
                            </div>
                        </div>
                    </td>
                    <td>Понедельник
                        5 пара,16:20
                        ауд. 215, Солянка</td>
                    <td>Васильев Васильев Васильевич</td>
                    </tr>
                    <tr>
                        <td>
                            <div class="fac-desc">
                                <div class="fac-desc_header">
                                    Экспериментальная химия
                                </div>
                                <div class="fac-desc_body">
                                    Взрывы, интересные эксперименты, ракеты - все это на экспериментальной химии. Вы научитесь вырабатывать алгоритм получения различных
                                    веществ с заданными химическими и физическими свойствами и проводить их
                                    идентификацию.
                                </div>
                            </div>
                        </td>
                        <td>Понедельник
                            5 пара,16:20
                            ауд. 215, Солянка
                        </td>
                        <td>Васильев Васильев Васильевич</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
  
</template>

<script>
export default {

}
</script>

<style scoped lang="scss">
    .facultatives {
        .name1, .name2 {
            color: transparent;
            width: fit-content;
            display: block;
            font-size: 44px;
            font-weight: 700;
            font-family: 'IBM Plex Sans';
            margin-top: -12px;
            -webkit-text-stroke: 1px $header-color;

        .name1 {
            margin-top: 0;
            @media (max-width: $large) {
                display: none;
            } 
        }
        .name2 {
            color: $header-color;
            -webkit-text-stroke-width: 0;
            @media (max-width: $large) {
                display: none;
            }
        }
        }
    }
    .lowerContent_table {
        width: 100%;
        min-height: 200px;
        margin-top: 30px;
        text-align: center;
        border-collapse: separate;
        border-spacing: 0;
        background-color: #f7e3a3;
        font-family: Montserrat;
    }
    .th {
        border-bottom: 0;
        height: 66px;
        background: rgba(139, 174, 114, 0.7);
        font-size: 16px;
        font-family: Montserrat;
        line-height: 20px;
        text-align: center;
        text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
        color: #FFF;
    }
    .fac-desc {
        padding: 15px 0;
        font-family: Montserrat;
    }
    .fac-desc_header {
        font-size: 16px;
        line-height: 20px;
        display: inline;
        border-bottom: 1px solid rgba(6, 6, 6, 0.13);
        color: #000;
        font-family: Montserrat;
    }
    .fac-desc_body {
        font-size: 12px;
        font-family: Montserrat;
    }
    .left-blot {
      position: absolute;
      height: 60%;
      width: auto;
      margin-bottom: 40px;
      margin-top: -20px;
    }
    .right-blot {
      position: absolute;
      height: 60%;
      width: auto;
      left: auto;
      right: 0;
      top: 0;
    }
</style>