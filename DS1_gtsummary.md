DS1_gtsummary
================

## gtsummary 패키지 소개

gtsummary 패키지는 논문에 들어갈 **Table 1**을 만드는 데에 효율적으로
쓰일 수 있습니다.

------------------------------------------------------------------------

## Setup

``` r
# install.packages("tidyverse")
# install.packages("data.table")
# install.packages("gtsummary")
# install.packages("smd")
library(tidyverse)
library(data.table)
library(gtsummary)
library(smd)
```

------------------------------------------------------------------------

## Data load & Variable selection

연습을 위한 데이터셋을 만든다.

-   출처: <https://blog.zarathu.com/>

<!-- -->

    ##    EXMD_BZ_YYYY Q_PHX_DX_STK Q_SMK_YN HGHT WGHT TOT_CHOL  TG
    ## 1:         2009            0        1  144   61      264 128
    ## 2:         2009            0        1  162   51      169  92
    ## 3:         2009            0        1  163   65      216 132
    ## 4:         2009           NA        1  152   51      199 100
    ## 5:         2009           NA        1  159   50      162  58
    ## 6:         2009           NA        1  157   55      192 109

------------------------------------------------------------------------

## tbl_summary

tbl_summary는 다양한 옵션을 제공합니다.

-   label : 테이블에 출력되는 변수명 지정  
-   type : 변수 유형 지정 (ex. 연속형, 범주형)  
-   statistic : 요약 통계량 지정  
-   digits : 자릿수 지정  
-   missing : 결측값이 있는 행을 표시할지 여부  
-   missing_text : 결측행의 변수명 지정  
-   sort : 빈도에 따라 범주형 변수의 level 정렬  
-   percent : 열/행의 백분율 출력  
-   include : 테이블에 포함할 변수 지정

``` r
dt2 %>% select(-EXMD_BZ_YYYY) %>% tbl_summary()
```

<div id="soowtbphiw" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#soowtbphiw .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#soowtbphiw .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#soowtbphiw .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#soowtbphiw .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#soowtbphiw .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#soowtbphiw .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#soowtbphiw .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#soowtbphiw .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#soowtbphiw .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#soowtbphiw .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#soowtbphiw .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#soowtbphiw .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#soowtbphiw .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#soowtbphiw .gt_from_md > :first-child {
  margin-top: 0;
}

#soowtbphiw .gt_from_md > :last-child {
  margin-bottom: 0;
}

#soowtbphiw .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#soowtbphiw .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}

#soowtbphiw .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}

#soowtbphiw .gt_row_group_first td {
  border-top-width: 2px;
}

#soowtbphiw .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#soowtbphiw .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}

#soowtbphiw .gt_first_summary_row.thick {
  border-top-width: 2px;
}

#soowtbphiw .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#soowtbphiw .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#soowtbphiw .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#soowtbphiw .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#soowtbphiw .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#soowtbphiw .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#soowtbphiw .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-left: 4px;
  padding-right: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#soowtbphiw .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#soowtbphiw .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#soowtbphiw .gt_left {
  text-align: left;
}

#soowtbphiw .gt_center {
  text-align: center;
}

#soowtbphiw .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#soowtbphiw .gt_font_normal {
  font-weight: normal;
}

#soowtbphiw .gt_font_bold {
  font-weight: bold;
}

#soowtbphiw .gt_font_italic {
  font-style: italic;
}

#soowtbphiw .gt_super {
  font-size: 65%;
}

#soowtbphiw .gt_footnote_marks {
  font-style: italic;
  font-weight: normal;
  font-size: 75%;
  vertical-align: 0.4em;
}

#soowtbphiw .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}

#soowtbphiw .gt_slash_mark {
  font-size: 0.7em;
  line-height: 0.7em;
  vertical-align: 0.15em;
}

#soowtbphiw .gt_fraction_numerator {
  font-size: 0.6em;
  line-height: 0.6em;
  vertical-align: 0.45em;
}

