---
title: Visual C++ dil uyumluluğu | Microsoft Docs
ms.date: 11/15/2017
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 475da6e9-0d78-4b4e-bd23-f41c406c4efe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd4848ae88d7bd66286ef13b3505a741d9b55c5c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060891"
---
# <a name="visual-c-language-conformance"></a>Visual C++ dil uyumluluğu

Bu konuda, ISO C ++ 03, C ++ 11, C ++ 14, C ++ 17 ve taslak C ++ 20 dil standartlara uyumluluk derleyici özelliklerini ve Visual Studio 2017 ve önceki sürümlerde C++ derleyicisi için standart kitaplık özellikleri özetlenmektedir. Her derleyici ve standart kitaplığı özellik adı bağlantılar özelliği, bir yayın zaman olup olmadığını açıklayan ISO C++ standardı teklif kağıt. Özelliğin ilk göründüğü için desteklenen sütun destekleyen Visual Studio sürümünde listeler.

Uyumluluk geliştirmeleri ve Visual Studio 2017'deki diğer değişiklikler hakkında daha fazla bilgi için bkz: [Visual Studio 2017'deki C++ uyumluluk geliştirmeleri](cpp-conformance-improvements-2017.md) ve [Visual c++ Visual Studio 2017'deki yenilikler](what-s-new-for-visual-cpp-in-visual-studio.md). Önceki sürümlerde uyumluluk değişiklikleri için bkz. [Visual C++ değişiklik geçmişi](porting/visual-cpp-change-history-2003-2015.md) ve [Visual C++ neler yeni 2003 ile 2015 arasındaki](porting/visual-cpp-what-s-new-2003-through-2015.md). C++ ekibinden güncel Haberleri için ziyaret [Visual C++ ekip blogu'ndan](https://blogs.msdn.microsoft.com/vcblog/).

> [!NOTE]
> Visual Studio 2015 ve Visual Studio 2017 arasında yeni değişiklikler hiçbir ikili dosya vardır.

## <a name="compiler-features"></a>Derleme özellikleri

|Özellik alanı| |
|----|---|
|__C ++ 03/11 çekirdek dil özellikleri__|__Desteklenen__|
|&nbsp;&nbsp;Diğer her şey|VS 2015 <sup>[A](#note_A)</sup>|
|&nbsp;&nbsp;İki aşamalı ad arama|VS 2017 15.7 <sup> [B](#note_B)</sup>|
|&nbsp;&nbsp;[N2634 İfade SFINAE](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2634.html)|VS 2017 15.7|
|&nbsp;&nbsp;[N1653 C99 önişlemcisi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1653.htm)|Kısmi <sup> [D](#note_D)</sup>|
|&nbsp;&nbsp;[N1988 genişletilmiş tamsayı türleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1988.pdf)|YOK <sup> [E](#note_E)</sup>|
|__C ++ 14 çekirdek dil özellikleri__|__Desteklenen__|
|&nbsp;&nbsp;[Bağlamsal dönüştürmeleri için N3323 Tweaked ifadesi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3323.pdf)|VS 2013|
|&nbsp;&nbsp;[N3472 ikili sabit dizeler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3472.pdf)|VS 2015|
|&nbsp;&nbsp;[N3638 otomatik ve decltype(auto) dönüş türleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3638.html)|VS 2015|
|&nbsp;&nbsp;[N3648 init-yakalamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3648.html)|VS 2015|
|&nbsp;&nbsp;[N3649 genel lambda ifadeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3649.html)|VS 2015|
|&nbsp;&nbsp;[[[Kullanım dışı]] N3760 özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3760.html)|VS 2015|
|&nbsp;&nbsp;[N3778 boyutlandırılmış ayırmayı kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3781 basamak ayırıcılar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3781.pdf)|VS 2015|
|&nbsp;&nbsp;[N3651 değişken şablonlar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3651.pdf)|VS 2015.2|
|&nbsp;&nbsp;[N3652 genişletilmiş constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)|VS 2017|
|&nbsp;&nbsp;[Toplamlar için N3653 Nsdmıs](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3653.html)|VS 2017|
|&nbsp;&nbsp;[N3664 Sakınma ve işlerken ayırmalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3664.html)|YOK <sup> [F](#note_F)</sup>|
|__C ++ 17 çekirdek dil özellikleri__|__Desteklenen__|
|&nbsp;&nbsp;[Trigrafları N4086 kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)|VS 2010 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[İle küme ayraçlı başlatma listelerinde auto için N3922 yeni kurallar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Şablon Şablon parametrelerinde N4051 typename](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Ad alanlarında ve numaralandırıcılarda N4266 öznitelikleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4267 u8 karakter değişmez değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Ad alanı tanımları N4230 iç içe geçmiş](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4230.html)|VS 2015.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N3928 Terse static_assert](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)|VS 2017 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0184R0 genelleştirilmiş aralık tabanlı for-döngüleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)|VS 2017 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0188R1 [[fallthrough]] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r1.pdf)|VS 2017 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[Register anahtar sözcüğü P0001R1 kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0002R1 kaldırma operator ++ bool için](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0018R3 yakalama * bu değere göre](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Yineleme olmadan öznitelik ad alanları P0028R4 kullanma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0028r4.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0061R1 __has_include](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0061r1.html)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0138R2 doğrudan-liste-init tamsayılar gelen sabit bir sabit listeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0170R1 constexpr lambdaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0170r1.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0189R1 [[nodiscard]] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0189r1.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0212R1 [[maybe_unused]] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0212r1.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0217R3 yapılandırılmış bağlamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0217r3.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0292R2 constexpr if-deyimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0292r2.html)|VS 2017 15.3 <sup> [G](#note_G)</sup>|
|&nbsp;&nbsp;[Başlatıcılar ile P0305R1 seçim deyimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0305r1.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0245R1 Hexfloat sabit değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0245r1.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4268 izin vererek daha fazla tür olmayan şablon bağımsız değişkenleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4268.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4295 Katlama ifadeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4295.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Belirtimlere dinamik P0003R5 kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Tür sisteminde noexcept P0012R1 ekleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0012r1.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0035R4 aşırı hizalanmış dinamik bellek ayırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0035r4.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0386R2 satır içi değişkenler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0386r2.pdf)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0522R0 eşleşen şablon şablon-parametre uyumlu bağımsız değişkenleri için](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0522r0.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0036R0 kaldırma bazı boş birli hatları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0036r0.pdf)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Nitelik dönüştürme N4261 düzeltme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4261.html)|VS 2017 15.7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Genişletilmiş P0017R1 toplu başlatma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)|VS 2017 15.7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Sınıf şablonları P0091R3 şablon bağımsız değişken kesintisi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)<br />&nbsp;&nbsp;[P0512R0 sınıf şablonu bağımsız değişkeni kesintisi sorunları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0512r0.pdf)|VS 2017 15.7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Otomatik tür olmayan şablon parametreleri P0127R2 bildirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)|VS 2017 15.7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0135R1 garantili kopya eleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0135r1.html)|VS 2017 15.6<sup>[H](#note_H)</sup>|
|&nbsp;&nbsp;[Oluşturucuların devralınması P0136R1 yeni ifade biçimiyle](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html)|VS 2017 15.7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0137R1 std::launder](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0137r1.html)|VS 2017 15.7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[İfade değerlendirme sırası P0145R3 iyileştirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0145r3.pdf)<br />&nbsp;&nbsp;[İşlev bağımsız değişkenlerinin değerlendirme P0400R0 sırası](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0400r0.html)|VS 2017 15.7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Using-declarations içinde P0195R2 paket genişletmeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0195r2.html)|VS 2017 15.7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Tanınmayan P0283R2 yoksayılıyor öznitelikleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0283r2.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[Başlatıcı listesi oluşturucuları için sınıfın şablon bağımsız değişkeni kesintisi P0702R1 düzeltme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0702r1.html)|VS 2017 15.7 <sup> [17](#note_17)</sup>|

|Özellik alanı| |
|----|---|
|__(Hata raporları) c ++ 17 çekirdek dil özellikleri__|__Desteklenen__|
|&nbsp;&nbsp;[Başlatıcı listesi oluşturucuları için sınıfın şablon bağımsız değişkeni kesintisi P0702R1 düzeltme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0702r1.html)|VS 2017 15.7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Örtük lambda yakalama P0588R1 basitleştirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0588r1.html)|Hayır|
|&nbsp;&nbsp;[CWG 1581: Ne zaman constexpr üye işlevleri tanımlanır?](https://wg21.cmeerw.net/cwg/issue1581)|Hayır|
|&nbsp;&nbsp;[Bulma kuralları noktası P0962R1 gevşetme yapılandırılmış bağlamalar özelleştirme](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0961r1.html)|Hayır|
|&nbsp;&nbsp;[P0962R2 gevşetme aralığı-döngü özelleştirme noktası bulma kuralları](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0962r1.html)|Hayır|
|&nbsp;&nbsp;[Erişilebilir üyeler bağlamaları yapılandırılmış P0969R0 izin verme](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0969r0.pdf)|Hayır|

|Özellik alanı| |
|----|---|
|__C ++ 20 çekirdek dil özellikleri__|__Desteklenen__|
|&nbsp;&nbsp;[P0306R4 ekleme &#95; &#95;VA_OPT&#95; &#95; virgülle atlama ve virgül silme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0306r4.pdf)|Hayır|
|&nbsp;&nbsp;[P0329R4 belirtilen başlatma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf)|Hayır|
|&nbsp;&nbsp;[P0409R2 izin vererek lambda [=, bu] yakalama](http://open-std.org/JTC1/SC22/WG21/docs/papers/2017/p0409r2.html)|Hayır|
|&nbsp;&nbsp;[Genel lambda ifadeleri için P0428R2 tanıdık şablon söz dizimi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0428r2.pdf)|Hayır|
|&nbsp;&nbsp;[Bit alanları için P0683R1 varsayılan üye Başlatıcı](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0683r1.html)|Hayır|
|&nbsp;&nbsp;[P0704R1 düzeltme const lvalue başvuru nitelikli üye işaretçileri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0704r1.html)|Hayır|
|&nbsp;&nbsp;[P0734R0 kavramları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0734r0.pdf)|Hayır|

## <a name="standard-library-features"></a>Standart kitaplık özellikleri

|Özellik alanı| |
|---|---|
|__C ++ 20 standart kitaplık özellikleri__|__Desteklenen__|
|&nbsp;&nbsp; [Gereksiz Decay P0777R1 kaçınma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0777r1.pdf)|VS 2017 15.7 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0463R1 endian](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0463r1.html)|Hayır|
|&nbsp;&nbsp;[Diziler için P0674R1 make_shared()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0674r1.html)|Hayır|
|&nbsp;&nbsp;[P0858R0 Constexpr yineleyici gereksinimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0858r0.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Kapsayıcıları sırasız P0809R0 karşılaştırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0809r0.pdf)| VS 2010 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp; [Atomik P0020R3\<float > atomik\<çift > atomik\<uzun çift >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0020r6.html)|Hayır|
|&nbsp;&nbsp; [P0053R7 \<syncstream >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0053r7.pdf)<br />&nbsp;&nbsp; [P0753R2 osyncstream Manipülatörleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0753r2.pdf)|Hayır|
|&nbsp;&nbsp; [P0122R7 \<span >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0122r7.pdf)|Hayır|
|&nbsp;&nbsp; [P0202R3 constexpr için \<algoritma > ve exchange()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0202r3.html)|Hayır|
|&nbsp;&nbsp; [P0355R7 \<chrono > Takvim ve saat dilimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0355r7.html)|Hayır|
|&nbsp;&nbsp; [P0415R1 constexpr için \<karmaşık > (yeniden)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0415r1.html)|Hayır|
|&nbsp;&nbsp; [P0439R0 enum sınıfı memory_order](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0439r0.html)|Hayır|
|&nbsp;&nbsp; [Basic_string/basic_string_view için P0457R2 starts_with()/ends_with()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0457r2.html)|Hayır|
|&nbsp;&nbsp; [P0550R2 remove_cvref](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf)|Hayır|
|&nbsp;&nbsp; [P0551R3 sen std işlev şablonları Specialize Shalt değil!](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0551r3.pdf)|Hayır|
|&nbsp;&nbsp; [P0600R1 \[ \[nodiscard\] \] STL için bölüm 1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0600r1.pdf)|Hayır|
|&nbsp;&nbsp; [İçinde P0616R0 kullanarak move() \<sayısal >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0616r0.pdf)|Hayır|
|&nbsp;&nbsp; [P0653R2 to_address()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0653r2.html)|Hayır|
|&nbsp;&nbsp; [Atomik P0718R2\<shared_ptr\<T >> atomik\<weak_ptr\<T >>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0718r2.html)|Hayır|
|&nbsp;&nbsp; [P0754R2 \<sürüm >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0754r2.pdf)|Hayır|
|&nbsp;&nbsp; [İs_pod P0767R1 kullanım dışı bırakılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0767r1.html)|Hayır|
|&nbsp;&nbsp; [P0768R1 savaş Gemisi karşılaştırma işleci için kitaplık desteği \<=>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0768r1.pdf)|Hayır|
|&nbsp;&nbsp; [P0966R1 dize:: reserve() küçültme değil](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0966r1.html)|Hayır|
|__C ++ 17 standart kitaplığı özellikleri__|__Desteklenen__|
|&nbsp;&nbsp;[P0433R2 tümleştirme şablon kesintisi sınıf şablonları standart kitaplığa](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html)<br />&nbsp;&nbsp;[Standart kitaplığa sınıf şablonu bağımsız değişkeni kesintisi tümleştirme P0739R0 geliştirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html)|VS 2017 15.7|
|&nbsp;&nbsp;[Char_traits için P0426R1 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html)|VS 2017 15.7|
|&nbsp;&nbsp;[P0030R1 hypot (x, y, z)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf)|VS 2017 15.7|
|&nbsp;&nbsp;[P0220R1 kitaplığı temelleri V1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html)|VS 2017 15.6 <sup> [J](#note_J)</sup>|
|&nbsp;&nbsp;[P0067R5 temel dize dönüştürme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html)|VS 2017 15.7 <sup> [charconv](#note_charconv)</sup>|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<memory_resource >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#memory.resource.synop)<br />&nbsp;&nbsp;[Polymorphic_allocator atama P0337R0 siliniyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0337r0.html)|VS 2017 15.6|
|&nbsp;&nbsp;[P0024R2 paralel algoritmalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html)<br />&nbsp;&nbsp;[Paralel yürütme ilkeleri P0336R1 yeniden adlandırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0336r1.pdf)<br />&nbsp;&nbsp;[Paralel algoritmalar P0394R4 terminate() için özel durumları gerekir.](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0394r4.html)<br />&nbsp;&nbsp;[P0452R1 birleştirme \<sayısal > paralel algoritmalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0452r1.html)|VS 2017 15.7|
|&nbsp;&nbsp;[P0226R1 özel matematik işlevleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0226r1.pdf)|VS 2017 15.7|
|&nbsp;&nbsp;[P0218R1 \<filesystem >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html)<br />&nbsp;&nbsp;[Dosya sistemi için P0219R1 göreli yolları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0219r1.html)<br />&nbsp;&nbsp;[Dosya sistemi için önbelleğe alma P0317R1 dizin girdisi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p03179r1.html)<br />&nbsp;&nbsp;[P0392R0 destekleyen string_view, dosya sistemi yolları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0392r0.pdf)<br />&nbsp;&nbsp;[P0430R2 destekleyen olmayan POSIX dosya sistemleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0430r2.pdf)<br />&nbsp;&nbsp;[Dosya sistemi için P0492R2 NB yorum çözümleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0492r2.html)|VS 2017 15.7 <sup> [K](#note_K)</sup>|
|&nbsp;&nbsp;[P0003R5 dinamik özel durum belirtimleri kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0005R4 not_fn()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html)<br />&nbsp;&nbsp;[Not_fn() P0358R1 düzeltmelerin](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Enable_shared_from_this P0033R1 yeni ifade biçimiyle](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html)|VS 2017 15.5 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0083R3 boşluklarına ayıran Haritalar ve kümeler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)<br />&nbsp;&nbsp;[P0508R0 açıklığa kavuşturan insert_return_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0174R2 işlevini kaybetmiş kitaplık parçaları kullanımdan kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Std::function P0302R1 kaldırma ayırıcı desteği de](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0414R2 shared_ptr\<T [] >, shared_ptr\<T [N] >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html)<br />&nbsp;&nbsp;[Shared_ptr P0497R0 düzeltmek için diziler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html)|VS 2017 15.5 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Shared_ptr::unique() P0521R0 kullanım dışı bırakılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0521r0.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Standart kitaplık için P0607R0 satır içi değişkenler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0618R0 kullanımdan \<codecvt >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0618r0.html)|VS 2017 15.5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: Boyer-Moore search()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#func.searchers.boyer_moore)<br/>&nbsp;&nbsp;[P0253R1 düzeltme noktasıdır dönüş türleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0253r1.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0031R0 constexpr için \<array > (yeniden) ve \<yineleyici >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0031r0.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0040R3 genişletme bellek yönetimi araçları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0040r3.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0084R2 Emplace dönüş türü](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0084r2.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0152R1 atomic::is_always_lock_free](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0152r1.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0154R1 hardware_destructive_interference_size, vb.](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0154r1.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Yeniden adlandırma P0156R2 Variadic kilit\_koruma sağlamak üzere kapsamlı\_Kilitle](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0156r2.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0258R2 has_unique_object_representations](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0258r2.html)|VS 2017 15.3 <sup> [M](#note_L)</sup>|
|&nbsp;&nbsp;[P0295R0 gcd(), lcm()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0295r0.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0298R3 std::byte](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0298r3.pdf)|VS 2017 15.3 <sup> [17](#note_17), [bayt](#note_byte)</sup>|
|&nbsp;&nbsp;[P0403R1 Udl'ler için \<string_view > ("meow" sv, vs.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0403r1.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0418R2 atomik compare_exchange memory_order gereksinimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0418r2.html)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Common_type P0435R1 elden](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0435r1.pdf)<br />&nbsp;&nbsp;[Ortak P0548R1 ince ayar yapma\_türü ve süresi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0548r1.pdf)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0505R0 constexpr için \<chrono > (yeniden)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0505r0.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0513R0 zehirleme karması](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0513r0.pdf)<br />&nbsp;&nbsp;[P0599R1 noexcept karması](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0599r1.pdf)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Shared_future noexcept kopyalama olarak P0516R0 işaretleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0516r0.html)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Future_errc gelen future_error P0517R0 oluşturma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0517r0.html)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0558R1 çözümleme atomik<T> adlı temel sınıf tutarsızlıklar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0558r1.pdf)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0604R0 değiştirme\_çağrılabilir/sonuç\_, çağrılacak\_olduğu, neden\_çağrılmayan, olan\_nothrow\_çağrılmayan](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0604r0.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<algoritma > sample()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#alg.random.sample)|VS 2017|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<herhangi >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#any)|VS 2017|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<isteğe bağlı >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#optional)|VS 2017 |
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<string_view >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#string.view)|VS 2017|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<demet > apply()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#tuple)|VS 2017|
|&nbsp;&nbsp;[P0032R3 homojen arabirimi için değişken/any/isteğe bağlı](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0032r3.pdf)|VS 2017|
|&nbsp;&nbsp;[P0077R2 is_callable, is_nothrow_callable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0077r2.html)|VS 2017|
|&nbsp;&nbsp;[P0088R3 \<değişken >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0088r3.html)|VS 2017|
|&nbsp;&nbsp;[P0163R0 shared_ptr::weak_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0163r0.html)|VS 2017|
|&nbsp;&nbsp;[P0209R2 make_from_tuple()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0209r2.pdf)|VS 2017|
|&nbsp;&nbsp;[String_view P0254R2 tümleştirme ve std::string](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0254r2.pdf)|VS 2017|
|&nbsp;&nbsp;[P0307R2 yapma isteğe bağlı büyük eşittir yeniden](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0307r2.pdf)|VS 2017|
|&nbsp;&nbsp;[Değişken büyük eşittir P0393R3 yapma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0393r3.html)|VS 2017|
|&nbsp;&nbsp;[P0504R0 da in_place_t/in_place_type_t\<T > / in_place_index_t\<miyim >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0504r0.html)|VS 2017|
|&nbsp;&nbsp;[P0510R0 reddetme çeşitleri, Nothing, diziler, başvurular ve eksik türler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0510r0.html)|VS 2017|
|&nbsp;&nbsp;[P0025R1 clamp()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0025r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0185R1 is_swappable, is_nothrow_swappable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0185r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0272R1 Non-const basic_string::data()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0272r1.html)|VS 2015.3|
|&nbsp;&nbsp;[Çifti N4387 geliştirme ve demet](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4387.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4508 shared_mutex (Untimed)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4508.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Kullanım dışı Iostreams Aliases P0004R1 kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0004r1.html)|VS 2015.2 <sup> [rem](#note_rem)</sup>|
|&nbsp;&nbsp;[P0006R0 değişken şablonlar için türü nitelikler (is_same_v, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0006r0.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0007R1 as_const()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0007r1.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0013R1 mantıksal işleç türü nitelikler (birlikte, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0013r1.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0074R0 owner_less\<>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0074r0.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0092R1 \<chrono > floor(), ceil(), round(), abs()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0092r1.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Lock_guard P0156R0 değişen sayıda bağımsız değişken](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0156r0.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
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
|&nbsp;&nbsp;[N4389 bool_constant](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4389.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0063R3 C11 standart kitaplığı](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0063r3.html)|VS 2015 <sup>[C11](#note_C11), [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4510 destekleyen eksik türleri, vektör/listesi/forward_list](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4510.html)|VS 2013 <sup>[14](#note_14)</sup>|
|__C ++ 14 standart kitaplık özellikleri__|__Desteklenen__|
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
|&nbsp;&nbsp;[N3924 rand() Discouraging](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3924.pdf)|Yok|

Bir grup İnceleme birlikte listelenen özellik standart oy ve ardından artırmak veya bu özelliği genişletmek için bir veya daha fazla inceleme de oy gösterir. Bu özellikler birlikte uygulanır.

### <a name="supported-values"></a>Desteklenen değerler

__Hayır__ henüz uygulanmadı anlamına gelir.<br/>
__Kısmi__ Visual Studio 2017'de uygulama eksik olduğu anlamına gelir. Daha fazla ayrıntı için Notlar bölümüne bakın.<br/>
__Yok__ öneri incelemeleri açıklanmayan özellikleri anlamına gelir. Bu raporları dil standart değiştirilemez, ancak uygulayıcılar için herhangi bir iş oluşturmamışsınızdır. Bütünlük açısından buraya listelendikleri.<br/>
__VS 2010__ Visual Studio 2010'da desteklenen özellikleri gösterir.<br/>
__VS 2013__ Visual Studio 2013'te desteklenen özellikleri gösterir.<br/>
__VS 2015__ Visual Studio 2015 için RTM'de desteklenmeyen özellikleri gösterir.<br/>
__VS 2015.2__ ve __VS 2015.3__ Visual Studio 2015 güncelleştirme 2 ile Visual Studio 2015 güncelleştirme 3, sırasıyla desteklenmeyen özellikleri gösterir.<br/>
__VS 2017__ Visual Studio 2017 RTM'de desteklenmeyen özellikleri gösterir.<br/>
__VS 2017 15.3__ Visual Studio 2017 sürüm 15.3 desteklenmeyen özellikleri gösterir.<br/>
__VS 2017 15.5__ Visual Studio 2017 sürüm 15.5 desteklenmeyen özellikleri gösterir.<br/>
__VS 2017 15.7__ Visual Studio 2017 sürüm 15.7 sürümünde desteklenmeyen özellikleri gösterir.<br/>

### <a name="notes"></a>Notlar

<a name="note_A"></a>__A__ /Std: C ++ 14 modu dinamik özel durum belirtimleri uygulanmayan kalır ve throw() eşanlamlısı olarak kabul hala \_ \_declspec(nothrow). C ++ 17'de, çıkmadan bir vestige P0003R5 tarafından çoğunlukla dinamik özel durum belirtimleri kaldırıldı: throw() kullanım dışıdır ve noexcept eşanlamlısı olarak davranır gerekmez. / Std: c ++ 17 modunda MSVC artık uyumlu standart noexcept, yani zorlama sonlandırma aracılığıyla aynı davranışı throw() vererek.

Bizim eski davranışını derleyici seçeneği /Zc:noexceptTypes-istekleri \_ \_declspec(nothrow). C ++ 20, throw() kaldırılacak olasıdır. Geçiş konusunda yardımcı olmak için standart ve özel durum belirtimi sorunlar için yeni Derleyici uyarılarını kararlılığımızın bu değişikliklere yanıt kodu eklenmiştir altında **/Std: c ++ 17** ve **/permissive-**.

<a name="note_B"></a>__B__ Visual Studio 2017 sürüm 15.7 /permissive-mode desteklenen. Bkz: [MSVC için iki aşamalı ad arama desteği geldi](https://blogs.msdn.microsoft.com/vcblog/2017/09/11/two-phase-name-lookup-support-comes-to-msvc/) daha fazla bilgi için.

<a name="note_C"></a>__C__ Visual Studio 2015 güncelleştirme 2'den derleyicinin ifade SFINAE desteği için standart kitaplık yeterli olmuştur. Visual Studio 2017 15.7 sürümündeki /permissive-mode ayarlanma şeklinden bağımsız olarak desteklenir. Düzeltilen bazı hatalar kalır. "Benzersiz etiket türü" geçici çözüm artık gerekli değildir ve bu geçici çözüm STL kararlılığımızın kaldırdık.

<a name="note_D"></a>__D__ C99 önişlemci kuralları için derleyici desteği, Visual Studio 2017'de eksik. Variadic makrolar desteklenir ancak önişlemci'nin davranışını birçok hataları vardır.  Biz önişlemci elden ve bu değişiklikleri altında experimentally sevk edilir **/ permissive-** yakında modu.

<a name="note_E"></a>__E__ derleyiciler izin verilir, ancak, genişletilmiş tamsayı türleri desteklemek için gerekli değildir çünkü bu uygulanamaz olarak işaretlenir.  GCC ve Clang gibi biz kullanıcıyı seçtiniz.

<a name="note_F"></a>__F__ derleyiciler izin verilir, ancak, bu en iyi duruma getirme uygulamak için gerekli değildir çünkü benzer şekilde, bu uygulanamaz olarak işaretlenir.

<a name="note_G"></a>__G__ altında desteklenen [/Std: c ++ 14](./build/reference/std-specify-language-standard-version.md) suppressible bir uyarı.

<a name="note_J"></a>__J__ Visual Studio 2015'te tamamlanmamış özellikleri ayrıştırılmış başka bir yerde bu tabloda.

<a name="note_K"></a>__K__ Bu, sembolik bağlantısını desteği, hata düzeltmeleri, tarafından olmaması önceki std::experimental sürümü ile uyumlu tamamen yeni bir uygulama ve standart gerekli davranışını değiştirir. Şu anda dahil olmak üzere \<filesystem > Yeni std::filesystem ve önceki std::experimental::filesystem sağlar ve dahil olmak üzere \<Deneysel/dosya sistemi > yalnızca eski Deneysel uygulamasını sağlar. Deneysel uygulama KALDIRILACAK kitaplıkları sonraki ABI en son sürümünde.

<a name="note_L"></a>__M__ iç derleyici tarafından desteklenir.

<a name="note_14"></a>__14__ bu C ++ 17/20 özellikler her zaman etkindir, bile [/Std: c ++ 14](build/reference/std-specify-language-standard-version.md) (varsayılan) belirtilir. Başlamadan önce uygulanan bir özellik ya da olmasıdır **/Std** seçenekleri veya koşullu uygulama açabileceğinin karmaşıktı.

<a name="note_17"></a>__17__ bu özellikler tarafından etkinleştirilen [/Std: c ++ 17](./build/reference/std-specify-language-standard-version.md) (veya [/Std: c ++ Son](./build/reference/std-specify-language-standard-version.md)) derleyici seçeneği.

<a name="note_byte"></a>__bayt__ `std::byte` etkinleştirilir [/Std: c ++ 17](./build/reference/std-specify-language-standard-version.md) (veya [/Std: c ++ Son](./build/reference/std-specify-language-standard-version.md)), ancak bazı durumlarda Windows SDK'sı üst bilgileri ile çakışabileceği için ayrıntılı çevirme makro sahiptir. Bunu tanımlayarak devre dışı bırakılabilir `_HAS_STD_BYTE` olarak `0`.

<a name="note_C11"></a>__C11__ Evrensel CRT uygulanan C ++ 17, C99 hariç olmak üzere gerekli olan bölümleri C11 standart Kitaplığı'nın `strftime()` E/O alternatif dönüştürme tanımlayıcıları, C11 `fopen()` Dışlayıcı ve C11 `aligned_alloc()`. C11 belirttiğinden uygulanacak, olası ikincisidir `aligned_alloc()` Microsoft uygulaması ile uyumsuz şekilde `free()`, yani, `free()` yüksek oranda hizalanmış ayırma işleyebilir olması gerekir.

<a name="note_rem"></a>__REM__ kaldırılan Özellikler [/Std: c ++ 17](./build/reference/std-specify-language-standard-version.md) (veya [/Std: c ++ Son](./build/reference/std-specify-language-standard-version.md)) derleyici seçeneği belirtildi. Çevirme makroları bu özelliklere sahip: `_HAS_AUTO_PTR_ETC`, `_HAS_FUNCTION_ALLOCATOR_SUPPORT`, `_HAS_OLD_IOSTREAMS_MEMBERS`, ve `_HAS_UNEXPECTED`.

<a name="note_charconv"></a>__charconv__ from_chars() ve to_chars() tamsayılar için kullanılabilir. Kayan nokta to_chars() tarafından izlenmesi için kayan nokta from_chars(), şu anda üzerinde çalışıyoruz.

<a name ="note_parallel"></a> __Paralel__ C ++ 17'ın paralel algoritmalar kitaplığı tamamlanmıştır. Bu her algoritma, her durumda paralelleştirildi anlamına gelmediğini unutmayın. en önemli algoritmalar paralelleştirildi ve hatta nerede algoritmaları Paralel yürütme İlkesi imzaları sağlanır. STL kararlılığımızın 's merkezi iç başlık yvals.h, aşağıdaki "paralel algoritmalar notları" içerir: C++ seri algoritmalar yapılan çağrılar gibi paralel algoritmalar uygulamak bir uygulama sağlar.   Bu uygulama, birkaç ortak algoritma çağrılarını, ancak tüm parallelizes.

Aşağıdaki algoritmaları paralelleştirildi:

- adjacent_difference, adjacent_find, all_of, any_of, sayısı, count_if, eşittir, exclusive_scan, bulma, find_end, find_first_of, find_if, for_each, for_each_n, inclusive_scan, uyuşmazlığı, none_of, küçültmek, Kaldır, remove_if, arama, search_n, sıralama, stable_ sıralama, dönüştürme, transform_exclusive_scan, transform_inclusive_scan transform_reduce.

Şu anda paralelleştirilmedi:

- Hedef donanım üzerinde görünen paralellik performans iyileştirmesi yok; yalnızca kopyalama veya öğeleri dal ile permute tüm algoritmalar genellikle bellek bant genişliği sınırlı şunlardır:
  - kopyalama, copy_backward, copy_n, dolgu, fill_n, taşıma, move_backward, Kaldır, remove_if, Değiştir, replace_if, ters, reverse_copy, swap_ranges rotate_copy, döndürme
- Karışıklığı önlemek için kullanıcı paralellik gereksinimlerini üzerinde var; Yukarıdaki kategorisinde olası yine de:
  - generate_n oluştur
- Etkili paralellik: şüpheli uygulanamaz
  - partial_sort, partial_sort_copy
- Henüz Değerlendirilmedi; paralellik gelecekteki bir sürümde uygulanabilir ve yararlı şüphe ediliyor:
  - inplace_merge is_heap, is_heap_until, is_partitioned, is_sorted, is_sorted_until, lexicographical_compare, max_element, birleştirme, min_element, minmax_element, nth_element, partition_copy, remove_copy, remove_copy_if, replace_ copy_if, içerir kopyalama, replace_copy_if, set_difference, set_intersection, set_symmetric_difference, set_union, stable_partition, benzersiz unique_copy

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](standard-library/cpp-standard-library-reference.md)<br/>
[Visual Studio 2017’deki C++ uyumluluk geliştirmeleri](cpp-conformance-improvements-2017.md)<br/>
[Visual Studio 2017'deki Visual C++ Yenilikleri](what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Visual C++ değişiklik geçmişi 2003-2015](porting/visual-cpp-change-history-2003-2015.md)<br/>
[Visual C++ 2003 ile 2015 Arasındaki Farklar](porting/visual-cpp-what-s-new-2003-through-2015.md)<br/>
[Visual C++ ekip blogu](https://blogs.msdn.microsoft.com/vcblog/)
