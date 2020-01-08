---
title: Microsoft C++ dil uygunluk tablosu
ms.date: 10/31/2019
ms.technology: cpp-language
ms.assetid: 475da6e9-0d78-4b4e-bd23-f41c406c4efe
author: corob-msft
ms.author: corob
ms.openlocfilehash: e029752ebaae5debb33d8e4a3920c5572f4d923b
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302152"
---
# <a name="microsoft-c-language-conformance-table"></a>Microsoft C++ dil uygunluk tablosu

Visual Studio 'da Microsoft C++ derleyicisi için standartlar uyumluluğu (MSVC), sürmekte olan bir çalışmadır. Aşağıda, Visual Studio sürümü tarafından ISO standart C++ dilimizin ve kitaplık uyumsuzluğuna ilişkin bir Özet verilmiştir. Her derleyici ve standart kitaplık Özellik adı, yayınlama zamanında kullanılabilir olan C++ ÖZELLIĞI açıklayan ISO standart teklif kağıdına bağlanır. **Desteklenen** sütun, ilk olarak özelliğin desteklediği Visual Studio sürümünü listeler.

Visual Studio 2017 veya Visual Studio 2019 MSVC uyumluluk geliştirmeleri hakkında daha fazla bilgi için bkz [ C++ . Visual Studio 'da uyumluluk geliştirmeleri](cpp-conformance-improvements.md). Diğer değişikliklerin listesi için bkz. [Visual Studio 'Da Visual C++ için yenilikler](what-s-new-for-visual-cpp-in-visual-studio.md). Önceki sürümlerde uygunluk değişiklikleri için bkz. [ C++ görsel değişiklik geçmişi](../porting/visual-cpp-change-history-2003-2015.md) ve [görsel C++ yenilikler 2003 ile 2015 arasındaki](../porting/visual-cpp-what-s-new-2003-through-2015.md)yenilikler. C++ Ekipten güncel haberler için [ C++ ekip blogunu](https://devblogs.microsoft.com/cppblog/)ziyaret edin.

> [!NOTE]
> Visual Studio 2015, Visual Studio 2017 ve Visual Studio 2019 arasında ikili bir son değişiklik yoktur. Daha fazla bilgi için bkz [ C++ . Visual Studio 2015, 2017 ve 2019 arasında ikili uyumluluk](../porting/binary-compat-2015-2017.md)

## <a name="compiler-features"></a>Derleyici özellikleri

| | |
|----|---|
|__C++ 03/11 çekirdek dil özellikleri__|__Destekleniyor__|
|diğer her şeyi &nbsp;&nbsp;|VS 2015 <sup>[A](#note_A)</sup>|
|Iki aşamalı ad aramasını &nbsp;&nbsp;|VS 2017 15,7 <sup> [B](#note_B)</sup>|
|&nbsp;&nbsp;[N2634 ifadesi SFINAE](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2634.html)|VS 2017 15,7|
|&nbsp;&nbsp;[N1653 C99 ön işlemcisi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1653.htm)|Kısmi <sup> [C](#note_C)</sup>|
|__C++ 14 çekirdek dil özellikleri__|__Destekleniyor__|
|[bağlamsal dönüşümler için &nbsp;&nbsp;N3323 tweaked ifadesi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3323.pdf)|VS 2013|
|&nbsp;&nbsp;[N3472 ikili sabit değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3472.pdf)|VS 2015|
|&nbsp;&nbsp;[N3638 Auto ve decltype (Auto) dönüş türleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3638.html)|VS 2015|
|&nbsp;&nbsp;[N3648 init-yakalamaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3648.html)|VS 2015|
|&nbsp;&nbsp;[N3649 genel Lambdalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3649.html)|VS 2015|
|&nbsp;&nbsp;[N3760 \[\[kullanım dışı\]\] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3760.html)|VS 2015|
|&nbsp;&nbsp;[N3778 boyutu ayırmayı kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3781 basamak ayırıcıları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3781.pdf)|VS 2015|
|&nbsp;&nbsp;[N3651 değişken şablonları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3651.pdf)|VS 2015,2|
|&nbsp;&nbsp;[N3652 genişletilmiş constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)|VS 2017 15,0|
|[toplamalar Için varsayılan N3653 üye başlatıcıları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3653.html) &nbsp;&nbsp;|VS 2017 15,0|
|__C++ 17 çekirdek dil özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[N4086 trigraf kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)|VS 2010 <sup>[14](#note_14)</sup>|
|N3922 &nbsp;&nbsp;[, örgü-init-Lists ile otomatik Için yeni kurallar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)|VS 2015 <sup>[14](#note_14)</sup>|
|[şablon şablonunda &nbsp;&nbsp;N4051 TypeName-parametreler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)|VS 2015 <sup>[14](#note_14)</sup>|
|[ad alanları ve Numaralandırıcılar için &nbsp;N4266 öznitelikleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html) &nbsp;|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4267 u8 karakter sabit değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4230 Iç içe ad alanı tanımları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4230.html)|VS 2015,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N3928 Terse static_assert](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)|VS 2017 15,0 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0184R0 Genelleştirilmiş Aralık tabanlı for-döngüleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)|VS 2017 15,0 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0188R1 \[\[fallthrough\]\] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r1.pdf)|VS 2017 15,0 <sup> [17](#note_17)</sup>|
|[register anahtar sözcüğünü kaldırmak](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html) &nbsp;&nbsp;P0001R1|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|[bool için &nbsp;P0002R1 &nbsp;Işlecini kaldırır](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0018R3 yakalama * bu değere göre](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|[yineleme olmadan öznitelik ad alanlarını kullanarak &nbsp;P0028R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0028r4.html) &nbsp;|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0061R1 \_\_has_include](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0061r1.html)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0138R2 doğrudan-List-tamsayıların sabit Numaralandırmaların init](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0170R1 constexpr lambdaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0170r1.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0189R1 \[\[noDiscard\]\] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0189r1.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0212R1 \[\[maybe_unused\]\] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0212r1.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0217R3 yapısal bağlamaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0217r3.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0292R2 constexpr if-deyimlerini](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0292r2.html)|VS 2017 15,3 <sup> [D](#note_D)</sup>|
|[başlatıcılarla &nbsp;P0305R1 Selection deyimlerini](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0305r1.html) &nbsp;|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0245R1 onaltıya kayan harfler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0245r1.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4268 daha fazla tür olmayan şablon bağımsız değişkeni sağlar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4268.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4295 katlama ifadeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4295.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0003R5 dinamik özel durum belirtimlerini kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|[tür sistemine P0012R1 &nbsp;&nbsp;noexcept ekleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0012r1.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0035R4 üzeri hizalanmış dinamik bellek ayırmayı](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0035r4.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0386R2 satır içi değişkenleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0386r2.pdf)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0522R0 eşleşen şablon şablonu-parametreleri uyumlu bağımsız değişkenlere](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0522r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0036R0 kaldırma bazı boş birli katlar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0036r0.pdf)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[N4261 düzeltme nitelikleri dönüştürmeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4261.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0017R1 genişletilmiş toplu başlatma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|[sınıf şablonları için &nbsp;&nbsp;P0091R3 şablon bağımsız değişken kesintisi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)<br/>&nbsp;&nbsp;[P0512R0 sınıf şablonu bağımsız değişken kesintisi sorunları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0512r0.pdf)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0127R2, otomatik olarak tür olmayan şablon parametrelerini bildirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0135R1 garantili kopya](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0135r1.html)|VS 2017 15,6|
|&nbsp;&nbsp;[P0136R1 rehiri devralan oluşturucular](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0137R1 std:: Lain](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0137r1.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0145R3 iyileştirme ifade değerlendirmesi sırası](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0145r3.pdf)<br/>[işlev bağımsız değişkenlerinin P0400R0 &nbsp;&nbsp;değerlendirmesi sırası](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0400r0.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0195R2 Pack genişletmeleri, using bildirimleri içinde](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0195r2.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0283R2 tanınmayan öznitelikleri yok sayıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0283r2.html)|VS 2015 <sup>[14](#note_14)</sup>|
|__C++ 17 çekirdek dil özellikleri (hata raporları)__|__Destekleniyor__|
|&nbsp;&nbsp;[P0702R1 düzeltme sınıfı şablon bağımsız değişken kesintisi başlatıcı-liste oluşturucuları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0702r1.html)|VS 2017 15,7 <sup> [17](#note_17)</sup>|
|&nbsp;[P0961R1 &nbsp;yapılandırılmış bağlamalar özelleştirme noktası bulma kuralları bulma](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0961r1.html)|VS 2019 16,0 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0969R0, erişilebilir üyelere yapılandırılmış bağlamalar sağlar](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0969r0.pdf)|VS 2019 16,0 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0588R1 örtük lambda yakalamayı basitleştirir](http://wg21.link/p0588r1)|VS 2019 16,4 <sup> [17](#note_17)</sup>|
|[oluşturucular için &nbsp;&nbsp;P1771R1 \[\[noDiscard\]\]](https://wg21.link/p1771r1)|VS 2019 16,4 <sup> [17](#note_17)</sup>|
|[P0527R1 ve P1155R3 için &nbsp;P1825R0 &nbsp;birleştirilmiş ifadesi, daha örtük olarak taşınan](https://wg21.link/p1825r0)|VS 2019 16,4 <sup> [17](#note_17)</sup>|
|[soyut sınıf türleri için &nbsp;P0929R2 denetimi](https://wg21.link/P0929R2) &nbsp;|Hayır|
|&nbsp;&nbsp;[P0962R2 aralığını yeniden edinme-for döngüsü özelleştirme noktası kuralları bulma](https://wg21.link/p0962r1)|Hayır|
|&nbsp;&nbsp;[P0859R0 CWG 1581: constexpr üye işlevleri tanımlandığında](https://wg21.link/p0859r0)|Hayır|
|&nbsp;&nbsp;[P1009R2 dizi boyut kesintisi New-ifadelerde](https://wg21.link/P1009R2)|Hayır|
|&nbsp;&nbsp;[P1286R2 Contra CWG DR1778](https://wg21.link/P1286R2)|Hayır|
|__C++ 20 çekirdek dil özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[P0704R1, const lvalue başvurusunu düzeltme, üyelere nitelenmiş işaretçiler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0704r1.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P1041R4 char16_t/char32_t dize sabit DEĞERLERI UTF-16/32 olmalıdır](https://wg21.link/P1041R4)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P1330R0, constexpr içindeki bir birleşimin etkin üyesini değiştirme](https://wg21.link/P1330R0)|VS 2017 15,0 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0972R0 noexcept \<zaman hatası > sıfır (), min (), Max ()](https://wg21.link/P0972R0)|VS 2017 15,7 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0515R3 üç yönlü (Spaceship) karşılaştırma işleci < = >](https://wg21.link/P0515R3)|VS 2019 16,0 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0941R2 özelliği-test makroları](https://wg21.link/P0941R2)|VS 2019 16,0 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P1008R1, Kullanıcı tarafından belirtilen oluşturucularla toplamalar](https://wg21.link/P1008R1) yasaklıyor|VS 2019 16,0 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0329R4 belirlenmiş başlatma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0846R0 ADL ve görünmeyen işlev şablonları](https://wg21.link/P0846R0)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0409R2, Lambda yakalama \[=, bu\]](http://open-std.org/JTC1/SC22/WG21/docs/papers/2017/p0409r2.html)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|[genel Lambdalar için &nbsp;&nbsp;P0428R2 tanıdık şablon söz dizimi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0428r2.pdf)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0624R2 varsayılan oluşturulabilir ve atanabilir durum bilgisi olmayan Lambdalar](https://wg21.link/P0624R2)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0780R2, lambda init-Capture içinde paket genişletmesine Izin verir](https://wg21.link/P0780R2)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0806R2 \[=aracılığıyla örtülü yakalamayı kullanımdan kaldırır \]](https://wg21.link/P0806R2)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|[< = > ve diğer karşılaştırma işleçleri için &nbsp;P1120R0 &nbsp;tutarlılık iyileştirmeleri](https://wg21.link/P1120R0)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P1185R2 \<=\> != ==](https://wg21.link/P1185R2)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0734R0 kavramları](https://wg21.link/P0734R0)|VS 2019 16,3 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0857R0 Işlevselliği düzeltme aralıkları](https://wg21.link/P0857R0)|VS 2019 16,3 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P1084R2 Bugünün dönüş türü-gereksinimler yetersiz](https://wg21.link/P1084R2)|VS 2019 16,3 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0892R2 koşullu açık](https://wg21.link/P0892R2)|VS 2019 16,4 <sup> [20](#note_20)</sup>|
|[yapılandırılmış bağlamaları P1091R3 değişken bildirimleri gibi bir şekilde genişletmek](https://wg21.link/P1091R3) &nbsp;&nbsp;|VS 2019 16,4 <sup> [20](#note_20)</sup>|
|[enum kullanarak &nbsp;P1099R5](https://wg21.link/P1099R5) &nbsp;|VS 2019 16,4 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[\<gerçekten kullandığınızda =>](https://wg21.link/P1186R3)|VS 2019 16,4 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P1630R1 Spaceship bir ayarlama gerektirir](https://wg21.link/P1630R1)|VS 2019 16,4 <sup> [20](#note_20)</sup>|
|[Varsayılan olarak kopya Oluşturucu ile &nbsp;&nbsp;P0641R2 const uyuşmazlığı](https://wg21.link/P0641R2)|Kısmi|
|&nbsp;&nbsp;[P0306R4 ekleme \_\_VA_OPT\_virgül çıkarma ve virgül silme için](https://wg21.link/P0306R4) \_|Hayır|
|&nbsp;&nbsp;[P0315R4, değerlendirilen bağlamlarda lambdalara Izin verir](https://wg21.link/P0315R4)|Hayır|
|&nbsp;&nbsp;[P0479R5 \[\[büyük olasılıkla\]\] ve \[\[olası\]\] öznitelikleri](https://wg21.link/P0479R5)|Hayır|
|&nbsp;&nbsp;[P0542R5 sözleşmeleri](https://wg21.link/P0542R5)|Hayır|
|&nbsp;&nbsp;[P0614R1 Aralık tabanlı for-döngüleri Başlatıcı](https://wg21.link/P0614R1)|Hayır|
|[TypeName ile &nbsp;P0634R3](https://wg21.link/P0634R3) &nbsp;.|Hayır|
|[bit alanları için &nbsp;P0683R1 &nbsp;varsayılan üye başlatıcıları](https://wg21.link/P0683R1)|Hayır|
|&nbsp;&nbsp;[P0692R1, Uzmanlıklar üzerinde erişim denetimi](https://wg21.link/P0692R1)|Hayır|
|[değişken boyutlu sınıflar için &nbsp;&nbsp;P0722R3 boyutlu silme](https://wg21.link/P0722R3)|Hayır|
|[tür olmayan şablon parametrelerinde &nbsp;P0732R2 sınıf türleri](https://wg21.link/P0732R2) &nbsp;|Hayır|
|&nbsp;&nbsp;[P0840R2 \[\[no_unique_address\]\] özniteliği](https://wg21.link/P0840R2)|Hayır|
|&nbsp;&nbsp;[P0912R5 coroutines](https://wg21.link/P0912R5)|Hayır|
|&nbsp;&nbsp;[P0960R3, parantez içinde değerler listesinden toplamalar başlatmaya Izin ver](https://wg21.link/P0960R3)|Hayır|
|[constexpr işlevlerinde &nbsp;&nbsp;P1002R1 try-catch blokları](https://wg21.link/P1002R1)|Hayır|
|[sabit ifadelerde sanal işlev çağrılarına Izin veren &nbsp;P1064R0](https://wg21.link/P1064R0) &nbsp;|Hayır|
|&nbsp;&nbsp;[P1073R3 anlık işlevleri](https://wg21.link/P1073R3)|Hayır|
|&nbsp;&nbsp;[P1094R2 Iç Içe geçmiş satır adları](https://wg21.link/P1094R2)|Hayır|
|&nbsp;&nbsp;[P1103R3 modülleri](https://wg21.link/P1103R3)|Hayır|
|&nbsp;&nbsp;[P1139R2 adres IFADESI ıso 10646 ile ilgili sorunları](https://wg21.link/P1139R2)|Hayır|
|[Kısıtlanmış bildirimlere yönelik başka bir yaklaşım &nbsp;P1141R2](https://wg21.link/P1141R2) &nbsp;|Hayır|
|&nbsp;&nbsp;[P1236R1 işaretli tamsayılar iki tamamlayanı](https://wg21.link/P1236R1)|Hayır|
|[sözleşme koşullarında &nbsp;&nbsp;P1289R1 erişim denetimi](https://wg21.link/P1289R1)|Hayır|
|&nbsp;&nbsp;[P1323R2 sözleşmesi Sonkoşulları ve dönüş türü kesintisi](https://wg21.link/P1323R2)|Hayır|
|&nbsp;&nbsp;[P1327R1 dynamic_cast, sabit ifadelerde polimorfik TypeId](https://wg21.link/P1327R1)|Hayır|
|[P1353R0 eksik özellik-test makroları](https://wg21.link/P1353R0) &nbsp;&nbsp;|Hayır|
|[yapılandırılmış bağlamalardan oluşan &nbsp;P1381R1 başvuru yakalaması](https://wg21.link/P1381R1) &nbsp;|Hayır|

## <a name="standard-library-features"></a>Standart Kitaplık Özellikleri

| | |
|---|---|
|__C++ 20 Standart Kitaplık Özellikleri__|__Destekleniyor__|
|[sıralanmamış kapsayıcıları karşılaştıran &nbsp;P0809R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0809r0.pdf) &nbsp;| VS 2010 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0858R0 constexpr Yineleyici gereksinimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0858r0.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0777R1 gereksiz Decay](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0777r1.pdf)|VS 2017 15,7 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P1164R1 yapma create_directory () sezgisel](https://wg21.link/P1164R1)|VS 2019 16,0 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0550R2 remove_cvref](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf)|VS 2019 16,0 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0318R1 unwrap_reference, unwrap_ref_decay](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0318r1.pdf)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|[basic_string/Basic_string_view için &nbsp;&nbsp;P0457R2 starts_with ()/ends_with ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0457r2.html)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|[sıralanmış ve sıralanmamış Ilişkilendirilebilir kapsayıcılar için &nbsp;&nbsp;P0458R2 Contains ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0458r2.html)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0646R1 List/forward_list Remove ()/remove_if ()/Unique () Return size_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0646r1.pdf)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0769R2 shift_left (), shift_right ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0769r2.pdf)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0887R1 type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf)|VS 2019 16,1 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0020R6 atomik\<float >, atomik\<çift >, atomik\<uzun çift >](https://wg21.link/p0020r6)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0463R1 endian](https://wg21.link/p0463r1)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0482R6 char8_t: UTF-8 karakter ve dizeleri Için bir tür](https://wg21.link/P0482R6)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0600R1 \[\[noDiscard\]STL, Bölüm 1 için \]](https://wg21.link/p0600r1)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0653R2 to_address ()](https://wg21.link/p0653r2)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0754R2 \<sürümü >](https://wg21.link/p0754r2)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|[std:: Işlevin taşıma Oluşturucusu için &nbsp;&nbsp;P0771R1 noexcept](https://wg21.link/P0771R1)|VS 2019 16,2 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0487R1 düzeltme işleci > > (basic_istream &, grafik *)](https://wg21.link/P0487R1)|VS 2019 16,3 <sup> [20](#note_20)</sup>|
|[\<sayısal > Move () kullanarak &nbsp;P0616R0](https://wg21.link/p0616r0) &nbsp;|VS 2019 16,3 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0758R1 is_nothrow_convertible](https://wg21.link/P0758R1)|VS 2019 16,3 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0898R3 standart kitaplığı kavramları](https://wg21.link/P0898R3)|VS 2019 16,3 <sup> [20](#note_20)</sup>|
|[sıralanmamış kapsayıcılar için &nbsp;P0919R3 &nbsp;heterojen arama](https://wg21.link/P0919R3)|VS 2019 16,3 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P1754R1 yeniden adlandırma kavramları standard_case](https://wg21.link/P1754R1)|VS 2019 16,4 <sup> [20](#note_20)</sup>|
|&nbsp;&nbsp;[P0019R8 atomic_ref](https://wg21.link/P0019R8)|Hayır|
|&nbsp;&nbsp;[P0053R7 \<syncstream >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0053r7.pdf)<br/>&nbsp;&nbsp;[P0753R2 osyncstream Işleicileri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0753r2.pdf)|Hayır|
|&nbsp;&nbsp;[P0122R7 \<span >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0122r7.pdf)|Hayır|
|[\<algoritma > ve Exchange () için &nbsp;P0202R3 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0202r3.html) &nbsp;|Hayır|
|&nbsp;&nbsp;[P0339R6 polymorphic_allocator < >](https://wg21.link/P0339R6)|Hayır|
|&nbsp;&nbsp;[P0340R3 SFINAE kullanımı kolay underlying_type](https://wg21.link/P0340R3)|Hayır|
|&nbsp;&nbsp;[P0355R7 \<zaman dilimi > takvimler ve saat dilimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0355r7.html)|Hayır|
|&nbsp;&nbsp;[P0356R5 bind_front ()](https://wg21.link/P0356R5)|Hayır|
|[Reference_wrapper eksik türleri desteklemek](https://wg21.link/P0357R3) &nbsp;&nbsp;P0357R3|Hayır|
|[\<karmaşık > için &nbsp;P0415R1 constexpr &nbsp;(yeniden)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0415r1.html)|Hayır|
|&nbsp;&nbsp;[P0439R0 enum sınıfı memory_order](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0439r0.html)|Hayır|
|[piecewise oluşturma için &nbsp;&nbsp;P0475R1 garantili kopya](https://wg21.link/P0475R1)|Hayır|
|&nbsp;&nbsp;[P0476R2 <bit> bit_cast](https://wg21.link/P0476R2)|Hayır|
|&nbsp;&nbsp;[P0528R3 atomik karşılaştırma-ve-doldurma bitleri Ile değişim](https://wg21.link/P0528R3)|Hayır|
|&nbsp;&nbsp;[P0556R3 <bit> ispow2 (), ceil2 (), Floor2 (), log2p1 ()](https://wg21.link/P0556R3)|Hayır|
|[kullanımlar-ayırıcı oluşturma için &nbsp;P0591R4 yardımcı program işlevleri](https://wg21.link/P0591R4) &nbsp;|Hayır|
|&nbsp;&nbsp;[P0608R3 artırma, oluşturucuyu/atamayı dönüştürme](https://wg21.link/P0608R3)|Hayır|
|&nbsp;&nbsp;[P0619R4 kaldırma C + +17-c++ 20 ' de kullanım dışı Özellikler](https://wg21.link/P0619R4)|Hayır|
|&nbsp;&nbsp;[P0653R2 to_address ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0653r2.html)|Hayır|
|&nbsp;&nbsp;[P0655R1 ziyaret<R>()](https://wg21.link/P0655R1)|Hayır|
|[diziler için &nbsp;&nbsp;P0674R1 make_shared ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0674r1.html)|Hayır|
|&nbsp;&nbsp;[P0718R2 atomik\<shared_ptr\<t > >, atomik\<weak_ptr\<t >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0718r2.html) >|Hayır|
|&nbsp;&nbsp;[P0738R2 Istream_iterator Temizleme](https://wg21.link/P0738R2)|Hayır|
|&nbsp;&nbsp;[P0767R1 Is_pod kullanımdan](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0767r1.html) kaldırıldı|Hayır|
|[Spaceship karşılaştırma işleci \<için &nbsp;P0768R1 kitaplık desteği &nbsp;=>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0768r1.pdf)|Hayır|
|&nbsp;&nbsp;[P0811R3 Orta (), Lerp ()](https://wg21.link/P0811R3)|Hayır|
|[değiştirme Işlevleri için &nbsp;&nbsp;P0879R0 constexpr](https://wg21.link/P0879R0)|Hayır|
|&nbsp;&nbsp;[P0896R4 \<aralıkları\>](https://wg21.link/P0896R4)|Hayır|
|Eş yordamları [için &nbsp;P0912R5 kitaplık desteği](https://wg21.link/P0912R5) &nbsp;|Hayır|
|&nbsp;&nbsp;[P0920R2 önceden hesaplanmış karma değer araması](https://wg21.link/P0920R2)|Hayır|
|&nbsp;&nbsp;[P0935R0 Eryngereksiz açık varsayılan oluşturucular başlatılıyor](https://wg21.link/P0935R0)|Hayır|
|&nbsp;&nbsp;[P0966R1 String:: Reserve () daraltılamıyor](https://wg21.link/P0966R1)|Hayır|
|&nbsp;&nbsp;[P1001R2 yürütmesi:: unseq](https://wg21.link/P1001R2)|Hayır|
|[pointer_traits < t * > için &nbsp;&nbsp;P1006R1 constexpr::p ointer_to ()](https://wg21.link/P1006R1)|Hayır|
|&nbsp;&nbsp;[P1007R3 assume_aligned ()](https://wg21.link/P1007R3)|Hayır|
|[varsayılan başlatma ile &nbsp;&nbsp;P1020R1 akıllı Işaretçi oluşturma](https://wg21.link/P1020R1)|Hayır|
|[std:: Array karşılaştırmaları için &nbsp;&nbsp;P1023R0 constexpr](https://wg21.link/P1023R0)|Hayır|
|&nbsp;&nbsp;[P1032R1 çeşitli constexpr](https://wg21.link/P1032R1)|Hayır|
|&nbsp;&nbsp;[P1165R1 basic_string işleci + () Içinde durum bilgisi olan ayırıcıları tutarlı bir şekilde yayın](https://wg21.link/P1165R1)|Hayır|
|&nbsp;&nbsp;[P1209R0 erase_if (), Erase ()](https://wg21.link/P1209R0)|Hayır|
|&nbsp;&nbsp;[P1227R2 signed std:: ssize (), işaretsiz span:: size ()](https://wg21.link/P1227R2)|Hayır|
|&nbsp;&nbsp;[P1285R0, tür nitelikleri Için tamamlayıcı gereksinimleri iyileştiriliyor](https://wg21.link/P1285R0)|Hayır|
|&nbsp;&nbsp;[P1357R1 is_bounded_array, is_unbounded_array](https://wg21.link/P1357R1)|Hayır|
|__C++ 17 standart kitaplığı özellikleri__|__Destekleniyor__|
|[nullptr için &nbsp;&nbsp;LWG 2221 biçimli çıktı işleci](https://cplusplus.github.io/LWG/issue2221)|VS 2019 16,1|
|&nbsp;&nbsp;[N3911 void_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3911.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|[unique_ptr\<t [] &nbsp;N4089 &nbsp;güvenli dönüştürmeleri >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4089.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4169 Invoke ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4169.html)|VS 2015 <sup>[14](#note_14)</sup>|
|[auto_ptr, random_shuffle () ve eski \<işlevsel > &nbsp;&nbsp;N4190 kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4190.htm)|VS 2015 <sup> [kal](#note_rem)</sup>|
|&nbsp;&nbsp;[N4258 nolanlar hariç](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4258.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4259 uncaught_exceptions ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4259.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4277 Trivisel kopyalanabilir reference_wrapper](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4277.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4279 insert_or_assign ()/try_emplace () eşleme/unordered_map](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4279.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4280 size (), boş (), veri (](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4280.pdf) )|VS 2015 <sup>[14](#note_14)</sup>|
|[Unique_ptr atamasını kesin olarak kısıtlayan](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4366.html) &nbsp;&nbsp;N4366|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4387 artırma çifti ve tanımlama grubu](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4387.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4389 bool_constant](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4389.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4508 shared_mutex (zaman aşımına uğradı)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4508.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4510 eksik türleri vektör/liste/forward_list destekleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4510.html)|VS 2013 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: \<algoritması > örnek ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#alg.random.sample)|VS 2017 15,0|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: \<tüm >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#any)|VS 2017 15,0|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: \<memory_resource >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#memory.resource.synop)<br/>&nbsp;&nbsp;[P0337R0 Polymorphic_allocator atamasını silme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0337r0.html)|VS 2017 15,6|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: \<isteğe bağlı >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#optional)|VS 2017 15,0|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: \<string_view >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#string.view)|VS 2017 15,0|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: \<tanımlama grubu > Apply ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#tuple)|VS 2017 15,0|
|&nbsp;&nbsp;[N4562 kitaplığı temelleri: Boyer-Moore arama ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#func.searchers.boyer_moore)<br/>&nbsp;&nbsp;[P0253R1, Searcher dönüş türlerini düzeltme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0253r1.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0003R5 dinamik özel durum belirtimlerini kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0004R1 kaldırılan Iostreams diğer adlarını kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0004r1.html)|VS 2015,2 <sup> [kal](#note_rem)</sup>|
|&nbsp;&nbsp;[P0005R4 not_fn()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html)<br/>[not_fn () için &nbsp;P0358R1 düzeltmeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html) &nbsp;|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|[tür nitelikleri için &nbsp;P0006R0 değişken şablonları &nbsp;(is_same_v, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0006r0.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0007R1 as_const()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0007r1.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0013R1 mantıksal Işleç türü nitelikleri (bağlantılı, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0013r1.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0024R2 paralel algoritmaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html)<br/>&nbsp;&nbsp;[P0336R1 paralel yürütme Ilkelerini yeniden adlandırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0336r1.pdf)<br/>[özel durumlar için &nbsp;&nbsp;P0394R4 paralel algoritmaların () sonlandırılması gerekir](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0394r4.html)<br/>&nbsp;&nbsp;[P0452R1 Unifying \<sayısal > paralel algoritmalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0452r1.html)|VS 2017 15,7|
|&nbsp;&nbsp;[P0025R1 Clamp ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0025r1.html)|VS 2015,3|
|&nbsp;&nbsp;[P0030R1 hypot (x, y, z)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf)|VS 2017 15,7|
|[\<dizi > (yeniden) ve \<Yineleyici için &nbsp;P0031R0 constexpr &nbsp;](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0031r0.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|[Varyant/any/optional için &nbsp;P0032R3 homojen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0032r3.pdf) &nbsp;|VS 2017 15,0|
|&nbsp;&nbsp;[P0033R1 Reifadesi enable_shared_from_this](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html)|VS 2017 15,5 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0040R3 genişletme bellek yönetimi araçları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0040r3.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0063R3 C11 standart kitaplığı](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0063r3.html)|VS 2015 <sup>[C11](#note_C11), [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0067R5 Elemensel dize dönüştürmeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html)|VS 2019 16,4 <sup> [charconv](#note_charconv)</sup>|
|&nbsp;&nbsp;[P0074R0 owner_less\<>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0074r0.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0077R2 is_callable, is_nothrow_callable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0077r2.html)|VS 2017 15,0|
|&nbsp;&nbsp;[P0083R3 splicing haritaları ve kümeleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)<br/>&nbsp;&nbsp;[P0508R0 Clarifying insert_return_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0084R2 emplace dönüş türü](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0084r2.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0088R3 \<varyant >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0088r3.html)|VS 2017 15,0|
|&nbsp;&nbsp;[P0092R1 \<hatası, > Floor (), CEIL (), Round (), ABS](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0092r1.html) ()|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0152R1 atomik:: is_always_lock_free](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0152r1.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0154R1 hardware_destructive_interference_size, vb.](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0154r1.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0156R0 Variadıc lock_guard](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0156r0.html)|VS 2015,2 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0156R2 yeniden adlandırma\_koruyucu, kapsamlı\_kilitlemeye](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0156r2.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0163R0 shared_ptr:: weak_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0163r0.html)|VS 2017 15,0|
|&nbsp;&nbsp;[P0174R2 kalıntı kitaplık parçalarını kullanımdan](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html) kaldırır|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0185R1 is_swappable, is_nothrow_swappable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0185r1.html)|VS 2015,3|
|&nbsp;&nbsp;[P0209R2 make_from_tuple ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0209r2.pdf)|VS 2017 15,0|
|&nbsp;&nbsp;[P0218R1 \<dosya sistemi >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html)<br/>[dosya sistemi Için P0219R1 &nbsp;&nbsp;göreli yollar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0219r1.html)<br/>[dosya sistemi için &nbsp;P0317R1 &nbsp;Dizin girişi önbelleğe alma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0317r1.html)<br/>[dosya sistemi yollarındaki string_view &nbsp;&nbsp;P0392R0 destekleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0392r0.pdf)<br/>&nbsp;&nbsp;[P0430R2, POSIX olmayan dosya sistemlerini destekleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0430r2.pdf)<br/>&nbsp;&nbsp;[P0492R2 dosya sistemi IÇIN NB açıklamalarını çözme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0492r2.html)|VS 2017 15,7 <sup> [E](#note_E)</sup>|
|&nbsp;&nbsp;[P0220R1 kitaplığı temelleri v1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html)|VS 2017 15,6|
|&nbsp;&nbsp;[P0226R1 matematik özel işlevleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0226r1.pdf)|VS 2017 15,7|
|&nbsp;&nbsp;[P0254R2 tümleştirme String_view ve std:: String](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0254r2.pdf)|VS 2017 15,0|
|&nbsp;&nbsp;[P0258R2 has_unique_object_representations](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0258r2.html)|VS 2017 15,3 <sup> [G](#note_G)</sup>|
|&nbsp;&nbsp;[P0272R1 const olmayan basic_string::d ata ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0272r1.html)|VS 2015,3|
|&nbsp;&nbsp;[P0295R0 GCD (), LCM ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0295r0.pdf)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0298R3 std:: Byte](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0298r3.pdf)|VS 2017 15,3 <sup> [17](#note_17),&nbsp;[bayt](#note_byte)</sup>|
|[std:: Işlevinde ayırıcı desteğini kaldırmak](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html) &nbsp;&nbsp;P0302R1|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0307R2 daha sonra yeniden eşit hale getirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0307r2.pdf)|VS 2017 15,0|
|&nbsp;&nbsp;[P0393R3 varyansı daha büyük hale getirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0393r3.html)|VS 2017 15,0|
|[\<string_view > için &nbsp;&nbsp;P0403R1 UDLs ("meow" ZF vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0403r1.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0414R2 shared_ptr\<t [] >, shared_ptr\<t [N] >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html)<br/>&nbsp;&nbsp;[P0497R0 Shared_ptr diziler Için düzeltme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html)|VS 2017 15,5 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0418R2 atomik compare_exchange Memory_order gereksinimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0418r2.html)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|[Char_traits için &nbsp;P0426R1 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html) &nbsp;|VS 2017 15,7|
|&nbsp;&nbsp;[P0433R2, sınıf şablonları için şablon kesintiyi standart kitaplığına tümleştiriyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html)<br/>&nbsp;&nbsp;[P0739R0, sınıf şablonu bağımsız değişken kesintisi tümleştirmesini standart kitaplığına geliştirir](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html)|VS 2017 15,7|
|&nbsp;&nbsp;[P0435R1 Overhauling common_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0435r1.pdf)<br/>&nbsp;&nbsp;[P0548R1, tür ve süre genel\_](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0548r1.pdf)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0504R0 yeniden ziyaret in_place_t/in_place_type_t\<t >/in_place_index_t\<ı >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0504r0.html)|VS 2017 15,0|
|[\<tarihçe > için &nbsp;&nbsp;P0505R0 constexpr (yeniden)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0505r0.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|&nbsp;[Nothing, diziler, başvurular ve tamamlanmamış türlerin türevlerini reddetme &nbsp;P0510R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0510r0.html)|VS 2017 15,0|
|&nbsp;&nbsp;[P0513R0 Kirleme karması](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0513r0.pdf)<br/>&nbsp;&nbsp;[P0599R1 noexcept karması](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0599r1.pdf)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0516R0 shared_future noexcept olarak kopyalamayı işaretle](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0516r0.html)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0517R0 oluşturma future_error future_errc](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0517r0.html)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0521R0 Için kullanımdan kaldırıldı shared_ptr:: Unique ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0521r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0558R1, temel sınıf tutarsızlıkları adlı atomik\<t > çözümleme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0558r1.pdf)|VS 2017 15,3 <sup> [14](#note_14)</sup>|
|&nbsp;&nbsp;[P0595R2 std:: is_constant_evaluated ()](https://wg21.link/P0595R2)|Hayır|
|&nbsp;&nbsp;[P0602R4 yayan kopyalama/taşıma, değişken/isteğe bağlı](https://wg21.link/P0602R4)|VS 2017 15.3<sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0604R0 değiştirme,\_sonucunu çağırmak için çağrılabilir/sonuç\_\_ve\_ınvocable,\_nothrow\_ınvocable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0604r0.html)|VS 2017 15,3 <sup> [17](#note_17)</sup>|
|[standart kitaplık için &nbsp;P0607R0 satır Içi değişkenlerini](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html) &nbsp;|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0618R0 \<codecvt >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0618r0.html)|VS 2017 15,5 <sup> [17](#note_17)</sup>|
|&nbsp;&nbsp;[P0682R1, Elemensel dize dönüşümlerini onarmayı](https://wg21.link/P0682R1)|VS 2015 15,7 <sup> [17](#note_17)</sup>|
|__C++ 14 standart kitaplık özellikleri__|__Destekleniyor__|
|&nbsp;&nbsp;[N3462 SFINAE kullanımı kolay result_of](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3462.html)|VS 2015,2|
|[\<karmaşık > için &nbsp;N3302 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2011/n3302.html) &nbsp;|VS 2015|
|[\<Tarihçe için &nbsp;&nbsp;N3469 constexpr >](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3469.html)|VS 2015|
|[\<dizisi için &nbsp;N3470 constexpr &nbsp;](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3470.html)|VS 2015|
|[\<initializer_list >, \<tanımlama grubu >, \<yardımcı programı için &nbsp;N3471 constexpr &nbsp;](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3471.html)|VS 2015|
|&nbsp;&nbsp;[N3545 integral_constant:: operator () ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3545.pdf)|VS 2015|
|&nbsp;&nbsp;[N3642 UDLs > \<, \<dize > (1729ms, "meow" s, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3642.pdf)|VS 2015|
|&nbsp;&nbsp;[N3644 null Ileri yineleyiciler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3644.pdf)|VS 2015|
|&nbsp;&nbsp;[N3654 tırnak işareti ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3654.html)|VS 2015|
|&nbsp;&nbsp;[N3657 heterojen Ilişkilendirilebilir arama](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3657.htm)|VS 2015|
|&nbsp;&nbsp;[N3658 integer_sequence](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3658.html)|VS 2015|
|&nbsp;&nbsp;[N3659 shared_mutex (zaman aşımına uğradı)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3659.html)|VS 2015|
|&nbsp;&nbsp;[N3668 Exchange ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3668.html)|VS 2015|
|&nbsp;&nbsp;[N3669, sabit olmayan constexpr üye Işlevlerini düzeltme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3669.pdf)|VS 2015|
|&nbsp;&nbsp;[N3670 get\<T>()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3670.html)|VS 2015|
|&nbsp;&nbsp;[N3671 çift aralıklı eşittir (), is_permutation (), uyuşmazlık ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3671.html)|VS 2015|
|&nbsp;&nbsp;[N3778 boyutu ayırmayı kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|[\<karmaşık > için &nbsp;&nbsp;N3779 UDLs (3.14 i vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3779.pdf)|VS 2015|
|[\<işlevsel > için &nbsp;N3789 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3789.htm) &nbsp;|VS 2015|
|&nbsp;&nbsp;[N3887 tuple_element_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3887.pdf)|VS 2015|
|&nbsp;&nbsp;[N3891 yeniden adlandırma shared_mutex (zaman aşımına uğradı) shared_timed_mutex](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3891.htm)|VS 2015|
|&nbsp;&nbsp;[N3346 en az kapsayıcı öğesi gereksinimleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3346.pdf)|VS 2013|
|&nbsp;&nbsp;[N3421 saydam Işleç Finansdüler (daha az\<> vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3421.htm)|VS 2013|
|[\<type_traits > için &nbsp;N3655 diğer ad şablonları &nbsp;(decay_t, vb.)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3655.pdf)|VS 2013|
|&nbsp;&nbsp;[N3656 make_unique ()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3656.htm)|VS 2013|

Birlikte listelenen bir grup İnceleme, bir veya daha fazla onaylanan geliştirmeler veya expanme ile birlikte standart bir özelliği gösterir. Bu özellikler birlikte uygulanır.

### <a name="supported-values"></a>Desteklenen değerler

__Hayır__ , henüz uygulanmadı anlamına gelir. \
__Kısmi__ , uygulamanın tamamlanmamış olduğu anlamına gelir. Daha fazla bilgi için Notlar bölümüne bakın. \
__VS 2010__ , Visual Studio 2010 ' de desteklenen özellikleri gösterir. \
__VS 2013__ , Visual Studio 2013 desteklenen özellikleri gösterir. \
__VS 2015__ , Visual Studio 2015 ' de (RTW) desteklenen özellikleri gösterir. \
__Vs 2015,2__ ve __vs 2015,3__ , sırasıyla Visual Studio 2015 güncelleştirme 2 ve Visual Studio 2015 güncelleştirme 3 ' te desteklenen özellikleri belirtir. \
__VS 2017 15,0__ , Visual Studio 2017 sürüm 15,0 (RTW) içinde desteklenen özellikleri belirtir. \
__VS 2017 15,3__ , Visual Studio 2017 sürüm 15,3 ' te desteklenen özellikleri belirtir. \
__VS 2017 15,5__ , Visual Studio 2017 sürüm 15,5 ' te desteklenen özellikleri belirtir. \
__VS 2017 15,7__ , Visual Studio 2017 sürüm 15,7 ' te desteklenen özellikleri belirtir. \
__VS 2019 16,0__ , Visual Studio 2019 sürüm 16,0 (RTW) içinde desteklenen özellikleri belirtir. \
__VS 2019 16,1__ , Visual Studio 2019 sürüm 16,1 ' te desteklenen özellikleri belirtir. \
__VS 2019 16,2__ , Visual Studio 2019 sürüm 16,2 ' te desteklenen özellikleri belirtir. \
__VS 2019 16,3__ , Visual Studio 2019 sürüm 16,3 ' te desteklenen özellikleri belirtir. \
__VS 2019 16,4__ , Visual Studio 2019 sürüm 16,4 ' te desteklenen özellikleri gösterir.

### <a name="notes"></a>Notlar

<a name="note_A"></a>[/Std: c++ 14](../build/reference/std-specify-language-standard-version.md) modunda, dinamik özel durum belirtimleri __uygulanmadı olarak kalır__ ve `throw()` hala `__declspec(nothrow)`için bir eş anlamlı olarak değerlendirilir. C++ 17 ' de, dinamik özel durum belirtimleri çoğunlukla P0003R5 tarafından kaldırılmıştır ve bir vestige bırakarak `throw()`: Kullanımdan kalktı ve `noexcept`için bir eş anlamlı olarak davranması gerekir. [/Std: c++ 17](../build/reference/std-specify-language-standard-version.md) modunda, MSVC artık `throw()` aynı davranışı `noexcept`, diğer bir deyişle sonlandırma yoluyla zorlayarak standart 'ye uyar.

[/Zc: noexceptTypes](../build/reference/zc-noexcepttypes.md) derleyici seçeneği `__declspec(nothrow)`eski davranışımızı ister. `throw()`, C++ 20 ' de kaldırılacak. Standart ve uygulamamız içindeki bu değişikliklere yanıt olarak kod geçirmeye yardımcı olmak için [/std: c++ 17](../build/reference/std-specify-language-standard-version.md) ve [/Permissive-](../build/reference/permissive-standards-conformance.md)altına özel durum belirtimi sorunlarıyla ilgili yeni derleyici uyarıları eklenmiştir.

<a name="note_B"></a>__B__ [/Permissive-](../build/reference/permissive-standards-conformance.md) modunda Visual Studio 2017 sürüm 15,7 ' de desteklenir. Daha fazla bilgi için bkz. [iki aşamalı ad arama DESTEĞI MSVC](https://devblogs.microsoft.com/cppblog/two-phase-name-lookup-support-comes-to-msvc/).

<a name="note_C"></a>__C__ derleyicinin C99 Önişlemci kuralları için destek, Visual Studio 2017 içinde eksik. Ön işlemci overhauling ve bu değişiklikleri Visual Studio 2017 sürüm 15,8 ' de [/deneysel: Önişlemci](../build/reference/experimental-preprocessor.md) derleyici anahtarıyla sevk eteceğiz.

<a name="note_D"></a>__D__ [/std: c++ 14](../build/reference/std-specify-language-standard-version.md) altında gizlenecek bir uyarı ile [C4984](../error-messages/compiler-warnings/compiler-warning-c4984.md).

<a name="note_E"></a>__Bu,__ tam olarak yeni bir uygulama olan, önceki `std::experimental` sürümüyle uyumsuz, oluşturmaksızın desteği, hata düzeltmeleri ve standart zorunlu davranıştaki değişiklikler için gerekli hale getirilir. Şu anda \<dosya sistemi > dahil, yeni `std::filesystem` ve önceki `std::experimental::filesystem`sağlar ve \<deneysel/FileSystem > dahil olmak üzere yalnızca eski deneysel uygulamayı sağlar. Deneysel uygulama, kitaplıkların sonraki ABı-kırılımı sürümünde KALDıRıLACAK.

<a name="note_G"></a>Bir derleyici iç tarafından desteklenen __G__ .

<a name="note_14"></a>__14__ bu c++ 17/20 özellikleri, [/std: c++ 14](../build/reference/std-specify-language-standard-version.md) (varsayılan) belirtildiğinde bile her zaman etkindir. Bunun nedeni, özelliğin **/STD** seçeneklerinin sunumundan önce uygulandığından veya koşullu uygulamanın istenmediği karmaşıklıkta olmasından kaynaklanır.

<a name="note_17"></a>__17__ bu özellikler [/std: c++ 17](../build/reference/std-specify-language-standard-version.md) (veya [/std: c + + latest](../build/reference/std-specify-language-standard-version.md)) derleyici seçeneği tarafından etkinleştirilir.

<a name="note_20"></a>__20__ bu özellikler [/std: c + + en son](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği tarafından etkinleştirilir. C++ 20 uygulama tamamlandığında, bu özelliklerin de kullanılabildiği yeni bir **/std: c++ 20** derleyici seçeneği eklenir.

<a name="note_byte"></a>__byte__ `std::byte`, [/std: c++ 17](../build/reference/std-specify-language-standard-version.md) (veya [/std: c + + latest](../build/reference/std-specify-language-standard-version.md)) tarafından etkinleştirilir, ancak bazı durumlarda Windows SDK üstbilgileri ile çakışabileceğinden, hassas bir geri alma makrosu vardır. `_HAS_STD_BYTE` `0`olarak tanımlayarak devre dışı bırakılabilir.

<a name="note_C11"></a>__C11__ Evrensel CRT, C99 `strftime()` E/O alternatif Dönüştürme belirticileri, C11 `fopen()` özel mod ve C11 `aligned_alloc()`dışında C++ 17 için gerekli olan C11 standart kitaplığının parçalarını uyguladık. C11 belirtilen Microsoft `free()`uygulamasıyla uyumsuz bir şekilde `aligned_alloc()` belirtildiği için, ikincisi uygulanmamalıdır. Bu, `free()` yüksek oranda hizalanmış ayırmaları işleyebilmelidir.

<a name="note_rem"></a>__REM__ [/Std: c++ 17](../build/reference/std-specify-language-standard-version.md) (veya [/std: c + + latest](../build/reference/std-specify-language-standard-version.md)) derleyici seçeneği belirtildiğinde kaldırılan özellikler. Bu özellikler, bu makroları kullanarak daha yeni dil modlarına geçiş kolaylığı sağlamak üzere yeniden etkinleştirilebilir: `_HAS_AUTO_PTR_ETC`, `_HAS_FUNCTION_ALLOCATOR_SUPPORT`, `_HAS_OLD_IOSTREAMS_MEMBERS`ve `_HAS_UNEXPECTED`.

<a name="note_charconv"></a>__charconv__ `from_chars()` ve `to_chars()` tamsayılar için kullanılabilir. Kayan nokta `from_chars()` ve kayan nokta `to_chars()` zaman çizelgesi aşağıdaki gibidir:
- VS 2017 15,7: Integer `from_chars()` ve `to_chars()`.
- VS 2017 15,8: kayan nokta `from_chars()`.
- VS 2017 15,9: en kısa ondalık için kayan nokta `to_chars()` aşırı yüklemeler.
- VS 2019 16,0: en kısa onaltılı ve duyarlık onaltılı için kayan nokta `to_chars()` aşırı yüklemeler.
- VS 2019 16,2: Precision fixed ve Precision bilimsel için kayan nokta `to_chars()` aşırı yüklemeler.
- VS 2019 16,4: duyarlık genel için kayan nokta `to_chars()` aşırı yüklemesi.

<a name ="note_parallel"></a>__paralel__ C++ 17 ' nin paralel algoritma kitaplığı tamamlanmıştır. Tamamlanma her durumda her algoritmanın paralelleştirilmedi anlamına gelmez. En önemli algoritmalar paralelleştirildi ve algoritmalar paralelleştirilmedi bile yürütme ilkesi imzaları sağlanır. Uygulamanın merkezi iç üst bilgisi olan yvals_core. h, aşağıdaki "paralel algoritmalar notlarını" içerir: C++ bir uygulamanın seri algoritmalara çağrı olarak paralel algoritmalar uygulamasına izin verir. Bu uygulama birkaç ortak algoritma çağrısının paralelleştirmesi, ancak tümünü içermez.

Aşağıdaki algoritmalar paralelleştirildi:

- `adjacent_difference`, `adjacent_find`, `all_of`, `any_of`, `count`, `count_if`, `equal`, `exclusive_scan`, `find`, `find_end`, `find_first_of`, `find_if`, `find_if_not`, `for_each`, `for_each_n`, `inclusive_scan`, `is_heap`, `is_heap_until`, `is_partitioned`, `is_sorted`, `is_sorted_until`, `mismatch`, `none_of`, `partition`, `reduce`, `remove``remove_if`, `set_difference`, `set_intersection`, `sort`, `stable_sort`, `transform`, `transform_exclusive_scan`, `transform_inclusive_scan`, `transform_reduce`

Aşağıdakiler şu anda paralelleştirilmedi:

- Hedef donanımda belirgin bir paralellik performansı geliştirmesi yoktur; yalnızca dal içermeyen öğeleri oluşturan veya permute tüm algoritmalar genellikle bellek bant genişliği sınırlıdır:
  - `copy`, `copy_n`, `fill`, `fill_n`, `move`, `reverse`, `reverse_copy`, `rotate`, `rotate_copy`, `shift_left`, `shift_right`, `swap_ranges`
- Kullanıcı paralellik gereksinimleri üzerinde karışıklık var; büyük olasılıkla yukarıdaki kategoride:
  - `generate`, `generate_n`
- Etkin paralellik, uygun maliyetli şüpheli:
  - `partial_sort`, `partial_sort_copy`
- Henüz değerlendirilmedi; paralellik, gelecek bir sürümde uygulanabilir ve yararlı olması şüpheli:
  - `copy_if`, `includes`, `inplace_merge`, `lexicographical_compare`, `max_element`, `merge`, `min_element`, `minmax_element`, `nth_element`, `partition_copy`, `remove_copy`, `remove_copy_if`, `replace_copy`, `replace_copy_if`, `set_symmetric_difference`, `set_union`, `stable_partition`, `unique`, `unique_copy`

## <a name="see-also"></a>Ayrıca bkz.

[ C++ Dil başvurusu](../cpp/cpp-language-reference.md)\
[ C++ Standart kitaplık](../standard-library/cpp-standard-library-reference.md)\
[Visual Studio\ uygunluk geliştirmeleri C++ ](cpp-conformance-improvements.md)
Visual [Studio 'Daki görsele C++ yönelik](what-s-new-for-visual-cpp-in-visual-studio.md) yenilikler\
[Görsel C++ değişiklik geçmişi 2003 ile 2015](../porting/visual-cpp-change-history-2003-2015.md)\
[Visual C++ 2003 ile 2015 arasındaki](../porting/visual-cpp-what-s-new-2003-through-2015.md) yenilikler\
[C++Ekip Blogu](https://devblogs.microsoft.com/cppblog/)