#soowtbphiw .gt_fraction_denominator {
  font-size: 0.6em;
  line-height: 0.6em;
  vertical-align: -0.05em;
}
</style>
<table class="gt_table">
  
  <thead class="gt_col_headings">
    <tr>
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1"><strong>Characteristic</strong></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>N = 1,644</strong><sup class="gt_footnote_marks">1</sup></th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td class="gt_row gt_left">Q_PHX_DX_STK</td>
<td class="gt_row gt_center">12 (1.1%)</td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">Unknown</td>
<td class="gt_row gt_center">573</td></tr>
    <tr><td class="gt_row gt_left">Q_SMK_YN</td>
<td class="gt_row gt_center"></td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">1</td>
<td class="gt_row gt_center">995 (61%)</td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">2</td>
<td class="gt_row gt_center">256 (16%)</td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">3</td>
<td class="gt_row gt_center">391 (24%)</td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">Unknown</td>
<td class="gt_row gt_center">2</td></tr>
    <tr><td class="gt_row gt_left">HGHT</td>
<td class="gt_row gt_center">165 (158, 171)</td></tr>
    <tr><td class="gt_row gt_left">WGHT</td>
<td class="gt_row gt_center">64 (56, 73)</td></tr>
    <tr><td class="gt_row gt_left">TOT_CHOL</td>
<td class="gt_row gt_center">193 (170, 218)</td></tr>
    <tr><td class="gt_row gt_left">TG</td>
<td class="gt_row gt_center">106 (72, 163)</td></tr>
  </tbody>
  
  <tfoot class="gt_footnotes">
    <tr>
      <td class="gt_footnote" colspan="2"><sup class="gt_footnote_marks">1</sup> n (%); Median (IQR)</td>
    </tr>
  </tfoot>
</table>
</div>

``` r
dt2 %>%
  tbl_summary(
    by = EXMD_BZ_YYYY,
    statistic = list(all_continuous() ~ "{mean} ({sd})",
                     all_categorical() ~ "{n} / {N} ({p}%)"),
    label = Q_SMK_YN ~ "smoking y/n",
    missing_text = "Missing"
  ) %>% 
  add_p() %>%
  add_overall() %>% 
  add_n() 
```

<div id="cyagsfjmds" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#cyagsfjmds .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#cyagsfjmds .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#cyagsfjmds .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#cyagsfjmds .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#cyagsfjmds .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#cyagsfjmds .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#cyagsfjmds .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#cyagsfjmds .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#cyagsfjmds .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#cyagsfjmds .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#cyagsfjmds .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#cyagsfjmds .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#cyagsfjmds .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#cyagsfjmds .gt_from_md > :first-child {
  margin-top: 0;
}

#cyagsfjmds .gt_from_md > :last-child {
  margin-bottom: 0;
}

#cyagsfjmds .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#cyagsfjmds .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}

#cyagsfjmds .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}

#cyagsfjmds .gt_row_group_first td {
  border-top-width: 2px;
}

#cyagsfjmds .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#cyagsfjmds .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}

#cyagsfjmds .gt_first_summary_row.thick {
  border-top-width: 2px;
}

#cyagsfjmds .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#cyagsfjmds .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#cyagsfjmds .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#cyagsfjmds .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#cyagsfjmds .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#cyagsfjmds .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#cyagsfjmds .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-left: 4px;
  padding-right: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#cyagsfjmds .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#cyagsfjmds .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#cyagsfjmds .gt_left {
  text-align: left;
}

#cyagsfjmds .gt_center {
  text-align: center;
}

#cyagsfjmds .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#cyagsfjmds .gt_font_normal {
  font-weight: normal;
}

#cyagsfjmds .gt_font_bold {
  font-weight: bold;
}

#cyagsfjmds .gt_font_italic {
  font-style: italic;
}

#cyagsfjmds .gt_super {
  font-size: 65%;
}

