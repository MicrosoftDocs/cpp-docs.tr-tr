---
title: Visual C++ dili uygunluk | Microsoft Docs
ms.date: 11/15/2017
ms.technology: cpp-language
ms.topic: article
dev_langs: C++
ms.assetid: 475da6e9-0d78-4b4e-bd23-f41c406c4efe
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8e9d4d86abd15f59e94ce7e51d40e119f8ebd336
ms.sourcegitcommit: 1b480aa74886930b3bd0435d71cfcc3ccda36424
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="visual-c-language-conformance"></a>Visual C++ dili uyumluluğu

Bu konu, C ++ 03 ISO, C ++ 11, C ++ 14, C ++ 17 ve taslak C ++ 20 dil standartlara uygunluk derleyici özellikleri ve standart kitaplığı özellikleri Visual c++, Visual Studio 2017 ve önceki sürümlerinde özetler. Her derleyicisi ve standart kitaplığı özellik adı bağlantılar özelliği, yayım saatinde varsa tanımlayan ISO C++ Standart teklif kağıt. Özelliğin ilk göründüğü için destekleyen Visual Studio sürümünde desteklenen sütununda listelenir.

Uygunluk geliştirmeleri ve Visual Studio 2017 diğer değişiklikler hakkında daha fazla bilgi için bkz: [C++ uygunluk Visual Studio 2017 yenilikleri](cpp-conformance-improvements-2017.md) ve [Visual Studio 2017'de Visual C++ için Yenilikler](what-s-new-for-visual-cpp-in-visual-studio.md). Önceki sürümlerde uygunluk değişiklikleri için görmek [Visual C++ değişiklik geçmişini](porting/visual-cpp-change-history-2003-2015.md) ve [Visual C++ ne ait yeni 2003 2015 aracılığıyla](porting/visual-cpp-what-s-new-2003-through-2015.md). C++ ekibinden güncel Haberleri için ziyaret [Visual C++ ekip blogu](https://blogs.msdn.microsoft.com/vcblog/).  

 > [!NOTE]
 > Visual Studio 2015 ve Visual Studio 2017 arasında önemli değişiklikler hiçbir ikili vardır.

## <a name="compiler-features"></a>Derleyici özellikleri

|Özellik alanı| |
|----|---|
|__C ++ 11 03 çekirdek dil özellikleri__|__Desteklenen__|
|&nbsp;&nbsp;Şey|VS 2015 <sup> [A](#note_A)</sup>|
|&nbsp;&nbsp;İki aşamalı ad arama|Kısmi <sup> [B](#note_B)</sup>|
|&nbsp;&nbsp;[N2634 İfade SFINAE](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2634.html)|Kısmi <sup> [C](#note_C)</sup>|
|&nbsp;&nbsp;[N1653 C99 ön işlemci](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1653.htm)|Kısmi <sup> [D](#note_D)</sup>|
|&nbsp;&nbsp;[N1988 genişletilmiş tamsayı türleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1988.pdf)|YOK <sup> [E](#note_E)</sup>|
|__C ++ 14 çekirdek dil özellikleri__|__Desteklenen__|
|&nbsp;&nbsp;[Bağlamsal dönüştürmeleri için N3323 Tweaked ifadesi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3323.pdf)|VS 2013|
|&nbsp;&nbsp;[N3472 ikili değişmez değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3472.pdf)|VS 2015|
|&nbsp;&nbsp;[N3638 otomatik olarak ve decltype(auto) dönüş türleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3638.html)|VS 2015|
|&nbsp;&nbsp;[N3648 init-yakalamaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3648.html)|VS 2015|
|&nbsp;&nbsp;[N3649 genel lambdas](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3649.html)|VS 2015|
|&nbsp;&nbsp;[[[Kullanım dışı]] N3760 özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3760.html)|VS 2015|
|&nbsp;&nbsp;[N3778 boyutta ayırmayı kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3781 basamak ayırıcıları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3781.pdf)|VS 2015|
|&nbsp;&nbsp;[N3651 değişken şablonlar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3651.pdf)|VS 2015.2|
|&nbsp;&nbsp;[N3652 genişletilmiş constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)|VS 2017|
|&nbsp;&nbsp;[Toplamalar için N3653 NSDMIs](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3653.html)|VS 2017|
|&nbsp;&nbsp;[N3664 Sakınma ve işlerken ayırmaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3664.html)|YOK <sup> [F](#note_F)</sup>|
|__C ++ 17 çekirdek dil özellikleri__|__Desteklenen__|
|&nbsp;&nbsp;[Trigrafları N4086 kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)|VS 2010 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Otomatik braced-init-listeleriyle için N3922 yeni kuralları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4051 typename şablon şablon parametrelerinde](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Ad alanları ve numaralandırmalar N4266 öznitelikleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4267 u8 karakter değişmez değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Ad alanı tanımları N4230 iç içe geçmiş](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4230.html)|VS 2015.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N3928 Terse static_assert](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)|VS 2017 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0184R0 genelleştirilmiş aralık tabanlı için-döngüler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)|VS 2017 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0188R1 [[fallthrough]] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r1.pdf)|VS 2017 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0001R1 kaldırma register anahtar sözcüğü](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0002R1 kaldırma operator ++ bool için](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0018R3 yakalama * bu değere göre](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Yineleme olmadan özniteliği ad alanları P0028R4 kullanma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0028r4.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0061R1 __has_include](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0061r1.html)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0138R2 doğrudan-listesi-init tamsayılar gelen sabit Numaralandırmaların](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0170R1 constexpr lambdas](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0170r1.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0189R1 [[nodiscard]] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0189r1.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0212R1 [[maybe_unused]] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0212r1.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0217R3 yapılandırılmış bağlamaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0217r3.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0292R2 constexpr IF-deyimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0292r2.html)|VS 2017 15.3 <sup> [G](#note_G)</sup>|
|&nbsp;&nbsp;[Başlatıcılar ile P0305R1 seçim deyimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0305r1.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0245R1 Hexfloat değişmez değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0245r1.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4268 izin vererek daha fazla tür olmayan şablon bağımsız değişken](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4268.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4295 Katlama ifadeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4295.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Dinamik-özel durum-belirtimleri P0003R5 kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Tür sistemi için noexcept P0012R1 ekleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0012r1.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0035R4 aşırı hizalanmış dinamik bellek ayırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0035r4.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0386R2 satır içi değişkenleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0386r2.pdf)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0522R0 eşleşen şablonu şablon-parametreleri uyumlu bağımsız değişkenler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0522r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0036R0 kaldırma bazı boş birli Katlama](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0036r0.pdf)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4261 düzelttikten niteliğe dönüşümleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4261.html)|Hayır|
|&nbsp;&nbsp;[P0017R1 genişletilmiş toplu başlatma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)|Hayır|
|&nbsp;&nbsp;[Sınıf şablonları P0091R3 şablon bağımsız değişken kesintisi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)<br />&nbsp;&nbsp;[P0512R0 sınıfı şablon bağımsız değişken kesintisi sorunları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0512r0.pdf)|Hayır|
|&nbsp;&nbsp;[Tür olmayan şablon parametreleri otomatik P0127R2 bildirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)|Hayır|
|&nbsp;&nbsp;[Kopya elision P0135R1 garanti](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0135r1.html)|Hayır <sup> [H](#note_H)</sup>|
|&nbsp;&nbsp;[Oluşturucular devralma P0136R1 uygun sözcükler kullanmak](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html)|Hayır|
|&nbsp;&nbsp;[İfade değerlendirme sırası P0145R3 iyileştirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0145r3.pdf)<br />&nbsp;&nbsp;[İşlev bağımsız değişkenleri, değerlendirme P0400R0 sırası](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0400r0.html)|Hayır|
|&nbsp;&nbsp;[Kullanarak bildirimlerden P0195R2 paketi genişletmeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0195r2.html)|Hayır|
|&nbsp;&nbsp;[Tanınmayan P0283R2 yoksayılıyor öznitelikleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0283r2.html)|Hayır|
|&nbsp;&nbsp;[Başlatıcı listesi oluşturucuları için sınıf şablon bağımsız değişken kesintisi P0702R1 düzeltme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0702r1.html)|Hayır|
|__C ++ 20 çekirdek dil özellikleri__|__Desteklenen__|
|&nbsp;&nbsp;[P0306R4 ekleme #95; &#95; VA_OPT &#95; &#95; virgül atlandığını ve virgül silme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0306r4.pdf)|Hayır|
|&nbsp;&nbsp;[P0329R4 belirlenmiş başlatma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf)|Hayır|
|&nbsp;&nbsp;[P0409R2 izin vererek lambda [=, bu] yakalama](http://open-std.org/JTC1/SC22/WG21/docs/papers/2017/p0409r2.html)|Hayır|
|&nbsp;&nbsp;[Genel Lambda'lar için P0428R2 tanıdık şablon söz dizimi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0428r2.pdf)|Hayır|
|&nbsp;&nbsp;[Bit alanları P0683R1 varsayılan üye başlatıcıları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0683r1.html)|Hayır|
|&nbsp;&nbsp;[P0704R1 düzelttikten const lvalue başvuru tam üyeleri işaretçileri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0704r1.html)|Hayır|
|&nbsp;&nbsp;[P0734R0 kavramları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0734r0.pdf)|Hayır|


## <a name="standard-library-features"></a>Standart kitaplığı özellikleri

|Özellik alanı| |
|---|---|
|__C ++ 20 standart kitaplığı özellikleri__|__Desteklenen__|
|&nbsp;&nbsp;[P0463R1 endian](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0463r1.html)|Hayır|
|&nbsp;&nbsp;[Diziler için P0674R1 make_shared()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0674r1.html)|Hayır|
|__C ++ 17 standart kitaplığı özellikleri__|__Desteklenen__|
|&nbsp;&nbsp;[P0433R2 tümleştirme şablon kesintisi sınıf şablonları standart kitaplığına](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html)<br />&nbsp;&nbsp;[Standart kitaplığına sınıfı şablon bağımsız değişken kesintisi tümleştirmesi P0739R0 artırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html)|Hayır|
|&nbsp;&nbsp;[Char_traits P0426R1 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html)|Hayır|
|&nbsp;&nbsp;[P0030R1 hypot (x, y, z)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf)|Hayır|
|&nbsp;&nbsp;[P0220R1 kitaplığı temelleri V1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html)|Kısmi <sup> [J](#note_J)</sup>|
|&nbsp;&nbsp;[P0067R5 başlangıç dize dönüşümleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html)|Hayır|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<memory_resource >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#memory.resource.synop)<br />&nbsp;&nbsp;[P0337R0 silme polymorphic_allocator atama](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0337r0.html)|Hayır|
|&nbsp;&nbsp;[P0024R2 paralel algoritmalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html)<br />&nbsp;&nbsp;[P0336R1 Paralel yürütme ilkelerini yeniden adlandırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0336r1.pdf)<br />&nbsp;&nbsp;[P0394R4 paralel algoritmalar terminate() için özel durumlar gerekir.](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0394r4.html)<br />&nbsp;&nbsp;[P0452R1 birleştirin \<sayısal > paralel algoritmalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0452r1.html)|Hayır|
|&nbsp;&nbsp;[P0226R1 matematiksel özel işlevler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0226r1.pdf)|Hayır|
|&nbsp;&nbsp;[P0218R1 \<filesystem >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html)<br />&nbsp;&nbsp;[Dosya sistemi için P0219R1 göreli yollar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0219r1.html)<br />&nbsp;&nbsp;[Dosya sistemi için önbelleğe alma P0317R1 dizin girişi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p03179r1.html)<br />&nbsp;&nbsp;[P0392R0 destekleyen string_view içinde dosya sistemi yolları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0392r0.pdf)<br />&nbsp;&nbsp;[P0430R2 destekleyen POSIX olmayan bağlanan dosya sistemlerinin](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0430r2.pdf)<br />&nbsp;&nbsp;[Dosya sistemi için P0492R2 NB açıklamaları çözme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0492r2.html)|Hayır <sup> [K](#note_K)</sup>|
|&nbsp;&nbsp;[P0003R5 kaldırma dinamik özel durum belirtimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0005R4 not_fn()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html)<br />&nbsp;&nbsp;[Not_fn() P0358R1 düzeltmeler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Enable_shared_from_this P0033R1 uygun sözcükler kullanmak](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0083R3 boşluklarına ayıran eşler ve ayarlar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)<br />&nbsp;&nbsp;[P0508R0 açıklığa kavuşturan insert_return_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0174R2 onaysız kılınmadan Vestigial kitaplığı bölümleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0302R1 kaldırma ayırıcısı destek içinde std::function](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0414R2 shared_ptr\<T [] >, shared_ptr\<T [N] >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html)<br />&nbsp;&nbsp;[Shared_ptr P0497R0 düzeltmek için diziler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0521R0 onaysız kılınmadan shared_ptr::unique()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0521r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[Standart Kitaplığı P0607R0 satır içi değişkenleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0618R0 onaysız kılınmadan \<codecvt >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0618r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: Boyer Moore search()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#func.searchers.boyer_moore)<br/>&nbsp;&nbsp;[P0253R1 düzelttikten noktasıdır dönüş türleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0253r1.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0031R0 constexpr \<dizi > (yeniden) ve \<yineleyici >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0031r0.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0040R3 genişletme bellek yönetimi araçları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0040r3.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0084R2 Emplace dönüş türü](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0084r2.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0152R1 atomic::is_always_lock_free](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0152r1.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0154R1 hardware_destructive_interference_size, vb.](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0154r1.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0156R2 yeniden adlandırma Variadic kilit\_için kapsamlı koruma\_Kilitle](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0156r2.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0258R2 has_unique_object_representations](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0258r2.html)|VS 2017 15.3 <sup> [M](#note_L)</sup>|
|&nbsp;&nbsp;[P0295R0 gcd(), lcm()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0295r0.pdf)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0298R3 std::byte](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0298r3.pdf)|VS 2017 15.3 <sup> [17](#note_17), [bayt](#note_byte)</sup>|
|&nbsp;&nbsp;[P0403R1 UDLs için \<string_view > ("meow" sv, vs.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0403r1.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0418R2 atomik compare_exchange memory_order gereksinimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0418r2.html)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Common_type P0435R1 elden](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0435r1.pdf)<br />&nbsp;&nbsp;[Ortak P0548R1 Uyguladıkça\_türü ve süresi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0548r1.pdf)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0505R0 constexpr \<chrono > (yeniden)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0505r0.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0513R0 zehirleme karma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0513r0.pdf)<br />&nbsp;&nbsp;[P0599R1 noexcept karma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0599r1.pdf)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Kopyalama olarak shared_future noexcept P0516R0 işaretleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0516r0.html)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Future_errc gelen future_error P0517R0 oluşturma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0517r0.html)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0558R1 çözme atomik<T> adlı temel sınıfı tutarsızlıklar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0558r1.pdf)|VS 2017 15.3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0604R0 değiştirmek,\_aranabilir/sonuç\_, çağrılacak\_neden, olan\_invocable, olan\_nothrow\_invocable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0604r0.html)|VS 2017 15.3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<algoritması > sample()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#alg.random.sample)|VS 2017|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<herhangi >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#any)|VS 2017|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<isteğe bağlı >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#optional)|VS 2017|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<string_view >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#string.view)|VS 2017|
|&nbsp;&nbsp;[N4562 Kitaplığı temelleri: \<tanımlama grubu > apply()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#tuple)|VS 2017|
|&nbsp;&nbsp;[P0032R3 homojen arabirimi için variant/any/isteğe bağlı](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0032r3.pdf)|VS 2017|
|&nbsp;&nbsp;[P0077R2 is_callable, is_nothrow_callable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0077r2.html)|VS 2017|
|&nbsp;&nbsp;[P0088R3 \<değişken >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0088r3.html)|VS 2017|
|&nbsp;&nbsp;[P0163R0 shared_ptr::weak_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0163r0.html)|VS 2017|
|&nbsp;&nbsp;[P0209R2 make_from_tuple()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0209r2.pdf)|VS 2017|
|&nbsp;&nbsp;[P0254R2 tümleştirme string_view ve std::string](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0254r2.pdf)|VS 2017|
|&nbsp;&nbsp;[P0307R2 yapma isteğe bağlı büyük eşittir yeniden](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0307r2.pdf)|VS 2017|
|&nbsp;&nbsp;[P0393R3 yapma değişken büyük eşittir](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0393r3.html)|VS 2017|
|&nbsp;&nbsp;[P0504R0 yeniden ziyaret etme in_place_t/in_place_type_t\<T > / in_place_index_t\<t >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0504r0.html)|VS 2017|
|&nbsp;&nbsp;[P0510R0 reddetme çeşitleri, hiçbir şey, dizileri, başvuruları ve eksik türler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0510r0.html)|VS 2017|
|&nbsp;&nbsp;[P0025R1 clamp()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0025r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0185R1 is_swappable, is_nothrow_swappable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0185r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0272R1 Non-const basic_string::data()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0272r1.html)|VS 2015.3|
|&nbsp;&nbsp;[Çifti N4387 artırma ve tanımlama grubu](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4387.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4508 shared_mutex (Untimed)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4508.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Kullanım dışı Iostreams Aliases P0004R1 kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0004r1.html)|VS 2015.2 <sup> [rem](#note_rem)</sup>|
|&nbsp;&nbsp;[P0006R0 değişken şablonlar için tür özellikleri (is_same_v, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0006r0.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0007R1 as_const()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0007r1.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0013R1 mantıksal işleç tür özellikleri (birlikte, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0013r1.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0074R0 owner_less\<>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0074r0.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0092R1 \<chrono > floor(), ceil(), round(), abs()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0092r1.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0156R0 Variadic lock_guard](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0156r0.html)|VS 2015.2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N3911 void_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3911.pdf)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Unique_ptr N4089 güvenli dönüşümleri içinde\<T [] >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4089.pdf)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4169 olması](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4169.html)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4190 kaldırma auto_ptr, random_shuffle() And Old \<işlevsel > Hizmetler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4190.htm)|VS 2015 <sup> [rem](#note_rem)</sup>|
|&nbsp;&nbsp;[N4258 noexcept Temizlemeler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4258.pdf)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4259 uncaught_exceptions()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4259.pdf)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4277 Trivially Copyable reference_wrapper](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4277.html)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Harita/unordered_map N4279 insert_or_assign()/try_emplace()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4279.html)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4280 size(), empty(), data()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4280.pdf)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[Unique_ptr N4366 tam olarak sınırlama atama](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4366.html)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4389 bool_constant](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4389.html)|VS 2015 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0063R3 C11 standart kitaplığı](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0063r3.html)|VS 2015 <sup> [C11](#note_C11), [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4510 destekleyen tamamlanmamış türleri içinde vektör/listesi/forward_list](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4510.html)|VS 2013 <sup> [14](#note_14)</sup>|
|__C ++ 14 standart kitaplığı özellikleri__|__Desteklenen__|
|&nbsp;&nbsp;[N3462 SFINAE kolay result_of](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3462.html)|VS 2015.2|
|&nbsp;&nbsp;[N3302 constexpr \<karmaşık >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2011/n3302.html)|VS 2015|
|&nbsp;&nbsp;[N3469 constexpr \<chrono >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3469.html)|VS 2015|
|&nbsp;&nbsp;[N3470 constexpr \<dizi >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3470.html)|VS 2015|
|&nbsp;&nbsp;[N3471 constexpr \<initializer_list >, \<tanımlama grubu >, \<yardımcı programı >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3471.html)|VS 2015|
|&nbsp;&nbsp;[N3545 integral_constant::operator()()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3545.pdf)|VS 2015|
|&nbsp;&nbsp;[N3642 UDLs için \<chrono >, \<dize > (1729ms, "meow" s, vs.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3642.pdf)|VS 2015|
|&nbsp;&nbsp;[N3644 Null iletme yineleyiciler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3644.pdf)|VS 2015|
|&nbsp;&nbsp;[N3654 quoted()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3654.html)|VS 2015|
|&nbsp;&nbsp;[N3657 Heterojen ilişkilendirilebilir arama](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3657.htm)|VS 2015|
|&nbsp;&nbsp;[N3658 integer_sequence](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3658.html)|VS 2015|
|&nbsp;&nbsp;[N3659 shared_mutex (zamanlanmış)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3659.html)|VS 2015|
|&nbsp;&nbsp;[N3668 exchange()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3668.html)|VS 2015|
|&nbsp;&nbsp;[Üye işlevleri olmadan const constexpr N3669 düzeltme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3669.pdf)|VS 2015|
|&nbsp;&nbsp;[N3670 get\<T >)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3670.html)|VS 2015|
|&nbsp;&nbsp;[N3671 Çift aralıklı equal(), is_permutation(), mismatch()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3671.html)|VS 2015|
|&nbsp;&nbsp;[N3778 Boyutlu ayırmayı kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3779 UDLs için \<karmaşık > (3.14i, vs.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3779.pdf)|VS 2015|
|&nbsp;&nbsp;[N3789 constexpr \<işlevsel >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3789.htm)|VS 2015|
|&nbsp;&nbsp;[N3887 tuple_element_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3887.pdf)|VS 2015|
|&nbsp;&nbsp;[Shared_mutex (zamanlanmış) shared_timed_mutex için N3891 yeniden adlandırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3891.htm)|VS 2015|
|&nbsp;&nbsp;[N3346 En az bir kapsayıcı öğe gereksinimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3346.pdf)|VS 2013|
|&nbsp;&nbsp;[N3421 saydam işleci Functors (daha az\<> vb..)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3421.htm)|VS 2013|
|&nbsp;&nbsp;[N3655 diğer şablonlar için \<type_traits > (decay_t, vs.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3655.pdf)|VS 2013|
|&nbsp;&nbsp;[N3656 make_unique()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3656.htm)|VS 2013|
|&nbsp;&nbsp;[N3924 rand() Discouraging](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3924.pdf)|Yok|

Birlikte listelenen yazıları bir grup özellik standart oy ve ardından artırmak veya bu özelliği genişletmek için bir veya daha fazla yazıları da oy gösterir. Bu özellikleri birlikte uygulanır.

### <a name="supported-values"></a>Desteklenen değerler

__Hayır__ henüz uygulanmadı anlamına gelir.  
__Kısmi__ Visual Studio 2017 uygulamasında eksik olduğu anlamına gelir. Daha fazla ayrıntı için Notlar bölümüne bakın.  
__Yok__ teklifi yazıları özelliklerini açıklayan değil anlamına gelir. Bu raporları, standart dilinin değiştirilmiş ancak uygulayıcılar için herhangi bir iş oluşturmamışsınızdır. Bütünlük açısından buraya listelendikleri.  
__VS 2010__ Visual Studio 2010'da desteklenen özellikleri gösterir.  
__VS 2013__ Visual Studio 2013'te desteklenen özellikleri gösterir.  
__VS 2015__ Visual Studio 2015 RTM ile desteklenen özellikleri gösterir.  
__VS 2015.2__ ve __VS 2015.3__ Visual Studio 2015 güncelleştirme 2 ve Visual Studio 2015 güncelleştirme 3, sırasıyla desteklenen özellikleri belirtin.  
__VS 2017__ Visual Studio 2017 RTM içinde desteklenen özellikleri gösterir.  
__VS 2017 15.3__ Visual Studio 2017 sürüm 15.3 desteklenen özellikleri gösterir.  
__VS 2017 15,5__ Visual Studio 2017 sürüm 15,5 desteklenen özellikleri gösterir.

### <a name="notes"></a>Notlar

<a name="note_A"></a>__A__ bu C ++ 11'de kullanım dışı bırakılan C ++ 03's dinamik özel durum belirtimleri yok sayar. Bunları, bir gelecekteki C++ Standart kaldırılması Beklenti uygulama için hiçbir plan yoktur.  
<a name="note_B"></a>__B__ iki aşamalı ad arama derleyicinin desteği geliştirilmiştir ancak tamamlanmamış kalır.  
<a name="note_C"></a>__C__ Visual Studio 2015 güncelleştirme 2'den derleyicinin ifade SFINAE desteği için standart kitaplığı yeterli olmuştur, ancak destek tamamlanmamış kalır.  
<a name="note_D"></a>__D__ C99 önişlemci kuralı derleyicinin desteği Visual Studio 2017 içinde tamamlanmadı. Variadic makrolar desteklenir, ancak önişlemci'nin davranışını birçok hata vardır.  
<a name="note_E"></a>__E__ derleyicileri izin verilir, ancak, genişletilmiş tamsayı türlerini desteklemek için gerekli değildir çünkü bu uygulanamaz olarak işaretlenir.  GCC ve Clang gibi biz bunları desteklemiyor seçtiniz.  
<a name="note_F"></a>__F__ derleyicileri izin verilir, ancak, bu en iyi duruma getirme uygulamak için gerekli değildir çünkü benzer şekilde, bu uygulanamaz olarak işaretlenir.  
<a name="note_G"></a>__G__ altında desteklenen [/Std: c ++ 14](./build/reference/std-specify-language-standard-version.md) suppressible bir uyarı.  
<a name="note_H"></a>__H__ bu özellik Visual Studio 2017 sürüm 15.3 önizlemelerde kullanılabilir, ancak hatalar bulunduğundan ve sürümünden kaldırılmıştır.  
<a name="note_J"></a>__J__ Visual Studio 2015'te tamamlanmamış özellikleri bozuk başka bir yerde bu tabloda.  
<a name="note_K"></a>__K__ Filesystem TS hem de uygulanır \<Deneysel/dosya sistemi > ve \<filesystem > için geçmiş nedeniyle, ancak kendi uygulama kendi ad taşımadan önce düzeltilmelidir. Bu tamamlanana kadar bu özellik henüz uygulanmadı olarak işaretlenir.  
<a name="note_L"></a>__M__ iç derleyici tarafından desteklenir. Bu iç henüz Clang içinde kullanılamaz. , Kullanılabilir, ancak henüz etkin değil olarak IntelliSense özelliğidir.   
<a name="note_14"></a>__14__ bu C ++ 17 özellikler her zaman etkindir, bile [/Std: c ++ 14](./build/reference/std-specify-language-standard-version.md) (varsayılan) belirtilir. Özellik giriş önce uygulanan ya da olmasıdır **/std** seçenekleri veya koşullu uygulama açabileceğinin karmaşıktı.  
<a name="note_17"></a>__17__ bu özellikler tarafından etkinleştirilen [/Std: c ++ 17](./build/reference/std-specify-language-standard-version.md) (veya [/Std: c ++ Son](./build/reference/std-specify-language-standard-version.md)) derleyici seçeneği.  
<a name="note_byte"></a>__bayt__ `std::byte` tarafından etkin [/Std: c ++ 17](./build/reference/std-specify-language-standard-version.md) (veya [/Std: c ++ Son](./build/reference/std-specify-language-standard-version.md)), ancak bazı durumlarda Windows SDK'sı üst bilgileri ile çakışabileceği için bir hassas çevirin Makro. Bunu tanımlayarak devre dışı bırakılabilir `_HAS_STD_BYTE` olarak `0`.  
<a name="note_C11"></a>__C11__ Evrensel CRT uygulanan C99 dışında C ++ 17, gerekli olan C11 standart kitaplığı bölümlerini `strftime()` E/O alternatif dönüştürme tanımlayıcıları C11 `fopen()` özel kullanım modu ve C11 `aligned_alloc()`. C11 belirtilen ikinci uygulanması olası olduğundan `aligned_alloc()` Microsoft uygulaması ile uyumsuz şekilde `free()`, ayrıca, `free()` yüksek oranda hizalanmış ayırmaları olması gerekir.  
<a name="note_rem"></a>__REM__ kaldırılan Özellikler [/Std: c ++ 17](./build/reference/std-specify-language-standard-version.md) (veya [/Std: c ++ Son](./build/reference/std-specify-language-standard-version.md)) derleyici seçeneği belirtildi. Bu özellikler çevirin makrolar sahip: `_HAS_AUTO_PTR_ETC`, `_HAS_FUNCTION_ALLOCATOR_SUPPORT`, `_HAS_OLD_IOSTREAMS_MEMBERS`, ve `_HAS_UNEXPECTED`.
  
## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](cpp/cpp-language-reference.md)  
[C++ Standart Kitaplığı](standard-library/cpp-standard-library-reference.md)   
[Visual Studio 2017 C++ uygunluk yenilikleri](cpp-conformance-improvements-2017.md)  
[Visual Studio 2017'de Visual C++ yenilikleri](what-s-new-for-visual-cpp-in-visual-studio.md)  
[Visual C++ değişiklik geçmişini 2015 üzerinden 2003](porting/visual-cpp-change-history-2003-2015.md)  
[Visual C++ 2015 aracılığıyla yeni 2003 nedir](porting/visual-cpp-what-s-new-2003-through-2015.md)  
[Visual C++ ekip blogu](https://blogs.msdn.microsoft.com/vcblog/)  
