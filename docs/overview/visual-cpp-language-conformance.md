---
title: Microsoft C++ dil uygunluk tablosu
description: Visual Studio sürümüne göre Microsoft C++ uyumluluk güncelleştirmeleri tablosu.
ms.date: 03/17/2020
ms.technology: cpp-language
ms.assetid: 475da6e9-0d78-4b4e-bd23-f41c406c4efe
author: corob-msft
ms.author: corob
ms.openlocfilehash: 18f8db28fab83f795baced82a346f07d73256716
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365233"
---
# <a name="microsoft-c-language-conformance-table"></a>Microsoft C++ dil uygunluk tablosu

Visual Studio'daki Microsoft C++ derleyicisi (MSVC) için standartlara uygunluk devam eden bir çalışmadır. Visual Studio sürümüne göre ISO Standart C++ dilimizin ve kitaplığı uygunluğunun bir özeti ni aşağıda bulabilirsiniz. Her derleyici ve standart kitaplık özelliği, yayın zamanında kullanılabilirse özelliği açıklayan ISO Standart C++ teklif kağıdına ad bağlantılarına sahiptir. **Desteklenen** sütun, özellik için desteğin ilk kez göründüğü Visual Studio sürümünü listeler.

Visual Studio 2017 veya Visual Studio 2019 MSVC uygunluk geliştirmeleri hakkında ayrıntılı bilgi için [Visual Studio'daki C++ uyumluluk iyileştirmelerine](cpp-conformance-improvements.md)bakın. Diğer değişikliklerin listesi için [Visual Studio'da Visual C++ için Yenilikler bölümüne](what-s-new-for-visual-cpp-in-visual-studio.md)bakın. Önceki sürümlerde uygunluk değişiklikleri için [Visual C++ değişiklik geçmişi](../porting/visual-cpp-change-history-2003-2015.md) ve Visual [C++ What's New 2003-2015 'e](../porting/visual-cpp-what-s-new-2003-through-2015.md)bakın. C++ ekibinden güncel haberler için [C++ takım blogunu](https://devblogs.microsoft.com/cppblog/)ziyaret edin.

> [!NOTE]
> Visual Studio 2015, Visual Studio 2017 ve Visual Studio 2019 arasında ikili kırılma yoktur. Daha fazla bilgi için Visual [Studio 2015, 2017 ve 2019 arasındaki C++ ikili uyumluluğu](../porting/binary-compat-2015-2017.md)

## <a name="compiler-features"></a>Derleyici özellikleri

|  |  |
|--|--|
| __C++03/11 Temel dil özellikleri__ | __Desteklenen__ |
| &nbsp;&nbsp;Diğer her şey | VS 2015 <sup> [A](#note_A)</sup> |
| &nbsp;&nbsp;İki aşamalı ad araması | VS 2017 15,7 <sup> [Milyar](#note_B)</sup> |
| &nbsp;&nbsp;[N2634 İfade SFINAE](https://wg21.link/N2634) | VS 2017 15,7 |
| &nbsp;&nbsp;[N1653 C99 ön işlemci](https://wg21.link/N1653) | Kısmi <sup> [C](#note_C)</sup> |
| __C++14 Temel dil özellikleri__ | __Desteklenen__ |
| &nbsp;&nbsp;[N3323 Bağlamsal dönüşümler için tweaked ifadeler](https://wg21.link/N3323) | VS 2013 |
| &nbsp;&nbsp;[N3472 İkili edebi](https://wg21.link/N3472) | VS 2015 |
| &nbsp;&nbsp;[N3638 otomatik ve decltype(otomatik) iade türleri](https://wg21.link/n3638) | VS 2015 |
| &nbsp;&nbsp;[N3648 init yakalar](https://wg21.link/n3648) | VS 2015 |
| &nbsp;&nbsp;[N3649 Jenerik lambdas](https://wg21.link/n3649) | VS 2015 |
| &nbsp;&nbsp;[N3760 \[ \[amortismana\] \] uyran öznitelik](https://wg21.link/n3760) | VS 2015 |
| &nbsp;&nbsp;[N3778 Ölçekli deallocation](https://wg21.link/n3778) | VS 2015 |
| &nbsp;&nbsp;[N3781 Basamak ayırıcılar](https://wg21.link/n3781) | VS 2015 |
| &nbsp;&nbsp;[N3651 Değişken şablonları](https://wg21.link/n3651) | VS 2015.2 |
| &nbsp;&nbsp;[N3652 Genişletilmiş constexpr](https://wg21.link/n3652) | VS 2017 15,0 |
| &nbsp;&nbsp;[N3653 Toplamlar için varsayılan üye başharfleri](https://wg21.link/n3653) | VS 2017 15,0 |
| __C++17 Temel dil özellikleri__ | __Desteklenen__ |
| &nbsp;&nbsp;[N4086 Trigrafların çıkarılması](https://wg21.link/n4086) | VS 2010 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N3922 Braced-init-listeleri ile otomatik için yeni kurallar](https://wg21.link/n3922) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[Şablon şablon parametrelerinde N4051 yazı adı](https://wg21.link/n4051) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4266 Ad boşlukları ve sayısallaştırıcılar için öznitelikler](https://wg21.link/n4266) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4267 u8 karakter literals](https://wg21.link/n4267) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4230 İç içe ad alanı tanımları](https://wg21.link/n4230) | VS 2015,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[N3928 Terse static_assert](https://wg21.link/n3928) | VS 2017 15,0 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0184R0 Genelleştirilmiş aralık tabanlı for-loops](https://wg21.link/p0184r0) | VS 2017 15,0 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0188R1 \[ \[düşme\] \] özniteliği](https://wg21.link/p0188r1) | VS 2017 15,0 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0001R1 Kayıt anahtar kelimesini kaldırma](https://wg21.link/p0001r1) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0002R1 Bool için kaldırma operatörü++](https://wg21.link/p0002r1) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0018R3 Yakalama *bu değere göre](https://wg21.link/p0018r3) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0028R4 Yineleme olmadan öznitelik ad boşluklarını kullanma](https://wg21.link/p0028r4) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0061R1 \_ \_has_include](https://wg21.link/p0061r1) | VS 2017 15,3 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0138R2 Sabit enumların, tümselerden gelen doğrudan liste-initi](https://wg21.link/p0138r2) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0170R1 constexpr lambdas](https://wg21.link/p0170r1) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0189R1 \[ \[nodiscard\] \] özniteliği](https://wg21.link/p0189r1) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0212R1 \[ \[\] \] maybe_unused özniteliği](https://wg21.link/p0212r1) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0217R3 Yapılandırılmış ciltler](https://wg21.link/p0217r3) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0292R2 constexpr if-ifadeler](https://wg21.link/p0292r2) | VS 2017 15,3 <sup> [D](#note_D)</sup> |
| &nbsp;&nbsp;[P0305R1 Başlangıçlı seçim ifadeleri](https://wg21.link/p0305r1) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0245R1 Hexfloat edebi](https://wg21.link/p0245r1) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[N4268 Daha fazla tür dışı şablon args izin](https://wg21.link/n4268) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[N4295 Kat ifadeler](https://wg21.link/n4295) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0003R5 Dinamik-özel durum özelliklerinin kaldırılması](https://wg21.link/p0003r5) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0012R1 Tip sistemine noexcept ekleme](https://wg21.link/p0012r1) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0035R4 Aşırı hizalanmış dinamik bellek ayırma](https://wg21.link/p0035r4) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0386R2 Satır dışı değişkenler](https://wg21.link/p0386r2) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0522R0 Şablon parametrelerini uyumlu bağımsız değişkenlere eşleştirme](https://wg21.link/p0522r0) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0036R0 Bazı boş unary kıvrımları kaldırma](https://wg21.link/p0036r0) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[N4261 Yeterlilik dönüşümlerinin düzeltilmesi](https://wg21.link/n4261) | VS 2017 15,7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0017R1 Genişletilmiş toplam başlatma](https://wg21.link/p0017r1) | VS 2017 15,7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[Sınıf şablonları için P0091R3 Şablon bağımsız değişken kesintisi](https://wg21.link/p0091r3)<br/>&nbsp;&nbsp;[P0512R0 Sınıf şablonu bağımsız değişken tümdengelim sorunları](https://wg21.link/p0512r0) | VS 2017 15,7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0127R2 Otomatik ile tür olmayan şablon parametreleri bildirme](https://wg21.link/p0127r2) | VS 2017 15,7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0135R1 Garantili kopya elision](https://wg21.link/p0135r1) | VS 2017 15,6 |
| &nbsp;&nbsp;[P0136R1 Devralan yapıcıları yeniden ifade etme](https://wg21.link/p0136r1) | VS 2017 15,7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0137R1 std::aklama](https://wg21.link/p0137r1) | VS 2017 15,7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0145R3 Rafine ifade değerlendirme sırası](https://wg21.link/p0145r3)<br/>&nbsp;&nbsp;[P0400R0 Fonksiyon bağımsız değişkenlerinin değerlendirilmesi sırası](https://wg21.link/p0400r0) | VS 2017 15,7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0195R2 Paket genişletmeleri](https://wg21.link/p0195r2) | VS 2017 15,7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0283R2 Tanınmayan özellikleri yoksayma](https://wg21.link/p0283r2) | VS 2015 <sup> [14](#note_14)</sup> |
| __C++17 Temel dil özellikleri (Kusur raporları)__ | __Desteklenen__ |
| &nbsp;&nbsp;[P0702R1 Initializer-list ctors için sınıf şablonu bağımsız değişken kesintisi sabitleme](https://wg21.link/p0702r1) | VS 2017 15,7 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0961R1 Yapılandırılmış ciltler özelleştirme noktası bulma kuralları rahatlatıcı](https://wg21.link/p0961r1) | VS 2019 16,0 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0969R0 Erişilebilir üyelere yapılandırılmış bağlamalar izin](https://wg21.link/p0969r0) | VS 2019 16,0 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0588R1 Örtük lambda yakalama basitleştirilmesi](https://wg21.link/p0588r1) | VS 2019 16,4 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[Yapıcılar için P1771R1 \[ \[nodiscard\] \]](https://wg21.link/p1771r1) | VS 2019 16,4 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0527R1 ve P1155R3 için P1825R0 Birleştirme li ifadeler, daha örtük hamle](https://wg21.link/p1825r0) | VS 2019 16,4 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0929R2 Soyut sınıf türleri için kontrol](https://wg21.link/P0929R2) | Hayır |
| &nbsp;&nbsp;[P0962R2 Aralık için döngü özelleştirme noktası bulma kurallarını gevşetme](https://wg21.link/p0962r1) | Hayır |
| &nbsp;&nbsp;[P0859R0 CWG 1581: Constexpr üye fonksiyonları ne zaman tanımlanır](https://wg21.link/p0859r0) | Hayır |
| &nbsp;&nbsp;[Yeni ifadelerde P1009R2 Dizi boyutu kesintisi](https://wg21.link/P1009R2) | Hayır |
| &nbsp;&nbsp;[P1286R2 Kontra CWG DR1778](https://wg21.link/P1286R2) | Hayır |
| __C++20 Temel dil özellikleri__ | __Desteklenen__ |
| &nbsp;&nbsp;[P0704R1 Üyelere ref nitelikli işaretçilerin const lvalue düzeltilmesi](https://wg21.link/p0704r1) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P1041R4 char16_t/char32_t dize edebi olun UTF-16/32](https://wg21.link/P1041R4) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P1330R0 Constexpr içinde bir sendikanın aktif üyesi değiştirme](https://wg21.link/P1330R0) | VS 2017 15,0 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0972R0 noexcept \<Chrono> zero(), min(), max()](https://wg21.link/P0972R0) | VS 2017 15,7 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0515R3 Üç yönlü (uzay gemisi) karşılaştırma işleci <=>](https://wg21.link/P0515R3) | VS 2019 16,0 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0941R2 Özellik testi makroları](https://wg21.link/P0941R2) | VS 2019 16,0 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P1008R1 Kullanıcı tarafından beyan edilen yapıcılarla agregaların yasaklanması](https://wg21.link/P1008R1) | VS 2019 16,0 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0329R4 Belirlenmiş başlatma](https://wg21.link/p0329r4) | VS 2019 16,1 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0846R0 ADL ve görünür olmayan işlev şablonları](https://wg21.link/P0846R0) | VS 2019 16,1 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0409R2 Lambda \[yakalamaya izin vermek =, bu\]](https://wg21.link/p0409r2) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0428R2 Jenerik lambdas için tanıdık şablon sözdizimi](https://wg21.link/p0428r2) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0624R2 Varsayılan yapıcı ve devredilemez vatansız lambdas](https://wg21.link/P0624R2) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0780R2 Lambda init-yakalama paketi genişletme izin](https://wg21.link/P0780R2) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0806R2 Deprecate örtük yakalama bu üzerinden\[=\]](https://wg21.link/P0806R2) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[<=> ve diğer karşılaştırma işleçleri için P1120R0 Tutarlılık iyileştirmeleri](https://wg21.link/P1120R0) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1185R2 \< = \> != ==](https://wg21.link/P1185R2) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0734R0 Kavramlar](https://wg21.link/P0734R0) | VS 2019 16,3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0857R0 Kısıtlamalardaki işlevsellik boşluklarını sabitleme](https://wg21.link/P0857R0) | VS 2019 16,3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1084R2 Bugünün dönüş tipi gereksinimleri yetersizdir](https://wg21.link/P1084R2) | VS 2019 16,3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0892R2 Koşullu açık](https://wg21.link/P0892R2) | VS 2019 16,4 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1091R3 Yapılandırılmış bağlamaların değişken bildirimlere daha çok benzemesini genişletme](https://wg21.link/P1091R3) | VS 2019 16,4 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1099R5 enum kullanma](https://wg21.link/P1099R5) | VS 2019 16,4 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1186R3 Ne zaman kullanıyorsunuz\<=>](https://wg21.link/P1186R3) | VS 2019 16,4 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1630R1 Uzay Gemisi'nin bir ayarlamaya ihtiyacı var](https://wg21.link/P1630R1) | VS 2019 16,4 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0306R4 \_ \_Virgül ihmali ve virgül silme için VA_OPT\_ \_ ekleme](https://wg21.link/P0306R4) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0614R1 Başlangıçlı aralık tabanlı for-loops](https://wg21.link/P0614R1) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0683R1 Bit alanları için varsayılan üye başlatma](https://wg21.link/P0683R1) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[Constexpr fonksiyonlarında P1002R1 try-catch blokları](https://wg21.link/P1002R1) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1161R3 Virgül işlecinin ifadeleri alt yazılaştırmada kullanma](https://wg21.link/P1161R3) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1301R4 \[ \[nodiscard("mesaj")\]\]](https://wg21.link/P1301R4) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1703R1 Üstbilgi birimi ithalatını tanımak tam ön işleme gerektirir](https://wg21.link/P1703R1) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1946R0 Değere göre varsayılan karşılaştırmalara izin ver](https://wg21.link/P1946R0) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[Varsayılan kopya oluşturucu ile P0641R2 const uyumsuzluk](https://wg21.link/P0641R2) | Kısmi |
| &nbsp;&nbsp;[P0912R5 Coroutines](https://wg21.link/P0912R5) | Kısmi |
| &nbsp;&nbsp;[P1103R3 Modülleri](https://wg21.link/P1103R3) | Kısmi |
| &nbsp;&nbsp;[P0315R4 Değerlendirilmemiş bağlamlarda lambdas izin](https://wg21.link/P0315R4) | Hayır |
| &nbsp;&nbsp;[P0388R4 Bilinmeyen bağlı dizilere dönüştürmeizni](https://wg21.link/P0388R4) | Hayır |
| &nbsp;&nbsp;[P0479R5 \[ \[\] \] olası \[ \[\] \] ve olası öznitelikleri](https://wg21.link/P0479R5) | Hayır |
| &nbsp;&nbsp;[P0634R3 Aşağı yazı adı ile!](https://wg21.link/P0634R3) | Hayır |
| &nbsp;&nbsp;[P0692R1 Uzmanlıkları kontrol eden rahatlatıcı erişim kontrolü](https://wg21.link/P0692R1) | Hayır |
| &nbsp;&nbsp;[P0722R3 Değişken boyutlu sınıflar için verimli boyutlu silme](https://wg21.link/P0722R3) | Hayır |
| &nbsp;&nbsp;[P0732R2 Tür olmayan şablon parametrelerinde sınıf türleri](https://wg21.link/P0732R2) | Hayır |
| &nbsp;&nbsp;[P0735R1 memory_order_consume salınım dizileri ile etkileşimi](https://wg21.link/P0735R1) | Hayır |
| &nbsp;&nbsp;[P0784R7 Daha fazla constexpr konteyner](https://wg21.link/P0784R7) | Hayır |
| &nbsp;&nbsp;[P0840R2 \[ \[\] \] no_unique_address özniteliği](https://wg21.link/P0840R2) | Hayır |
| &nbsp;&nbsp;[P0848R3 Koşullu önemsiz özel üye işlevler](https://wg21.link/P0848R3) | Hayır |
| &nbsp;&nbsp;[P0960R3 Parantez içinde bulunan değerler listesinden agregaların başlatılmasına izin ver](https://wg21.link/P0960R3) | Hayır |
| &nbsp;&nbsp;[P1064R0 Sürekli ifadelerde sanal işlev çağrılarına izin verme](https://wg21.link/P1064R0) | Hayır |
| &nbsp;&nbsp;[P1073R3 Acil fonksiyonlar](https://wg21.link/P1073R3) | Hayır |
| &nbsp;&nbsp;[P1094R2 İç içe ad boşlukları](https://wg21.link/P1094R2) | Hayır |
| &nbsp;&nbsp;[P1139R2 ISO 10646 ile ilgili adres ifade sorunları](https://wg21.link/P1139R2) | Hayır |
| &nbsp;&nbsp;[P1141R2 Kısıtlı beyanlar için başka bir yaklaşım](https://wg21.link/P1141R2) | Hayır |
| &nbsp;&nbsp;[P1143R2 constinit](https://wg21.link/P1143R2) | Hayır |
| &nbsp;&nbsp;[P1152R4 Deprecating uçucu](https://wg21.link/P1152R4) | Hayır |
| &nbsp;&nbsp;[P1236R1 İmzalı tümsalar ikinin tamamlayıcısıdır](https://wg21.link/P1236R1) | Hayır |
| &nbsp;&nbsp;[P1327R1 Sürekli ifadelerde dynamic_cast, polimorfik typeid izin](https://wg21.link/P1327R1) | Hayır |
| &nbsp;&nbsp;[P1331R2 Constexpr bağlamlarında önemsiz varsayılan başlatmaya izin](https://wg21.link/P1331R2) | Hayır |
| &nbsp;&nbsp;[P1353R0 Eksik özellik testi makroları](https://wg21.link/P1353R0) | Hayır |
| &nbsp;&nbsp;[P1381R1 Yapılandırılmış bağlayıcıların referans yakalaması](https://wg21.link/P1381R1) | Hayır |
| &nbsp;&nbsp;[P1452R2 İade tipi gereksinimlerin tek tip olmayan semantiklerinde](https://wg21.link/P1452R2) | Hayır |
| &nbsp;&nbsp;[P1616R1 Kısıtlı şablonlarla sınırlandırılmamış TTP'ler kullanma](https://wg21.link/P1616R1) | Hayır |
| &nbsp;&nbsp;[P1668R1 Constexpr fonksiyonlarında değerlendirilmemiş sıralı montaja izin](https://wg21.link/P1668R1) | Hayır |
| &nbsp;&nbsp;[P1766R1 Azaltıcı küçük modüller hastalıkları](https://wg21.link/P1766R1) | Hayır |
| &nbsp;&nbsp;[P1811R0 Yeniden ihracat sağlamlığı için rahatlatıcı yeniden tanımlama kısıtlamaları](https://wg21.link/P1811R0) | Hayır |
| &nbsp;&nbsp;[Diğer ad şablonları için P1814R0 CTAD](https://wg21.link/P1814R0) | Hayır |
| &nbsp;&nbsp;[Agregalar için P1816R0 CTAD](https://wg21.link/P1816R0) | Hayır |
| &nbsp;&nbsp;[P1874R1 Modüllerde Yerel Olmayan Değişkenlerin Dinamik Başlatma Sırası](https://wg21.link/P1874R1) | Hayır |
| &nbsp;&nbsp;[P1907R1 Türü olmayan şablon parametreleri ile tutarsızlıklar](https://wg21.link/P1907R1) | Hayır |
| &nbsp;&nbsp;[Kasım 2019 (Belfast) toplantısında NB Yorumlar için P1971R0 Çekirdek Değişiklikler](https://wg21.link/P1971R0) | Hayır |
| &nbsp;&nbsp;[P1972R0 US105 İşlev için işaretçi oluştururken şablon olmayan kısıtlamalar için denetim](https://wg21.link/P1972R0) | Hayır |
| &nbsp;&nbsp;[P1975R0 Parantez içinde toplam başlatma ifadelerinin düzeltilmesi](https://wg21.link/P1975R0) | Hayır |
| &nbsp;&nbsp;[P1979R0 US086 Kararı](https://wg21.link/P1979R0) | Hayır |
| &nbsp;&nbsp;[P1980R0 CA096: Bağımlı olmayan gereksinimler için bildirim eşleştirme](https://wg21.link/P1980R0) | Hayır |

## <a name="standard-library-features"></a>Standart kütüphane özellikleri

|  |  |
|--|--|
| __C++20 Standart kitaplık özellikleri__ | __Desteklenen__ |
| &nbsp;&nbsp;[P0809R0 Sırasız Kapları Karşılaştırma](https://wg21.link/p0809r0) | VS 2010 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0858R0 Constexpr Iterator Gereksinimleri](https://wg21.link/p0858r0) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0777R1 Gereksiz Çürümeden Kaçınma](https://wg21.link/p0777r1) | VS 2017 15,7 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P1164R1 Yapma create_directory() Sezgisel](https://wg21.link/P1164R1) | VS 2019 16,0 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0550R2 remove_cvref](https://wg21.link/p0550r2) | VS 2019 16,0 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0318R1 unwrap_reference, unwrap_ref_decay](https://wg21.link/p0318r1) | VS 2019 16,1 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0457R2 starts_with()/ends_with() basic_string/basic_string_view](https://wg21.link/p0457r2) | VS 2019 16,1 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0458R2,() Sipariş edilen ve Sipariş Edilmeyen Birleştirici Kaplar İçin](https://wg21.link/p0458r2) | VS 2019 16,1 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0646R1 listesi/forward_list remove()/remove_if()/benzersiz() İade size_type](https://wg21.link/p0646r1) | VS 2019 16,1 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0769R2 shift_left(), shift_right()](https://wg21.link/p0769r2) | VS 2019 16,1 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0887R1 type_identity](https://wg21.link/p0887r1) | VS 2019 16,1 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0020R6\<atomik şamandıra>, atomik\<çift>, atomik\<uzun çift>](https://wg21.link/p0020r6) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0463R1 endian](https://wg21.link/p0463r1) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0482R6 char8_t: UTF-8 karakterleri ve dizeleri için bir tür](https://wg21.link/P0482R6) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[STL için P0600R1 \[ \[nodiscard,\] \] Bölüm 1](https://wg21.link/p0600r1) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0653R2 to_address()](https://wg21.link/p0653r2) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0754R2 \<sürüm>](https://wg21.link/p0754r2) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0771R1 noexcept std için::function's Move Constructor](https://wg21.link/P0771R1) | VS 2019 16,2 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0487R1 Sabitleme operatörü>>(basic_istream&, CharT*)](https://wg21.link/P0487R1) | VS 2019 16,3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0616R0 Sayısal>\<taşıma() kullanma](https://wg21.link/p0616r0) | VS 2019 16,3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0758R1 is_nothrow_convertible](https://wg21.link/P0758R1) | VS 2019 16,3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0898R3 Standart Kütüphane Konseptleri](https://wg21.link/P0898R3) | VS 2019 16,3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0919R3 Sırasız Konteynerler İçin Heterojen Arama](https://wg21.link/P0919R3) | VS 2019 16,3 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1754R1 Kavramları standard_case Yeniden Adlandır](https://wg21.link/P1754R1) | VS 2019 16,4 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0325R4 güncellemeleri ile LFTS to_array](https://wg21.link/P0325R4) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0340R3 SFINAE Dostu underlying_type](https://wg21.link/P0340R3) | VS 2019 16,5 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0356R5 bind_front()](https://wg21.link/P0356R5) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0439R0 enum sınıfı memory_order](https://wg21.link/p0439r0) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0553R4 \<bit> Döndürme ve Sayma Fonksiyonları](https://wg21.link/P0553R4) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0556R3 \<bit> ispow2(), ceil2(), floor2(), log2p1()](https://wg21.link/P0556R3) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0595R2 is_constant_evaluated()](https://wg21.link/P0595R2) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0631R8 \<sayılar> Matematik Sabitleri](https://wg21.link/P0631R8) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0738R2 istream_iterator Temizleme](https://wg21.link/P0738R2) | VS 2019 16,5 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0767R1 Amortisman is_pod](https://wg21.link/P0767R1) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0966R1 dizesi::reserve() Küçültmemeli](https://wg21.link/P0966R1) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1209R0 erase_if(), silme()](https://wg21.link/P1209R0) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1227R2 İmzalı std::ssize(), Imzasız yayılma::boyut()](https://wg21.link/P1227R2) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1355R2 Dar Sözleşme için ceil2()](https://wg21.link/P1355R2) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1357R1 is_bounded_array, is_unbounded_array](https://wg21.link/P1357R1) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1612R1 Endian'ın \<bit>taşınması](https://wg21.link/P1612R1) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1651R0 bind_front() reference_wrapper açmamalıdır](https://wg21.link/P1651R0) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1690R1 Sırasız Konteynerler Için Heterojen Aramayı Rafine Etme](https://wg21.link/P1690R1) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P1902R1 Eksik Özellik-Test Makroları 2017-2019](https://wg21.link/P1902R1) | VS 2019 16,5 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0019R8 atomic_ref](https://wg21.link/P0019R8) | Hayır |
| &nbsp;&nbsp;[P0053R7 \<syncstream>](https://wg21.link/p0053r7)<br/>&nbsp;&nbsp;[P0753R2 osyncstream Manipülatörler](https://wg21.link/p0753r2) | Hayır |
| &nbsp;&nbsp;[P0122R7 \<açıklıklı>](https://wg21.link/p0122r7) | Hayır |
| &nbsp;&nbsp;[P0202R3 constexpr \<Algoritma> ve değişim için()](https://wg21.link/p0202r3) | Hayır |
| &nbsp;&nbsp;[P0339R6 polymorphic_allocator<>](https://wg21.link/P0339R6) | Hayır |
| &nbsp;&nbsp;[P0355R7 \<chrono> Takvimler Ve Saat Dilimleri](https://wg21.link/p0355r7) | Hayır |
| &nbsp;&nbsp;[P0357R3 Reference_wrapper Eksik Tipleri Destekleme](https://wg21.link/P0357R3) | Hayır |
| &nbsp;&nbsp;[P0415R1 constexpr \<Kompleks> için (Tekrar)](https://wg21.link/p0415r1) | Hayır |
| &nbsp;&nbsp;[P0475R1 Piecewise İnşaat Için Garantili Kopya Elision](https://wg21.link/P0475R1) | Hayır |
| &nbsp;&nbsp;[P0476R2 \<bit> bit_cast](https://wg21.link/P0476R2) | Hayır |
| &nbsp;&nbsp;[P0528R3 Dolgu Uçları ile Atomik Karşılaştırma Ve Değişim](https://wg21.link/P0528R3) | Hayır |
| &nbsp;&nbsp;[P0591R4 Kullanım-Allocator İnşaat için Yardımcı Fonksiyonlar](https://wg21.link/P0591R4) | Hayır |
| &nbsp;&nbsp;[P0608R3 Varyantın Dönüştürücü/Atamayı Geliştirme](https://wg21.link/P0608R3) | Hayır |
| &nbsp;&nbsp;[P0619R4 C++17-Amortismana Ait Özelliklerin Kaldırılması C++20](https://wg21.link/P0619R4) | Hayır |
| &nbsp;&nbsp;[P0653R2 to_address()](https://wg21.link/p0653r2) | Hayır |
| &nbsp;&nbsp;[P0655R1\<ziyaret R>()](https://wg21.link/P0655R1) | Hayır |
| &nbsp;&nbsp;[P0674R1 make_shared() Diziler İçin](https://wg21.link/p0674r1) | Hayır |
| &nbsp;&nbsp;[P0718R2\<atomik\<shared_ptr T\<\<>>, atom weak_ptr T>>](https://wg21.link/p0718r2) | Hayır |
| &nbsp;&nbsp;[Spaceship Karşılaştırma Operatörü için P0768R1 Kütüphane Desteği\<=>](https://wg21.link/p0768r1) | Hayır |
| &nbsp;&nbsp;[P0811R3 orta nokta(), lerp()](https://wg21.link/P0811R3) | Hayır |
| &nbsp;&nbsp;[P0879R0 constexpr Swapping Fonksiyonları için](https://wg21.link/P0879R0) | Hayır |
| &nbsp;&nbsp;[P0896R4 \<aralıkları\>](https://wg21.link/P0896R4) | Hayır |
| &nbsp;&nbsp;[P0912R5 Ortak Yordamlar için Kütüphane Desteği](https://wg21.link/P0912R5) | Hayır |
| &nbsp;&nbsp;[P0920R2 Önceden Hesaplanmış Hash Değer Arama](https://wg21.link/P0920R2) | Hayır |
| &nbsp;&nbsp;[P0935R0 Gereksiz Yere Açık Varsayılan Yapıcıları Ortadan Kaldırma](https://wg21.link/P0935R0) | Hayır |
| &nbsp;&nbsp;[P1001R2 yürütme::unseq](https://wg21.link/P1001R2) | Hayır |
| &nbsp;&nbsp;[P1006R1 constexpr pointer_traits<için T*>::pointer_to()](https://wg21.link/P1006R1) | Hayır |
| &nbsp;&nbsp;[P1007R3 assume_aligned()](https://wg21.link/P1007R3) | Hayır |
| &nbsp;&nbsp;[Varsayılan Başlatma ile P1020R1 Akıllı İşaretçi Oluşturma](https://wg21.link/P1020R1) | Hayır |
| &nbsp;&nbsp;[P1023R0 constexpr Std için::dizi Karşılaştırmalar](https://wg21.link/P1023R0) | Hayır |
| &nbsp;&nbsp;[P1032R1 Muhtelif konstexpr](https://wg21.link/P1032R1) | Hayır |
| &nbsp;&nbsp;[P1165R1 basic_string operatöründe Stateful Allocators'ı Sürekli Olarak Yayma+()](https://wg21.link/P1165R1) | Hayır |
| &nbsp;&nbsp;[P1285R0 Tip Özellikleri için Bütünlük Gereksinimlerini N](https://wg21.link/P1285R0) | Hayır |
| __C++17 Standart kitaplık özellikleri__ | __Desteklenen__ |
| &nbsp;&nbsp;[Nullptr için LWG 2221 Biçimlendirilmiş çıkış operatörü](https://cplusplus.github.io/LWG/issue2221) | VS 2019 16,1 |
| &nbsp;&nbsp;[N3911 void_t](https://wg21.link/n3911) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4089 Güvenli Dönüşümler\<unique_ptr T[]>](https://wg21.link/n4089) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4169 invoke()](https://wg21.link/n4169) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4190 kaldırma auto_ptr, random_shuffle(), \<Ve Eski fonksiyonel>](https://wg21.link/n4190) | VS 2015 <sup> [rem](#note_rem)</sup> |
| &nbsp;&nbsp;[N4258 noexcept Temizlik](https://wg21.link/n4258) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4259 uncaught_exceptions()](https://wg21.link/n4259) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4277 Trivially Kopyalanabilir reference_wrapper](https://wg21.link/n4277) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4279 insert_or_assign()/try_emplace() Harita/unordered_map için](https://wg21.link/n4279) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4280 boyutu(), boş(), veri()](https://wg21.link/n4280) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4366 Tam Unique_ptr Atama](https://wg21.link/n4366) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4387 İyileştirme çifti Ve tuple](https://wg21.link/n4387) | VS 2015,2 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4389 bool_constant](https://wg21.link/n4389) | VS 2015 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4508 shared_mutex (Zamansız)](https://wg21.link/n4508) | VS 2015,2 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4510 Eksik Türleri Destekleme Vektör/Liste/forward_list](https://wg21.link/n4510) | VS 2013 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[N4562 Kütüphane Temelleri: \<algoritma> örnek()](https://wg21.link/n4562#alg.random.sample) | VS 2017 15,0 |
| &nbsp;&nbsp;[N4562 Kütüphane Temelleri: \<herhangi bir>](https://wg21.link/n4562#any) | VS 2017 15,0 |
| &nbsp;&nbsp;[N4562 Kütüphane Nin \<Temelleri: memory_resource>](https://wg21.link/n4562#memory.resource.synop)<br/>&nbsp;&nbsp;[P0337R0 Polymorphic_allocator Atama Silme](https://wg21.link/p0337r0) | VS 2017 15,6 |
| &nbsp;&nbsp;[N4562 Kütüphane Temelleri: \<isteğe bağlı>](https://wg21.link/n4562#optional) | VS 2017 15,0 |
| &nbsp;&nbsp;[N4562 Kütüphane Nin \<Temelleri: string_view>](https://wg21.link/n4562#string.view) | VS 2017 15,0 |
| &nbsp;&nbsp;[N4562 Kütüphane Temelleri: \<tuple> uygulamak()](https://wg21.link/n4562#tuple) | VS 2017 15,0 |
| &nbsp;&nbsp;[N4562 Kütüphane Temelleri: Boyer-Moore arama()](https://wg21.link/n4562#func.searchers.boyer_moore)<br/>&nbsp;&nbsp;[P0253R1 Sabitleme Arama İade Türleri](https://wg21.link/p0253r1) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0003R5 Dinamik Özel Durum Özellikleri Nin Kaldırılması](https://wg21.link/p0003r5) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0004R1 Amortismana Ait İostreams Takma Adları Kaldırma](https://wg21.link/p0004r1) | VS 2015.2 <sup> [rem](#note_rem)</sup> |
| &nbsp;&nbsp;[P0005R4 not_fn()](https://wg21.link/p0005r4)<br/>&nbsp;&nbsp;[P0358R1 not_fn için düzeltmeler()](https://wg21.link/p0358r1) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0006R0 Tip Özellikleri için Değişken Şablonlar (is_same_v, vb.)](https://wg21.link/p0006r0) | VS 2015,2 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0007R1 as_const()](https://wg21.link/p0007r1) | VS 2015,2 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0013R1 Mantıksal Operatör Tipi Özellikleri (bağlaç, vb.)](https://wg21.link/p0013r1) | VS 2015,2 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0024R2 Paralel Algoritmalar](https://wg21.link/p0024r2)<br/>&nbsp;&nbsp;[P0336R1 Paralel Yürütme İlkelerinin Yeniden Adlandırılması](https://wg21.link/p0336r1)<br/>&nbsp;&nbsp;[P0394R4 Paralel Algoritmalar Sonlandırmalı() İstisnalar İçin](https://wg21.link/p0394r4)<br/>&nbsp;&nbsp;[P0452R1 Birleştirici \<sayısal> Paralel Algoritmalar](https://wg21.link/p0452r1) | VS 2017 15,7 |
| &nbsp;&nbsp;[P0025R1 kelepçe()](https://wg21.link/p0025r1) | VS 2015,3 |
| &nbsp;&nbsp;[P0030R1 hipot(x, y, z)](https://wg21.link/p0030r1) | VS 2017 15,7 |
| &nbsp;&nbsp;[P0031R0 constexpr \<Dizi> için \<(Tekrar) Ve>reerator](https://wg21.link/p0031r0) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0032R3 Homojen Arayüz Varyant/any/isteğe bağlı](https://wg21.link/p0032r3) | VS 2017 15,0 |
| &nbsp;&nbsp;[P0033R1 Enable_shared_from_this Yeniden İfade](https://wg21.link/p0033r1) | VS 2017 15,5 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0040R3 Bellek Yönetim Araçları Genişletme](https://wg21.link/p0040r3) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0063R3 C11 Standart Kütüphane](https://wg21.link/p0063r3) | VS 2015 <sup> [C11](#note_C11), [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0067R5 Temel Dize Dönüşümleri](https://wg21.link/p0067r5) | VS 2019 16.4 <sup> [charconv](#note_charconv)</sup> |
| &nbsp;&nbsp;[P0074R0 owner_less\<>](https://wg21.link/p0074r0) | VS 2015,2 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0077R2 is_callable is_nothrow_callable](https://wg21.link/p0077r2) | VS 2017 15,0 |
| &nbsp;&nbsp;[P0083R3 Yapıştırma Harita ve Setleri](https://wg21.link/p0083r3)<br/>&nbsp;&nbsp;[P0508R0 insert_return_type](https://wg21.link/p0508r0) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0084R2 Emplace Dönüş Tipi](https://wg21.link/p0084r2) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0088R3 \<varyant>](https://wg21.link/p0088r3) | VS 2017 15,0 |
| &nbsp;&nbsp;[P0092R1 \<chrono> zemin(), ceil(), yuvarlak(), abs()](https://wg21.link/p0092r1) | VS 2015,2 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0152R1 atom::is_always_lock_free](https://wg21.link/p0152r1) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0154R1 hardware_destructive_interference_size, vb.](https://wg21.link/p0154r1) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0156R0 Variadik lock_guard](https://wg21.link/p0156r0) | VS 2015,2 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0156R2 Kapsamlı\_\_kilit için Variadic kilit koruma yeniden adlandırma](https://wg21.link/p0156r2) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0163R0 shared_ptr::weak_type](https://wg21.link/p0163r0) | VS 2017 15,0 |
| &nbsp;&nbsp;[P0174R2 Amortisman Vestigial Kütüphane Parçaları](https://wg21.link/p0174r2) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0185R1 is_swappable, is_nothrow_swappable](https://wg21.link/p0185r1) | VS 2015,3 |
| &nbsp;&nbsp;[P0209R2 make_from_tuple()](https://wg21.link/p0209r2) | VS 2017 15,0 |
| &nbsp;&nbsp;[P0218R1 \<dosya sistemi>](https://wg21.link/p0218r1)<br/>&nbsp;&nbsp;[P0219R1 Dosya Sistemi için Göreli Yollar](https://wg21.link/p0219r1)<br/>&nbsp;&nbsp;[P0317R1 Dizin Giriş Önbelleğe Alma Dosya Sistemi](https://wg21.link/p0317r1)<br/>&nbsp;&nbsp;[P0392R0 Dosya Sistemi Yollarında string_view Destekleme](https://wg21.link/p0392r0)<br/>&nbsp;&nbsp;[P0430R2 POSIX Olmayan File sistemlerini destekleme](https://wg21.link/p0430r2)<br/>&nbsp;&nbsp;[P0492R2 Dosya Sistemi için NB Yorumları çözme](https://wg21.link/p0492r2) | VS 2017 15,7 <sup> [E](#note_E)</sup> |
| &nbsp;&nbsp;[P0220R1 Kütüphane Temelleri V1](https://wg21.link/p0220r1) | VS 2017 15,6 |
| &nbsp;&nbsp;[P0226R1 Matematiksel Özel Fonksiyonlar](https://wg21.link/p0226r1) | VS 2017 15,7 |
| &nbsp;&nbsp;[P0254R2 Entegre string_view Ve std::string](https://wg21.link/p0254r2) | VS 2017 15,0 |
| &nbsp;&nbsp;[P0258R2 has_unique_object_representations](https://wg21.link/p0258r2) | VS 2017 15,3 <sup> [G](#note_G)</sup> |
| &nbsp;&nbsp;[P0272R1 Const olmayan basic_string::data()](https://wg21.link/p0272r1) | VS 2015,3 |
| &nbsp;&nbsp;[P0295R0 gcd(), lcm()](https://wg21.link/p0295r0) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0298R3 std::bayt](https://wg21.link/p0298r3) | VS 2017 15.3 <sup> [17](#note_17),&nbsp;[bayt](#note_byte)</sup> |
| &nbsp;&nbsp;[P0302R1 Std'de Allocator Desteği Kaldırma::fonksiyon](https://wg21.link/p0302r1) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0307R2 İsteğe Bağlı Daha Fazla Eşit Yapma](https://wg21.link/p0307r2) | VS 2017 15,0 |
| &nbsp;&nbsp;[P0393R3 Yapma Varyantı Daha Fazla Eşit](https://wg21.link/p0393r3) | VS 2017 15,0 |
| &nbsp;&nbsp;[P0403R1 UDL'ler \<string_view> için ("miyav"sv, vb.)](https://wg21.link/p0403r1) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0414R2 shared_ptr\<T[]>, shared_ptr\<T[N]>](https://wg21.link/p0414r2)<br/>&nbsp;&nbsp;[P0497R0 Diziler için sabitleme shared_ptr](https://wg21.link/p0497r0) | VS 2017 15,5 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0418R2 atom compare_exchange memory_order Gereksinimleri](https://wg21.link/p0418r2) | VS 2017 15,3 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0426R1 constexpr char_traits](https://wg21.link/p0426r1) | VS 2017 15,7 |
| &nbsp;&nbsp;[P0433R2 Sınıf şablonları için şablon tümleştirmesi standart kitaplığa](https://wg21.link/p0433r2)<br/>&nbsp;&nbsp;[P0739R0 Standart kitaplığa sınıf şablonu bağımsız değişken tümleştirmesini geliştirme](https://wg21.link/p0739r0) | VS 2017 15,7 |
| &nbsp;&nbsp;[P0435R1 Revizyon common_type](https://wg21.link/p0435r1)<br/>&nbsp;&nbsp;[P0548R1 Tweaking\_ortak türü ve süresi](https://wg21.link/p0548r1) | VS 2017 15,3 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0504R0 Revisiting in_place_t/in_place_type_t\<T\<>/in_place_index_t I>](https://wg21.link/p0504r0) | VS 2017 15,0 |
| &nbsp;&nbsp;[P0505R0 constexpr \<Chrono> için (Tekrar)](https://wg21.link/p0505r0) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0510R0 Hiçbir şeyin, dizilerin, başvuruların ve eksik türlerinin reddi](https://wg21.link/p0510r0) | VS 2017 15,0 |
| &nbsp;&nbsp;[P0513R0 Zehirlenme hash](https://wg21.link/p0513r0)<br/>&nbsp;&nbsp;[P0599R1 noexcept karma](https://wg21.link/p0599r1) | VS 2017 15,3 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0516R0 İşaretleme shared_future Noexcept Olarak Kopyalama](https://wg21.link/p0516r0) | VS 2017 15,3 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0517R0 future_errc'dan future_error Oluşturma](https://wg21.link/p0517r0) | VS 2017 15,3 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0521R0 Amortisman shared_ptr::unique()](https://wg21.link/p0521r0) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0558R1 Atom\<T> İsimli Taban Sınıf Tutarsızlıklarının Çözümü](https://wg21.link/p0558r1) | VS 2017 15,3 <sup> [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0595R2 std::is_constant_evaluated()](https://wg21.link/P0595R2) | VS 2019 16,5 <sup> [20](#note_20)</sup> |
| &nbsp;&nbsp;[P0602R4 Çoğaltma Kopyalama Kopyalama/Taşıma Triviality Varyant/isteğe bağlı](https://wg21.link/P0602R4) | VS 2017 15,3<sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0604R0 Değiştirme\_çağrılabilir/sonucu\_\_çağırmak\_için, çağrılabilir, nothrow\_\_invocable olduğunu](https://wg21.link/p0604r0) | VS 2017 15,3 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0607R0 Standart Kitaplık için Satır İçi Değişkenler](https://wg21.link/p0607r0) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0618R0 Deprecating \<codecvt>](https://wg21.link/p0618r0) | VS 2017 15,5 <sup> [17](#note_17)</sup> |
| &nbsp;&nbsp;[P0682R1 Temel Dize Dönüşümlerinin Onarılması](https://wg21.link/P0682R1) | VS 2015 15,7 <sup> [17](#note_17)</sup> |
| __C++14 Standart kitaplık özellikleri__ | __Desteklenen__ |
| &nbsp;&nbsp;[N3462 SFINAE Dostu result_of](https://wg21.link/n3462) | VS 2015.2 |
| &nbsp;&nbsp;[N3302 constexpr \<Karmaşık>için](https://wg21.link/n3302) | VS 2015 |
| &nbsp;&nbsp;[N3469 constexpr \<Chrono>için](https://wg21.link/n3469) | VS 2015 |
| &nbsp;&nbsp;[N3470 constexpr \<Dizi>için](https://wg21.link/n3470) | VS 2015 |
| &nbsp;&nbsp;[N3471 constexpr \<initializer_list \<> için, \<tuple>, yardımcı>](https://wg21.link/n3471) | VS 2015 |
| &nbsp;&nbsp;[N3545 integral_constant::operator()()](https://wg21.link/n3545) | VS 2015 |
| &nbsp;&nbsp;[N3642 UDLs \<Chrono \<> için, string> (1729ms, "miyav"lar, vb)](https://wg21.link/n3642) | VS 2015 |
| &nbsp;&nbsp;[N3644 Null Forward Yineleyiciler](https://wg21.link/n3644) | VS 2015 |
| &nbsp;&nbsp;[N3654 alıntı()](https://wg21.link/n3654) | VS 2015 |
| &nbsp;&nbsp;[N3657 Heterojen Birleştirici Arama](https://wg21.link/n3657) | VS 2015 |
| &nbsp;&nbsp;[N3658 integer_sequence](https://wg21.link/n3658) | VS 2015 |
| &nbsp;&nbsp;[N3659 shared_mutex (Zamanlı)](https://wg21.link/n3659) | VS 2015 |
| &nbsp;&nbsp;[N3668 değişim()](https://wg21.link/n3668) | VS 2015 |
| &nbsp;&nbsp;[N3669 Const olmadan constexpr Üye Fonksiyonları sabitleme](https://wg21.link/n3669) | VS 2015 |
| &nbsp;&nbsp;[N3670\<T> olsun()](https://wg21.link/n3670) | VS 2015 |
| &nbsp;&nbsp;[N3671 Çift Aralıklı eşit(), is_permutation(), uyuşmazlık()](https://wg21.link/n3671) | VS 2015 |
| &nbsp;&nbsp;[N3778 Ölçekli Deallocation](https://wg21.link/n3778) | VS 2015 |
| &nbsp;&nbsp;[N3779 UDLs \<Karmaşık> için (3.14i, vb.)](https://wg21.link/n3779) | VS 2015 |
| &nbsp;&nbsp;[Fonksiyonel>için \<N3789 constexpr](https://wg21.link/n3789) | VS 2015 |
| &nbsp;&nbsp;[N3887 tuple_element_t](https://wg21.link/n3887) | VS 2015 |
| &nbsp;&nbsp;[N3891 shared_mutex (Zamanlanmış) shared_timed_mutex Yeniden Adlandırma](https://wg21.link/n3891) | VS 2015 |
| &nbsp;&nbsp;[N3346 Minimal Konteyner Elemanı Gereksinimleri](https://wg21.link/n3346) | VS 2013 |
| &nbsp;&nbsp;[N3421 Şeffaf Operatör Functors (daha az\<>, vb)](https://wg21.link/n3421) | VS 2013 |
| &nbsp;&nbsp;[N3655 Diğer Ad \<Şablonları type_traits> (decay_t, vb.)](https://wg21.link/n3655) | VS 2013 |
| &nbsp;&nbsp;[N3656 make_unique()](https://wg21.link/n3656) | VS 2013 |

Birlikte listelenen bir kağıt grubu, bir veya daha fazla onaylı iyileştirme veya genişletmenin yanı sıra standart özelliği gösterir. Bu özellikler birlikte uygulanır.

### <a name="supported-values"></a>Desteklenen değerler

__Henüz__ uygulanmamış anlamına gelmez.\
__Kısmi__ uygulama eksik olduğu anlamına gelir. Daha fazla bilgi için Notlar bölümüne bakın.\
__VS 2010__ Visual Studio 2010'da desteklenen özellikleri gösterir.\
__VS 2013,__ Visual Studio 2013'te desteklenen özellikleri gösterir.\
__VS 2015,__ Visual Studio 2015'te desteklenen özellikleri gösterir (RTW).\
__VS 2015.2__ ve __VS 2015.3,__ Visual Studio 2015 Update 2 ve Visual Studio 2015 Update 3'te desteklenen özellikleri sırasıyla belirtir.\
__VS 2017 15.0,__ Visual Studio 2017 sürüm 15.0 (RTW) ile desteklenen özellikleri gösterir.
__VS 2017 15.3__ Visual Studio 2017 sürümü 15.3.\
__VS 2017 15.5__ Visual Studio 2017 sürümü 15.5.\
__VS 2017 15.7__ Visual Studio 2017 sürümü 15.7.\
__VS 2019 16.0__ Visual Studio 2019 sürüm 16.0 (RTW) desteklenen özellikleri gösterir.
__VS 2019 16.1__ Visual Studio 2019 sürümü 16.1.\
__VS 2019 16.2__ Visual Studio 2019 sürümü 16.2'de desteklenen özellikleri gösterir.\
__VS 2019 16.3__ Visual Studio 2019 sürümü 16.3'te desteklenen özellikleri gösterir.\
__VS 2019 16.4__ Visual Studio 2019 sürümü 16.4'te desteklenen özellikleri gösterir.\
__VS 2019 16.5,__ Visual Studio 2019 sürüm 16.5'te desteklenen özellikleri gösterir.

### <a name="notes"></a>Notlar

<a name="note_A"></a>__A__ In [/std:c++14](../build/reference/std-specify-language-standard-version.md) modu, dinamik özel durum `throw()` belirtimleri uygulanmamış kalır `__declspec(nothrow)`ve hala eşanlamlı olarak kabul edilir. C++17'de dinamik özel durum özellikleri çoğunlukla P0003R5 tarafından `throw()` kaldırıldı ve bir kalıntı kaldı: amortismana kaldırıldı `noexcept`ve eş anlamlı olarak olması gerekiyor. [/std:c++17](../build/reference/std-specify-language-standard-version.md) modunda, MSVC artık sonlandırma yoluyla `throw()` zorlama ile `noexcept`aynı davranışı vererek Standarda uygundur.

Derleyici seçeneği [/Zc:noexceptTypes](../build/reference/zc-noexcepttypes.md) eski davranışımızı `__declspec(nothrow)`istiyor. C++20'de `throw()` kaldırılacak gibi görünüyor. Standarttaki bu değişikliklere ve uygulamamıza yanıt olarak kod geçirmekonusunda yardımcı olmak için [/std:c++17](../build/reference/std-specify-language-standard-version.md) ve [/izin-](../build/reference/permissive-standards-conformance.md)altında özel durum belirtimi sorunları için yeni derleyici uyarıları eklendi.

<a name="note_B"></a>__B__ Visual Studio 2017 sürüm 15.7'de [/izin modunda](../build/reference/permissive-standards-conformance.md) desteklenmiştir. Daha fazla bilgi için, [iki aşamalı ad arama desteği MSVC geliyor](https://devblogs.microsoft.com/cppblog/two-phase-name-lookup-support-comes-to-msvc/)bakın.

<a name="note_C"></a>__C__ Visual Studio 2017'de C99 Önişlemci kuralları için derleyici desteği tamamlanmaz. Önişlemciyi elden geçiriyoruz ve visual studio 2017 sürüm 15.8'deki bu değişiklikleri [/experimental:preprocessor](../build/reference/experimental-preprocessor.md) derleyici anahtarıyla gönderip başladık.

<a name="note_D"></a>__D__ [/std:c++14](../build/reference/std-specify-language-standard-version.md) altında bastırılabilir bir uyarı ile desteklenen, [C4984](../error-messages/compiler-warnings/compiler-warning-c4984.md).

<a name="note_E"></a>__E__ Bu tamamen yeni bir uygulama, önceki `std::experimental` sürümü ile uyumsuz, symlink desteği, hata düzeltmeleri ve standart gerekli davranış değişiklikleri tarafından gerekli yapılır. Şu \<anda, dosya sistemi `std::filesystem`> yeni `std::experimental::filesystem`ve önceki \<, ve deneysel / dosya sistemi> dahil olmak üzere sadece eski deneysel uygulama sağlar. Deneysel uygulama, kütüphanelerin bir sonraki ABI-breaking sürümünde KALDıRıLacak.

<a name="note_G"></a>__G__ Bir derleyici tarafından içsel olarak desteklenir.

<a name="note_14"></a>__14__ Bu C++17/20 özellikleri [/std:c++14](../build/reference/std-specify-language-standard-version.md) (varsayılan) belirtilse bile her zaman etkinleştirilir. Bunun nedeni, özelliğin **/std** seçeneklerinin sunulmasından önce uygulanması veya koşullu uygulamanın istenmeyen derecede karmaşık olmasıdır.

<a name="note_17"></a>__17__ Bu özellikler [/std:c++17](../build/reference/std-specify-language-standard-version.md) (veya [/std:c++latest)](../build/reference/std-specify-language-standard-version.md)derleyici seçeneği ile etkinleştirilir.

<a name="note_20"></a>__20__ Bu özellikler [/std:c++en son](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği ile etkinleştirilir. C++20 uygulaması tamamlandığında, bu özelliklerin de kullanılabileceğinin altında yeni bir **/std:c++20** derleyici seçeneği eklenecektir.

<a name="note_byte"></a>__bayt__ `std::byte` [/std:c++17](../build/reference/std-specify-language-standard-version.md) (veya [/std:c++son),](../build/reference/std-specify-language-standard-version.md)ancak bazı durumlarda Windows SDK üstbilgileriyle çakışabildiği için, ince taneli bir devre dışı bırakma makrosu vardır. Olarak tanımlayarak `_HAS_STD_BYTE` devre dışı `0`tutulabilir.

<a name="note_C11"></a>__C11__ Universal CRT, C99 `strftime()` E/O alternatif dönüşüm belirteçleri, C11 `fopen()` özel modu ve C11 dışında C++17'nin gerektirdiği C11 Standart Kitaplığı bölümlerini uygulamaya koymuştur. `aligned_alloc()` C11 Microsoft uygulaması ile uyumsuz bir `aligned_alloc()` şekilde belirtildiği için ikincisi, uygulanması olası `free()`değildir: yani, bu `free()` son derece hizalanmış ayırmaları işlemek gerekir.

<a name="note_rem"></a>__rem__ [/std:c++17](../build/reference/std-specify-language-standard-version.md) (veya [/std:c++en son)](../build/reference/std-specify-language-standard-version.md)derleyici seçeneği belirtildiğinde kaldırılan özellikler. Bu özellikler, bu makrolar kullanarak yeni dil modlarına geçişi kolaylaştırmak için `_HAS_AUTO_PTR_ETC` `_HAS_FUNCTION_ALLOCATOR_SUPPORT`yeniden `_HAS_OLD_IOSTREAMS_MEMBERS`etkinleştirilebilir: , , ve `_HAS_UNEXPECTED`.

<a name="note_charconv"></a>__charconv__ `from_chars()` `to_chars()` ve integers için kullanılabilir. Kayan nokta ve `from_chars()` kayan nokta `to_chars()` için zaman çizelgesi aşağıdaki gibidir:

- VS 2017 15.7: `from_chars()` İnteger ve `to_chars()`.
- VS 2017 15.8: Kayan nokta `from_chars()`.
- VS 2017 15,9: Kayan nokta `to_chars()` en kısa ondalık için aşırı yüklenir.
- VS 2019 16.0: Kayan nokta `to_chars()` en kısa hex ve hassas hex için aşırı yükler.
- VS 2019 16.2: Hassas `to_chars()` sabit ve hassas bilimsel için kayan nokta aşırı yükler.
- VS 2019 16.4: Hassas `to_chars()` genel için kayan nokta aşırı yük.

<a name ="note_parallel"></a>__paralel__ C++17'nin paralel algoritmalar kitaplığı tamamlandı. Tam, her algoritmanın her durumda paralelleştiği anlamına gelmez. En önemli algoritmalar paralelleştirilmiş ve yürütme ilkesi imzaları algoritmalar paralelleştirilemese bile sağlanmıştır. Uygulamamızın merkezi iç başlığı yvals_core.h aşağıdaki "Paralel Algoritmalar Notları"nı içerir: C++, bir uygulamanın seri algoritmalara çağrı olarak paralel algoritmalar uygulamasına izin verir. Bu uygulama, birkaç ortak algoritma çağrıları paralelleştirir, ancak tüm değil.

Aşağıdaki algoritmalar paralelleştirilmiştir:

- `adjacent_difference`, `adjacent_find`, `all_of`, `any_of`, `count`, `count_if`, `equal`, `exclusive_scan`, `find`, `find_end`, `find_first_of`, `find_if`, `find_if_not`, `for_each`, `for_each_n`, `inclusive_scan`, `is_heap`, `is_heap_until`, `is_partitioned`, `is_sorted`, `is_sorted_until`, `mismatch`, `none_of`, `partition`, `reduce`, `remove`, `remove_if`, `replace`, `replace_if`, `search`, `search_n`, `set_difference`, `set_intersection`, `sort`, `stable_sort`, `transform`, `transform_exclusive_scan`, `transform_inclusive_scan`, `transform_reduce`

Aşağıdakiler şu anda paralelleştirilemez:

- Hedef donanımda fark edilir bir paralellik performansı iyileştirmesi yok; dalları olmayan öğeleri yalnızca kopyalayan veya permute eden tüm algoritmalar genellikle bellek bant genişliği sınırlıdır:
  - `copy`, `copy_n`, `fill`, `fill_n`, `move`, `reverse`, `reverse_copy`, `rotate`, `rotate_copy`, `shift_left`, `shift_right`, `swap_ranges`
- Kullanıcı paralelliği gereksinimleri üzerinde karışıklık var; yukarıdaki kategoride zaten muhtemel:
  - `generate`, `generate_n`
- Etkili paralellik mümkün olduğundan şüpheleniliyor:
  - `partial_sort`, `partial_sort_copy`
- Henüz değerlendirilmemiş; paralellik ileride bir sürümde uygulanabilir ve yararlı olduğundan şüpheleniliyor:
  - `copy_if`, `includes`, `inplace_merge`, `lexicographical_compare`, `max_element`, `merge`, `min_element`, `minmax_element`, `nth_element`, `partition_copy`, `remove_copy`, `remove_copy_if`, `replace_copy`, `replace_copy_if`, `set_symmetric_difference`, `set_union`, `stable_partition`, `unique`, `unique_copy`

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Referansı](../cpp/cpp-language-reference.md)\
[C++ Standart Kitaplık](../standard-library/cpp-standard-library-reference.md)\
[Visual Studio'da C++ uygunluk iyileştirmeleri](cpp-conformance-improvements.md)\
[Visual Studio'da Visual C++ İçin Yenilikler](what-s-new-for-visual-cpp-in-visual-studio.md)\
[Visual C++ değişim geçmişi 2003'ten 2015'e](../porting/visual-cpp-change-history-2003-2015.md)\
[Visual C++ What's New 2003-2015](../porting/visual-cpp-what-s-new-2003-through-2015.md)\
[C++ takım günlüğü](https://devblogs.microsoft.com/cppblog/)