#cyagsfjmds .gt_footnote_marks {
  font-style: italic;
  font-weight: normal;
  font-size: 75%;
  vertical-align: 0.4em;
}

#cyagsfjmds .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}

#cyagsfjmds .gt_slash_mark {
  font-size: 0.7em;
  line-height: 0.7em;
  vertical-align: 0.15em;
}

#cyagsfjmds .gt_fraction_numerator {
  font-size: 0.6em;
  line-height: 0.6em;
  vertical-align: 0.45em;
}

#cyagsfjmds .gt_fraction_denominator {
  font-size: 0.6em;
  line-height: 0.6em;
  vertical-align: -0.05em;
}
</style>
<table class="gt_table">
  
  <thead class="gt_col_headings">
    <tr>
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1"><strong>Characteristic</strong></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>N</strong></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>Overall</strong>, N = 1,644<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2009</strong>, N = 214<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2010</strong>, N = 236<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2011</strong>, N = 223<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2012</strong>, N = 234<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2013</strong>, N = 243<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2014</strong>, N = 254<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2015</strong>, N = 240<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>p-value</strong><sup class="gt_footnote_marks">2</sup></th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td class="gt_row gt_left">Q_PHX_DX_STK</td>
<td class="gt_row gt_center">1,071</td>
<td class="gt_row gt_center">12 / 1,071 (1.1%)</td>
<td class="gt_row gt_center">2 / 132 (1.5%)</td>
<td class="gt_row gt_center">2 / 162 (1.2%)</td>
<td class="gt_row gt_center">1 / 138 (0.7%)</td>
<td class="gt_row gt_center">2 / 156 (1.3%)</td>
<td class="gt_row gt_center">2 / 168 (1.2%)</td>
<td class="gt_row gt_center">2 / 159 (1.3%)</td>
<td class="gt_row gt_center">1 / 156 (0.6%)</td>
<td class="gt_row gt_center">>0.9</td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">Missing</td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center">573</td>
<td class="gt_row gt_center">82</td>
<td class="gt_row gt_center">74</td>
<td class="gt_row gt_center">85</td>
<td class="gt_row gt_center">78</td>
<td class="gt_row gt_center">75</td>
<td class="gt_row gt_center">95</td>
<td class="gt_row gt_center">84</td>
<td class="gt_row gt_center"></td></tr>
    <tr><td class="gt_row gt_left">smoking y/n</td>
<td class="gt_row gt_center">1,642</td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center">0.9</td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">1</td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center">995 / 1,642 (61%)</td>
<td class="gt_row gt_center">125 / 212 (59%)</td>
<td class="gt_row gt_center">132 / 236 (56%)</td>
<td class="gt_row gt_center">140 / 223 (63%)</td>
<td class="gt_row gt_center">146 / 234 (62%)</td>
<td class="gt_row gt_center">141 / 243 (58%)</td>
<td class="gt_row gt_center">157 / 254 (62%)</td>
<td class="gt_row gt_center">154 / 240 (64%)</td>
<td class="gt_row gt_center"></td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">2</td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center">256 / 1,642 (16%)</td>
<td class="gt_row gt_center">34 / 212 (16%)</td>
<td class="gt_row gt_center">42 / 236 (18%)</td>
<td class="gt_row gt_center">35 / 223 (16%)</td>
<td class="gt_row gt_center">36 / 234 (15%)</td>
<td class="gt_row gt_center">35 / 243 (14%)</td>
<td class="gt_row gt_center">38 / 254 (15%)</td>
<td class="gt_row gt_center">36 / 240 (15%)</td>
<td class="gt_row gt_center"></td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">3</td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center">391 / 1,642 (24%)</td>
<td class="gt_row gt_center">53 / 212 (25%)</td>
<td class="gt_row gt_center">62 / 236 (26%)</td>
<td class="gt_row gt_center">48 / 223 (22%)</td>
<td class="gt_row gt_center">52 / 234 (22%)</td>
<td class="gt_row gt_center">67 / 243 (28%)</td>
<td class="gt_row gt_center">59 / 254 (23%)</td>
<td class="gt_row gt_center">50 / 240 (21%)</td>
<td class="gt_row gt_center"></td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">Missing</td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center">2</td>
<td class="gt_row gt_center">2</td>
<td class="gt_row gt_center">0</td>
<td class="gt_row gt_center">0</td>
<td class="gt_row gt_center">0</td>
<td class="gt_row gt_center">0</td>
<td class="gt_row gt_center">0</td>
<td class="gt_row gt_center">0</td>
<td class="gt_row gt_center"></td></tr>
    <tr><td class="gt_row gt_left">HGHT</td>
