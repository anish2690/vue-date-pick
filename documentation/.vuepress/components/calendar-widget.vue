<template>
    <div class="calendarWidget">
        <date-pick
            class="datePickExample"
            v-model="date"
            :hasInputElement="false"
            :startDate="'2020-02-05'"
            format="YYYY-MM-DD"

        ></date-pick>
    </div>
</template>

<script>
import DatePick from '../../../src/vueDatePick';
import fecha from 'fecha';

export default {
    components: {DatePick},
    data(){
        const d = new Date()
        let month = '' + (d.getMonth() + 1)
        let day = '' + d.getDate()
        const year = d.getFullYear()
        if (month.length < 2)
            month = '0' + month;
        if (day.length < 2)
            day = '0' + day;

        const date = [year, month, day].join('-');
            return {
                date
            }
    }
};
</script>

<style lang="scss" scoped>

    .calendarWidget {

        margin-bottom: 15px;

        @media screen and (min-width: 720px) {

            padding: 30px 20px;
            background-color: #fff; border-radius: 4px;
            border: 1px solid #ededed;

        }

    }

    .vdpComponent {

        display: block; max-width: 32em; margin: 0 auto;

    }

</style>
