<template>
  <div class="Flow">
    <div class="Flow-Heading">
      <CovidIcon />
      <h2 class="Flow-Heading-Title">新型コロナウイルス感染症が心配なときに</h2>
      <PrinterButton :wrapper-class="'Flow-PullRight'" />
    </div>
    <div class="Flow-Card">
      <div class="Flow-Card-Images only-pc">
        <FlowPc />
      </div>
      <div class="only-sp">
        <flow-sp />
      </div>
      <a
        href="https://www.pref.yamanashi.jp/koucho/coronavirus/info_coronavirus_consultation.html#Covid19_HealthConsultation"
        target="_blank"
        rel="noopener"
        class="Flow-Card-Button"
      >
        詳細を見る(山梨県のウェブサイト)
        <v-icon class="Flow-Card-Button-ExternalLinkIcon" size="20">
          mdi-open-in-new
        </v-icon>
      </a>

      <h2>発熱等の症状がある場合</h2>
      <dev class="Flow-Card">
        <div>
          <ul style="list-style: none;">
            <li>
              かかりつけ医がいる場合　→　かかりつけ医等最寄りの医療機関に電話をして相談
            </li>
            <li>
              かかりつけ医がいない場合　→　山梨県新型コロナウイルス感染症受診・相談センターに相談
            </li>
            <span>TEL：055-223-8896（24時間対応</span>
            <span
              >※甲府市の方は甲府市受診・相談センターに相談　TEL：055-237-8952（24時間対応</span
            >
          </ul>
        </div>
      </dev>
      <dev class="Flow-Card">
        <ul style="list-style: none;">
          <li>FAXでの相談はお住まいの地域の保健所へ</li>
          <li class="top_space">中北保健所　　　　FAX　0551－23－3075（平日　８時30分～17時15分）</li>
          <li>峡東保健所　　　　FAX　0553－20－2754（平日　８時30分～17時15分）</li>
          <li>峡南保健所　　　　FAX　0556－22－8159（平日　８時30分～17時15分）</li>
          <li>富士・東部保健所　FAX　0555－24－9037（平日　８時30分～17時15分）</li>
          <li>甲府市保健所　　　FAX　055－242－6178（平日・土日祝日　８時30分～17時15分）</li>
        </ul>
      </dev>

      <div class="AdvisoryContainer_3CI24">
        <div>
          <h2 class="Flow-Heading">不安に思う方</h2>
          <p>
            <ul style="list-style: none; text-align: left;">
              <li>山梨県新型コロナウイルス感染症受診・相談センターに相談　</li>
              <li>TEL：055-223-8896（24時間対応）</li>
              <li class="top_space">FAXでの相談は山梨県健康増進課　</li>
              <li>FAX:055－223－1499（平日　8時30分～17時15分）</li>
              <li class="top_space">甲府市保健所（甲府市にお住まいの方）</li>
              <li>FAX:055－242－6178（平日・土日祝日　８時30分～17時15分）</li>
            </ul>
            </p>
        </div>
        <div  class="AdvisoryContents_21MQf">
          <h2 class="Flow-Heading">電話やオンラインによる診療を行う医療機関</h2>
          <p>
            新型コロナウイルス感染症の拡大に際し、電話や情報通信機器を用いた診療が特例的に認められています。
            電話や情報通信機器による診療を行う医療機関の一覧はこちらをご覧ください。
          </p>
        </div>
      </div>
      <div style="text-align: center; margin-top: 10px">
        <span class="FlowLine__mDD1">詳細は以下のチラシをご覧ください</span>
        <br>
        <a
          class="Flow-Card-Button"
          href="https://www.pref.yamanashi.jp/koucho/coronavirus/documents/new.pdf"
        >
          新しい相談体制（11月1日より）（PDF：821KB）</a>
      </div>
    </div>
  </div>
</template>

<script>
import CovidIcon from '@/static/covid.svg'
import PrinterButton from '@/components/PrinterButton'
import FlowPc from '@/components/flow/FlowPc.vue'
import FlowSp from '@/components/flow/FlowSp.vue'

export default {
  components: { CovidIcon, PrinterButton, FlowPc, FlowSp },
  head() {
    return {
      title: '新型コロナウイルス感染症が心配なときに',
    }
  },
}
</script>

<style lang="scss">
.Flow {
  margin-bottom: 20px;
  &-Heading {
    display: flex;
    align-items: center;
    margin-bottom: 12px;
    > svg {
      width: 30px;
      height: 30px;
      > path:not(:first-of-type) {
        fill: $gray-2;
      }
    }
    &-Title {
      @include font-size(30);
      font-weight: normal;
      color: $gray-2;
      margin-left: 8px;
      @include lessThan($medium) {
        @include font-size(20);
        margin-right: 0.5em;
        line-height: 1.35;
      }
    }
  }
  &-Card {
    display: flex;
    flex-direction: column;
    @include card-container();
    padding: 20px;
    margin-bottom: 20px;
    > h2 {
      @include card-h1();
      margin-bottom: 12px;
    }
    &-Images {
      text-align: center;
      > img {
        margin: 18px 0;
      }
    }
    &-Parts {
      @include card-container();
      padding: 30px 20px;
      margin-bottom: 20px;
      &.Flat {
        background-color: $gray-5;
      }
      .TelLink {
        width: 80%;
        margin: 0 auto;
      }
      .Link {
        @include text-link();
      }
      .SodanHeader {
        text-align: center;
        &.Title {
          @include font-size(24);
        }
      }
      .SodanChip {
        display: inline-block;
        background-color: $white;
        border-radius: 4px;
        padding: 8px 24px;
        margin: 0 auto 12px;
        color: $purple-1;
        font-weight: bold;
      }
      .SodanHeijitsu {
        display: flex;
        align-items: center;
        padding: 12px 0;
        border-width: 0.5px 0;
        border-style: solid;
        border-color: $gray-4;
        .Heijitsu {
          width: 70%;
          margin-right: 5px;
        }
      }
      .SodanYakan {
        padding-top: 12px;
        .Yakan {
          text-align: center;
          .SodanTime {
            @include font-size(14);
          }
        }
      }
      .Col2Btn {
        display: flex;
      }
      .Smaller {
        width: 70%;
        margin: 0 auto;
      }
    }
    &-Button {
      @include button-text('md');
      margin: 12px auto 0;
      @include font-size(20);
      text-align: center;
      font-weight: 600;
      text-decoration: none;
      color: $purple-1 !important;
      &:hover {
        color: $white !important;
      }
      &-ExternalLinkIcon {
        margin-left: 2px;
        color: $purple-1 !important;
      }
    }
  }
  &-PullRight {
    margin: 0 0 0 auto;
  }
}
@include largerThan($medium) {
  .only-sp {
    display: none;
  }
  .only-pc {
    display: block;
  }
}
@include lessThan($medium) {
  .only-sp {
    display: block;
  }
  .only-pc {
    display: none;
  }
}

.top_space {
  margin-top: 10px;
}
</style>