<td class="gt_row gt_center">1,644</td>
<td class="gt_row gt_center">165 (9)</td>
<td class="gt_row gt_center">164 (9)</td>
<td class="gt_row gt_center">165 (9)</td>
<td class="gt_row gt_center">164 (10)</td>
<td class="gt_row gt_center">165 (9)</td>
<td class="gt_row gt_center">165 (9)</td>
<td class="gt_row gt_center">164 (9)</td>
<td class="gt_row gt_center">164 (9)</td>
<td class="gt_row gt_center">>0.9</td></tr>
    <tr><td class="gt_row gt_left">WGHT</td>
<td class="gt_row gt_center">1,644</td>
<td class="gt_row gt_center">65 (13)</td>
<td class="gt_row gt_center">64 (13)</td>
<td class="gt_row gt_center">65 (12)</td>
<td class="gt_row gt_center">65 (13)</td>
<td class="gt_row gt_center">66 (12)</td>
<td class="gt_row gt_center">65 (12)</td>
<td class="gt_row gt_center">64 (12)</td>
<td class="gt_row gt_center">66 (13)</td>
<td class="gt_row gt_center">0.8</td></tr>
    <tr><td class="gt_row gt_left">TOT_CHOL</td>
<td class="gt_row gt_center">1,644</td>
<td class="gt_row gt_center">195 (37)</td>
<td class="gt_row gt_center">195 (37)</td>
<td class="gt_row gt_center">195 (39)</td>
<td class="gt_row gt_center">194 (38)</td>
<td class="gt_row gt_center">199 (35)</td>
<td class="gt_row gt_center">192 (36)</td>
<td class="gt_row gt_center">195 (36)</td>
<td class="gt_row gt_center">195 (36)</td>
<td class="gt_row gt_center">0.7</td></tr>
    <tr><td class="gt_row gt_left">TG</td>
<td class="gt_row gt_center">1,644</td>
<td class="gt_row gt_center">135 (105)</td>
<td class="gt_row gt_center">129 (90)</td>
<td class="gt_row gt_center">136 (101)</td>
<td class="gt_row gt_center">138 (108)</td>
<td class="gt_row gt_center">129 (89)</td>
<td class="gt_row gt_center">132 (98)</td>
<td class="gt_row gt_center">138 (127)</td>
<td class="gt_row gt_center">141 (113)</td>
<td class="gt_row gt_center">>0.9</td></tr>
  </tbody>
  
  <tfoot class="gt_footnotes">
    <tr>
      <td class="gt_footnote" colspan="11"><sup class="gt_footnote_marks">1</sup> n / N (%); Mean (SD)</td>
    </tr>
    <tr>
      <td class="gt_footnote" colspan="11"><sup class="gt_footnote_marks">2</sup> Fisher's exact test; Pearson's Chi-squared test; Kruskal-Wallis rank sum test</td>
    </tr>
  </tfoot>
</table>
</div>

------------------------------------------------------------------------

#### 그룹간 차이

add_difference() 을 통해 그룹간 차이를 확인할 수 있다.

