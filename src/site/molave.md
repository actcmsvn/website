---
title: ACTCMS Vietnam
subtitle: ACTCMS is an IT company, We provide our clients with unique solutions of any level of complexity.
layout: layouts/app.njk
---
<article class="row-block-top" id='tabmap'>
    <div class='tab container-fluid' style="min-height: 789px; overflow: hidden;">
        <div class='container header-container'>
            <ul class='tab-list button-map-weather '>
                <li class='tab-header px-3 py-2 my-2 selected' data-target='.tab1'>Thời tiết các điểm</li>
                <li class='tab-header px-3 py-2 my-2' data-target='.tab2'>Mực nước các điểm</li>
                <li class='tab-header px-3 py-2 my-2' data-target='.tab3'>Dự báo điểm hải văn </li>
                <li class='tab-header px-3 py-2 my-2' data-target='.tab4'>Bản đồ phân tích thời tiết</li>
            </ul>
        </div>
        <div class='content-container'>
            <div class='tab-content tab1'>
                <div class='container'>
                    <div id="mapid" style="width: 850px; height: 750px;"></div>
                </div>
            </div>
            <div class='tab-content tab2'>
                <div class='container'>
                    <div id="mapidHydro" style="width: 850px; height: 750px;"></div>
                </div>
            </div>
            <div class='tab-content tab3'>
                <div class='container'>
                    <div id="mapidMarine" style="width: 850px; height: 750px;"></div>
                </div>
            </div>
            <div class='tab-content tab4'>
                <div class='container'>
                    <div class="uk-position-relative" uk-slider="autoplay: true;autoplay-interval: 1000;">
                        <ul class="uk-slider-items">
                            <li>
                                <img src="https://thoitietvietnam.gov.vn//Upload/SynopImage/2020/10/27/UA-MD-00.png" alt="" style="width: 850px; height: 750px;"><!-- Phần hiển thị ảnh 1-->
                            </li>
                            <li>
                                <img src="https://thoitietvietnam.gov.vn//Upload/SynopImage/2020/10/27/UA-850-00.png" alt="" style="width: 850px; height: 750px;"><!-- Phần hiển thị ảnh 1-->
                            </li>
                            <li>
                                <img src="https://thoitietvietnam.gov.vn//Upload/SynopImage/2020/10/27/UA-700-00.png" alt="" style="width: 850px; height: 750px;"><!-- Phần hiển thị ảnh 1-->
                            </li>
                            <li>
                                <img src="https://thoitietvietnam.gov.vn//Upload/SynopImage/2020/10/27/UA-500-00.png" alt="" style="width: 850px; height: 750px;"><!-- Phần hiển thị ảnh 1-->
                            </li>
                        </ul>
                        <a class="uk-position-center-left uk-position-small uk-hidden-hover" href="#" uk-slidenav-previous uk-slider-item="previous"></a>
                        <a class="uk-position-center-right uk-position-small uk-hidden-hover" href="#" uk-slidenav-next uk-slider-item="next"></a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</article>
