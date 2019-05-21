---
title: Microsoft C++ dil uyumluluğu tablosu
ms.date: 05/20/2019
ms.technology: cpp-language
ms.assetid: 475da6e9-0d78-4b4e-bd23-f41c406c4efe
author: corob-msft
ms.author: corob
ms.openlocfilehash: 994878509c4fc1bf14390fad8ff4c112a4af8242
ms.sourcegitcommit: a61d17cffdd50f1c3c6e082a01bbcbc85b6cc5a7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/21/2019
ms.locfileid: "65975173"
---
# <a name="microsoft-c-language-conformance-table"></a>Microsoft C++ dil uyumluluğu tablosu

Bu konuda, ISO C ++ 03, C ++ 11, C ++ 14, C ++ 17 ve Microsoft C ++ 20 dil standartlara uyumluluk derleyici özelliklerini ve standart kitaplık özellikleri özetlenmektedir C++ Visual Studio 2019 ve önceki sürümlerinde derleyici. Her derleyici ve standart kitaplığı özellik adı bağlantılar özelliği, bir yayın zaman olup olmadığını açıklayan ISO C++ standardı teklif kağıt. Özelliğin ilk göründüğü için desteklenen sütun destekleyen Visual Studio sürümünde listeler.

Uyumluluk geliştirmeleri ve Visual Studio 2017 veya Visual Studio 2019 diğer değişiklikler hakkında daha fazla bilgi için bu sayfanın üst sol sürüm Seçici ayarlayın ve ardından bkz [ C++ Visual Studio'da uyumluluk geliştirmeleri](cpp-conformance-improvements.md) ve [ Görsel için Yenilikler C++ Visual Studio'daki](what-s-new-for-visual-cpp-in-visual-studio.md). Önceki sürümlerde uyumluluk değişiklikleri için bkz. [Visual C++ değişiklik geçmişi](../porting/visual-cpp-change-history-2003-2015.md) ve [Visual C++ neler yeni 2003 ile 2015 arasındaki](../porting/visual-cpp-what-s-new-2003-through-2015.md). Geçerli haber için C++ ekip, ziyaret [ C++ ekip blogu](https://devblogs.microsoft.com/cppblog/).

> [!NOTE]
> Visual Studio 2015, Visual Studio 2017 ve Visual Studio 2019 arasında yeni değişiklikler hiçbir ikili dosya vardır.

## <a name="compiler-features"></a>Derleme özellikleri

|Özellik alanı| |
|----|---|
|__C ++ 03/11 çekirdek dil özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;Diğer her şey|VS 2015 <sup>[A](#note_A)</sup>|
|&nbsp;&nbsp;İki aşamalı ad arama|VS 2017 15.7 <sup>[B](#note_B)</sup>|
|&nbsp;&nbsp;[N2634 İfade SFINAE](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2634.html)|VS 2017 15.7|
|&nbsp;&nbsp;[N1653 C99 önişlemcisi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1653.htm)|Kısmi <sup> [C](#note_C)</sup>|
|__C ++ 14 çekirdek dil özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[Bağlamsal dönüştürmeleri için N3323 Tweaked ifadesi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3323.pdf)|VS 2013|
|&nbsp;&nbsp;[N3472 ikili sabit dizeler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3472.pdf)|VS 2015|
|&nbsp;&nbsp;[N3638 otomatik ve decltype(auto) dönüş türleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3638.html)|VS 2015|
|&nbsp;&nbsp;[N3648 init-yakalamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3648.html)|VS 2015|
|&nbsp;&nbsp;[N3649 genel lambda ifadeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3649.html)|VS 2015|
|&nbsp;&nbsp;[N3760 \[ \[kullanım dışı\] \] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3760.html)|VS 2015|
|&nbsp;&nbsp;[N3778 boyutlandırılmış ayırmayı kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3781 basamak ayırıcılar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3781.pdf)|VS 2015|
|&nbsp;&nbsp;[N3651 değişken şablonlar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3651.pdf)|VS 2015.2|
|&nbsp;&nbsp;[N3652 genişletilmiş constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)|VS 2017 15.0|
|&nbsp;&nbsp;[Toplamlar için N3653 varsayılan üye Başlatıcı](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3653.html)|VS 2017 15.0|
|__C ++ 17 çekirdek dil özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[Trigrafları N4086 kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)|VS 2010 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[İle küme ayraçlı başlatma listelerinde auto için N3922 yeni kurallar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Şablon Şablon parametrelerinde N4051 typename](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Ad alanlarında ve numaralandırıcılarda N4266 öznitelikleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4267 u8 karakter değişmez değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Ad alanı tanımları N4230 iç içe geçmiş](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4230.html)|VS 2015.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[N3928 Terse static_assert](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)|VS 2017 15.0 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0184R0 genelleştirilmiş aralık tabanlı for-döngüleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)|VS 2017 15.0 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0188R1 \[ \[fallthrough\] \] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r1.pdf)|VS 2017 15.0 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Register anahtar sözcüğü P0001R1 kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0002R1 kaldırma operator ++ bool için](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0018R3 yakalama * bu değere göre](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Yineleme olmadan öznitelik ad alanları P0028R4 kullanma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0028r4.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0061R1 \_ \_has_include](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0061r1.html)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0138R2 doğrudan-liste-init tamsayılar gelen sabit bir sabit listeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0170R1 constexpr lambdaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0170r1.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0189R1 \[ \[nodiscard\] \] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0189r1.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0212R1 \[ \[maybe_unused\] \] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0212r1.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0217R3 yapılandırılmış bağlamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0217r3.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0292R2 constexpr if-deyimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0292r2.html)|VS 2017 15.3 <sup>[D](#note_D)</sup>|
|&nbsp;&nbsp;[Başlatıcılar ile P0305R1 seçim deyimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0305r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0245R1 Hexfloat sabit değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0245r1.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[N4268 izin vererek daha fazla tür olmayan şablon bağımsız değişkenleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4268.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[N4295 Katlama ifadeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4295.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Belirtimlere dinamik P0003R5 kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Tür sisteminde noexcept P0012R1 ekleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0012r1.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0035R4 aşırı hizalanmış dinamik bellek ayırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0035r4.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0386R2 satır içi değişkenler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0386r2.pdf)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0522R0 eşleşen şablon şablon-parametre uyumlu bağımsız değişkenleri için](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0522r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0036R0 kaldırma bazı boş birli hatları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0036r0.pdf)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Nitelik dönüştürme N4261 düzeltme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4261.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Genişletilmiş P0017R1 toplu başlatma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Sınıf şablonları P0091R3 şablon bağımsız değişken kesintisi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)<br/>&nbsp;&nbsp;[P0512R0 sınıf şablonu bağımsız değişkeni kesintisi sorunları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0512r0.pdf)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Otomatik tür olmayan şablon parametreleri P0127R2 bildirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0135R1 garantili kopya eleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0135r1.html)|VS 2017 15.6|
|&nbsp;&nbsp;[Oluşturucuların devralınması P0136R1 yeni ifade biçimiyle](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0137R1 std::launder](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0137r1.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[İfade değerlendirme sırası P0145R3 iyileştirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0145r3.pdf)<br/>&nbsp;&nbsp;[İşlev bağımsız değişkenlerinin değerlendirme P0400R0 sırası](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0400r0.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Using-declarations içinde P0195R2 paket genişletmeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0195r2.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Tanınmayan P0283R2 yoksayılıyor öznitelikleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0283r2.html)|VS 2015 <sup>[14](#note_14)</sup>|


|Özellik alanı| |
|----|---|
|__(Hata raporları) c ++ 17 çekirdek dil özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[Başlatıcı listesi oluşturucuları için sınıfın şablon bağımsız değişkeni kesintisi P0702R1 düzeltme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0702r1.html)|VS 2017 15.7 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Bulma kuralları noktası P0961R1 gevşetme yapılandırılmış bağlamalar özelleştirme](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0961r1.html)|VS 2019 16.0 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Erişilebilir üyeler bağlamaları yapılandırılmış P0969R0 izin verme](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0969r0.pdf)|VS 2019 16.0 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Örtük lambda yakalama P0588R1 basitleştirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0588r1.html)|Hayır|
|&nbsp;&nbsp;[P0962R2 gevşetme aralığı-döngü özelleştirme noktası bulma kuralları](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0962r1.html)|Hayır|
|&nbsp;&nbsp;[Soyut sınıf türleri için P0929R2 denetleniyor](https://wg21.link/P0929R2)|Hayır|
|&nbsp;&nbsp;[Yeni ifadelerde P1009R2 dizi boyutu kesintisi](https://wg21.link/P1009R2)|Hayır|
|&nbsp;&nbsp;[P1286R2 karşıt CWG DR1778](https://wg21.link/P1286R2)|Hayır|
|Özellik alanı| |
|----|---|
|__C ++ 20 çekirdek dil özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[P0704R1 düzeltme const lvalue başvuru nitelikli üye işaretçileri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0704r1.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[UTF-16/32 P1041R4 olun char16_t/char32_t dize değişmez değerleri olabilir](https://wg21.link/P1041R4)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Bir birleşimin constexpr içinde etkin üyesi P1330R0 değiştirme](https://wg21.link/P1330R0)|VS 2017 15.0 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[İçin P0972R0 noexcept \<chrono > zero(), MIN() max()](https://wg21.link/P0972R0)|VS 2017 15.7 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0515R3 üç yönlü (savaş Gemisi) karşılaştırma işleci <> =](https://wg21.link/P0515R3)|VS 2019 16.0 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[Kullanıcı olarak bildirilen oluşturuculara sahip P1008R1 yasaklanması toplamaları](https://wg21.link/P1008R1)|VS 2019 16.0 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0329R4 belirtilen başlatma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[Lambda-capture P0409R2 izin vererek \[=, bu\]](http://open-std.org/JTC1/SC22/WG21/docs/papers/2017/p0409r2.html)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0515R3 üç yönlü (savaş Gemisi) karşılaştırma işleci <> =](https://wg21.link/P0515R3)|VS 2019 16.0 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0941R2 özellik testi makroları](https://wg21.link/P0941R2)|VS 2019 16.0 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Kullanıcı olarak bildirilen oluşturuculara sahip P1008R1 yasaklanması toplamaları](https://wg21.link/P1008R1)|VS 2019 16.0 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[Görünmez P0846R0 ADL ve işlev şablonları](https://wg21.link/P0846R0)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[Varsayılan olarak ayarlanmış bir kopya Oluşturucu P0641R2 const uyuşmazlığı](https://wg21.link/P0641R2)|Kısmi|
|&nbsp;&nbsp;[P0306R4 ekleme \_ \_VA_OPT\_ \_ virgülle atlama ve virgül silme](https://wg21.link/P0306R4)|Hayır|
|&nbsp;&nbsp;[Değerlendirilmemiş bağlamlarda lambdalar P0315R4 izin verme](https://wg21.link/P0315R4)|Hayır|
|&nbsp;&nbsp;[Lambda-capture P0409R2 izin vererek \[=, bu\]](https://wg21.link/P0409R2)|Hayır|
|&nbsp;&nbsp;[Genel lambda ifadeleri için P0428R2 tanıdık şablon söz dizimi](http://www.open-std.org/jtc1/sc22/wg21/docs/pa pers/2017/p0428r2.pdf)|Hayır|
|&nbsp;&nbsp;[P0479R5 \[ \[büyük olasılıkla\] \] ve \[ \[olası\] \] öznitelikleri](https://wg21.link/P0479R5)|Hayır|
|&nbsp;&nbsp;[P0542R5 sözleşmeleri](https://wg21.link/P0542R5)|Hayır|
|&nbsp;&nbsp;[P0614R1 aralık tabanlı for-döngüleri başlatıcıları olan](https://wg21.link/P0614R1)|Hayır|
|&nbsp;&nbsp;[P0624R2 varsayılan atmamalıdır ve atanabilir durum bilgisiz lambdalar](https://wg21.link/P0624R2)|Hayır|
|&nbsp;&nbsp;[P0634R3 aşağı typename ile!](https://wg21.link/P0634R3)|Hayır|
|&nbsp;&nbsp;[Bit alanları için P0683R1 varsayılan üye Başlatıcı](https://wg21.link/P0683R1)|Hayır|
|&nbsp;&nbsp;[P0692R1 gevşetme erişim uzmanlıkları üzerinde denetleniyor](https://wg21.link/P0692R1)|Hayır|
|&nbsp;&nbsp;[Değişken için P0722R3 boyutlandırılmış verimli silme sınıfları boyutu](https://wg21.link/P0722R3)|Hayır|
|&nbsp;&nbsp;[Tür olmayan şablon parametreleri P0732R2 sınıf türleri](https://wg21.link/P0732R2)|Hayır|
|&nbsp;&nbsp;[P0734R0 kavramları](https://wg21.link/P0734R0)|Hayır|
|&nbsp;&nbsp;[Lambda init-capture içinde paket genişletmesi P0780R2 izin verme](https://wg21.link/P0780R2)|Hayır|
|&nbsp;&nbsp;[Bu örtük yakalama P0806R2 kullanımdan kaldırma \[=\]](https://wg21.link/P0806R2)|Hayır|
|&nbsp;&nbsp;[P0840R2 \[ \[no_unique_address\] \] özniteliği](https://wg21.link/P0840R2)|Hayır|
|&nbsp;&nbsp;[İşlevselliği boşlukları P0857R0 düzeltme kısıtlamaları](https://wg21.link/P0857R0)|Hayır|
|&nbsp;&nbsp;[P0892R2 koşullu açık](https://wg21.link/P0892R2)|Hayır|
|&nbsp;&nbsp;[P0912R5 eş yordamlar](https://wg21.link/P0912R5)|Hayır|
|&nbsp;&nbsp;[Değerlerini parantez içine alınmış listesinden toplamaları başlatma P0960R3 izin ver](https://wg21.link/P0960R3)|Hayır|
|&nbsp;&nbsp;[Constexpr işlevlerinde P1002R1 try-catch blokları](https://wg21.link/P1002R1)|Hayır|
|&nbsp;&nbsp;[Sabit ifadelerde P1064R0 sağlayan sanal işlev çağrıları](https://wg21.link/P1064R0)|Hayır|
|&nbsp;&nbsp;[P1073R3 hemen işlevleri](https://wg21.link/P1073R3)|Hayır|
|&nbsp;&nbsp;[P1084R2 Bugün'in return-türü-gereksinimleri yeterli değil](https://wg21.link/P1084R2)|Hayır|
|&nbsp;&nbsp;[Bağlamaları değişken bildirimleri gibi daha fazla olacak şekilde yapılandırılmış P1091R3 genişletme](https://wg21.link/P1091R3)|Hayır|
|&nbsp;&nbsp;[Satır içi ad alanları P1094R2 iç içe geçmiş](https://wg21.link/P1094R2)|Hayır|
|&nbsp;&nbsp;[P1103R3 modülleri](https://wg21.link/P1103R3)|Hayır|
|&nbsp;&nbsp;[<> = İçin P1120R0 tutarlılık geliştirmeleri ve diğer Karşılaştırma işleçleri](https://wg21.link/P1120R0)|Hayır|
|&nbsp;&nbsp;[ISO 10646 için ilgili P1139R2 adresi ifadesi sorunları](https://wg21.link/P1139R2)|Hayır|
|&nbsp;&nbsp;[Bildirimleri P1141R2 henüz başka bir yaklaşım için kısıtlı](https://wg21.link/P1141R2)|Hayır|
|&nbsp;&nbsp;[P1185R2 \<=\> != ==](https://wg21.link/P1185R2)|Hayır|
|&nbsp;&nbsp;[P1236R1 imzalı tamsayı iki tamamlayıcısı olduğunu](https://wg21.link/P1236R1)|Hayır|
|&nbsp;&nbsp;[Sözleşme koşullarını P1289R1 erişim denetimi](https://wg21.link/P1289R1)|Hayır|
|&nbsp;&nbsp;[P1323R2 sözleşme koşul sonralarına ve dönüş türü çıkarma](https://wg21.link/P1323R2)|Hayır|
|&nbsp;&nbsp;[Dynamic_cast, sabit ifadeler çok biçimli TypeID P1327R1 izin verme](https://wg21.link/P1327R1)|Hayır|
|&nbsp;&nbsp;[Özellik testi makroları P1353R0 eksik](https://wg21.link/P1353R0)|Hayır|
|&nbsp;&nbsp;[Yapılandırılmış bağlamalar P1381R1 başvuru yakalama](https://wg21.link/P1381R1)|Hayır|

## <a name="standard-library-features"></a>Standart kitaplık özellikleri

|Özellik alanı| |
|---|---|
|__C ++ 20 standart kitaplık özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[Kapsayıcıları sırasız P0809R0 karşılaştırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0809r0.pdf)| VS 2010 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0858R0 Constexpr yineleyici gereksinimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0858r0.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Gereksiz Decay P0777R1 kaçınma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0777r1.pdf)|VS 2017 15.7 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0550R2 remove_cvref](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf)|VS 2019 16.0 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0318R1 unwrap_reference, unwrap_ref_decay](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0318r1.pdf)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[Basic_string/basic_string_view için P0457R2 starts_with()/ends_with()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0457r2.html)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[Sıralı ve sırasız ilişkili kapsayıcılar için P0458R2 contains()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0458r2.html)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0646R1 list/forward_list remove()/remove_if()/unique() Return size_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0646r1.pdf)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0769R2 shift_left(), shift_right()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0769r2.pdf)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0887R1 type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf)|VS 2019 16.1 <sup>[20](#note_20)</sup>|
|&nbsp;&nbsp;[P0019R8 atomic_ref](https://wg21.link/P0019R8)|Hayır|
|&nbsp;&nbsp;[Atomik P0020R6\<float > atomik\<çift > atomik\<uzun çift >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0020r6.html)|Hayır|
|&nbsp;&nbsp;[P0053R7 \<syncstream >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0053r7.pdf)<br/>&nbsp;&nbsp;[P0753R2 osyncstream Manipülatörleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0753r2.pdf)|Hayır|
|&nbsp;&nbsp;[P0122R7 \<span>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0122r7.pdf)|Hayır|
|&nbsp;&nbsp;[P0202R3 constexpr için \<algoritma > ve exchange()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0202r3.html)|Hayır|
|&nbsp;&nbsp;[P0339R6 polymorphic_allocator <>](https://wg21.link/P0339R6)|Hayır|
|&nbsp;&nbsp;[P0340R3 SFINAE dostu underlying_type](https://wg21.link/P0340R3)|Hayır|
|&nbsp;&nbsp;[P0355R7 \<chrono > Takvim ve saat dilimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0355r7.html)|Hayır|
|&nbsp;&nbsp;[P0356R5 bind_front()](https://wg21.link/P0356R5)|Hayır|
|&nbsp;&nbsp;[Reference_wrapper P0357R3 destekleyen eksik türleri olarak](https://wg21.link/P0357R3)|Hayır|
|&nbsp;&nbsp;[P0415R1 constexpr için \<karmaşık > (yeniden)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0415r1.html)|Hayır|
|&nbsp;&nbsp;[P0439R0 enum sınıfı memory_order](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0439r0.html)|Hayır|
|&nbsp;&nbsp;[P0463R1 endian](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0463r1.html)|Hayır|
|&nbsp;&nbsp;[P0475R1 garantili kopya eleme Piecewise yapı için](https://wg21.link/P0475R1)|Hayır|
|&nbsp;&nbsp;[P0476R2 <bit> bit_cast](https://wg21.link/P0476R2)|Hayır|
|&nbsp;&nbsp;[P0482R6 char8_t: UTF-8 karakter ve dize için bir tür](https://wg21.link/P0482R6)|Hayır|
|&nbsp;&nbsp;[İşleç P0487R1 düzeltme >> (basic_istream &, grafik *)](https://wg21.link/P0487R1)|Hayır|
|&nbsp;&nbsp;[P0528R3 atomik karşılaştırma ve-bit doldurma ile Exchange](https://wg21.link/P0528R3)|Hayır|
|&nbsp;&nbsp;[P0556R3 <bit> ispow2(), ceil2(), floor2(), log2p1()](https://wg21.link/P0556R3)|Hayır|
|&nbsp;&nbsp;[P0591R4 kullandığı ayırıcı oluşturma için yardımcı işlevleri](https://wg21.link/P0591R4)|Hayır|
|&nbsp;&nbsp;[P0600R1 \[ \[nodiscard\] \] STL için bölüm 1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0600r1.pdf)|Hayır|
|&nbsp;&nbsp;[P0608R3 geliştirme değişken'ın dönüştürme Oluşturucusu/atama](https://wg21.link/P0608R3)|Hayır|
|&nbsp;&nbsp;[İçinde P0616R0 kullanarak move() \<sayısal >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0616r0.pdf)|Hayır|
|&nbsp;&nbsp;[P0619R4 kaldırma C ++ 17-kullanım dışı bırakılan özellikler içinde C ++ 20](https://wg21.link/P0619R4)|Hayır|
|&nbsp;&nbsp;[P0653R2 to_address()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0653r2.html)|Hayır|
|&nbsp;&nbsp;[P0655R1 ziyaret<R>)](https://wg21.link/P0655R1)|Hayır|
|&nbsp;&nbsp;[Diziler için P0674R1 make_shared()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0674r1.html)|Hayır|
|&nbsp;&nbsp;[Atomik P0718R2\<shared_ptr\<T >> atomik\<weak_ptr\<T >>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0718r2.html)|Hayır|
|&nbsp;&nbsp;[P0738R2 istream_iterator temizleme](https://wg21.link/P0738R2)|Hayır|
|&nbsp;&nbsp;[P0754R2 \<sürüm >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0754r2.pdf)|Hayır|
|&nbsp;&nbsp;[P0758R1 is_nothrow_convertible](https://wg21.link/P0758R1)|Hayır|
|&nbsp;&nbsp;[İs_pod P0767R1 kullanım dışı bırakılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0767r1.html)|Hayır|
|&nbsp;&nbsp;[P0768R1 savaş Gemisi karşılaştırma işleci için kitaplık desteği \<=>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0768r1.pdf)|Hayır|
|&nbsp;&nbsp;[Std::function'ın taşıma oluşturucusu için P0771R1 noexcept](https://wg21.link/P0771R1)|Hayır|
|&nbsp;&nbsp;[P0811R3 midpoint(), lerp()](https://wg21.link/P0811R3)|Hayır|
|&nbsp;&nbsp;[P0879R0 constexpr için işlevleri değiştirme](https://wg21.link/P0879R0)|Hayır|
|&nbsp;&nbsp;[P0896R4 \<aralıkları\>](https://wg21.link/P0896R4)|Hayır|
|&nbsp;&nbsp;[P0898R3 standart kitaplığı kavramları](https://wg21.link/P0898R3)|Hayır|
|&nbsp;&nbsp;[Eş yordamlar için P0912R5 kitaplık desteği](https://wg21.link/P0912R5)|Hayır|
|&nbsp;&nbsp;[Sırasız kapsayıcılar için heterojen arama P0919R3](https://wg21.link/P0919R3)|Hayır|
|&nbsp;&nbsp;[Karma değer arama P0920R2 önceden](https://wg21.link/P0920R2)|Hayır|
|&nbsp;&nbsp;[Gereksiz açık P0935R0 Eradicating varsayılan oluşturucular](https://wg21.link/P0935R0)|Hayır|
|&nbsp;&nbsp;[P0966R1 dize:: reserve() küçültme değil](https://wg21.link/P0966R1)|Hayır|
|&nbsp;&nbsp;[P1001R2 execution::unseq](https://wg21.link/P1001R2)|Hayır|
|&nbsp;&nbsp;[P1006R1 constexpr için pointer_traits < T * >:: pointer_to()](https://wg21.link/P1006R1)|Hayır|
|&nbsp;&nbsp;[P1007R3 assume_aligned()](https://wg21.link/P1007R3)|Hayır|
|&nbsp;&nbsp;[Varsayılan başlatma ile P1020R1 akıllı işaretçi oluşturma](https://wg21.link/P1020R1)|Hayır|
|&nbsp;&nbsp;[P1023R0 constexpr std::array karşılaştırmaları için](https://wg21.link/P1023R0)|Hayır|
|&nbsp;&nbsp;[P1032R1 çeşitli constexpr](https://wg21.link/P1032R1)|Hayır|
|&nbsp;&nbsp;[P1165R1 tutarlı bir şekilde yayma durum bilgisi olan ayırıcıların içinde basic_string's operator+()](https://wg21.link/P1165R1)|Hayır|
|&nbsp;&nbsp;[P1209R0 erase_if(), erase()](https://wg21.link/P1209R0)|Hayır|
|&nbsp;&nbsp;[P1227R2 imzalı std::ssize(), işaretsiz span:: size()](https://wg21.link/P1227R2)|Hayır|
|&nbsp;&nbsp;[Tür özellikleri için P1285R0 bütünlük gereksinimlerini geliştirme](https://wg21.link/P1285R0)|Hayır|
|&nbsp;&nbsp;[P1357R1 is_bounded_array, is_unbounded_array](https://wg21.link/P1357R1)|Hayır|
|__C ++ 17 standart kitaplığı özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[Nullptr LWG 2221 biçimlendirilmiş çıkış işleci](https://cplusplus.github.io/LWG/issue2221)|VS 2019 16.1|
|&nbsp;&nbsp;[N3911 void_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3911.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Unique_ptr N4089 güvenli dönüştürmeler de\<T [] >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4089.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4169 olması](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4169.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4190 kaldırma auto_ptr, random_shuffle() ve eski \<işlevsel > öğe](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4190.htm)|VS 2015 <sup> [rem](#note_rem)</sup>|
|&nbsp;&nbsp;[N4258 noexcept Göndermediklerini](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4258.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4259 uncaught_exceptions()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4259.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4277 artık önemsiz olarak kopyalanabilir reference_wrapper](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4277.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Map/unordered_map için N4279 insert_or_assign()/try_emplace() işlevini](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4279.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4280 size(), empty() data()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4280.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Unique_ptr atama N4366 kesin bir şekilde sınırlama](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4366.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Çifti N4387 geliştirme ve demet](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4387.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4389 bool_constant](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4389.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4508 shared_mutex (Untimed)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4508.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4510 destekleyen eksik türleri, vektör/listesi/forward_list](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4510.html)|VS 2013 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<algoritma > sample()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#alg.random.sample)|VS 2017 15.0|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<herhangi >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#any)|VS 2017 15.0|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<memory_resource >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#memory.resource.synop)<br/>&nbsp;&nbsp;[Polymorphic_allocator atama P0337R0 siliniyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0337r0.html)|VS 2017 15.6|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<isteğe bağlı >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#optional)|VS 2017 15.0|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<string_view >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#string.view)|VS 2017 15.0|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<demet > apply()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#tuple)|VS 2017 15.0|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: Boyer-Moore search()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#func.searchers.boyer_moore)<br/>&nbsp;&nbsp;[P0253R1 düzeltme noktasıdır dönüş türleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0253r1.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0003R5 dinamik özel durum belirtimleri kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Kullanım dışı Iostreams Aliases P0004R1 kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0004r1.html)|VS 2015.2 <sup> [rem](#note_rem)</sup>|
|&nbsp;&nbsp;[P0005R4 not_fn()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html)<br/>&nbsp;&nbsp;[Not_fn() P0358R1 düzeltmelerin](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0006R0 değişken şablonlar için türü nitelikler (is_same_v, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0006r0.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0007R1 as_const()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0007r1.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0013R1 mantıksal işleç türü nitelikler (birlikte, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0013r1.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0024R2 paralel algoritmalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html)<br/>&nbsp;&nbsp;[Paralel yürütme ilkeleri P0336R1 yeniden adlandırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0336r1.pdf)<br/>&nbsp;&nbsp;[Paralel algoritmalar P0394R4 terminate() için özel durumları gerekir.](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0394r4.html)<br/>&nbsp;&nbsp;[P0452R1 birleştirme \<sayısal > paralel algoritmalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0452r1.html)|VS 2017 15.7|
|&nbsp;&nbsp;[P0025R1 clamp()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0025r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0030R1 hypot (x, y, z)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf)|VS 2017 15.7|
|&nbsp;&nbsp;[P0031R0 constexpr için \<array > (yeniden) ve \<yineleyici >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0031r0.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0032R3 homojen arabirimi için değişken/any/isteğe bağlı](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0032r3.pdf)|VS 2017 15.0|
|&nbsp;&nbsp;[Enable_shared_from_this P0033R1 yeni ifade biçimiyle](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html)|VS 2017 15.5 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0040R3 genişletme bellek yönetimi araçları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0040r3.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0063R3 C11 standart kitaplığı](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0063r3.html)|VS 2015 <sup>[C11](#note_C11), [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0067R5 temel dize dönüştürme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html)|VS 2017 15.7 <sup> [charconv](#note_charconv)</sup>|
|&nbsp;&nbsp;[P0074R0 owner_less\<>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0074r0.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0077R2 is_callable, is_nothrow_callable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0077r2.html)|VS 2017 15.0|
|&nbsp;&nbsp;[P0083R3 boşluklarına ayıran Haritalar ve kümeler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)<br/>&nbsp;&nbsp;[P0508R0 açıklığa kavuşturan insert_return_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0084R2 Emplace dönüş türü](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0084r2.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0088R3 \<değişken >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0088r3.html)|VS 2017 15.0|
|&nbsp;&nbsp;[P0092R1 \<chrono > floor(), ceil(), round(), abs()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0092r1.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0152R1 atomic::is_always_lock_free](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0152r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0154R1 hardware_destructive_interference_size, vb.](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0154r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Lock_guard P0156R0 değişen sayıda bağımsız değişken](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0156r0.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Yeniden adlandırma P0156R2 Variadic kilit\_koruma sağlamak üzere kapsamlı\_Kilitle](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0156r2.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0163R0 shared_ptr::weak_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0163r0.html)|VS 2017 15.0|
|&nbsp;&nbsp;[P0174R2 işlevini kaybetmiş kitaplık parçaları kullanımdan kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0185R1 is_swappable, is_nothrow_swappable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0185r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0209R2 make_from_tuple()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0209r2.pdf)|VS 2017 15.0|
|&nbsp;&nbsp;[P0218R1 \<filesystem >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html)<br/>&nbsp;&nbsp;[Dosya sistemi için P0219R1 göreli yolları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0219r1.html)<br/>&nbsp;&nbsp;[Dosya sistemi için önbelleğe alma P0317R1 dizin girdisi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0317r1.html)<br/>&nbsp;&nbsp;[P0392R0 destekleyen string_view, dosya sistemi yolları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0392r0.pdf)<br/>&nbsp;&nbsp;[P0430R2 destekleyen olmayan POSIX dosya sistemleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0430r2.pdf)<br/>&nbsp;&nbsp;[Dosya sistemi için P0492R2 NB yorum çözümleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0492r2.html)|VS 2017 15.7 <sup>[E](#note_E)</sup>|
|&nbsp;&nbsp;[P0220R1 kitaplığı temelleri V1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html)|VS 2017 15.6|
|&nbsp;&nbsp;[P0226R1 özel matematik işlevleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0226r1.pdf)|VS 2017 15.7|
|&nbsp;&nbsp;[String_view P0254R2 tümleştirme ve std::string](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0254r2.pdf)|VS 2017 15.0|
|&nbsp;&nbsp;[P0258R2 has_unique_object_representations](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0258r2.html)|VS 2017 15.3 <sup>[G](#note_G)</sup>|
|&nbsp;&nbsp;[P0272R1 Non-const basic_string::data()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0272r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0295R0 gcd(), lcm()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0295r0.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0298R3 std::byte](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0298r3.pdf)|VS 2017 15.3 <sup>[17](#note_17),&nbsp;[byte](#note_byte)</sup>|
|&nbsp;&nbsp;[Std::function P0302R1 kaldırma ayırıcı desteği de](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0307R2 yapma isteğe bağlı büyük eşittir yeniden](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0307r2.pdf)|VS 2017 15.0|
|&nbsp;&nbsp;[Değişken büyük eşittir P0393R3 yapma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0393r3.html)|VS 2017 15.0|
|&nbsp;&nbsp;[P0403R1 Udl'ler için \<string_view > ("meow" sv, vs.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0403r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0414R2 shared_ptr\<T [] >, shared_ptr\<T [N] >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html)<br/>&nbsp;&nbsp;[Shared_ptr P0497R0 düzeltmek için diziler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html)|VS 2017 15.5 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0418R2 atomik compare_exchange memory_order gereksinimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0418r2.html)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Char_traits için P0426R1 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html)|VS 2017 15.7|
|&nbsp;&nbsp;[P0433R2 tümleştirme şablon kesintisi sınıf şablonları standart kitaplığa](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html)<br/>&nbsp;&nbsp;[Standart kitaplığa sınıf şablonu bağımsız değişkeni kesintisi tümleştirme P0739R0 geliştirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html)|VS 2017 15.7|
|&nbsp;&nbsp;[Common_type P0435R1 elden](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0435r1.pdf)<br/>&nbsp;&nbsp;[Ortak P0548R1 ince ayar yapma\_türü ve süresi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0548r1.pdf)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0504R0 da in_place_t/in_place_type_t\<T > / in_place_index_t\<miyim >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0504r0.html)|VS 2017 15.0|
|&nbsp;&nbsp;[P0505R0 constexpr için \<chrono > (yeniden)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0505r0.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0510R0 reddetme çeşitleri, Nothing, diziler, başvurular ve eksik türler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0510r0.html)|VS 2017 15.0|
|&nbsp;&nbsp;[P0513R0 zehirleme karması](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0513r0.pdf)<br/>&nbsp;&nbsp;[P0599R1 noexcept karması](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0599r1.pdf)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Shared_future noexcept kopyalama olarak P0516R0 işaretleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0516r0.html)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Future_errc gelen future_error P0517R0 oluşturma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0517r0.html)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Shared_ptr::unique() P0521R0 kullanım dışı bırakılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0521r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0558R1 çözümleme atomik\<T > adlı temel sınıf tutarsızlıklar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0558r1.pdf)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0595R2 std::is_constant_evaluated()](https://wg21.link/P0595R2)|Hayır|
|&nbsp;&nbsp;[P0602R4 yayma kopyalama/taşıma Triviality içinde variant/isteğe bağlı](https://wg21.link/P0602R4)|VS 2017 15.3<sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0604R0 değiştirme\_çağrılabilir/sonuç\_, çağrılacak\_olduğu, neden\_çağrılmayan, olan\_nothrow\_çağrılmayan](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0604r0.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Standart kitaplık için P0607R0 satır içi değişkenler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0618R0 kullanımdan \<codecvt >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0618r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0682R1 onarma temel dize dönüştürme](https://wg21.link/P0682R1)|VS 2015 15.7 <sup>[17](#note_17)</sup>|
|__C ++ 14 standart kitaplık özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[N3462 SFINAE dostu result_of](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3462.html)|VS 2015.2|
|&nbsp;&nbsp;[N3302 constexpr için \<karmaşık >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2011/n3302.html)|VS 2015|
|&nbsp;&nbsp;[N3469 constexpr için \<chrono >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3469.html)|VS 2015|
|&nbsp;&nbsp;[N3470 constexpr için \<array >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3470.html)|VS 2015|
|&nbsp;&nbsp;[N3471 constexpr için \<initializer_list >, \<demet >, \<yardımcı programı >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3471.html)|VS 2015|
|&nbsp;&nbsp;[N3545 integral_constant::operator()()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3545.pdf)|VS 2015|
|&nbsp;&nbsp;[N3642 Udl'ler için \<chrono >, \<dizesi > (1729ms, "meow" s, vs.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3642.pdf)|VS 2015|
|&nbsp;&nbsp;[N3644 Null İleri yineleyiciler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3644.pdf)|VS 2015|
|&nbsp;&nbsp;[N3654 quoted()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3654.html)|VS 2015|
|&nbsp;&nbsp;[N3657 Heterojen ilişkili arama](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3657.htm)|VS 2015|
|&nbsp;&nbsp;[N3658 integer_sequence](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3658.html)|VS 2015|
|&nbsp;&nbsp;[N3659 shared_mutex (zamanlanmış)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3659.html)|VS 2015|
|&nbsp;&nbsp;[N3668 exchange()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3668.html)|VS 2015|
|&nbsp;&nbsp;[Üye işlevleri olmadan const constexpr N3669 düzeltme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3669.pdf)|VS 2015|
|&nbsp;&nbsp;[N3670 get\<T>()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3670.html)|VS 2015|
|&nbsp;&nbsp;[N3671 Çift aralıklı equal(), is_permutation(), mismatch()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3671.html)|VS 2015|
|&nbsp;&nbsp;[N3778 Boyutlandırılmış ayırmayı kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3779 Udl'ler için \<karmaşık > (3.14i, vs.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3779.pdf)|VS 2015|
|&nbsp;&nbsp;[N3789 constexpr için \<işlev >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3789.htm)|VS 2015|
|&nbsp;&nbsp;[N3887 tuple_element_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3887.pdf)|VS 2015|
|&nbsp;&nbsp;[Shared_mutex (zamanlanmış) shared_timed_mutex için N3891 yeniden adlandırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3891.htm)|VS 2015|
|&nbsp;&nbsp;[N3346 En az bir kapsayıcı öğe gereksinimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3346.pdf)|VS 2013|
|&nbsp;&nbsp;[N3421 saydam işleç işlev nesneleri (daha az\<> vb..)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3421.htm)|VS 2013|
|&nbsp;&nbsp;[N3655 diğer ad şablonları için \<type_traits > (decay_t, vs.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3655.pdf)|VS 2013|
|&nbsp;&nbsp;[N3656 make_unique()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3656.htm)|VS 2013|

Bir grup İnceleme birlikte listelenen özellik standart oy ve ardından artırmak veya bu özelliği genişletmek için bir veya daha fazla inceleme de oy gösterir. Bu özellikler birlikte uygulanır.

### <a name="supported-values"></a>Desteklenen değerler

__Hayır__ henüz uygulanmadı anlamına gelir.<br/>
__Kısmi__ uygulama eksik olduğu anlamına gelir. Daha fazla ayrıntı için Notlar bölümüne bakın.<br/>
__VS 2010__ Visual Studio 2010'da desteklenen özellikleri gösterir.<br/>
__VS 2013__ Visual Studio 2013'te desteklenen özellikleri gösterir.<br/>
__VS 2015__ Visual Studio 2015 RTW'de desteklenmeyen özellikleri gösterir.<br/>
__VS 2015.2__ ve __VS 2015.3__ Visual Studio 2015 güncelleştirme 2 ile Visual Studio 2015 güncelleştirme 3, sırasıyla desteklenmeyen özellikleri gösterir.<br/>
__VS 2017 15.0__ Visual Studio 2017 sürüm 15.0 (RTW) desteklenmeyen özellikleri gösterir.<br/>
__VS 2017 15.3__ Visual Studio 2017 sürüm 15.3 desteklenmeyen özellikleri gösterir.<br/>
__VS 2017 15.5__ Visual Studio 2017 sürüm 15.5 desteklenmeyen özellikleri gösterir.<br/>
__VS 2017 15.7__ Visual Studio 2017 sürüm 15.7 sürümünde desteklenmeyen özellikleri gösterir.<br/>
__VS 2019 16,0__ Visual Studio 2019 sürüm 16,0 (RTW) desteklenmeyen özellikleri gösterir.<br/>
__VS 2019 16.1__ Visual Studio 2019 sürüm 16.1 desteklenmeyen özellikleri gösterir.<br/>

### <a name="notes"></a>Notlar

<a name="note_A"></a>__A__ içinde [/Std: c ++ 14](../build/reference/std-specify-language-standard-version.md) modda dinamik özel durum belirtimleri dahi kalır ve `throw()` eşanlamlısı olarak kabul edilir `__declspec(nothrow)`. C ++ 17'de, çıkmadan bir vestige P0003R5 tarafından çoğunlukla dinamik özel durum belirtimleri kaldırıldı: `throw()` kullanım dışıdır ve eşanlamlısı olarak davranacak şekilde gerekli `noexcept`. İçinde [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) modu MSVC artık uyumlu standart vererek `throw()` aynı davranışı `noexcept`, yani sonlandırma aracılığıyla zorlama.

Derleyici seçeneği [/ZC: noexcepttypes](../build/reference/zc-noexcepttypes.md) bizim eski davranışını istekleri `__declspec(nothrow)`. Büyük olasılıkla, `throw()` C ++ 20 kaldırılacak. Geçiş konusunda yardımcı olmak için standart ve özel durum belirtimi sorunlar için yeni Derleyici uyarılarını kararlılığımızın bu değişikliklere yanıt kodu eklenmiştir altında [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) ve [/permissive-](../build/reference/permissive-standards-conformance.md).

<a name="note_B"></a>__B__ desteklenen [/ permissive-](../build/reference/permissive-standards-conformance.md) Visual Studio 2017 sürüm 15.7 modunda. Bkz: [MSVC için iki aşamalı ad arama desteği geldi](https://blogs.msdn.microsoft.com/vcblog/2017/09/11/two-phase-name-lookup-support-comes-to-msvc/) daha fazla bilgi için.

<a name="note_C"></a>__C__ C99 önişlemci kuralları için derleyici desteği, Visual Studio 2017'de eksik. Variadic makrolar desteklenir ancak önişlemci'nin davranışını birçok hataları vardır. Biz önişlemci elden ve bu değişiklikleri altında experimentally sevk edilir [/ permissive-](../build/reference/permissive-standards-conformance.md) yakında modu.

<a name="note_D"></a>__D__ altında desteklenen [/Std: c ++ 14](../build/reference/std-specify-language-standard-version.md) C4984 suppressible bir uyarıyla.

<a name="note_E"></a>__E__ , önceki ile uyumsuz tamamen yeni bir uygulama budur `std::experimental` sembolik bağlantısını desteği, hata düzeltmeleri ve standart gerekli davranışında değişiklik olmaması sürümü. Şu anda dahil olmak üzere \<filesystem > Yeni sağlar `std::filesystem` ve önceki `std::experimental::filesystem`, dahil olmak üzere \<Deneysel/dosya sistemi > yalnızca eski Deneysel uygulamasını sağlar. Deneysel uygulama KALDIRILACAK kitaplıkları sonraki ABI en son sürümünde.

<a name="note_G"></a>__G__ iç derleyici tarafından desteklenir.

<a name="note_14"></a>__14__ bu C ++ 17/20 özellikler her zaman etkindir, bile [/Std: c ++ 14](../build/reference/std-specify-language-standard-version.md) (varsayılan) belirtilir. Başlamadan önce uygulanan bir özellik ya da olmasıdır **/Std** seçenekleri veya koşullu uygulama açabileceğinin karmaşıktı.

<a name="note_17"></a>__17__ bu özellikler tarafından etkinleştirilen [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) (veya [/Std: c ++ Son](../build/reference/std-specify-language-standard-version.md)) derleyici seçeneği.

<a name="note_20"></a>__20__ bu özellikler tarafından etkinleştirilen [/Std: c ++ Son](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği. C ++ 20 uygulama tamamlandığında, yeni bir **/Std: c ++ 20** derleyici seçeneği eklenecek, altında bu özellikler de kullanılabilir olur.

<a name="note_byte"></a>__bayt__ `std::byte` etkinleştirilir [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) (veya [/Std: c ++ Son](../build/reference/std-specify-language-standard-version.md)), ancak bazı durumlarda Windows SDK'sı üst bilgileri ile çakışabileceği için ayrıntılı çevirme makro sahiptir. Bunu tanımlayarak devre dışı bırakılabilir `_HAS_STD_BYTE` olarak `0`.

<a name="note_C11"></a>__C11__ Evrensel CRT uygulanan C ++ 17, C99 hariç olmak üzere gerekli olan bölümleri C11 standart Kitaplığı'nın `strftime()` E/O alternatif dönüştürme tanımlayıcıları, C11 `fopen()` Dışlayıcı ve C11 `aligned_alloc()`. C11 belirttiğinden uygulanacak, olası ikincisidir `aligned_alloc()` Microsoft uygulaması ile uyumsuz şekilde `free()`, yani, `free()` yüksek oranda hizalanmış ayırma işleyebilir olması gerekir.

<a name="note_rem"></a>__REM__ kaldırılan Özellikler [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) (veya [/Std: c ++ Son](../build/reference/std-specify-language-standard-version.md)) derleyici seçeneği belirtildi. Bu özellikler bu makroları kullanarak yeni dil modları geçişi kolaylaştırmak için yeniden etkinleştirilebilir: `_HAS_AUTO_PTR_ETC`, `_HAS_FUNCTION_ALLOCATOR_SUPPORT`, `_HAS_OLD_IOSTREAMS_MEMBERS`, ve `_HAS_UNEXPECTED`.

<a name="note_charconv"></a>__charconv__ `from_chars()` ve `to_chars()` tamsayılar için kullanılabilir. Zaman çizelgesi için kayan nokta `from_chars()` ve kayan nokta `to_chars()` aşağıdaki gibidir:
- VS 2017 15.7: Tamsayı `from_chars()` ve `to_chars()`.
- VS 2017 15,8: Kayan nokta `from_chars()`.
- VS 2017 15.9: Kayan nokta `to_chars()` kısa ondalık için aşırı yüklemeleri.
- VS 2019 16.0: Kayan nokta `to_chars()` kısa onaltılık ve onaltılık duyarlık için aşırı yüklemeleri.
- VS 2019 16,2: Kayan nokta `to_chars()` Sabit duyarlık ve duyarlık bilimsel için aşırı yüklemeleri.
- Henüz uygulanmadı: Kayan nokta `to_chars()` duyarlık genel aşırı yükleme. 

<a name ="note_parallel"></a> __Paralel__ C ++ 17'ın paralel algoritmalar kitaplığı tamamlanmıştır. Bu, her algoritma, her durumda paralelleştirildi anlamına gelmez; en önemli algoritmalar paralelleştirildi ve hatta nerede algoritmaları Paralel yürütme İlkesi imzaları sağlanır. Kararlılığımızın 's merkezi iç başlık yvals_core.h, aşağıdaki "paralel algoritmalar notları" içerir: C++ seri algoritmalar yapılan çağrılar gibi paralel algoritmalar uygulamak bir uygulama sağlar.  Bu uygulama, birkaç ortak algoritma çağrılarını, ancak tüm parallelizes.

Aşağıdaki algoritmaları paralelleştirildi:

- `adjacent_difference`, `adjacent_find`, `all_of`, `any_of`, `count`, `count_if`, `equal`, `exclusive_scan`, `find`, `find_end`, `find_first_of`, `find_if`, `find_if_not`, `for_each`, `for_each_n`, `inclusive_scan`, `is_heap`, `is_heap_until`, `is_partitioned`, `is_sorted`, `is_sorted_until`, `mismatch`, `none_of`, `partition`, `reduce`, `remove`, `remove_if`, `replace`, `replace_if`, `search`, `search_n`, `set_difference`, `set_intersection`, `sort`, `stable_sort`, `transform`, `transform_exclusive_scan`, `transform_inclusive_scan`, `transform_reduce`

Şu anda paralelleştirilmedi:

- Hedef donanım üzerinde görünen paralellik performans iyileştirmesi yok; yalnızca kopyalama veya öğeleri dal ile permute tüm algoritmalar genellikle bellek bant genişliği sınırlı şunlardır:
  - `copy`, `copy_n`, `fill`, `fill_n`, `move`, `reverse`, `reverse_copy`, `rotate`, `rotate_copy`, `shift_left`, `shift_right`, `swap_ranges`
- Karışıklığı önlemek için kullanıcı paralellik gereksinimlerini üzerinde var; Yukarıdaki kategorisinde olası yine de:
  - `generate`, `generate_n`
- Etkili paralellik: şüpheli uygulanamaz
  - `partial_sort`, `partial_sort_copy`
- Henüz Değerlendirilmedi; paralellik gelecekteki bir sürümde uygulanabilir ve yararlı şüphe ediliyor:
  - `copy_if`, `includes`, `inplace_merge`, `lexicographical_compare`, `max_element`, `merge`, `min_element`, `minmax_element`, `nth_element`, `partition_copy`, `remove_copy`, `remove_copy_if`, `replace_copy`, `replace_copy_if`, `set_symmetric_difference`, `set_union`, `stable_partition`, `unique`, `unique_copy`

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)<br/>
[Visual Studio’deki C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md)<br/>
[Visual Studio'da Visual C++ yenilikleri](what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Visual C++ değişiklik geçmişi 2003-2015](../porting/visual-cpp-change-history-2003-2015.md)<br/>
[Visual C++ 2003 ile 2015 Arasındaki Farklar](../porting/visual-cpp-what-s-new-2003-through-2015.md)<br/>
[C++Ekip blogu](https://devblogs.microsoft.com/cppblog/)