``` r
dt2 %>% select(-Q_SMK_YN, -EXMD_BZ_YYYY) %>% 
  tbl_summary(by = Q_PHX_DX_STK) %>%
  add_difference()
```

<div id="nxjfbrdczv" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#nxjfbrdczv .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#nxjfbrdczv .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#nxjfbrdczv .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#nxjfbrdczv .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#nxjfbrdczv .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#nxjfbrdczv .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#nxjfbrdczv .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#nxjfbrdczv .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#nxjfbrdczv .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#nxjfbrdczv .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#nxjfbrdczv .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#nxjfbrdczv .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#nxjfbrdczv .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#nxjfbrdczv .gt_from_md > :first-child {
  margin-top: 0;
}

#nxjfbrdczv .gt_from_md > :last-child {
  margin-bottom: 0;
}

#nxjfbrdczv .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#nxjfbrdczv .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}

#nxjfbrdczv .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}

#nxjfbrdczv .gt_row_group_first td {
  border-top-width: 2px;
}

#nxjfbrdczv .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#nxjfbrdczv .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}

#nxjfbrdczv .gt_first_summary_row.thick {
  border-top-width: 2px;
}

#nxjfbrdczv .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#nxjfbrdczv .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#nxjfbrdczv .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#nxjfbrdczv .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#nxjfbrdczv .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#nxjfbrdczv .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#nxjfbrdczv .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-left: 4px;
  padding-right: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#nxjfbrdczv .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#nxjfbrdczv .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#nxjfbrdczv .gt_left {
  text-align: left;
}

#nxjfbrdczv .gt_center {
  text-align: center;
}

#nxjfbrdczv .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#nxjfbrdczv .gt_font_normal {
  font-weight: normal;
}

#nxjfbrdczv .gt_font_bold {
  font-weight: bold;
}

#nxjfbrdczv .gt_font_italic {
  font-style: italic;
}

#nxjfbrdczv .gt_super {
  font-size: 65%;
}

#nxjfbrdczv .gt_footnote_marks {
  font-style: italic;
  font-weight: normal;
  font-size: 75%;
  vertical-align: 0.4em;
}

#nxjfbrdczv .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}

#nxjfbrdczv .gt_slash_mark {
  font-size: 0.7em;
  line-height: 0.7em;
  vertical-align: 0.15em;
}

#nxjfbrdczv .gt_fraction_numerator {
  font-size: 0.6em;
  line-height: 0.6em;
  vertical-align: 0.45em;
}

#nxjfbrdczv .gt_fraction_denominator {
  font-size: 0.6em;
  line-height: 0.6em;
  vertical-align: -0.05em;
}
</style>
<table class="gt_table">
  
  <thead class="gt_col_headings">
    <tr>
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1"><strong>Characteristic</strong></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>0</strong>, N = 1,059<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>1</strong>, N = 12<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>Difference</strong><sup class="gt_footnote_marks">2</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>95% CI</strong><sup class="gt_footnote_marks">2,3</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>p-value</strong><sup class="gt_footnote_marks">2</sup></th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td class="gt_row gt_left">HGHT</td>
<td class="gt_row gt_center">166 (160, 172)</td>
<td class="gt_row gt_center">159 (155, 170)</td>
<td class="gt_row gt_center">6.5</td>
<td class="gt_row gt_center">-0.44, 14</td>
<td class="gt_row gt_center">0.064</td></tr>
    <tr><td class="gt_row gt_left">WGHT</td>
<td class="gt_row gt_center">65 (58, 73)</td>
<td class="gt_row gt_center">64 (56, 66)</td>
<td class="gt_row gt_center">5.4</td>
<td class="gt_row gt_center">-0.04, 11</td>
<td class="gt_row gt_center">0.051</td></tr>
    <tr><td class="gt_row gt_left">TOT_CHOL</td>