<script>
    $(document).ready(function() {
        if (window.matchMedia("(max-width: 767px)").matches) {
            // The viewport is less than 768 pixels wide           
            $('#tabmap').css({ 'display': 'none' });
        } else {
            $('#tabmap').css({ 'display': 'block' });
        }
    });


    var Icon_8 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/261.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_197 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/4051.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_1253 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4501.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_10 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/110.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_12 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/40.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_13 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/111.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_14 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/90.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_15 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/340.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_19 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/300.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_27 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/390.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_216 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/wer', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_28 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/110.gif', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_29 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/6_lge.gif', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_30 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/90.gif', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_523 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/321.gif', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_524 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/320.gif', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_525 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/310.gif', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_526 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/330.gif', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_527 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/270.gif', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_528 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/450.gif', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_795 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0001.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_796 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0002.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_797 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0003.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_798 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0011.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_799 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0012.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_800 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0021.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_801 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0022.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_802 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0031.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_803 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0032.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_804 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1001.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_805 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1002.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_806 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1003.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_807 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1011.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_808 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1012.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_809 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1021.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_810 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1022.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_811 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1031.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_812 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1032.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_813 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1081.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_814 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1082.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_815 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1083.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_816 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2001.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_817 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2002.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_818 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2003.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_819 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2301.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_820 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2302.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_821 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2303.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_822 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2501.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_823 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2502.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_824 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2503.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_825 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4001.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_826 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4041.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_827 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4051.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_831 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4061.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_832 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4341.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_833 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4351.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_834 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4361.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_835 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4391.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_836 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4091.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_837 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4101.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_838 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4181.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_839 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4201.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_840 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4301.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_841 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4401.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_842 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4541.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_843 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4601.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_844 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4701.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var Icon_845 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4571.png', iconSize: [40, 30], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_8 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/261.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_197 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/4051.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_1253 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4501.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_10 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/110.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_12 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/40.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_13 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/111.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_14 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/90.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_15 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/340.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_19 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/300.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_27 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/390.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_216 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/wer', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_28 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/110.gif', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_29 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/6_lge.gif', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_30 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/90.gif', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_523 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/321.gif', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_524 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/320.gif', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_525 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/310.gif', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_526 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/330.gif', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_527 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/270.gif', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_528 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/2008/8/22/450.gif', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_795 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0001.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_796 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0002.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_797 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0003.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_798 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0011.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_799 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0012.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_800 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0021.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_801 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0022.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_802 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0031.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_803 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/0032.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_804 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1001.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_805 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1002.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_806 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1003.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_807 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1011.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_808 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1012.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_809 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1021.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_810 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1022.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_811 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1031.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_812 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1032.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_813 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1081.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_814 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1082.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_815 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/1083.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_816 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2001.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_817 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2002.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_818 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2003.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_819 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2301.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_820 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2302.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_821 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2303.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_822 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2501.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_823 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2502.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_824 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2503.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_825 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4001.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_826 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4041.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_827 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4051.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_831 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4061.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_832 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4341.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_833 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4351.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_834 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4361.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_835 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4391.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_836 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4091.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_837 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4101.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_838 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4181.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_839 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4201.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_840 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4301.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_841 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4401.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_842 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4541.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_843 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4601.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_844 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4701.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var IconL_845 = L.icon({ iconUrl: 'https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4571.png', iconSize: [1, 1], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });

    var stationIcon = L.icon({ iconUrl: "https://thoitietvietnam.gov.vn//Upload/IconBT.png", iconSize: [12, 12], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    /*icon storm*/
    var stormIcon1 = L.icon({ iconUrl: "https://thoitietvietnam.gov.vn//Upload/Storm/1.png", iconSize: [12, 12], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var stormIcon11 = L.icon({ iconUrl: "https://thoitietvietnam.gov.vn//Upload/Storm/11.png", iconSize: [12, 12], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var stormIcon2 = L.icon({ iconUrl: "https://thoitietvietnam.gov.vn//Upload/Storm/2.png", iconSize: [12, 12], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var stormIcon22 = L.icon({ iconUrl: "https://thoitietvietnam.gov.vn//Upload/Storm/22.png", iconSize: [12, 12], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var stormIcon3 = L.icon({ iconUrl: "https://thoitietvietnam.gov.vn//Upload/Storm/3.png", iconSize: [12, 12], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });
    var stormIcon33 = L.icon({ iconUrl: "https://thoitietvietnam.gov.vn//Upload/Storm/33.png", iconSize: [12, 12], iconAnchor: [12, 12], popupAnchor: [0.5, 0.5] });

    //khởi tạo bản đồ với tọa độ và mức zoom ban đầu
    var map = L.map('mapid').setView([15.834536, 110.880273], 6);
    var mapHydro = L.map('mapidHydro').setView([15.834536, 110.880273], 6);
    var mapMarine = L.map('mapidMarine').setView([15.834536, 110.880273], 6);

    //thêm lớp bản đồ nền
    L.tileLayer('https://khituongvietnam.gov.vn/maptv/map/{z}/{x}/{y}.png', {
        tms: false,
        minZoom: 5,
        maxZoom: 14
    }).addTo(mapHydro);

    //thêm lớp bản đồ nền
    L.tileLayer('https://khituongvietnam.gov.vn/mapvn/map/{z}/{x}/{y}.png', {
        tms: false,
        minZoom: 5,
        maxZoom: 14
    }).addTo(map);

    //thêm lớp bản đồ nền
    L.tileLayer('https://khituongvietnam.gov.vn/maptv/map/{z}/{x}/{y}.png', {
        tms: false,
        minZoom: 5,
        maxZoom: 14
    }).addTo(mapMarine);



    var LHVCoTo = L.marker([20.98, 107.76], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=CoTo'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVCuaOng = L.marker([21.01, 107.35], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=CuaOng'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVBaiChay = L.marker([20.95, 107.06], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=BaiChay'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVHonDau = L.marker([20.66, 106.8], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=HonDau'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVBachLongVi = L.marker([20.13, 107.71], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=BachLongVi'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVTraCo = L.marker([21.43, 107.96], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=TraCo'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVSamSon = L.marker([19.75, 105.90], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=SamSon'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVHonNgu = L.marker([18.80, 105.76], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=HonNgu'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVHoanhSon = L.marker([17.91, 106.35], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=HoanhSon'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVConCo = L.marker([17.16, 107.35], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=ConCo'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVSonTra = L.marker([16.10, 108.21], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=SonTra'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVLySon = L.marker([15.38, 109.15], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=LySon'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVQuyNhon = L.marker([13.75, 109.21], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=QuyNhon'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVPhuQuy = L.marker([10.51, 108.93], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=PhuQuy'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVTruongSa = L.marker([8.65, 111.91], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=TruongSa'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVSongTuTay = L.marker([11.41, 114.33], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=SongTuTay'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVDKI7 = L.marker([8.01, 110.61], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=DKI7'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVVungTau = L.marker([10.33, 107.06], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=VungTau'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVConDao = L.marker([8.68, 106.60], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=ConDao'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVThoChu = L.marker([9.28, 103.46], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=ThoChu'></iframe></td></tr></table>", { maxWidth: 560 });
    var LHVPhuQuoc = L.marker([10.21, 103.96], { icon: stationIcon }).addTo(mapMarine).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv//Pages/MapHVInfor.aspx?id=PhuQuoc'></iframe></td></tr></table>", { maxWidth: 560 });


    var L91313 = L.marker([21.297, 106.192], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/91313/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L91316 = L.marker([21.331, 106.499], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/91316/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L91311 = L.marker([21.202, 106.098], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/91311/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L74165 = L.marker([21.031, 105.859], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/74165/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L74154 = L.marker([21.399, 105.226], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/74154/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L74155 = L.marker([21.571, 105.258], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/74155/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L74146 = L.marker([21.822, 105.219], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/74146/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L74129 = L.marker([21.704, 104.863], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/74129/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L74114 = L.marker([20.811, 105.313], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/74114/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L91170 = L.marker([21.114, 106.303], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/91170/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L74181 = L.marker([20.356, 105.798], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/74181/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L73405 = L.marker([19.866, 105.751], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/73405/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L72428 = L.marker([18.713, 105.483], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/72428/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L72444 = L.marker([18.533, 105.551], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/72444/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L71501 = L.marker([17.812, 106.183], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/71501/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L71520 = L.marker([16.416, 107.566], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/71520/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L71531 = L.marker([15.858, 108.274], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/71531/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L71540 = L.marker([15.133, 108.783], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/71540/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L71559 = L.marker([13.066, 109.312], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/71559/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L69759 = L.marker([10.801, 105.243], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/69759/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L66760 = L.marker([10.705, 105.134], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/66760/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L71550 = L.marker([13.912, 109.151], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/71550/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L72427 = L.marker([18.683, 105.383], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/72427/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L72442 = L.marker([18.381, 105.611], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/72442/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L71519 = L.marker([16.116, 107.683], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/71519/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L71527 = L.marker([15.883, 108.116], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/71527/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L71529 = L.marker([15.711, 108.051], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/71529/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L71539 = L.marker([15.031, 108.571], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/71539/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L71558 = L.marker([13.033, 108.983], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/71558/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L71567 = L.marker([12.283, 108.933], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/71567/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L69702 = L.marker([14.333, 108.016], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/69702/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L69718 = L.marker([12.511, 108.181], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/69718/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var L73403 = L.marker([20.211, 105.481], { icon: stationIcon }).addTo(mapHydro).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/73403/maphydroinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });

    var C48X03 = L.marker([22.378713, 103.317193], { icon: IconL_15 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/64/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48811 = L.marker([21.799802, 103.108536], { icon: IconL_29 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/38/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48806 = L.marker([21.090987, 103.733683], { icon: IconL_19 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/45/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48818 = L.marker([20.677864, 105.311966], { icon: IconL_15 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/2/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48803 = L.marker([22.337502, 104.145408], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/37/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48815 = L.marker([21.671871, 104.459475], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/53/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48805 = L.marker([22.802791, 104.972614], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/36/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48812 = L.marker([21.77761, 105.227126], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/50/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48810 = L.marker([22.142724, 105.831043], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/52/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48831 = L.marker([21.566989, 105.825375], { icon: IconL_19 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/51/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48813 = L.marker([21.422161, 105.22824], { icon: IconL_19 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/43/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48814 = L.marker([21.307454, 105.615058], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/44/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48808 = L.marker([22.666514, 106.262273], { icon: IconL_29 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/49/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48830 = L.marker([21.85406, 106.757584], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/48/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48833 = L.marker([20.998459, 106.999754], { icon: IconL_19 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/63/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48809 = L.marker([21.280006, 106.193419], { icon: IconL_19 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/46/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48X54 = L.marker([21.176596, 106.061735], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/47/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48826 = L.marker([20.844566, 106.685528], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/54/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48825 = L.marker([21.027465, 105.831042], { icon: IconL_19 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/28/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48827 = L.marker([20.934254, 106.308977], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/19/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48822 = L.marker([20.851765, 106.018288], { icon: IconL_19 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/33/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48823 = L.marker([20.438827, 106.156085], { icon: IconL_19 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/34/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48821 = L.marker([20.534477, 105.916751], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/20/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48824 = L.marker([20.251073, 105.970303], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/17/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48835 = L.marker([20.449398, 106.329545], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/18/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48840 = L.marker([19.810627, 105.780068], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/61/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48845 = L.marker([18.674759, 105.674316], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/3/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48846 = L.marker([18.355381, 105.884492], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/4/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48848 = L.marker([17.463706, 106.583753], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/5/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48849 = L.marker([16.794008, 106.955267], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/6/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48852 = L.marker([16.46326, 107.590678], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/7/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48855 = L.marker([16.054423, 108.201385], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/55/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48X93 = L.marker([15.552682, 108.024074], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/62/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48863 = L.marker([15.078989, 108.715698], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/8/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48870 = L.marker([14.182139, 108.891859], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/56/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48873 = L.marker([13.083244, 109.092488], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/59/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48877 = L.marker([12.255838, 109.069043], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/9/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48890 = L.marker([11.666545, 108.8632], { icon: IconL_28 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/60/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48887 = L.marker([11.088907, 108.080854], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/10/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48865 = L.marker([14.651538, 107.838059], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/11/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48866 = L.marker([13.973486, 108.014581], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/12/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48875 = L.marker([12.698348, 108.236846], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/13/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48886 = L.marker([12.264993, 107.607841], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/39/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48880 = L.marker([11.940175, 108.457944], { icon: IconL_13 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/14/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48883 = L.marker([11.750925, 106.727976], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/30/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48898 = L.marker([11.349353, 106.067546], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/35/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48896 = L.marker([11.056211, 107.167138], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/32/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48899 = L.marker([11.3235, 106.477971], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/16/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48894 = L.marker([10.820708, 106.629333], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/15/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48903 = L.marker([10.411087, 107.135414], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/31/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48906 = L.marker([10.69513, 106.237904], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/21/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48912 = L.marker([10.444682, 106.335338], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/23/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48911 = L.marker([10.085536, 106.018456], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/57/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48902 = L.marker([10.106756, 106.444771], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/24/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48908 = L.marker([10.494987, 105.692229], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/22/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48904 = L.marker([9.810435, 106.294844], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/25/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48909 = L.marker([10.526024, 105.121815], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/58/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48910 = L.marker([10.044834, 105.746756], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/26/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48905 = L.marker([9.756694, 105.638185], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/40/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48913 = L.marker([9.601247, 105.95929], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/27/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48907 = L.marker([9.832498, 105.123383], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/41/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48915 = L.marker([9.255362, 105.508796], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/29/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var C48914 = L.marker([9.152301, 105.195407], { icon: IconL_8 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='450' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/42/mapinfor.html'></iframe></td></tr></table>", { maxWidth: 560 });

    var pointTBB = L.marker([21.442673, 103.101363], { icon: Icon_822 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td colspan='2' align='left' class='forecast_detail_update' style='PADDING-LEFT: 40px'></td></tr><tr><td valign='top' align='center' width='30%'><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr><td bgcolor='#ffffff' align='center' style='PADDING-TOP: 5px'><span class='forecast_detail_update_Title'><span id='_ctl1__ctl0__ctl0_lbl_ThoiTietHienTai'>Thời tiết dự báo </span><br><b>Tây Bắc Bộ</span></td></tr></table><table id='_ctl1__ctl0__ctl0_pnl_img' class='tableMap' cellpadding='0' cellspacing='0' border='0' width='50%'><tr><td><img src='https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2501.png' style='PADDING-TOP: 10px'><br><span class='forecast_detail'></span></td></tr></table></td><td valign='top' align='left' bgcolor='#ffffff'><table id='_ctl1__ctl0__ctl0_pnl_infor' cellpadding='0' cellspacing='0' border='0' width='100%'><tr><td><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr height='25px'><td colspan='2' bgcolor='#ffffff' align='right'><span class='forecast_detail_update'><span id='_ctl1__ctl0__ctl0_lbl_DuBaoThoiTietCapNhatLuc'>Cập nhật lúc:</span>4h30 ngày 28/10/2020</span></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'><td colspan='2' class='forecast_detail' align='left'>Có mây, ngày nắng, đêm có mưa rào rải rác và có nơi có dông. Gió nhẹ. Sáng sớm và đêm trời lạnh.</td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Doam'>Cao nhất</span>:</strong></span></td><td class='forecast_detail' align='left'><strong> 27-30 độ, có nơi trên 30 độ</strong></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Gio'>Thấp nhất</span>:</strong> </span></td><td class='forecast_detail' align='left'><strong>18-21 độ, có nơi dưới 18 độ</strong></td></tr></table></td></tr></table>", { maxWidth: 450 });
    var pointDBB = L.marker([22.917755, 105.265670], { icon: Icon_822 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td colspan='2' align='left' class='forecast_detail_update' style='PADDING-LEFT: 40px'></td></tr><tr><td valign='top' align='center' width='30%'><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr><td bgcolor='#ffffff' align='center' style='PADDING-TOP: 5px'><span class='forecast_detail_update_Title'><span id='_ctl1__ctl0__ctl0_lbl_ThoiTietHienTai'>Thời tiết dự báo </span><br><b>Đông Bắc Bộ</span></td></tr></table><table id='_ctl1__ctl0__ctl0_pnl_img' class='tableMap' cellpadding='0' cellspacing='0' border='0' width='50%'><tr><td><img src='https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2501.png' style='PADDING-TOP: 10px'><br><span class='forecast_detail'></span></td></tr></table></td><td valign='top' align='left' bgcolor='#ffffff'><table id='_ctl1__ctl0__ctl0_pnl_infor' cellpadding='0' cellspacing='0' border='0' width='100%'><tr><td><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr height='25px'><td colspan='2' bgcolor='#ffffff' align='right'><span class='forecast_detail_update'><span id='_ctl1__ctl0__ctl0_lbl_DuBaoThoiTietCapNhatLuc'>Cập nhật lúc:</span>4h30 ngày 28/10/2020</span></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'> <td colspan='2' class='forecast_detail' align='left'>Có mây, ngày nắng, chiều tối và đêm có mưa rào rải rác và có nơi có dông. Gió đông bắc cấp 3, vùng ven biển cấp 4-5. Đêm và sáng sớm trời lạnh. </td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Doam'>Cao nhất</span>:</strong></span></td><td class='forecast_detail' align='left'><strong>27-30 độ, có nơi trên 30 độ</strong></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Gio'>Thấp nhất</span>:</strong> </span></td><td class='forecast_detail' align='left'><strong>20-23 độ, vùng núi có nơi dưới 19 độ</strong></td></tr></table></td></tr></table>", { maxWidth: 450 });
    var pointTH2TTH = L.marker([18.692909, 105.672164], { icon: Icon_843 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td colspan='2' align='left' class='forecast_detail_update' style='PADDING-LEFT: 40px'></td></tr><tr><td valign='top' align='center' width='30%'><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr><td bgcolor='#ffffff' align='center' style='PADDING-TOP: 5px'><span class='forecast_detail_update_Title'><span id='_ctl1__ctl0__ctl0_lbl_ThoiTietHienTai'>Thời tiết dự báo </span><br><b>Thanh Hóa - Thừa Thiên Huế</span></td></tr></table><table id='_ctl1__ctl0__ctl0_pnl_img' class='tableMap' cellpadding='0' cellspacing='0' border='0' width='50%'><tr><td><img src='https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4601.png' style='PADDING-TOP: 10px'><br><span class='forecast_detail'></span></td></tr></table></td><td valign='top' align='left' bgcolor='#ffffff'><table id='_ctl1__ctl0__ctl0_pnl_infor' cellpadding='0' cellspacing='0' border='0' width='100%'><tr><td><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr height='25px'><td colspan='2' bgcolor='#ffffff' align='right'><span class='forecast_detail_update'><span id='_ctl1__ctl0__ctl0_lbl_DuBaoThoiTietCapNhatLuc'>Cập nhật lúc:</span>4h30 ngày 28/10/2020</span></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'> <td colspan='2' class='forecast_detail' align='left'>Nhiều mây, có mưa to đến rất to. Gió bắc đến tây bắc cấp 3, ven biển cấp 4-5; riêng Quảng Bình, Quảng Trị gió mạnh dần lên cấp 6-7, giật cấp 10;  riêng Thừa Thiên Huế gió mạnh dần lên cấp 8-10, giật cấp 12; đêm gió yếu dần. Trong mưa dông có khả năng xảy ra lốc, sét và gió giật mạnh.</td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Doam'>Cao nhất</span>:</strong></span></td><td class='forecast_detail' align='left'><strong> 23-26 độ</strong></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Gio'>Thấp nhất</span>:</strong> </span></td><td class='forecast_detail' align='left'><strong>20-23 độ</strong></td></tr></table></td></tr></table>", { maxWidth: 450 });
    var pointDN2BT = L.marker([16.055861, 108.202470], { icon: Icon_843 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td colspan='2' align='left' class='forecast_detail_update' style='PADDING-LEFT: 40px'></td></tr><tr><td valign='top' align='center' width='30%'><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr><td bgcolor='#ffffff' align='center' style='PADDING-TOP: 5px'><span class='forecast_detail_update_Title'><span id='_ctl1__ctl0__ctl0_lbl_ThoiTietHienTai'>Thời tiết dự báo </span><br><b>Đà Nẵng đến Bình Thuận</span></td></tr></table><table id='_ctl1__ctl0__ctl0_pnl_img' class='tableMap' cellpadding='0' cellspacing='0' border='0' width='50%'><tr><td><img src='https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4601.png' style='PADDING-TOP: 10px'><br><span class='forecast_detail'></span></td></tr></table></td><td valign='top' align='left' bgcolor='#ffffff'><table id='_ctl1__ctl0__ctl0_pnl_infor' cellpadding='0' cellspacing='0' border='0' width='100%'><tr><td><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr height='25px'><td colspan='2' bgcolor='#ffffff' align='right'><span class='forecast_detail_update'><span id='_ctl1__ctl0__ctl0_lbl_DuBaoThoiTietCapNhatLuc'>Cập nhật lúc:</span>4h30 ngày 28/10/2020</span></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'> <td colspan='2' class='forecast_detail' align='left'>Nhiều mây, phía Bắc (Đà Nẵng đến Phú Yên) có mưa to đến rất to; phía Nam có mưa rào và rải rác có dông, cục bộ có mưa vừa, mưa to. Gió mạnh cấp 4-5; riêng các tỉnh Đà Nẵng đến Phú Yên gió mạnh cấp 8-10, giật cấp 12; vùng ven biển Đà Nẵng đến Bình Định gió mạnh cấp 11-13, giật cấp 15; Bắc Khánh Hòa gió mạnh cấp 6-7, giật cấp 10; đêm gió yếu dần.  </td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Doam'>Cao nhất</span>:</strong></span></td><td class='forecast_detail' align='left'><strong>Phía Bắc 23-26 độ, có nơi trên 26 độ; phía Nam 26-29 độ, có nơi trên 29 độ</strong></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Gio'>Thấp nhất</span>:</strong> </span></td><td class='forecast_detail' align='left'><strong>22-25 độ</strong></td></tr></table></td></tr></table>", { maxWidth: 450 });
    var pointTAYNGUYEN = L.marker([14.120417, 108.056197], { icon: Icon_843 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td colspan='2' align='left' class='forecast_detail_update' style='PADDING-LEFT: 40px'></td></tr><tr><td valign='top' align='center' width='30%'><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr><td bgcolor='#ffffff' align='center' style='PADDING-TOP: 5px'><span class='forecast_detail_update_Title'><span id='_ctl1__ctl0__ctl0_lbl_ThoiTietHienTai'>Thời tiết dự báo </span><br><b>Tây Nguyên</span></td></tr></table><table id='_ctl1__ctl0__ctl0_pnl_img' class='tableMap' cellpadding='0' cellspacing='0' border='0' width='50%'><tr><td><img src='https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/4601.png' style='PADDING-TOP: 10px'><br><span class='forecast_detail'></span></td></tr></table></td><td valign='top' align='left' bgcolor='#ffffff'><table id='_ctl1__ctl0__ctl0_pnl_infor' cellpadding='0' cellspacing='0' border='0' width='100%'><tr><td><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr height='25px'><td colspan='2' bgcolor='#ffffff' align='right'><span class='forecast_detail_update'><span id='_ctl1__ctl0__ctl0_lbl_DuBaoThoiTietCapNhatLuc'>Cập nhật lúc:</span>4h30 ngày 28/10/2020</span></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'> <td colspan='2' class='forecast_detail' align='left'>Nhiều mây, có mưa rào và rải rác có dông, cục bộ có mưa vừa, mưa to; riêng Bắc Tây Nguyên có mưa to đến rất to. Gió tây đến tây nam cấp 3-5; riêng khu vực Kontum, Gia Lai gió mạnh dần lên cấp 7-8, giật cấp 10. Trong cơn dông có khả năng xảy ra lốc, sét và gió giật mạnh.</td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Doam'>Cao nhất</span>:</strong></span></td><td class='forecast_detail' align='left'><strong>24-27 độ</strong></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Gio'>Thấp nhất</span>:</strong> </span></td><td class='forecast_detail' align='left'><strong>19-22 độ</strong></td></tr></table></td></tr></table>", { maxWidth: 450 });
    var pointHANOI = L.marker([21.027939, 105.804000], { icon: Icon_822 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td colspan='2' align='left' class='forecast_detail_update' style='PADDING-LEFT: 40px'></td></tr><tr><td valign='top' align='center' width='30%'><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr><td bgcolor='#ffffff' align='center' style='PADDING-TOP: 5px'><span class='forecast_detail_update_Title'><span id='_ctl1__ctl0__ctl0_lbl_ThoiTietHienTai'>Thời tiết dự báo </span><br><b>Hà Nội</span></td></tr></table><table id='_ctl1__ctl0__ctl0_pnl_img' class='tableMap' cellpadding='0' cellspacing='0' border='0' width='50%'><tr><td><img src='https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2501.png' style='PADDING-TOP: 10px'><br><span class='forecast_detail'></span></td></tr></table></td><td valign='top' align='left' bgcolor='#ffffff'><table id='_ctl1__ctl0__ctl0_pnl_infor' cellpadding='0' cellspacing='0' border='0' width='100%'><tr><td><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr height='25px'><td colspan='2' bgcolor='#ffffff' align='right'><span class='forecast_detail_update'><span id='_ctl1__ctl0__ctl0_lbl_DuBaoThoiTietCapNhatLuc'>Cập nhật lúc:</span>4h30 ngày 28/10/2020</span></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'> <td colspan='2' class='forecast_detail' align='left'>Có mây, ngày nắng, chiều tối và đêm có mưa rào rải rác và có nơi có dông. Gió đông bắc cấp 3. Đêm và sáng sớm trời lạnh. </td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Doam'>Cao nhất</span>:</strong></span></td><td class='forecast_detail' align='left'><strong>27-30 độ</strong></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Gio'>Thấp nhất</span>:</strong> </span></td><td class='forecast_detail' align='left'><strong>20-23 độ</strong></td></tr></table></td></tr></table>", { maxWidth: 450 });
    var pointNAMBO = L.marker([10.087674, 105.749068], { icon: Icon_822 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td colspan='2' align='left' class='forecast_detail_update' style='PADDING-LEFT: 40px'></td></tr><tr><td valign='top' align='center' width='30%'><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr><td bgcolor='#ffffff' align='center' style='PADDING-TOP: 5px'><span class='forecast_detail_update_Title'><span id='_ctl1__ctl0__ctl0_lbl_ThoiTietHienTai'>Thời tiết dự báo </span><br><b>Nam Bộ</span></td></tr></table><table id='_ctl1__ctl0__ctl0_pnl_img' class='tableMap' cellpadding='0' cellspacing='0' border='0' width='50%'><tr><td><img src='https://thoitietvietnam.gov.vn/Upload/WeatherSymbol/icon_resized/2501.png' style='PADDING-TOP: 10px'><br><span class='forecast_detail'></span></td></tr></table></td><td valign='top' align='left' bgcolor='#ffffff'><table id='_ctl1__ctl0__ctl0_pnl_infor' cellpadding='0' cellspacing='0' border='0' width='100%'><tr><td><table border='0' cellpadding='0' cellspacing='0' width='100%' bgcolor='#f1f1f1'><tr height='25px'><td colspan='2' bgcolor='#ffffff' align='right'><span class='forecast_detail_update'><span id='_ctl1__ctl0__ctl0_lbl_DuBaoThoiTietCapNhatLuc'>Cập nhật lúc:</span>4h30 ngày 28/10/2020</span></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'> <td colspan='2' class='forecast_detail' align='left'>Nhiều mây, có mưa rào và dông rải rác, cục bộ có mưa vừa, mưa to. Gió tây nam cấp 3. Trong cơn dông có khả năng xảy ra lốc, sét và gió giật mạnh. </td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Doam'>Cao nhất</span>:</strong></span></td><td class='forecast_detail' align='left'><strong>29-32 độ, có nơi trên 32 độ</strong></td></tr><tr><td colspan='2' height='1' bgcolor='#D9DBDC'></td></tr><tr height='25px' style='Display:Yes'><td><span class='forecast_detail'><strong><span id='_ctl1__ctl0__ctl0_lblHT_Gio'>Thấp nhất</span>:</strong> </span></td><td class='forecast_detail' align='left'><strong>23-26 độ</strong></td></tr></table></td></tr></table>", { maxWidth: 450 });

    map.on('zoomend', function() {
        if (map.getZoom() >= 7) {

            IconL_8.options.iconSize = [40, 30], IconL_10.options.iconSize = [40, 30], IconL_12.options.iconSize = [40, 30], IconL_13.options.iconSize = [40, 30], IconL_14.options.iconSize = [40, 30], IconL_15.options.iconSize = [40, 30], IconL_19.options.iconSize = [40, 30], IconL_27.options.iconSize = [40, 30], IconL_216.options.iconSize = [40, 30], IconL_28.options.iconSize = [40, 30], IconL_29.options.iconSize = [40, 30], IconL_30.options.iconSize = [40, 30], IconL_197.options.iconSize = [40, 30], IconL_523.options.iconSize = [40, 30], IconL_524.options.iconSize = [40, 30], IconL_525.options.iconSize = [40, 30], IconL_526.options.iconSize = [40, 30], IconL_527.options.iconSize = [40, 30], IconL_528.options.iconSize = [40, 30], IconL_795.options.iconSize = [40, 30], IconL_796.options.iconSize = [40, 30], IconL_797.options.iconSize = [40, 30], IconL_798.options.iconSize = [40, 30], IconL_799.options.iconSize = [40, 30], IconL_800.options.iconSize = [40, 30], IconL_801.options.iconSize = [40, 30], IconL_802.options.iconSize = [40, 30], IconL_803.options.iconSize = [40, 30], IconL_804.options.iconSize = [40, 30], IconL_805.options.iconSize = [40, 30], IconL_806.options.iconSize = [40, 30], IconL_807.options.iconSize = [40, 30], IconL_808.options.iconSize = [40, 30], IconL_809.options.iconSize = [40, 30], IconL_810.options.iconSize = [40, 30], IconL_811.options.iconSize = [40, 30], IconL_812.options.iconSize = [40, 30], IconL_813.options.iconSize = [40, 30], IconL_814.options.iconSize = [40, 30], IconL_815.options.iconSize = [40, 30], IconL_816.options.iconSize = [40, 30], IconL_817.options.iconSize = [40, 30], IconL_818.options.iconSize = [40, 30], IconL_819.options.iconSize = [40, 30], IconL_820.options.iconSize = [40, 30], IconL_821.options.iconSize = [40, 30], IconL_822.options.iconSize = [40, 30], IconL_823.options.iconSize = [40, 30], IconL_824.options.iconSize = [40, 30], IconL_825.options.iconSize = [40, 30], IconL_826.options.iconSize = [40, 30], IconL_827.options.iconSize = [40, 30], IconL_831.options.iconSize = [40, 30], IconL_832.options.iconSize = [40, 30], IconL_833.options.iconSize = [40, 30], IconL_834.options.iconSize = [40, 30], IconL_835.options.iconSize = [40, 30], IconL_836.options.iconSize = [40, 30], IconL_837.options.iconSize = [40, 30], IconL_838.options.iconSize = [40, 30], IconL_839.options.iconSize = [40, 30], IconL_840.options.iconSize = [40, 30], IconL_841.options.iconSize = [40, 30], IconL_842.options.iconSize = [40, 30], IconL_843.options.iconSize = [40, 30], IconL_844.options.iconSize = [40, 30], IconL_845.options.iconSize = [40, 30], Icon_8.options.iconSize = [1, 1], Icon_10.options.iconSize = [1, 1], Icon_12.options.iconSize = [1, 1], Icon_13.options.iconSize = [1, 1], Icon_14.options.iconSize = [1, 1], Icon_15.options.iconSize = [1, 1], Icon_19.options.iconSize = [1, 1], Icon_27.options.iconSize = [1, 1], Icon_216.options.iconSize = [1, 1], Icon_28.options.iconSize = [1, 1], Icon_29.options.iconSize = [1, 1], Icon_30.options.iconSize = [1, 1], Icon_197.options.iconSize = [1, 1], Icon_523.options.iconSize = [1, 1], Icon_524.options.iconSize = [1, 1], Icon_525.options.iconSize = [1, 1], Icon_526.options.iconSize = [1, 1], Icon_527.options.iconSize = [1, 1], Icon_528.options.iconSize = [1, 1], Icon_795.options.iconSize = [1, 1], Icon_796.options.iconSize = [1, 1], Icon_797.options.iconSize = [1, 1], Icon_798.options.iconSize = [1, 1], Icon_799.options.iconSize = [1, 1], Icon_800.options.iconSize = [1, 1], Icon_801.options.iconSize = [1, 1], Icon_802.options.iconSize = [1, 1], Icon_803.options.iconSize = [1, 1], Icon_804.options.iconSize = [1, 1], Icon_805.options.iconSize = [1, 1], Icon_806.options.iconSize = [1, 1], Icon_807.options.iconSize = [1, 1], Icon_808.options.iconSize = [1, 1], Icon_809.options.iconSize = [1, 1], Icon_810.options.iconSize = [1, 1], Icon_811.options.iconSize = [1, 1], Icon_812.options.iconSize = [1, 1], Icon_813.options.iconSize = [1, 1], Icon_814.options.iconSize = [1, 1], Icon_815.options.iconSize = [1, 1], Icon_816.options.iconSize = [1, 1], Icon_817.options.iconSize = [1, 1], Icon_818.options.iconSize = [1, 1], Icon_819.options.iconSize = [1, 1], Icon_820.options.iconSize = [1, 1], Icon_821.options.iconSize = [1, 1], Icon_822.options.iconSize = [1, 1], Icon_823.options.iconSize = [1, 1], Icon_824.options.iconSize = [1, 1], Icon_825.options.iconSize = [1, 1], Icon_826.options.iconSize = [1, 1], Icon_827.options.iconSize = [1, 1], Icon_831.options.iconSize = [1, 1], Icon_832.options.iconSize = [1, 1], Icon_833.options.iconSize = [1, 1], Icon_834.options.iconSize = [1, 1], Icon_835.options.iconSize = [1, 1], Icon_836.options.iconSize = [1, 1], Icon_837.options.iconSize = [1, 1], Icon_838.options.iconSize = [1, 1], Icon_839.options.iconSize = [1, 1], Icon_840.options.iconSize = [1, 1], Icon_841.options.iconSize = [1, 1], Icon_842.options.iconSize = [1, 1], Icon_843.options.iconSize = [1, 1], Icon_844.options.iconSize = [1, 1], Icon_845.options.iconSize = [1, 1];
        }
        if (map.getZoom() < 7) {
            IconL_8.options.iconSize = [1, 1], IconL_10.options.iconSize = [1, 1], IconL_12.options.iconSize = [1, 1], IconL_13.options.iconSize = [1, 1], IconL_14.options.iconSize = [1, 1], IconL_15.options.iconSize = [1, 1], IconL_19.options.iconSize = [1, 1], IconL_27.options.iconSize = [1, 1], IconL_216.options.iconSize = [1, 1], IconL_28.options.iconSize = [1, 1], IconL_29.options.iconSize = [1, 1], IconL_30.options.iconSize = [1, 1], IconL_197.options.iconSize = [1, 1], IconL_523.options.iconSize = [1, 1], IconL_524.options.iconSize = [1, 1], IconL_525.options.iconSize = [1, 1], IconL_526.options.iconSize = [1, 1], IconL_527.options.iconSize = [1, 1], IconL_528.options.iconSize = [1, 1], IconL_795.options.iconSize = [1, 1], IconL_796.options.iconSize = [1, 1], IconL_797.options.iconSize = [1, 1], IconL_798.options.iconSize = [1, 1], IconL_799.options.iconSize = [1, 1], IconL_800.options.iconSize = [1, 1], IconL_801.options.iconSize = [1, 1], IconL_802.options.iconSize = [1, 1], IconL_803.options.iconSize = [1, 1], IconL_804.options.iconSize = [1, 1], IconL_805.options.iconSize = [1, 1], IconL_806.options.iconSize = [1, 1], IconL_807.options.iconSize = [1, 1], IconL_808.options.iconSize = [1, 1], IconL_809.options.iconSize = [1, 1], IconL_810.options.iconSize = [1, 1], IconL_811.options.iconSize = [1, 1], IconL_812.options.iconSize = [1, 1], IconL_813.options.iconSize = [1, 1], IconL_814.options.iconSize = [1, 1], IconL_815.options.iconSize = [1, 1], IconL_816.options.iconSize = [1, 1], IconL_817.options.iconSize = [1, 1], IconL_818.options.iconSize = [1, 1], IconL_819.options.iconSize = [1, 1], IconL_820.options.iconSize = [1, 1], IconL_821.options.iconSize = [1, 1], IconL_822.options.iconSize = [1, 1], IconL_823.options.iconSize = [1, 1], IconL_824.options.iconSize = [1, 1], IconL_825.options.iconSize = [1, 1], IconL_826.options.iconSize = [1, 1], IconL_827.options.iconSize = [1, 1], IconL_831.options.iconSize = [1, 1], IconL_832.options.iconSize = [1, 1], IconL_833.options.iconSize = [1, 1], IconL_834.options.iconSize = [1, 1], IconL_835.options.iconSize = [1, 1], IconL_836.options.iconSize = [1, 1], IconL_837.options.iconSize = [1, 1], IconL_838.options.iconSize = [1, 1], IconL_839.options.iconSize = [1, 1], IconL_840.options.iconSize = [1, 1], IconL_841.options.iconSize = [1, 1], IconL_842.options.iconSize = [1, 1], IconL_843.options.iconSize = [1, 1], IconL_844.options.iconSize = [1, 1], IconL_845.options.iconSize = [1, 1], Icon_8.options.iconSize = [40, 30], Icon_10.options.iconSize = [40, 30], Icon_12.options.iconSize = [40, 30], Icon_13.options.iconSize = [40, 30], Icon_14.options.iconSize = [40, 30], Icon_15.options.iconSize = [40, 30], Icon_19.options.iconSize = [40, 30], Icon_27.options.iconSize = [40, 30], Icon_216.options.iconSize = [40, 30], Icon_28.options.iconSize = [40, 30], Icon_29.options.iconSize = [40, 30], Icon_30.options.iconSize = [40, 30], Icon_197.options.iconSize = [40, 30], Icon_523.options.iconSize = [40, 30], Icon_524.options.iconSize = [40, 30], Icon_525.options.iconSize = [40, 30], Icon_526.options.iconSize = [40, 30], Icon_527.options.iconSize = [40, 30], Icon_528.options.iconSize = [40, 30], Icon_795.options.iconSize = [40, 30], Icon_796.options.iconSize = [40, 30], Icon_797.options.iconSize = [40, 30], Icon_798.options.iconSize = [40, 30], Icon_799.options.iconSize = [40, 30], Icon_800.options.iconSize = [40, 30], Icon_801.options.iconSize = [40, 30], Icon_802.options.iconSize = [40, 30], Icon_803.options.iconSize = [40, 30], Icon_804.options.iconSize = [40, 30], Icon_805.options.iconSize = [40, 30], Icon_806.options.iconSize = [40, 30], Icon_807.options.iconSize = [40, 30], Icon_808.options.iconSize = [40, 30], Icon_809.options.iconSize = [40, 30], Icon_810.options.iconSize = [40, 30], Icon_811.options.iconSize = [40, 30], Icon_812.options.iconSize = [40, 30], Icon_813.options.iconSize = [40, 30], Icon_814.options.iconSize = [40, 30], Icon_815.options.iconSize = [40, 30], Icon_816.options.iconSize = [40, 30], Icon_817.options.iconSize = [40, 30], Icon_818.options.iconSize = [40, 30], Icon_819.options.iconSize = [40, 30], Icon_820.options.iconSize = [40, 30], Icon_821.options.iconSize = [40, 30], Icon_822.options.iconSize = [40, 30], Icon_823.options.iconSize = [40, 30], Icon_824.options.iconSize = [40, 30], Icon_825.options.iconSize = [40, 30], Icon_826.options.iconSize = [40, 30], Icon_827.options.iconSize = [40, 30], Icon_831.options.iconSize = [40, 30], Icon_832.options.iconSize = [40, 30], Icon_833.options.iconSize = [40, 30], Icon_834.options.iconSize = [40, 30], Icon_835.options.iconSize = [40, 30], Icon_836.options.iconSize = [40, 30], Icon_837.options.iconSize = [40, 30], Icon_838.options.iconSize = [40, 30], Icon_839.options.iconSize = [40, 30], Icon_840.options.iconSize = [40, 30], Icon_841.options.iconSize = [40, 30], Icon_842.options.iconSize = [40, 30], Icon_843.options.iconSize = [40, 30], Icon_844.options.iconSize = [40, 30], Icon_845.options.iconSize = [40, 30];
        }
        pointTBB.setIcon(Icon_822);
        pointDBB.setIcon(Icon_822);
        pointTH2TTH.setIcon(Icon_843);
        pointDN2BT.setIcon(Icon_843);
        pointTAYNGUYEN.setIcon(Icon_843);
        pointHANOI.setIcon(Icon_822);
        pointNAMBO.setIcon(Icon_822);
        C48X03.setIcon(IconL_15);
        C48811.setIcon(IconL_29);
        C48806.setIcon(IconL_19);
        C48818.setIcon(IconL_15);
        C48803.setIcon(IconL_8);
        C48815.setIcon(IconL_8);
        C48805.setIcon(IconL_8);
        C48812.setIcon(IconL_8);
        C48810.setIcon(IconL_8);
        C48831.setIcon(IconL_19);
        C48813.setIcon(IconL_19);
        C48814.setIcon(IconL_8);
        C48808.setIcon(IconL_29);
        C48830.setIcon(IconL_8);
        C48833.setIcon(IconL_19);
        C48809.setIcon(IconL_19);
        C48X54.setIcon(IconL_8);
        C48826.setIcon(IconL_8);
        C48825.setIcon(IconL_19);
        C48827.setIcon(IconL_8);
        C48822.setIcon(IconL_19);
        C48823.setIcon(IconL_19);
        C48821.setIcon(IconL_8);
        C48824.setIcon(IconL_8);
        C48835.setIcon(IconL_8);
        C48840.setIcon(IconL_8);
        C48845.setIcon(IconL_8);
        C48846.setIcon(IconL_8);
        C48848.setIcon(IconL_13);
        C48849.setIcon(IconL_13);
        C48852.setIcon(IconL_13);
        C48855.setIcon(IconL_13);
        C48X93.setIcon(IconL_13);
        C48863.setIcon(IconL_13);
        C48870.setIcon(IconL_13);
        C48873.setIcon(IconL_13);
        C48877.setIcon(IconL_13);
        C48890.setIcon(IconL_28);
        C48887.setIcon(IconL_8);
        C48865.setIcon(IconL_13);
        C48866.setIcon(IconL_13);
        C48875.setIcon(IconL_13);
        C48886.setIcon(IconL_13);
        C48880.setIcon(IconL_13);
        C48883.setIcon(IconL_8);
        C48898.setIcon(IconL_8);
        C48896.setIcon(IconL_8);
        C48899.setIcon(IconL_8);
        C48894.setIcon(IconL_8);
        C48903.setIcon(IconL_8);
        C48906.setIcon(IconL_8);
        C48912.setIcon(IconL_8);
        C48911.setIcon(IconL_8);
        C48902.setIcon(IconL_8);
        C48908.setIcon(IconL_8);
        C48904.setIcon(IconL_8);
        C48909.setIcon(IconL_8);
        C48910.setIcon(IconL_8);
        C48905.setIcon(IconL_8);
        C48913.setIcon(IconL_8);
        C48907.setIcon(IconL_8);
        C48915.setIcon(IconL_8);
        C48914.setIcon(IconL_8);


    });


    L.circle([13.1, 129.7], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208625/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_0 = new L.LatLng(13.1, 129.7);

    L.circle([13.3, 128.7], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208626/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_1 = new L.LatLng(13.3, 128.7);

    L.circle([13.4, 127.8], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208627/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_2 = new L.LatLng(13.4, 127.8);

    L.circle([13.5, 126.5], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208628/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_3 = new L.LatLng(13.5, 126.5);

    L.circle([13.5, 124.8], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208629/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_4 = new L.LatLng(13.5, 124.8);

    L.circle([13.5, 123.2], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208630/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_5 = new L.LatLng(13.5, 123.2);

    L.circle([13.5, 122.2], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208631/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_6 = new L.LatLng(13.5, 122.2);

    L.circle([13.3, 120.3], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208632/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_7 = new L.LatLng(13.3, 120.3);

    L.circle([13.3, 119.6], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208633/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_8 = new L.LatLng(13.3, 119.6);

    L.circle([13.5, 118.8], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208634/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_9 = new L.LatLng(13.5, 118.8);

    L.circle([13.5, 118.5], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208635/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_10 = new L.LatLng(13.5, 118.5);

    L.circle([13.6, 117.5], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208636/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_11 = new L.LatLng(13.6, 117.5);

    L.circle([13.7, 116.7], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208637/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_12 = new L.LatLng(13.7, 116.7);

    L.circle([13.7, 116], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208638/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_13 = new L.LatLng(13.7, 116);

    L.circle([13.7, 115.5], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208639/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_14 = new L.LatLng(13.7, 115.5);

    L.circle([13.5, 114.8], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208640/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_15 = new L.LatLng(13.5, 114.8);

    L.circle([13.4, 113.8], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208641/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_16 = new L.LatLng(13.4, 113.8);

    L.circle([13.5, 113.3], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208642/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_17 = new L.LatLng(13.5, 113.3);

    L.circle([13.6, 112.8], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208643/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_18 = new L.LatLng(13.6, 112.8);

    L.circle([13.7, 112.1], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208644/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_19 = new L.LatLng(13.7, 112.1);

    L.circle([13.8, 111.8], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208645/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_20 = new L.LatLng(13.8, 111.8);

    L.circle([14.1, 111.1], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208646/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_21 = new L.LatLng(14.1, 111.1);

    L.circle([14.4, 110.5], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208647/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_22 = new L.LatLng(14.4, 110.5);

    L.circle([14.8, 109.8], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208648/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_23 = new L.LatLng(14.8, 109.8);

    L.circle([14.8, 109.8], 7000, { color: 'black', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208649/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });
    var point_30_24 = new L.LatLng(14.8, 109.8);

    var pointList_30_0 = [point_30_0, point_30_1];

    var firstpolyline_30_0 = new L.Polyline(pointList_30_0, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_0.addTo(map);
    var pointList_30_1 = [point_30_1, point_30_2];

    var firstpolyline_30_1 = new L.Polyline(pointList_30_1, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_1.addTo(map);
    var pointList_30_2 = [point_30_2, point_30_3];

    var firstpolyline_30_2 = new L.Polyline(pointList_30_2, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_2.addTo(map);
    var pointList_30_3 = [point_30_3, point_30_4];

    var firstpolyline_30_3 = new L.Polyline(pointList_30_3, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_3.addTo(map);
    var pointList_30_4 = [point_30_4, point_30_5];

    var firstpolyline_30_4 = new L.Polyline(pointList_30_4, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_4.addTo(map);
    var pointList_30_5 = [point_30_5, point_30_6];

    var firstpolyline_30_5 = new L.Polyline(pointList_30_5, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_5.addTo(map);
    var pointList_30_6 = [point_30_6, point_30_7];

    var firstpolyline_30_6 = new L.Polyline(pointList_30_6, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_6.addTo(map);
    var pointList_30_7 = [point_30_7, point_30_8];

    var firstpolyline_30_7 = new L.Polyline(pointList_30_7, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_7.addTo(map);
    var pointList_30_8 = [point_30_8, point_30_9];

    var firstpolyline_30_8 = new L.Polyline(pointList_30_8, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_8.addTo(map);
    var pointList_30_9 = [point_30_9, point_30_10];

    var firstpolyline_30_9 = new L.Polyline(pointList_30_9, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_9.addTo(map);
    var pointList_30_10 = [point_30_10, point_30_11];

    var firstpolyline_30_10 = new L.Polyline(pointList_30_10, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_10.addTo(map);
    var pointList_30_11 = [point_30_11, point_30_12];

    var firstpolyline_30_11 = new L.Polyline(pointList_30_11, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_11.addTo(map);
    var pointList_30_12 = [point_30_12, point_30_13];

    var firstpolyline_30_12 = new L.Polyline(pointList_30_12, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_12.addTo(map);
    var pointList_30_13 = [point_30_13, point_30_14];

    var firstpolyline_30_13 = new L.Polyline(pointList_30_13, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_13.addTo(map);
    var pointList_30_14 = [point_30_14, point_30_15];

    var firstpolyline_30_14 = new L.Polyline(pointList_30_14, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_14.addTo(map);
    var pointList_30_15 = [point_30_15, point_30_16];

    var firstpolyline_30_15 = new L.Polyline(pointList_30_15, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_15.addTo(map);
    var pointList_30_16 = [point_30_16, point_30_17];

    var firstpolyline_30_16 = new L.Polyline(pointList_30_16, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_16.addTo(map);
    var pointList_30_17 = [point_30_17, point_30_18];

    var firstpolyline_30_17 = new L.Polyline(pointList_30_17, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_17.addTo(map);
    var pointList_30_18 = [point_30_18, point_30_19];

    var firstpolyline_30_18 = new L.Polyline(pointList_30_18, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_18.addTo(map);
    var pointList_30_19 = [point_30_19, point_30_20];

    var firstpolyline_30_19 = new L.Polyline(pointList_30_19, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_19.addTo(map);
    var pointList_30_20 = [point_30_20, point_30_21];

    var firstpolyline_30_20 = new L.Polyline(pointList_30_20, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_20.addTo(map);
    var pointList_30_21 = [point_30_21, point_30_22];

    var firstpolyline_30_21 = new L.Polyline(pointList_30_21, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_21.addTo(map);
    var pointList_30_22 = [point_30_22, point_30_23];

    var firstpolyline_30_22 = new L.Polyline(pointList_30_22, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_22.addTo(map);
    var pointList_30_23 = [point_30_23, point_30_24];

    var firstpolyline_30_23 = new L.Polyline(pointList_30_23, { color: 'black', weight: 2, opacity: 0.5, smoothFactor: 2 });
    firstpolyline_30_23.addTo(map);

    L.circle([14.8, 109.8], 50000, { color: '#FF0000', fillOpacity: 0.5 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208650/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });

    L.circle([14.8, 109.8], 250000, { color: '#FFFF00', fillColor: '#F9CC76', fillOpacity: 0.5 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208650/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });

    var point_30_0 = new L.LatLng(14.8, 109.8);

    L.circle([15, 107.2], 7000, { color: '#FF0000', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208651/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });

    L.circle([15, 107.2], 80000, { color: 'white', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208651/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });

    var point_30_1 = new L.LatLng(15, 107.2);

    L.circle([15.2, 104.8], 7000, { color: '#FF0000', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208652/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });

    L.circle([15.2, 104.8], 120000, { color: 'white', fillOpacity: 0 }).addTo(map).bindPopup("<table width='100%' border='0' cellspacing='1'><tr><td><iframe width='450' height='250' frameborder='0' src='https://thoitietvietnam.gov.vn/Kttv/vi-VN/208652/storminfor.html'></iframe></td></tr></table>", { maxWidth: 560 });

    var point_30_2 = new L.LatLng(15.2, 104.8);
    var pointList_30_0 = [point_30_0, point_30_1];
    var firstpolyline_30_0 = new L.Polyline(pointList_30_0, { color: 'white', weight: 1, opacity: 1.5, smoothFactor: 1 });
    firstpolyline_30_0.addTo(map);
    var pointList_30_1 = [point_30_1, point_30_2];
    var firstpolyline_30_1 = new L.Polyline(pointList_30_1, { color: 'white', weight: 1, opacity: 1.5, smoothFactor: 1 });
    firstpolyline_30_1.addTo(map);



    var data = [{ "loc": [22.378713, 103.317193], "title": "Lai Châu  " }, { "loc": [21.799802, 103.108536], "title": "Điên Biên" }, { "loc": [21.090987, 103.733683], "title": "Sơn La  " }, { "loc": [20.677864, 105.311966], "title": "Hòa Bình  " }, { "loc": [22.337502, 104.145408], "title": "Lào Cai  " }, { "loc": [21.671871, 104.459475], "title": "Yên Bái  " }, { "loc": [22.802791, 104.972614], "title": "Hà Giang  " }, { "loc": [21.77761, 105.227126], "title": "Tuyên Quang  " }, { "loc": [22.142724, 105.831043], "title": "Bắc cạn  " }, { "loc": [21.566989, 105.825375], "title": "Thái Nguyên  " }, { "loc": [21.422161, 105.22824], "title": "Phú Thọ  " }, { "loc": [21.307454, 105.615058], "title": "Vĩnh Phúc  " }, { "loc": [22.666514, 106.262273], "title": "Cao Bằng  " }, { "loc": [21.85406, 106.757584], "title": "Lạng Sơn  " }, { "loc": [20.998459, 106.999754], "title": "Quảng Ninh  " }, { "loc": [21.280006, 106.193419], "title": "Bắc Giang  " }, { "loc": [21.176596, 106.061735], "title": "Bắc Ninh  " }, { "loc": [20.844566, 106.685528], "title": "Hải Phòng  " }, { "loc": [21.027465, 105.831042], "title": "TP. Hà Nội  " }, { "loc": [20.934254, 106.308977], "title": "Hải Dương  " }, { "loc": [20.851765, 106.018288], "title": "Hưng Yên  " }, { "loc": [20.438827, 106.156085], "title": "Nam Định  " }, { "loc": [20.534477, 105.916751], "title": "Phủ Lý  " }, { "loc": [20.251073, 105.970303], "title": "Ninh Bình  " }, { "loc": [20.449398, 106.329545], "title": "Thái Bình  " }, { "loc": [19.810627, 105.780068], "title": "Thanh Hóa  " }, { "loc": [18.674759, 105.674316], "title": "Nghệ An" }, { "loc": [18.355381, 105.884492], "title": "Hà Tĩnh" }, { "loc": [17.463706, 106.583753], "title": "Quảng Bình  " }, { "loc": [16.794008, 106.955267], "title": "Quảng Trị  " }, { "loc": [16.46326, 107.590678], "title": "Huế  " }, { "loc": [16.054423, 108.201385], "title": "Đà nẵng  " }, { "loc": [15.552682, 108.024074], "title": "Quảng Nam  " }, { "loc": [15.078989, 108.715698], "title": "Quảng Ngãi  " }, { "loc": [14.182139, 108.891859], "title": "Bình Định  " }, { "loc": [13.083244, 109.092488], "title": "Phú Yên  " }, { "loc": [12.255838, 109.069043], "title": "Khánh Hòa  " }, { "loc": [11.666545, 108.8632], "title": "Ninh Thuận  " }, { "loc": [14.651538, 107.838059], "title": "Kon Tum  " }, { "loc": [13.973486, 108.014581], "title": "Pleiku  " }, { "loc": [12.698348, 108.236846], "title": "Dak Lak  " }, { "loc": [12.264993, 107.607841], "title": "Đắc Nông  " }, { "loc": [11.940175, 108.457944], "title": "Đà Lạt  " }, { "loc": [11.750925, 106.727976], "title": "Bình Phước  " }, { "loc": [11.349353, 106.067546], "title": "Tây Ninh  " }, { "loc": [11.056211, 107.167138], "title": "Đồng Nai  " }, { "loc": [10.820708, 106.629333], "title": "TP. Hồ Chí Minh  " }, { "loc": [10.411087, 107.135414], "title": "Vũng Tàu  " }, { "loc": [10.69513, 106.237904], "title": "Long An  " }, { "loc": [10.444682, 106.335338], "title": "Tiền Giang  " }, { "loc": [10.085536, 106.018456], "title": "Vĩnh Long  " }, { "loc": [10.106756, 106.444771], "title": "Bến tre  " }, { "loc": [10.494987, 105.692229], "title": "Đồng Tháp  " }, { "loc": [9.810435, 106.294844], "title": "Trà Vinh  " }, { "loc": [10.526024, 105.121815], "title": "An Giang  " }, { "loc": [10.044834, 105.746756], "title": "Cần Thơ  " }, { "loc": [9.756694, 105.638185], "title": "Hậu Giang  " }, { "loc": [9.601247, 105.95929], "title": "Sóc Trăng  " }, { "loc": [9.832498, 105.123383], "title": "Kiên Giang  " }, { "loc": [9.255362, 105.508796], "title": "Bạc Liêu" }, { "loc": [9.152301, 105.195407], "title": "Cà Mau  " }, ];

    function localData(text, callResponse) {
        //here can use custom criteria or merge data from multiple layer
        callResponse(data);
        return { //called to stop previous requests on map move
            abort: function() {
                console.log('aborted request:' + text);
            }
        };
    }

    map.addControl(new L.Control.Search({
        sourceData: localData,
        markerLocation: true,
        zoom: 9
    }));


    $(document).ready(function() {
        $('.tab1').css('right', '0');
        $('.tab').css('min-height', $('.tab1').innerHeight() + $('.header-container').innerHeight());
        $('.tab-header').click(function() {
            $('.tab-content').css('right', '100vw');
            $('.tab-header').removeClass('selected');
            $(this).addClass('selected');
            $($(this).attr('data-target')).css('right', '0');
            $('.tab').css('min-height', $($(this).attr('data-target')).innerHeight() + $('.header-container').innerHeight());
        });
    });
</script>
<script src="https://code.highcharts.com/highcharts.js"></script>
<script src="https://code.highcharts.com/modules/exporting.js"></script>
<script>
window.onload = function() {


    Highcharts.chart('chartContainer1', {
        chart: {
            zoomType: 'xy'
        },
        title: {
            text: null
        },
        credits: {
            enabled: false
        },

        xAxis: [{
            categories: ['1', '2', '3', '4', '5', '6',
                '7', '8', '9', '10', '11', '12'
            ],
            crosshair: true
        }],
        yAxis: [{ // Primary yAxis
            labels: {
                format: '{value}°C',
                style: {
                    color: '#FF9C2A'
                }
            },
            title: {
                text: 'Nhiệt độ',
                style: {
                    color: '#FF9C2A'
                }
            }
        }, { // Secondary yAxis
            title: {
                text: 'Lượng mưa',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            labels: {
                format: '{value} mm',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            opposite: true
        }],
        tooltip: {
            shared: true
        },
        legend: {
            layout: 'vertical',
            align: 'left',
            x: 120,
            verticalAlign: 'top',
            y: 100,
            floating: true,
            backgroundColor: Highcharts.defaultOptions.legend.backgroundColor || // theme
                'rgba(255,255,255,0.25)'
        },
        series: [{
            name: 'Lượng mưa',
            type: 'column',
            yAxis: 1,
            data: [21.6, 26.7, 53.4, 87, 197.1, 263.5, 263.5, 288.3, 190.9, 135.5, 78.2, 18.4],
            tooltip: {
                valueSuffix: ' mm'
            }

        }, {
            name: 'Nhiệt độ',
            type: 'spline',
            data: [16.9, 18, 20.4, 24.3, 27.5, 29.5, 29.5, 28.9, 28, 25.5, 22.1, 18.5],
            tooltip: {
                valueSuffix: '°C'
            },
            color: '#FF9C2A'
        }]
    });

    Highcharts.chart('chartContainerSL', {
        chart: {
            zoomType: 'xy'
        },
        title: {
            text: null
        },
        credits: {
            enabled: false
        },

        xAxis: [{
            categories: ['1', '2', '3', '4', '5', '6',
                '7', '8', '9', '10', '11', '12'
            ],
            crosshair: true
        }],
        yAxis: [{ // Primary yAxis
            labels: {
                format: '{value}°C',
                style: {
                    color: '#FF9C2A'
                }
            },
            title: {
                text: 'Nhiệt độ',
                style: {
                    color: '#FF9C2A'
                }
            }
        }, { // Secondary yAxis
            title: {
                text: 'Lượng mưa',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            labels: {
                format: '{value} mm',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            opposite: true
        }],
        tooltip: {
            shared: true
        },
        legend: {
            layout: 'vertical',
            align: 'left',
            x: 120,
            verticalAlign: 'top',
            y: 100,
            floating: true,
            backgroundColor: Highcharts.defaultOptions.legend.backgroundColor || // theme
                'rgba(255,255,255,0.25)'
        },
        series: [{
            name: 'Lượng mưa',
            type: 'column',
            yAxis: 1,
            data: [19.1, 25, 53.4, 112.6, 202.6, 224.8, 224.8, 238.9, 130, 60.2, 39.3, 16.3],
            tooltip: {
                valueSuffix: ' mm'
            }

        }, {
            name: 'Nhiệt độ',
            type: 'spline',
            data: [15.3, 17.4, 20.5, 23.5, 25, 25.4, 25.4, 25, 24, 21.9, 18.6, 15.5],
            tooltip: {
                valueSuffix: '°C'
            },
            color: '#FF9C2A'
        }]
    });




    Highcharts.chart('chartContainerTN', {
        chart: {
            zoomType: 'xy'
        },
        title: {
            text: null
        },
        credits: {
            enabled: false
        },

        xAxis: [{
            categories: ['1', '2', '3', '4', '5', '6',
                '7', '8', '9', '10', '11', '12'
            ],
            crosshair: true
        }],
        yAxis: [{ // Primary yAxis
            labels: {
                format: '{value}°C',
                style: {
                    color: '#FF9C2A'
                }
            },
            title: {
                text: 'Nhiệt độ',
                style: {
                    color: '#FF9C2A'
                }
            }
        }, { // Secondary yAxis
            title: {
                text: 'Lượng mưa',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            labels: {
                format: '{value} mm',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            opposite: true
        }],
        tooltip: {
            shared: true
        },
        legend: {
            layout: 'vertical',
            align: 'left',
            x: 120,
            verticalAlign: 'top',
            y: 100,
            floating: true,
            backgroundColor: Highcharts.defaultOptions.legend.backgroundColor || // theme
                'rgba(255,255,255,0.25)'
        },
        series: [{
            name: 'Lượng mưa',
            type: 'column',
            yAxis: 1,
            data: [24.5, 32.8, 70.2, 103.6, 246.9, 276.7, 276.7, 284.4, 200.9, 118, 57.6, 22.4],
            tooltip: {
                valueSuffix: ' mm'
            }

        }, {
            name: 'Nhiệt độ',
            type: 'spline',
            data: [16.3, 17.6, 20, 23.9, 27, 28.7, 28.7, 28.3, 27.3, 24.9, 21.3, 17.7],
            tooltip: {
                valueSuffix: '°C'
            },
            color: '#FF9C2A'
        }]
    });

    Highcharts.chart('chartContainerPL', {
        chart: {
            zoomType: 'xy'
        },
        title: {
            text: null
        },
        credits: {
            enabled: false
        },

        xAxis: [{
            categories: ['1', '2', '3', '4', '5', '6',
                '7', '8', '9', '10', '11', '12'
            ],
            crosshair: true
        }],
        yAxis: [{ // Primary yAxis
            labels: {
                format: '{value}°C',
                style: {
                    color: '#FF9C2A'
                }
            },
            title: {
                text: 'Nhiệt độ',
                style: {
                    color: '#FF9C2A'
                }
            }
        }, { // Secondary yAxis
            title: {
                text: 'Lượng mưa',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            labels: {
                format: '{value} mm',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            opposite: true
        }],
        tooltip: {
            shared: true
        },
        legend: {
            layout: 'vertical',
            align: 'left',
            x: 120,
            verticalAlign: 'top',
            y: 100,
            floating: true,
            backgroundColor: Highcharts.defaultOptions.legend.backgroundColor || // theme
                'rgba(255,255,255,0.25)'
        },
        series: [{
            name: 'Lượng mưa',
            type: 'column',
            yAxis: 1,
            data: [35, 27.5, 54.4, 71.3, 206.7, 222, 222, 329.1, 224.7, 128.2, 46.2, 21.3],
            tooltip: {
                valueSuffix: ' mm'
            }

        }, {
            name: 'Nhiệt độ',
            type: 'spline',
            data: [16.5, 17.3, 19.4, 23.2, 26.4, 28.3, 28.3, 27.9, 27, 24.8, 21.6, 18.2],
            tooltip: {
                valueSuffix: '°C'
            },
            color: '#FF9C2A'
        }]
    });


    Highcharts.chart('chartContainerVinh', {
        chart: {
            zoomType: 'xy'
        },
        title: {
            text: null
        },
        credits: {
            enabled: false
        },

        xAxis: [{
            categories: ['1', '2', '3', '4', '5', '6',
                '7', '8', '9', '10', '11', '12'
            ],
            crosshair: true
        }],
        yAxis: [{ // Primary yAxis
            labels: {
                format: '{value}°C',
                style: {
                    color: '#FF9C2A'
                }
            },
            title: {
                text: 'Nhiệt độ',
                style: {
                    color: '#FF9C2A'
                }
            }
        }, { // Secondary yAxis
            title: {
                text: 'Lượng mưa',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            labels: {
                format: '{value} mm',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            opposite: true
        }],
        tooltip: {
            shared: true
        },
        legend: {
            layout: 'vertical',
            align: 'left',
            x: 120,
            verticalAlign: 'top',
            y: 100,
            floating: true,
            backgroundColor: Highcharts.defaultOptions.legend.backgroundColor || // theme
                'rgba(255,255,255,0.25)'
        },
        series: [{
            name: 'Lượng mưa',
            type: 'column',
            yAxis: 1,
            data: [61.9, 38.2, 48.9, 61.7, 157.1, 96.8, 96.8, 263.5, 394.4, 614.4, 148.3, 66.1],
            tooltip: {
                valueSuffix: ' mm'
            }

        }, {
            name: 'Nhiệt độ',
            type: 'spline',
            data: [17.8, 18.6, 20.7, 24.5, 27.9, 30.1, 30.1, 28.9, 27.2, 24.8, 21.9, 18.8],
            tooltip: {
                valueSuffix: '°C'
            },
            color: '#FF9C2A'
        }]
    });






    Highcharts.chart('chartContainerNT', {
        chart: {
            zoomType: 'xy'
        },
        title: {
            text: null
        },
        credits: {
            enabled: false
        },

        xAxis: [{
            categories: ['1', '2', '3', '4', '5', '6',
                '7', '8', '9', '10', '11', '12'
            ],
            crosshair: true
        }],
        yAxis: [{ // Primary yAxis
            labels: {
                format: '{value}°C',
                style: {
                    color: '#FF9C2A'
                }
            },
            title: {
                text: 'Nhiệt độ',
                style: {
                    color: '#FF9C2A'
                }
            }
        }, { // Secondary yAxis
            title: {
                text: 'Lượng mưa',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            labels: {
                format: '{value} mm',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            opposite: true
        }],
        tooltip: {
            shared: true
        },
        legend: {
            layout: 'vertical',
            align: 'left',
            x: 120,
            verticalAlign: 'top',
            y: 100,
            floating: true,
            backgroundColor: Highcharts.defaultOptions.legend.backgroundColor || // theme
                'rgba(255,255,255,0.25)'
        },
        series: [{
            name: 'Lượng mưa',
            type: 'column',
            yAxis: 1,
            data: [40.2, 12.1, 42.4, 39.1, 75.8, 50.7, 50.7, 58.2, 185.5, 351.3, 379.4, 166.6],
            tooltip: {
                valueSuffix: ' mm'
            }

        }, {
            name: 'Nhiệt độ',
            type: 'spline',
            data: [24, 24.6, 25.9, 27.5, 28.5, 28.8, 28.8, 28.5, 27.8, 26.7, 25.7, 24.5],
            tooltip: {
                valueSuffix: '°C'
            },
            color: '#FF9C2A'
        }]
    });




    Highcharts.chart('chartContainerPK', {
        chart: {
            zoomType: 'xy'
        },
        title: {
            text: null
        },
        credits: {
            enabled: false
        },

        xAxis: [{
            categories: ['1', '2', '3', '4', '5', '6',
                '7', '8', '9', '10', '11', '12'
            ],
            crosshair: true
        }],
        yAxis: [{ // Primary yAxis
            labels: {
                format: '{value}°C',
                style: {
                    color: '#FF9C2A'
                }
            },
            title: {
                text: 'Nhiệt độ',
                style: {
                    color: '#FF9C2A'
                }
            }
        }, { // Secondary yAxis
            title: {
                text: 'Lượng mưa',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            labels: {
                format: '{value} mm',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            opposite: true
        }],
        tooltip: {
            shared: true
        },
        legend: {
            layout: 'vertical',
            align: 'left',
            x: 120,
            verticalAlign: 'top',
            y: 100,
            floating: true,
            backgroundColor: Highcharts.defaultOptions.legend.backgroundColor || // theme
                'rgba(255,255,255,0.25)'
        },
        series: [{
            name: 'Lượng mưa',
            type: 'column',
            yAxis: 1,
            data: [1.9, 6.3, 31.7, 91.5, 223.5, 327.1, 327.1, 466.2, 346, 212.3, 73.2, 10.5],
            tooltip: {
                valueSuffix: ' mm'
            }

        }, {
            name: 'Nhiệt độ',
            type: 'spline',
            data: [19.1, 20.8, 22.9, 24.2, 23.9, 23.1, 23.1, 22.3, 22.4, 21.9, 20.8, 19.4],
            tooltip: {
                valueSuffix: '°C'
            },
            color: '#FF9C2A'
        }]
    });



    Highcharts.chart('chartContainerPK', {
        chart: {
            zoomType: 'xy'
        },
        title: {
            text: null
        },
        credits: {
            enabled: false
        },

        xAxis: [{
            categories: ['1', '2', '3', '4', '5', '6',
                '7', '8', '9', '10', '11', '12'
            ],
            crosshair: true
        }],
        yAxis: [{ // Primary yAxis
            labels: {
                format: '{value}°C',
                style: {
                    color: '#FF9C2A'
                }
            },
            title: {
                text: 'Nhiệt độ',
                style: {
                    color: '#FF9C2A'
                }
            }
        }, { // Secondary yAxis
            title: {
                text: 'Lượng mưa',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            labels: {
                format: '{value} mm',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            opposite: true
        }],
        tooltip: {
            shared: true
        },
        legend: {
            layout: 'vertical',
            align: 'left',
            x: 120,
            verticalAlign: 'top',
            y: 100,
            floating: true,
            backgroundColor: Highcharts.defaultOptions.legend.backgroundColor || // theme
                'rgba(255,255,255,0.25)'
        },
        series: [{
            name: 'Lượng mưa',
            type: 'column',
            yAxis: 1,
            data: [1.9, 6.3, 31.7, 91.5, 223.5, 327.1, 327.1, 466.2, 346, 212.3, 73.2, 10.5],
            tooltip: {
                valueSuffix: ' mm'
            }

        }, {
            name: 'Nhiệt độ',
            type: 'spline',
            data: [19.1, 20.8, 22.9, 24.2, 23.9, 23.1, 23.1, 22.3, 22.4, 21.9, 20.8, 19.4],
            tooltip: {
                valueSuffix: '°C'
            },
            color: '#FF9C2A'
        }]
    });



    Highcharts.chart('chartContainerHCM', {
        chart: {
            zoomType: 'xy'
        },
        title: {
            text: null
        },
        credits: {
            enabled: false
        },

        xAxis: [{
            categories: ['1', '2', '3', '4', '5', '6',
                '7', '8', '9', '10', '11', '12'
            ],
            crosshair: true
        }],
        yAxis: [{ // Primary yAxis
            labels: {
                format: '{value}°C',
                style: {
                    color: '#FF9C2A'
                }
            },
            title: {
                text: 'Nhiệt độ',
                style: {
                    color: '#FF9C2A'
                }
            }
        }, { // Secondary yAxis
            title: {
                text: 'Lượng mưa',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            labels: {
                format: '{value} mm',
                style: {
                    color: Highcharts.getOptions().colors[0]
                }
            },
            opposite: true
        }],
        tooltip: {
            shared: true
        },
        legend: {
            layout: 'vertical',
            align: 'left',
            x: 120,
            verticalAlign: 'top',
            y: 100,
            floating: true,
            backgroundColor: Highcharts.defaultOptions.legend.backgroundColor || // theme
                'rgba(255,255,255,0.25)'
        },
        series: [{
            name: 'Lượng mưa',
            type: 'column',
            yAxis: 1,
            data: [10, 30, 42, 76, 199, 255, 255, 278, 284, 294, 158, 41],
            tooltip: {
                valueSuffix: ' mm'
            }

        }, {
            name: 'Nhiệt độ',
            type: 'spline',
            data: [26.5, 27.2, 28.4, 29.6, 29.1, 28.1, 28.1, 27.6, 27.5, 27.2, 27, 26.4],
            tooltip: {
                valueSuffix: '°C'
            },
            color: '#FF9C2A'
        }]
    });


}
</script>