---
title: Microsoft C++ dil uygunluk tablosu
ms.date: 08/12/2019
ms.technology: cpp-language
ms.assetid: 475da6e9-0d78-4b4e-bd23-f41c406c4efe
author: corob-msft
ms.author: corob
ms.openlocfilehash: 15226d41991d5a09d104d2edbfb3dbf2f7432b65
ms.sourcegitcommit: db1ed91fa7451ade91c3fb76bc7a2b857f8a5eef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68980524"
---
# <a name="microsoft-c-language-conformance-table"></a>Microsoft C++ dil uygunluk tablosu

Bu konu başlığında, Visual Studio 2019 ve önceki sürümlerde Microsoft C++ derleyicisi için derleyici özelliklerinin ve standart KITAPLıK özelliklerinin ISO c++ 03, c++ 11, c++ 14, c++ 17 ve c++ 20 dil standartları uyumluluğu özetlenmektedir. Her derleyici ve standart kitaplık Özellik adı, yayınlama zamanında kullanılabilir C++ olan ÖZELLIĞI açıklayan ISO standart teklif kağıdına bağlanır. Desteklenen sütun, ilk olarak özelliğin desteklediği Visual Studio sürümünü listeler.

Uyumluluk geliştirmeleri ve Visual Studio 2017 ya da Visual Studio 2019 ' deki diğer değişiklikler hakkında daha fazla bilgi için, bu sayfanın sol üst kısmındaki sürüm seçicisini ayarlayın, ardından [ C++ Visual Studio 'da uygunluk iyileştirmeleri](cpp-conformance-improvements.md) ve [görsel C++Visual Studio 'da](what-s-new-for-visual-cpp-in-visual-studio.md). Önceki sürümlerde uygunluk değişiklikleri için bkz. [ C++ görsel değişiklik geçmişi](../porting/visual-cpp-change-history-2003-2015.md) ve [görsel C++ yenilikler 2003 ile 2015 arasındaki](../porting/visual-cpp-what-s-new-2003-through-2015.md)yenilikler. C++ Ekipten güncel haberler için [ C++ ekip blogunu](https://devblogs.microsoft.com/cppblog/)ziyaret edin.

> [!NOTE]
> Visual Studio 2015, Visual Studio 2017 ve Visual Studio 2019 arasında ikili bir son değişiklik yoktur.

## <a name="compiler-features"></a>Derleyici özellikleri

| | |
|----|---|
|__C++ 03/11 çekirdek dil özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;Diğer her şey|VS 2015 <sup>[A](#note_A)</sup>|
|&nbsp;&nbsp;İki aşamalı ad arama|VS 2017 15,7 <sup> [B](#note_B)</sup>|
|&nbsp;&nbsp;[N2634 Ifadesi SFıNAE](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2634.html)|VS 2017 15,7|
|&nbsp;&nbsp;[N1653 C99 ön işlemcisi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1653.htm)|Kısmi <sup> [C](#note_C)</sup>|
|__C++ 14 çekirdek dil özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[Bağlamsal dönüşümler için N3323 tweaked ifadesi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3323.pdf)|VS 2013|
|&nbsp;&nbsp;[N3472 Ikili sabit değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3472.pdf)|VS 2015|
|&nbsp;&nbsp;[N3638 Auto ve decltype (Auto) dönüş türleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3638.html)|VS 2015|
|&nbsp;&nbsp;[N3648 Init-yakalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3648.html)|VS 2015|
|&nbsp;&nbsp;[N3649 genel Lambdalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3649.html)|VS 2015|
|&nbsp;&nbsp;[N3760 \[ kullanım\[dışı özniteliği\] \]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3760.html)|VS 2015|
|&nbsp;&nbsp;[N3778 boyutu kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3781 basamak ayırıcılar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3781.pdf)|VS 2015|
|&nbsp;&nbsp;[N3651 değişken şablonları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3651.pdf)|VS 2015,2|
|&nbsp;&nbsp;[N3652 genişletilmiş constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)|VS 2017 15,0|
|&nbsp;&nbsp;[Toplamalar için varsayılan N3653 üye başlatıcıları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3653.html)|VS 2017 15,0|
|__C++ 17 çekirdek dil özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[Trigraf N4086 kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)|VS 2010 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N3922 otomatik for the braced-init-Lists için yeni kurallar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Şablon şablonunda N4051 TypeName-parametreler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Ad alanları ve Numaralandırıcılar için N4266 öznitelikleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4267 u8 karakter sabit değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4230 Iç Içe ad alanı tanımları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4230.html)|VS 2015,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N3928 terse static_assert](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)|VS 2017 15,0 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0184R0 Genelleştirilmiş Aralık tabanlı for-döngüleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)|VS 2017 15,0 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0188R1 \[ \[fallthrough özniteliği\] \]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r1.pdf)|VS 2017 15,0 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0001R1 register anahtar sözcüğünü kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Bool için P0002R1 işlecini kaldırma + +](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0018R3 yakalama * bu değere göre](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0028R4 öznitelik ad alanlarını yineleme olmadan kullanma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0028r4.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0061R1 \_ has_include\_](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0061r1.html)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0138R2 doğrudan-List-tamsayıların sabit Numaralandırmaların init](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0170R1 constexpr lambdaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0170r1.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0189R1 \[ \[noDiscard özniteliği\] \]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0189r1.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0212R1 \[ maybe_unused\[özniteliği\] \]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0212r1.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0217R3 yapılandırılmış bağlamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0217r3.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0292R2 constexpr if-deyimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0292r2.html)|VS 2017 15,3 <sup> [D](#note_D)</sup>|
|&nbsp;&nbsp;[Başlatıcılarla P0305R1 seçim deyimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0305r1.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0245R1 onaltıya kayan harfler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0245r1.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4268 daha fazla tür olmayan şablon bağımsız değişkenlerinin kullanılmasına Izin verme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4268.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4295 katlama ifadeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4295.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Dinamik özel durum belirtimlerini P0003R5 kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Tür sistemine noexcept P0012R1 ekleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0012r1.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0035R4 üzerinde hizalanmış dinamik bellek ayırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0035r4.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0386R2 satır Içi değişkenler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0386r2.pdf)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0522R0 ile eşleşen şablon şablonu-uyumlu bağımsız değişkenlere parametreler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0522r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0036R0 bazı boş birli katları kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0036r0.pdf)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4261, nitelik dönüştürmeleri düzeltiliyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4261.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0017R1 genişletilmiş toplu başlatma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Sınıf şablonları için P0091R3 şablon bağımsız değişken kesintisi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)<br/>&nbsp;&nbsp;[P0512R0 sınıfı şablon bağımsız değişken kesintisi sorunları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0512r0.pdf)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Otomatik olarak tür olmayan şablon parametreleri bildirmek P0127R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0135R1 garantili kopya](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0135r1.html)|VS 2017 15,6|
|&nbsp;&nbsp;[P0136R1 Re, devralan oluşturucular](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0137R1 std:: Lain](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0137r1.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0145R3 Iyileştirme ifade değerlendirmesi sırası](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0145r3.pdf)<br/>&nbsp;&nbsp;[P0400R0 işlev bağımsız değişkenlerinin değerlendirmesi sırası](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0400r0.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Using bildirimleri içindeki P0195R2 Pack genişletmeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0195r2.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0283R2 tanınmayan öznitelikleri yok sayılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0283r2.html)|VS 2015 <sup>[14](#note_14)</sup>|
|__C++ 17 çekirdek dil özellikleri (hata raporları)__|__Destekleniyor__|
|&nbsp;&nbsp;[P0702R1-List örler için sınıf şablonu bağımsız değişken kesintisi düzeltiliyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0702r1.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0961R1 yapılandırılmış bağlamalar özelleştirme noktası bulma kuralları](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0961r1.html)|VS 2019 16,0 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0969R0, erişilebilir üyelere yapılandırılmış bağlamalar sağlar](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0969r0.pdf)|VS 2019 16,0 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0588R1 örtük lambda yakalamayı basitleştirir](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0588r1.html)|Hayır|
|&nbsp;&nbsp;[P0962R2-aralığı yeniden Lama-for döngüsü özelleştirme noktası kuralları bulma](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0962r1.html)|Hayır|
|&nbsp;&nbsp;[Soyut sınıf türleri için P0929R2 denetimi](https://wg21.link/P0929R2)|Hayır|
|&nbsp;&nbsp;[New ifadelerinde P1009R2 dizi boyut kesintisi](https://wg21.link/P1009R2)|Hayır|
|&nbsp;&nbsp;[P1286R2 Contra CWG DR1778](https://wg21.link/P1286R2)|Hayır|
|__C++ 20 çekirdek dil özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[P0704R1 const lvalue başvurusunu düzeltme-üyelere nitelenmiş işaretçiler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0704r1.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P1041R4 Make char16_t/char32_t dize sabit değerleri UTF-16/32 olmalıdır](https://wg21.link/P1041R4)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P1330R0 içinde bir birleşimin etkin üyesini değiştirme](https://wg21.link/P1330R0)|VS 2017 15,0 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0972R0 noexcept \<, zaman hatası > sıfır (), min (), Max ()](https://wg21.link/P0972R0)|VS 2017 15,7 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0329R4 belirlenen başlatma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[Lambda-Capture \[=, P0409R2 izin verme\]](http://open-std.org/JTC1/SC22/WG21/docs/papers/2017/p0409r2.html)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0515R3 üç yönlü (Spaceship) karşılaştırma işleci < = >](https://wg21.link/P0515R3)|VS 2019 16,0 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0941R2 özelliği-test makroları](https://wg21.link/P0941R2)|VS 2019 16,0 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P1008R1, Kullanıcı tarafından belirtilen oluşturucularla toplamalar yasaklıyor](https://wg21.link/P1008R1)|VS 2019 16,0 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0846R0 ADL ve görünmeyen işlev şablonları](https://wg21.link/P0846R0)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[Varsayılan olarak kopya Oluşturucu ile P0641R2 const uyuşmazlığı](https://wg21.link/P0641R2)|Kısmi|
|&nbsp;&nbsp;[P0306R4, \_virgül\_ atlama ve virgül silme için VA_OPT ekleme \_\_](https://wg21.link/P0306R4)|Hayır|
|&nbsp;&nbsp;[P0315R4, değerlendirilen bağlamlarda lambdalara Izin verir](https://wg21.link/P0315R4)|Hayır|
|&nbsp;&nbsp;[Genel Lambdalar için P0428R2 tanıdık şablon söz dizimi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0428r2.pdf)|Hayır|
|&nbsp;&nbsp;[P0479R5 \[ muhtemel\[ ve\[olası olmayanöznitelikler\] \] \] \[\]](https://wg21.link/P0479R5)|Hayır|
|&nbsp;&nbsp;[P0542R5 sözleşmeleri](https://wg21.link/P0542R5)|Hayır|
|&nbsp;&nbsp;[Başlatıcıları ile P0614R1 Range tabanlı for-döngüleri](https://wg21.link/P0614R1)|Hayır|
|&nbsp;&nbsp;[P0624R2 varsayılan oluşturulabilir ve atanabilir durum bilgisi olmayan Lambdalar](https://wg21.link/P0624R2)|Hayır|
|&nbsp;&nbsp;[TypeName ile P0634R3](https://wg21.link/P0634R3)|Hayır|
|&nbsp;&nbsp;[Bit alanları için varsayılan P0683R1 üye başlatıcıları](https://wg21.link/P0683R1)|Hayır|
|&nbsp;&nbsp;[P0692R1, Uzmanlıklar üzerinde erişim denetimini Gevşlama](https://wg21.link/P0692R1)|Hayır|
|&nbsp;&nbsp;[P0722R3 değişken boyutlu sınıflar için etkin boyutlu silme](https://wg21.link/P0722R3)|Hayır|
|&nbsp;&nbsp;[Tür olmayan şablon parametrelerinde P0732R2 sınıf türleri](https://wg21.link/P0732R2)|Hayır|
|&nbsp;&nbsp;[P0734R0 kavramları](https://wg21.link/P0734R0)|Hayır|
|&nbsp;&nbsp;[Lambda init-Capture içinde paket genişletmeye Izin P0780R2](https://wg21.link/P0780R2)|Hayır|
|&nbsp;&nbsp;[P0806R2 bu ile örtük yakalamayı kullanımdan kaldırır\[=\]](https://wg21.link/P0806R2)|Hayır|
|&nbsp;&nbsp;[P0840R2 \[ no_unique_address\[özniteliği\] \]](https://wg21.link/P0840R2)|Hayır|
|&nbsp;&nbsp;[P0857R0 işlevselliği düzeltme aralıkları](https://wg21.link/P0857R0)|Hayır|
|&nbsp;&nbsp;[P0892R2 koşullu açık](https://wg21.link/P0892R2)|Hayır|
|&nbsp;&nbsp;[P0912R5 coroutines](https://wg21.link/P0912R5)|Hayır|
|&nbsp;&nbsp;[P0960R3, parantez içine alınmış değerler listesinden toplamalar başlatmaya Izin ver](https://wg21.link/P0960R3)|Hayır|
|&nbsp;&nbsp;[Constexpr işlevlerinde P1002R1 try-catch blokları](https://wg21.link/P1002R1)|Hayır|
|&nbsp;&nbsp;[Sabit ifadelerde sanal işlev çağrılarına Izin P1064R0](https://wg21.link/P1064R0)|Hayır|
|&nbsp;&nbsp;[P1073R3 hemen işlevleri](https://wg21.link/P1073R3)|Hayır|
|&nbsp;&nbsp;[P1084R2 Bugünün dönüş türü-gereksinimler yetersiz](https://wg21.link/P1084R2)|Hayır|
|&nbsp;&nbsp;[P1091R3 yapılandırılmış bağlamaları değişken bildirimleri gibi olacak şekilde genişletme](https://wg21.link/P1091R3)|Hayır|
|&nbsp;&nbsp;[P1094R2 Iç Içe geçmiş satır adları](https://wg21.link/P1094R2)|Hayır|
|&nbsp;&nbsp;[P1103R3 modülleri](https://wg21.link/P1103R3)|Hayır|
|&nbsp;&nbsp;[< = > Ve diğer karşılaştırma işleçleri için P1120R0 tutarlılığı iyileştirmeleri](https://wg21.link/P1120R0)|Hayır|
|&nbsp;&nbsp;[P1139R2 adres ifadesi ISO 10646 ile ilgili sorunlar](https://wg21.link/P1139R2)|Hayır|
|&nbsp;&nbsp;[Kısıtlanmış bildirimler için başka bir yaklaşım P1141R2](https://wg21.link/P1141R2)|Hayır|
|&nbsp;&nbsp;[P1185R2 \<=\> != ==](https://wg21.link/P1185R2)|Hayır|
|&nbsp;&nbsp;[P1236R1 Işaretli tamsayılar ikinin tamamlayıcısı](https://wg21.link/P1236R1)|Hayır|
|&nbsp;&nbsp;[Sözleşme koşullarında P1289R1 Access Control](https://wg21.link/P1289R1)|Hayır|
|&nbsp;&nbsp;[P1323R2 sözleşmesi Sonkoşulları ve dönüş türü kesintisi](https://wg21.link/P1323R2)|Hayır|
|&nbsp;&nbsp;[P1327R1, sabit ifadelerde dynamic_cast, polimorfik TypeId kullanılmasına Izin verir](https://wg21.link/P1327R1)|Hayır|
|&nbsp;&nbsp;[P1353R0 eksik özellik-test makroları](https://wg21.link/P1353R0)|Hayır|
|&nbsp;&nbsp;[Yapılandırılmış bağlamalar için P1381R1 başvuru yakalama](https://wg21.link/P1381R1)|Hayır|

## <a name="standard-library-features"></a>Standart Kitaplık Özellikleri

| | |
|---|---|
|__C++ 20 Standart Kitaplık Özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[Sıralanmamış kapsayıcıları karşılaştıran P0809R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0809r0.pdf)| VS 2010 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0858R0 constexpr Yineleyici gereksinimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0858r0.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Gereksiz Decay P0777R1 önleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0777r1.pdf)|VS 2017 15,7 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0550R2 remove_cvref](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf)|VS 2019 16,0 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0318R1 unwrap_reference, unwrap_ref_decay](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0318r1.pdf)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[Basic_string/basic_string_view Için P0457R2 starts_with ()/ends_with ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0457r2.html)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[Sıralı ve sırasız Ilişkilendirilebilir kapsayıcılar Için P0458R2 Contains ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0458r2.html)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0646R1 List/forward_list Remove ()/remove_if ()/Unique () return size_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0646r1.pdf)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0769R2 shift_left(), shift_right()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0769r2.pdf)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0887R1 type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0019R8 atomic_ref](https://wg21.link/P0019R8)|Hayır|
|&nbsp;&nbsp;[P0020R6 atomik\<float >, atomik\<çift >, atomik\<uzun çift >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0020r6.html)|Hayır|
|&nbsp;&nbsp;[P0053R7 \<syncstream >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0053r7.pdf)<br/>&nbsp;&nbsp;[P0753R2 osyncstream Işleicileri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0753r2.pdf)|Hayır|
|&nbsp;&nbsp;[P0122R7 \<span >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0122r7.pdf)|Hayır|
|&nbsp;&nbsp;[Algoritma > ve \<Exchange () için P0202R3 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0202r3.html)|Hayır|
|&nbsp;&nbsp;[P0339R6 polymorphic_allocator < >](https://wg21.link/P0339R6)|Hayır|
|&nbsp;&nbsp;[P0340R3 SFINAE-kolay underlying_type](https://wg21.link/P0340R3)|Hayır|
|&nbsp;&nbsp;[> \<Takvim ve saat dilimlerini P0355R7 hatası](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0355r7.html)|Hayır|
|&nbsp;&nbsp;[P0356R5 bind_front()](https://wg21.link/P0356R5)|Hayır|
|&nbsp;&nbsp;[P0357R3, reference_wrapper Içinde eksik türleri destekleme](https://wg21.link/P0357R3)|Hayır|
|&nbsp;&nbsp;[Karmaşık > için \<P0415R1 constexpr (yeniden)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0415r1.html)|Hayır|
|&nbsp;&nbsp;[P0439R0 enum sınıfı memory_order](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0439r0.html)|Hayır|
|&nbsp;&nbsp;[P0463R1 endian](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0463r1.html)|Hayır|
|&nbsp;&nbsp;[Piecewise oluşturma Için P0475R1 garantili kopya](https://wg21.link/P0475R1)|Hayır|
|&nbsp;&nbsp;[P0476R2 <bit> bit_cast](https://wg21.link/P0476R2)|Hayır|
|&nbsp;&nbsp;[P0482R6 char8_t: UTF-8 karakter ve dizeleri için bir tür](https://wg21.link/P0482R6)|Hayır|
|&nbsp;&nbsp;[P0487R1 düzeltme işleci > > (basic_istream &, grafik *)](https://wg21.link/P0487R1)|Hayır|
|&nbsp;&nbsp;[P0528R3 atomik karşılaştırma-ve-doldurma bitleri Ile değişim](https://wg21.link/P0528R3)|Hayır|
|&nbsp;&nbsp;[P0556R3 <bit> ispow2 (), ceil2 (), Floor2 (), log2p1 ()](https://wg21.link/P0556R3)|Hayır|
|&nbsp;&nbsp;[Kullanımlar-ayırıcı oluşturma Için P0591R4 yardımcı program Işlevleri](https://wg21.link/P0591R4)|Hayır|
|&nbsp;&nbsp;[STL \[için P0600R1 \[\] noat\] , 1. Bölüm](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0600r1.pdf)|Hayır|
|&nbsp;&nbsp;[P0608R3 'in oluşturucuyu/atamayı dönüştürme](https://wg21.link/P0608R3)|Hayır|
|&nbsp;&nbsp;[\<Sayısal > Move () kullanarak P0616R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0616r0.pdf)|Hayır|
|&nbsp;&nbsp;[C++ 20 ' de P0619R4 ve +17-kullanım dışı Özellikler kaldırılıyor](https://wg21.link/P0619R4)|Hayır|
|&nbsp;&nbsp;[P0653R2 to_address()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0653r2.html)|Hayır|
|&nbsp;&nbsp;[<R>P0655R1 ()](https://wg21.link/P0655R1)|Hayır|
|&nbsp;&nbsp;[Diziler Için P0674R1 make_shared ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0674r1.html)|Hayır|
|&nbsp;&nbsp;[P0718R2 atomik\<shared_ptr\<t > >, atomik\<weak_ptr\<T > >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0718r2.html)|Hayır|
|&nbsp;&nbsp;[P0738R2 istream_iterator Cleanup](https://wg21.link/P0738R2)|Hayır|
|&nbsp;&nbsp;[P0754R2 \<sürüm >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0754r2.pdf)|Hayır|
|&nbsp;&nbsp;[P0758R1 is_nothrow_convertible](https://wg21.link/P0758R1)|Hayır|
|&nbsp;&nbsp;[P0767R1, is_pod 'yi kullanımdan kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0767r1.html)|Hayır|
|&nbsp;&nbsp;[Spaceship karşılaştırma Işleci Için P0768R1 kitaplığı desteği\<=>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0768r1.pdf)|Hayır|
|&nbsp;&nbsp;[Std:: Function 'ın taşıma Oluşturucusu Için P0771R1 noexcept](https://wg21.link/P0771R1)|Hayır|
|&nbsp;&nbsp;[P0811R3 Orta (), Lerp ()](https://wg21.link/P0811R3)|Hayır|
|&nbsp;&nbsp;[Takas Işlevleri Için P0879R0 constexpr](https://wg21.link/P0879R0)|Hayır|
|&nbsp;&nbsp;[P0896R4 \<aralıkları\>](https://wg21.link/P0896R4)|Hayır|
|&nbsp;&nbsp;[P0898R3 standart kitaplığı kavramları](https://wg21.link/P0898R3)|Hayır|
|&nbsp;&nbsp;[Eş yordamları Için P0912R5 kitaplık desteği](https://wg21.link/P0912R5)|Hayır|
|&nbsp;&nbsp;[Sıralanmamış kapsayıcılar Için heterojen arama P0919R3](https://wg21.link/P0919R3)|Hayır|
|&nbsp;&nbsp;[P0920R2 önceden hesaplanmış karma değer araması](https://wg21.link/P0920R2)|Hayır|
|&nbsp;&nbsp;[Gereksiz açık varsayılan oluşturucular P0935R0 Eradnasyon](https://wg21.link/P0935R0)|Hayır|
|&nbsp;&nbsp;[P0966R1 String:: Reserve () daraltılamıyor](https://wg21.link/P0966R1)|Hayır|
|&nbsp;&nbsp;[P1001R2 Execution:: unseq](https://wg21.link/P1001R2)|Hayır|
|&nbsp;&nbsp;[Pointer_traits < T * > Için P1006R1 constexpr::p ointer_to ()](https://wg21.link/P1006R1)|Hayır|
|&nbsp;&nbsp;[P1007R3 assume_aligned()](https://wg21.link/P1007R3)|Hayır|
|&nbsp;&nbsp;[P1020R1 varsayılan başlatma Ile akıllı Işaretçi oluşturma](https://wg21.link/P1020R1)|Hayır|
|&nbsp;&nbsp;[Std:: Array karşılaştırmaları Için P1023R0 constexpr](https://wg21.link/P1023R0)|Hayır|
|&nbsp;&nbsp;[P1032R1 çeşitli constexpr](https://wg21.link/P1032R1)|Hayır|
|&nbsp;&nbsp;[P1165R1, basic_string's işleci + () Içinde durum bilgisi olan ayırıcıları sürekli olarak yayma](https://wg21.link/P1165R1)|Hayır|
|&nbsp;&nbsp;[P1209R0 erase_if (), Erase ()](https://wg21.link/P1209R0)|Hayır|
|&nbsp;&nbsp;[P1227R2 signed std:: ssize (), Işaretsiz span:: size ()](https://wg21.link/P1227R2)|Hayır|
|&nbsp;&nbsp;[P1285R0 tür nitelikleri Için tamamlayıcı gereksinimleri artırma](https://wg21.link/P1285R0)|Hayır|
|&nbsp;&nbsp;[P1357R1 is_bounded_array, is_unbounded_array](https://wg21.link/P1357R1)|Hayır|
|__C++ 17 standart kitaplığı özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[Nullptr için LWG 2221 biçimli çıktı işleci](https://cplusplus.github.io/LWG/issue2221)|VS 2019 16,1|
|&nbsp;&nbsp;[N3911 void_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3911.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Unique_ptr\<T [] > için güvenli dönüşümler N4089](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4089.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4169 Invoke ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4169.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Auto_ptr, random_shuffle () ve eski \<işlevsel > N4190 kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4190.htm)|VS 2015 <sup> [kal](#note_rem)</sup>|
|&nbsp;&nbsp;[N4258 noexcept temizlemeler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4258.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4259 uncaught_exceptions()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4259.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4277 Trivisel kopyalanabilir reference_wrapper](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4277.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Map/unordered_map Için N4279 insert_or_assign ()/try_emplace ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4279.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4280 size (), boş (), veri ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4280.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4366 unique_ptr atamasını kesin olarak kısıtlama](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4366.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4387, Çift ve tanımlama grubu geliştirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4387.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4389 bool_constant](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4389.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4508 shared_mutex (zaman aşımına uğradı)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4508.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4510, vector/List/forward_list Içinde eksik türleri destekleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4510.html)|VS 2013 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: \<algoritma > örnek ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#alg.random.sample)|VS 2017 15,0|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: \<tüm >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#any)|VS 2017 15,0|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: \<memory_resource >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#memory.resource.synop)<br/>&nbsp;&nbsp;[Polymorphic_allocator atamasını silme P0337R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0337r0.html)|VS 2017 15,6|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: \<isteğe bağlı >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#optional)|VS 2017 15,0|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: \<string_view >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#string.view)|VS 2017 15,0|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: \<demet > Apply ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#tuple)|VS 2017 15,0|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: Boyer-Moore arama ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#func.searchers.boyer_moore)<br/>&nbsp;&nbsp;[P0253R1 Searcher dönüş türlerini Düzeltme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0253r1.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0003R5 dinamik özel durum belirtimlerini kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0004R1 kaldırılmış Iostreams diğer adlarını kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0004r1.html)|VS 2015,2 <sup> [kal](#note_rem)</sup>|
|&nbsp;&nbsp;[P0005R4 not_fn()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html)<br/>&nbsp;&nbsp;[Not_fn () Için P0358R1 düzeltmeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Tür nitelikleri Için P0006R0 değişken şablonları (is_same_v, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0006r0.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0007R1 as_const()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0007r1.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0013R1 mantıksal Işleç türü nitelikleri (bağlantılı, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0013r1.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0024R2 paralel algoritmaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html)<br/>&nbsp;&nbsp;[P0336R1 paralel yürütme Ilkelerini yeniden adlandırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0336r1.pdf)<br/>&nbsp;&nbsp;[Özel durumlar Için P0394R4 paralel algoritmaların sonlandırılması ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0394r4.html)<br/>&nbsp;&nbsp;[P0452R1 \<sayısal > paralel algoritmalara geri al](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0452r1.html)|VS 2017 15,7|
|&nbsp;&nbsp;[P0025R1 Clamp ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0025r1.html)|VS 2015,3|
|&nbsp;&nbsp;[P0030R1 hypot (x, y, z)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf)|VS 2017 15,7|
|&nbsp;&nbsp;[Dizi > için \<P0031R0 constexpr (tekrar) ve \<Yineleyici >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0031r0.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Değişken/any/isteğe bağlı Için homojen P0032R3 arabirimi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0032r3.pdf)|VS 2017 15,0|
|&nbsp;&nbsp;[P0033R1 Reifadesi enable_shared_from_this](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html)|VS 2017 15,5 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0040R3 genişletme bellek yönetimi araçları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0040r3.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0063R3 C11 standart kitaplığı](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0063r3.html)|VS 2015 <sup>[C11](#note_C11), [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0067R5 Elemensel dize dönüştürmeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html)|VS 2017 15,7 <sup> [charconv](#note_charconv)</sup>|
|&nbsp;&nbsp;[P0074R0 owner_less\<>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0074r0.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0077R2 is_callable, is_nothrow_callable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0077r2.html)|VS 2017 15,0|
|&nbsp;&nbsp;[P0083R3, haritalar ve kümeler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)<br/>&nbsp;&nbsp;[P0508R0 Clarifying insert_return_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0084R2 emplace dönüş türü](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0084r2.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0088R3 \<Variant >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0088r3.html)|VS 2017 15,0|
|&nbsp;&nbsp;[P0092R1 \<İTO > Floor (), CEIL (), Round (), ABS ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0092r1.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0152R1 atomik:: is_always_lock_free](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0152r1.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0154R1 hardware_destructive_interference_size, vb.](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0154r1.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0156R0 Variadıc lock_guard](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0156r0.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0156R2 yeniden adlandırma, değişken\_olmayan kilit korumasını\_kapsamlı kilit olarak](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0156r2.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0163R0 shared_ptr::weak_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0163r0.html)|VS 2017 15,0|
|&nbsp;&nbsp;[P0174R2 kalıntı kitaplık parçalarını kullanımdan kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0185R1 is_swappable, is_nothrow_swappable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0185r1.html)|VS 2015,3|
|&nbsp;&nbsp;[P0209R2 make_from_tuple()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0209r2.pdf)|VS 2017 15,0|
|&nbsp;&nbsp;[P0218R1 \<FileSystem >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html)<br/>&nbsp;&nbsp;[Dosya sistemi Için P0219R1 göreli yollar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0219r1.html)<br/>&nbsp;&nbsp;[Dosya sistemi Için P0317R1 Dizin girişi önbelleğe alma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0317r1.html)<br/>&nbsp;&nbsp;[Dosya sistemi yollarında P0392R0 destekleme string_view](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0392r0.pdf)<br/>&nbsp;&nbsp;[P0430R2, POSIX olmayan dosya sistemlerini destekleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0430r2.pdf)<br/>&nbsp;&nbsp;[P0492R2 dosya sistemi için NB açıklamalarını çözme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0492r2.html)|VS 2017 15,7 <sup> [E](#note_E)</sup>|
|&nbsp;&nbsp;[P0220R1 kitaplığı temelleri v1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html)|VS 2017 15,6|
|&nbsp;&nbsp;[P0226R1 matematik özel Işlevleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0226r1.pdf)|VS 2017 15,7|
|&nbsp;&nbsp;[String_view ve std:: String P0254R2 tümleştirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0254r2.pdf)|VS 2017 15,0|
|&nbsp;&nbsp;[P0258R2 has_unique_object_representations](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0258r2.html)|VS 2017 15,3 <sup> [G](#note_G)</sup>|
|&nbsp;&nbsp;[P0272R1 non-const basic_string::d ata ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0272r1.html)|VS 2015,3|
|&nbsp;&nbsp;[P0295R0 GCD (), LCM ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0295r0.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0298R3 std:: Byte](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0298r3.pdf)|VS 2017 15,3 <sup> [17](#note_17),&nbsp;[bayt](#note_byte)</sup>|
|&nbsp;&nbsp;[Std:: işlevinde ayırıcı desteğini P0302R1 kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Isteğe bağlı P0307R2 yeniden eşit hale getirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0307r2.pdf)|VS 2017 15,0|
|&nbsp;&nbsp;[P0393R3 değişken daha büyük hale getirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0393r3.html)|VS 2017 15,0|
|&nbsp;&nbsp;[String_view > için \<P0403R1 UDLs ("meow" ZF vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0403r1.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0414R2 shared_ptr\<t [] >, shared_ptr\<T [N] >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html)<br/>&nbsp;&nbsp;[Diziler Için shared_ptr düzeltme P0497R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html)|VS 2017 15,5 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0418R2 atomik compare_exchange memory_order gereksinimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0418r2.html)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Char_traits Için P0426R1 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html)|VS 2017 15,7|
|&nbsp;&nbsp;[P0433R2 sınıf şablonları için şablon kesintilerinizi standart kitaplığa tümleştirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html)<br/>&nbsp;&nbsp;[P0739R0 sınıf şablonu bağımsız değişken kesintisi tümleştirmesini standart kitaplığa artırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html)|VS 2017 15,7|
|&nbsp;&nbsp;[P0435R1 Overhauling common_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0435r1.pdf)<br/>&nbsp;&nbsp;[P0548R1 genel\_tür ve süre](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0548r1.pdf)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0504R0 yeniden ziyaret in_place_t/in_place_type_t\<t >/in_place_ındex_t\<ı >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0504r0.html)|VS 2017 15,0|
|&nbsp;&nbsp;[> Hatası için \<P0505R0 constexpr (yeniden)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0505r0.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Nothing, diziler, başvurular ve tamamlanmamış türlerin türevlerini P0510R0 reddetme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0510r0.html)|VS 2017 15,0|
|&nbsp;&nbsp;[P0513R0 Kirleme karması](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0513r0.pdf)<br/>&nbsp;&nbsp;[P0599R1 noexcept karması](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0599r1.pdf)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0516R0 shared_future kopyalamayı noexcept olarak Işaretleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0516r0.html)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Future_errc P0517R0 oluşturma future_error](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0517r0.html)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0521R0 shared_ptr:: Unique ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0521r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[> Temel sınıf\<tutarsızlıkları adlı atomik T 'yi çözmek P0558R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0558r1.pdf)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0595R2 std:: is_constant_evaluated ()](https://wg21.link/P0595R2)|Hayır|
|&nbsp;&nbsp;[Değişken/isteğe bağlı P0602R4 yayan kopyalama/taşıma](https://wg21.link/P0602R4)|VS 2017 15.3<sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0604R0 değiştirme işlemi\_çağrılabilir/sonuç\_çağırmak\_\_için sonuç, ınvocable\_, nothrow\_ınvocable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0604r0.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Standart Kitaplık için P0607R0 satır Içi değişkenler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0618R0, \<codecvt > 'yi kullanımdan kaldıracağız](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0618r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0682R1 basit dize dönüştürmelerini onarma](https://wg21.link/P0682R1)|VS 2015 15,7 <sup> [17](#note_17)</sup>|
|__C++ 14 standart kitaplık özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[N3462 SFINAE-kolay result_of](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3462.html)|VS 2015,2|
|&nbsp;&nbsp;[Karmaşık > için \<N3302 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2011/n3302.html)|VS 2015|
|&nbsp;&nbsp;[> Hatası için \<N3469 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3469.html)|VS 2015|
|&nbsp;&nbsp;[Dizi > için \<N3470 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3470.html)|VS 2015|
|&nbsp;&nbsp;[İnitializer_list > için \<N3471 constexpr, \<tanımlama grubu > \<, yardımcı programı >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3471.html)|VS 2015|
|&nbsp;&nbsp;[N3545 integral_constant:: operator () ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3545.pdf)|VS 2015|
|&nbsp;&nbsp;[>, Zaman hatası \<için N3642 UDLs \<, dize > (1729ms, "meow" s vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3642.pdf)|VS 2015|
|&nbsp;&nbsp;[N3644 null Ileri yineleyiciler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3644.pdf)|VS 2015|
|&nbsp;&nbsp;[N3654 alıntılanmış ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3654.html)|VS 2015|
|&nbsp;&nbsp;[N3657 heterojen Ilişkilendirilebilir arama](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3657.htm)|VS 2015|
|&nbsp;&nbsp;[N3658 integer_sequence](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3658.html)|VS 2015|
|&nbsp;&nbsp;[N3659 shared_mutex (zaman aşımına uğradı)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3659.html)|VS 2015|
|&nbsp;&nbsp;[N3668 Exchange ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3668.html)|VS 2015|
|&nbsp;&nbsp;[N3669, sabit olmayan constexpr üye Işlevlerini Düzeltme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3669.pdf)|VS 2015|
|&nbsp;&nbsp;[N3670 get\<T>()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3670.html)|VS 2015|
|&nbsp;&nbsp;[N3671 çift aralıklı eşittir (), is_permutation (), uyuşmazlık ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3671.html)|VS 2015|
|&nbsp;&nbsp;[N3778 boyutu kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3779 UDLs for \<Complex > (3.14 i vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3779.pdf)|VS 2015|
|&nbsp;&nbsp;[İşlevsel > için \<N3789 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3789.htm)|VS 2015|
|&nbsp;&nbsp;[N3887 tuple_element_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3887.pdf)|VS 2015|
|&nbsp;&nbsp;[N3891 yeniden adlandırma shared_mutex (zamanlanmış) shared_timed_mutex](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3891.htm)|VS 2015|
|&nbsp;&nbsp;[N3346 en az kapsayıcı öğe gereksinimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3346.pdf)|VS 2013|
|&nbsp;&nbsp;[N3421 saydam işleç finansdüler (\<daha az >, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3421.htm)|VS 2013|
|&nbsp;&nbsp;[Type_traits > için \<N3655 diğer ad şablonları (decay_t, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3655.pdf)|VS 2013|
|&nbsp;&nbsp;[N3656 make_unique()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3656.htm)|VS 2013|

Birlikte listelenen bir grup bilgi, bir özelliğin standart olarak geçtiğini ve daha sonra gelişmekte veya genişletmekte olan bir veya daha fazla bilgi için bu özelliği de oylandı olduğunu gösterir. Bu özellikler birlikte uygulanır.

### <a name="supported-values"></a>Desteklenen değerler

__Hayır__ , henüz uygulanmadı anlamına gelir.<br/>
__Kısmi__ , uygulamanın tamamlanmamış olduğu anlamına gelir. Daha ayrıntılı bilgi için Notlar bölümüne bakın.<br/>
__VS 2010__ , Visual Studio 2010 ' de desteklenen özellikleri gösterir.<br/>
__VS 2013__ , Visual Studio 2013 desteklenen özellikleri gösterir.<br/>
__VS 2015__ , Visual STUDIO 2015 RTW sürümünde desteklenen özellikleri gösterir.<br/>
__Vs 2015,2__ ve __vs 2015,3__ , sırasıyla Visual Studio 2015 güncelleştirme 2 ve Visual Studio 2015 güncelleştirme 3 ' te desteklenen özellikleri gösterir.<br/>
__VS 2017 15,0__ , Visual Studio 2017 sürüm 15,0 (RTW) içinde desteklenen özellikleri gösterir.<br/>
__VS 2017 15,3__ , Visual Studio 2017 sürüm 15,3 ' te desteklenen özellikleri gösterir.<br/>
__VS 2017 15,5__ , Visual Studio 2017 sürüm 15,5 ' te desteklenen özellikleri gösterir.<br/>
__VS 2017 15,7__ , Visual Studio 2017 sürüm 15,7 ' te desteklenen özellikleri gösterir.<br/>
__VS 2019 16,0__ , Visual Studio 2019 sürüm 16,0 (RTW) içinde desteklenen özellikleri gösterir.<br/>
__VS 2019 16,1__ , Visual Studio 2019 sürüm 16,1 ' te desteklenen özellikleri gösterir.

### <a name="notes"></a>Notlar

<a name="note_A"></a> [/Std: c++ 14](../build/reference/std-specify-language-standard-version.md) modunda, dinamik özel durum belirtimleri uygulanmadı olarak kalır ve `throw()` için `__declspec(nothrow)`de bir eş anlamlı olarak değerlendirilir. C++ 17 ' de, dinamik özel durum belirtimleri büyük ölçüde P0003R5 tarafından kaldırılmıştır, bir vestige `throw()` bırakarak bir: kullanım dışı ve için `noexcept`bir eş anlamlı olarak davranması gerekir. [/Std: c++ 17](../build/reference/std-specify-language-standard-version.md) modunda, MSVC artık, örneğin sonlandırmasına karşı uygulama gibi `throw()` `noexcept`aynı davranışı vererek standart 'e uyar.

[/Zc: noexceptTypes](../build/reference/zc-noexcepttypes.md) derleyici seçeneği eski davranışımızı `__declspec(nothrow)`ister. `throw()` Bu, c++ 20 ' de kaldırılacak. Standart ve uygulamamız içindeki bu değişikliklere yanıt olarak kod geçirmeye yardımcı olmak için [/std: c++ 17](../build/reference/std-specify-language-standard-version.md) ve [/Permissive-](../build/reference/permissive-standards-conformance.md)altına özel durum belirtimi sorunlarıyla ilgili yeni derleyici uyarıları eklenmiştir.

<a name="note_B"></a>__B__ [/Permissive-](../build/reference/permissive-standards-conformance.md) modunda Visual Studio 2017 sürüm 15,7 ' de desteklenir. daha fazla bilgi için bkz. [iki aşamalı ad arama DESTEĞI MSVC](https://blogs.msdn.microsoft.com/vcblog/2017/09/11/two-phase-name-lookup-support-comes-to-msvc/) .

<a name="note_C"></a>__C__ derleyicinin C99 Önişlemci kuralları için destek, Visual Studio 2017 içinde eksik. Bağımsız değişken olmayan makrolar desteklenir, ancak Önişlemci davranışında birçok hata vardır. Ön işlemci overhauling ve bu değişiklikleri [/Permissive-](../build/reference/permissive-standards-conformance.md) modunun kısa bir süre içinde experimentally alacak.

<a name="note_D"></a>__D__ [/std: c++ 14](../build/reference/std-specify-language-standard-version.md) altında gizlenecek bir uyarı ile C4984.

<a name="note_E"></a> Bu, bir önceki sürümle uyumsuz olan, oluşturmaksızın desteği, `std::experimental` hata düzeltmeleri ve standart-gerekli davranıştaki değişiklikler tarafından ortaya geçen tamamen yeni bir uygulama. Şu anda dosya \<sistemi > de dahil olmak `std::filesystem` üzere, New `std::experimental::filesystem`ve Previous ve \<deneysel/FileSystem > dahil olmak üzere yalnızca eski deneysel uygulamayı sağlar. Deneysel uygulama, kitaplıkların sonraki ABı-kırılımı sürümünde KALDıRıLACAK.

<a name="note_G"></a>Bir derleyici iç tarafından desteklenen __G__ .

<a name="note_14"></a>__14__ bu c++ 17/20 özellikleri, [/std: c++ 14](../build/reference/std-specify-language-standard-version.md) (varsayılan) belirtildiğinde bile her zaman etkindir. Bunun nedeni, özelliğin **/STD** seçeneklerinin sunumundan önce uygulandığından veya koşullu uygulamanın istenmediği karmaşıklıkta olması nedeniyle oluşur.

<a name="note_17"></a>__17__ bu özellikler [/std: c++ 17](../build/reference/std-specify-language-standard-version.md) (veya [/std: c + + latest](../build/reference/std-specify-language-standard-version.md)) derleyici seçeneği tarafından etkinleştirilir.

<a name="note_20"></a>__20__ bu özellikler [/std: c + + en son](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği tarafından etkinleştirilir. C++ 20 uygulama tamamlandığında, bu özelliklerin de kullanılabildiği yeni bir **/std: c++ 20** derleyici seçeneği eklenir.

<a name="note_byte"></a>__bayt__ ,/STD [: c++ 17](../build/reference/std-specify-language-standard-version.md) (veya [/std: c + + en son](../build/reference/std-specify-language-standard-version.md)) tarafından etkinleştirilir, ancak bazı durumlarda Windows SDK üst bilgileri ile çakışabileceğinden, hassas bir geri çevirme makrosu vardır. `std::byte` , Olarak `_HAS_STD_BYTE` `0`tanımlayarak devre dışı bırakılabilir.

<a name="note_C11"></a>__C11__ Evrensel CRT, C99 `strftime()` E/O alternatif Dönüştürme belirticileri, C11 `fopen()` dışlamalı mod ve C11 `aligned_alloc()`dışında c++ 17 için gerekli olan C11 standart kitaplığının parçalarını uyguladık. İkinci olarak, C11 ' nin `aligned_alloc()` `free()` `free()` , yüksek oranda hizalanmış ayırmaları işleyebilmesi gereken, Microsoft uygulamasıyla uyumsuz bir şekilde belirtildiği için uygulanması çok düşüktür.

<a name="note_rem"></a>__REM__ [/Std: c++ 17](../build/reference/std-specify-language-standard-version.md) (veya [/std: c + + latest](../build/reference/std-specify-language-standard-version.md)) derleyici seçeneği belirtildiğinde kaldırılan özellikler. Bu özellikler, bu makroları kullanarak daha yeni dil modlarına geçişi kolaylaştırmak için yeniden etkinleştirilebilir `_HAS_AUTO_PTR_ETC`:, `_HAS_FUNCTION_ALLOCATOR_SUPPORT`, `_HAS_OLD_IOSTREAMS_MEMBERS`ve `_HAS_UNEXPECTED`.

<a name="note_charconv"></a>__charconv__ `from_chars()` ve`to_chars()` tamsayılar için kullanılabilir. Kayan nokta `from_chars()` ve kayan nokta `to_chars()` için zaman çizelgesi aşağıdaki gibidir:
- VS 2017 15,7: Tamsayı `from_chars()` ve `to_chars()`.
- VS 2017 15,8: Kayan nokta `from_chars()`.
- VS 2017 15,9: En kısa ondalık `to_chars()` için kayan nokta aşırı yüklemeleri.
- VS 2019 16,0: En kısa onaltılık `to_chars()` ve duyarlık onaltılı için kayan nokta aşırı yüklemeleri.
- VS 2019 16,2: Precision fixed ve `to_chars()` Precision bilimsel için kayan nokta aşırı yüklemeleri.
- Henüz uygulanmadı: Duyarlık genel için kayan `to_chars()` nokta aşırı yüklemesi. 

<a name ="note_parallel"></a>__paralel__ C++ 17 ' nin paralel algoritma kitaplığı tamamlanmıştır. Bu, her iki durumda da her algoritmanın paralelleştirilmesine değil; en önemli algoritmalar paralelleştirilmiş ve yürütme ilkesi imzaları, algoritmaların paralelleştirilmedi durumunda bile sağlanır. Uygulamamız, yvals_core. h olan orta iç üst bilgi, aşağıdaki "paralel algoritmalar notlarını" içerir: C++bir uygulamanın seri algoritmalara çağrı olarak paralel algoritmalar uygulamasına olanak tanır.  Bu uygulama birkaç ortak algoritma çağrısının paralelleştirmesi, ancak tümünü içermez.

Aşağıdaki algoritmalar paralelleştirildi:

- `adjacent_difference`, `adjacent_find`, `all_of`, `any_of`, `count`, `count_if`, `equal`, `exclusive_scan`, `find`, `find_end`, `find_first_of`, `find_if`, `find_if_not`, `for_each`, `for_each_n`, `inclusive_scan`, `is_heap`, `is_heap_until`, `is_partitioned`, `is_sorted`, `is_sorted_until`, `mismatch`, `none_of`, `partition`, `reduce`, `remove`, `remove_if` , `replace`, `replace_if`, `search`, `search_n`, `set_difference`, `set_intersection`, `sort`, `stable_sort`, `transform`, `transform_exclusive_scan`, `transform_inclusive_scan`,`transform_reduce`

Aşağıdakiler şu anda paralelleştirilmedi:

- Hedef donanımda belirgin bir paralellik performansı geliştirmesi yoktur; yalnızca dalları olmayan öğeleri oluşturan veya permute tüm algoritmalar genellikle bellek bant genişliği sınırlıdır:
  - `copy`, `copy_n`, `fill`, `fill_n`, `move`, `reverse`, `reverse_copy`, `rotate`, `rotate_copy`, `shift_left`, `shift_right`, `swap_ranges`
- Kullanıcı paralellik gereksinimleri üzerinde karışıklık var; büyük olasılıkla yukarıdaki kategoride:
  - `generate`, `generate_n`
- Etkin paralellik, uygun maliyetli şüpheli:
  - `partial_sort`, `partial_sort_copy`
- Henüz değerlendirilmedi; paralellik, gelecek bir sürümde uygulanabilir ve yararlı olması şüpheli:
  - `copy_if`, `includes`, `inplace_merge`, `lexicographical_compare`, `max_element`, `merge`, `min_element`, `minmax_element`, `nth_element`, `partition_copy`, `remove_copy`, `remove_copy_if`, `replace_copy`, `replace_copy_if`, `set_symmetric_difference`, `set_union`, `stable_partition`, `unique`,`unique_copy`

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)<br/>
[Visual Studio’deki C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md)<br/>
[Visual Studio 'daki görsele C++ yenilikler](what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Görsel C++ değişiklik geçmişi 2003 ile 2015 arasında](../porting/visual-cpp-change-history-2003-2015.md)<br/>
[Visual C++ 2003 ile 2015 Arasındaki Farklar](../porting/visual-cpp-what-s-new-2003-through-2015.md)<br/>
[C++Ekip Blogu](https://devblogs.microsoft.com/cppblog/)