<td class="gt_row gt_center">194 (171, 218)</td>
<td class="gt_row gt_center">163 (146, 192)</td>
<td class="gt_row gt_center">23</td>
<td class="gt_row gt_center">1.9, 43</td>
<td class="gt_row gt_center">0.035</td></tr>
    <tr><td class="gt_row gt_left">TG</td>
<td class="gt_row gt_center">108 (73, 163)</td>
<td class="gt_row gt_center">128 (116, 148)</td>
<td class="gt_row gt_center">-12</td>
<td class="gt_row gt_center">-50, 26</td>
<td class="gt_row gt_center">0.5</td></tr>
  </tbody>
  
  <tfoot class="gt_footnotes">
    <tr>
      <td class="gt_footnote" colspan="6"><sup class="gt_footnote_marks">1</sup> Median (IQR)</td>
    </tr>
    <tr>
      <td class="gt_footnote" colspan="6"><sup class="gt_footnote_marks">2</sup> Welch Two Sample t-test</td>
    </tr>
    <tr>
      <td class="gt_footnote" colspan="6"><sup class="gt_footnote_marks">3</sup> CI = Confidence Interval</td>
    </tr>
  </tfoot>
</table>
</div>

------------------------------------------------------------------------

#### 테이블 디자인 및 포맷

-   modify_header() : 테이블 header 형식 지정  
-   modify_footnote() : 테이블 각주 형식 지정  
-   modify_spanning_header() : 테이블 spanning header 형식 지정  
-   modify_caption() : 테이블 캡션 형식 지정  
-   bold_labels() : 변수명 볼드체  
-   bold_levels() : 범주 볼드체  
-   italicize_labels() : 변수명 기울임  
-   italicize_levels() : 범주 기울임  
-   bold_p() : p-value 볼드체

``` r
MyTbl <- dt2 %>% 
  tbl_summary(by = EXMD_BZ_YYYY) %>%
  add_p() %>%
  add_n() %>% 
  modify_header(label ~ "**변수명**") %>% 
  modify_spanning_header(all_stat_cols() ~ "**해당연도**") %>% 
  modify_footnote(all_stat_cols() ~ "Median(IQR) 또는 Frequency(%)로 표기하였음") %>%
  modify_caption("연도별 기술통계량") %>% 
  bold_labels()
MyTbl
```

<div id="slnomilawb" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#slnomilawb .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#slnomilawb .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#slnomilawb .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#slnomilawb .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#slnomilawb .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#slnomilawb .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#slnomilawb .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#slnomilawb .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#slnomilawb .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#slnomilawb .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#slnomilawb .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#slnomilawb .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#slnomilawb .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#slnomilawb .gt_from_md > :first-child {
  margin-top: 0;
}

#slnomilawb .gt_from_md > :last-child {
  margin-bottom: 0;
}

#slnomilawb .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#slnomilawb .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}

#slnomilawb .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}

#slnomilawb .gt_row_group_first td {
  border-top-width: 2px;
}

#slnomilawb .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#slnomilawb .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}

#slnomilawb .gt_first_summary_row.thick {
  border-top-width: 2px;
}

#slnomilawb .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#slnomilawb .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#slnomilawb .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#slnomilawb .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#slnomilawb .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#slnomilawb .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#slnomilawb .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-left: 4px;
  padding-right: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#slnomilawb .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#slnomilawb .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}

#slnomilawb .gt_left {
  text-align: left;
}

#slnomilawb .gt_center {
  text-align: center;
}

#slnomilawb .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#slnomilawb .gt_font_normal {
  font-weight: normal;
}

#slnomilawb .gt_font_bold {
  font-weight: bold;
}

#slnomilawb .gt_font_italic {
  font-style: italic;
}

#slnomilawb .gt_super {
  font-size: 65%;
}

#slnomilawb .gt_footnote_marks {
  font-style: italic;
  font-weight: normal;
  font-size: 75%;
  vertical-align: 0.4em;
}

#slnomilawb .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}

#slnomilawb .gt_slash_mark {
  font-size: 0.7em;
  line-height: 0.7em;
  vertical-align: 0.15em;
}

#slnomilawb .gt_fraction_numerator {
  font-size: 0.6em;
  line-height: 0.6em;
  vertical-align: 0.45em;
}

#slnomilawb .gt_fraction_denominator {
  font-size: 0.6em;
  line-height: 0.6em;
  vertical-align: -0.05em;
}
</style>
<table class="gt_table">
  <caption>연도별 기술통계량</caption>
  
  <thead class="gt_col_headings">
    <tr>
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="2" colspan="1"><strong>변수명</strong></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="2" colspan="1"><strong>N</strong></th>
      <th class="gt_center gt_columns_top_border gt_column_spanner_outer" rowspan="1" colspan="7">
        <span class="gt_column_spanner"><strong>해당연도</strong></span>
      </th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="2" colspan="1"><strong>p-value</strong><sup class="gt_footnote_marks">2</sup></th>
    </tr>
    <tr>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2009</strong>, N = 214<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2010</strong>, N = 236<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2011</strong>, N = 223<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2012</strong>, N = 234<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2013</strong>, N = 243<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2014</strong>, N = 254<sup class="gt_footnote_marks">1</sup></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1"><strong>2015</strong>, N = 240<sup class="gt_footnote_marks">1</sup></th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td class="gt_row gt_left" style="font-weight: bold;">Q_PHX_DX_STK</td>
<td class="gt_row gt_center">1,071</td>
<td class="gt_row gt_center">2 (1.5%)</td>
<td class="gt_row gt_center">2 (1.2%)</td>
<td class="gt_row gt_center">1 (0.7%)</td>
<td class="gt_row gt_center">2 (1.3%)</td>
<td class="gt_row gt_center">2 (1.2%)</td>
<td class="gt_row gt_center">2 (1.3%)</td>
<td class="gt_row gt_center">1 (0.6%)</td>
<td class="gt_row gt_center">>0.9</td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">Unknown</td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center">82</td>
<td class="gt_row gt_center">74</td>
<td class="gt_row gt_center">85</td>
<td class="gt_row gt_center">78</td>
<td class="gt_row gt_center">75</td>
<td class="gt_row gt_center">95</td>
<td class="gt_row gt_center">84</td>
<td class="gt_row gt_center"></td></tr>
    <tr><td class="gt_row gt_left" style="font-weight: bold;">Q_SMK_YN</td>
<td class="gt_row gt_center">1,642</td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center">0.9</td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">1</td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center">125 (59%)</td>
<td class="gt_row gt_center">132 (56%)</td>
<td class="gt_row gt_center">140 (63%)</td>
<td class="gt_row gt_center">146 (62%)</td>
<td class="gt_row gt_center">141 (58%)</td>
<td class="gt_row gt_center">157 (62%)</td>
<td class="gt_row gt_center">154 (64%)</td>
<td class="gt_row gt_center"></td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">2</td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center">34 (16%)</td>
<td class="gt_row gt_center">42 (18%)</td>
<td class="gt_row gt_center">35 (16%)</td>
<td class="gt_row gt_center">36 (15%)</td>
<td class="gt_row gt_center">35 (14%)</td>
<td class="gt_row gt_center">38 (15%)</td>
<td class="gt_row gt_center">36 (15%)</td>
<td class="gt_row gt_center"></td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">3</td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center">53 (25%)</td>
<td class="gt_row gt_center">62 (26%)</td>
<td class="gt_row gt_center">48 (22%)</td>
<td class="gt_row gt_center">52 (22%)</td>
<td class="gt_row gt_center">67 (28%)</td>
<td class="gt_row gt_center">59 (23%)</td>
<td class="gt_row gt_center">50 (21%)</td>
<td class="gt_row gt_center"></td></tr>
    <tr><td class="gt_row gt_left" style="text-align: left; text-indent: 10px;">Unknown</td>
<td class="gt_row gt_center"></td>
<td class="gt_row gt_center">2</td>
<td class="gt_row gt_center">0</td>
<td class="gt_row gt_center">0</td>
<td class="gt_row gt_center">0</td>
<td class="gt_row gt_center">0</td>
<td class="gt_row gt_center">0</td>
<td class="gt_row gt_center">0</td>
<td class="gt_row gt_center"></td></tr>
    <tr><td class="gt_row gt_left" style="font-weight: bold;">HGHT</td>
<td class="gt_row gt_center">1,644</td>
<td class="gt_row gt_center">165 (159, 171)</td>
<td class="gt_row gt_center">165 (159, 171)</td>
<td class="gt_row gt_center">165 (157, 171)</td>
<td class="gt_row gt_center">164 (159, 172)</td>
<td class="gt_row gt_center">165 (159, 171)</td>
<td class="gt_row gt_center">164 (158, 172)</td>
<td class="gt_row gt_center">164 (158, 172)</td>
<td class="gt_row gt_center">>0.9</td></tr>
    <tr><td class="gt_row gt_left" style="font-weight: bold;">WGHT</td>
<td class="gt_row gt_center">1,644</td>
<td class="gt_row gt_center">64 (55, 72)</td>
<td class="gt_row gt_center">64 (56, 73)</td>
<td class="gt_row gt_center">63 (56, 72)</td>
<td class="gt_row gt_center">64 (57, 74)</td>
<td class="gt_row gt_center">64 (57, 72)</td>
<td class="gt_row gt_center">63 (56, 72)</td>
<td class="gt_row gt_center">64 (57, 74)</td>
<td class="gt_row gt_center">0.8</td></tr>
    <tr><td class="gt_row gt_left" style="font-weight: bold;">TOT_CHOL</td>
<td class="gt_row gt_center">1,644</td>
<td class="gt_row gt_center">192 (170, 216)</td>
<td class="gt_row gt_center">193 (168, 220)</td>
<td class="gt_row gt_center">190 (168, 214)</td>
<td class="gt_row gt_center">196 (173, 224)</td>
<td class="gt_row gt_center">190 (168, 218)</td>
<td class="gt_row gt_center">193 (171, 216)</td>
<td class="gt_row gt_center">194 (171, 217)</td>
<td class="gt_row gt_center">0.7</td></tr>
    <tr><td class="gt_row gt_left" style="font-weight: bold;">TG</td>
<td class="gt_row gt_center">1,644</td>
<td class="gt_row gt_center">105 (71, 148)</td>
<td class="gt_row gt_center">107 (70, 158)</td>
<td class="gt_row gt_center">104 (74, 164)</td>
<td class="gt_row gt_center">108 (69, 164)</td>
<td class="gt_row gt_center">107 (76, 160)</td>
<td class="gt_row gt_center">108 (75, 162)</td>
<td class="gt_row gt_center">111 (71, 167)</td>
<td class="gt_row gt_center">>0.9</td></tr>
  </tbody>
  
  <tfoot class="gt_footnotes">
    <tr>
      <td class="gt_footnote" colspan="10"><sup class="gt_footnote_marks">1</sup> Median(IQR) 또는 Frequency(%)로 표기하였음</td>
    </tr>
    <tr>
      <td class="gt_footnote" colspan="10"><sup class="gt_footnote_marks">2</sup> Fisher's exact test; Pearson's Chi-squared test; Kruskal-Wallis rank sum test</td>
    </tr>
  </tfoot>
</table>
</div>

------------------------------------------------------------------------

## 워드 파일로 저장하기

gtsummary 패키지를 이용해 만든 table을 flextable 객체로 바꾼 후 워드
파일로 저장할 수 있다.

``` r
MyTbl %>% 
  as_flex_table() %>% 
  flextable::save_as_docx(MyTbl, path = "table1.docx")
```

출처: <https://blog.zarathu.com/>
