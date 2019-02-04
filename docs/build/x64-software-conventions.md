---
title: x64 yazılım kuralları
ms.date: 12/17/2018
helpviewer_keywords:
- x64 coding conventions
- Visual C++, x64 calling conventions
ms.assetid: 750f3d97-1706-4840-b2fc-41a007329a08
ms.openlocfilehash: 55be8f381b39ee566b389350ff70a9b0a3fe7694
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702074"
---
# <a name="x64-software-conventions"></a>x64 yazılım kuralları

Bu bölümde x64, 64-bit uzantısı x86 kuralı yöntemi çağırma C++ açıklanmaktadır mimarisi.

## <a name="overview-of-x64-calling-conventions"></a>Çağırma kuralları x64 genel bakış

İki önemli fark x86 x64 arasındaki 64-bit adresleme yeteneği olan ve genel kullanım için 16 64-bit düz bir dizi kaydeder. Genişletilen kayıt kümesine göz önünde bulundurulduğunda, x64 kullanan [__fastcall](../cpp/fastcall.md) çağırma kuralı ve bir risk tabanlı özel durum işleme modeli. `__fastcall` Kuralı kayıtlara ilk dört bağımsız değişken ve yığın çerçevesi için ek bağımsız değişkenleri geçirmek için kullanılır. YAZMAÇ kullanımı dahil olmak üzere çağırma x64 ayrıntıları parametreleri yığın için değerleri ve yığın geriye doğru izleme, dönüş [çağırma kuralı x64](x64-calling-convention.md).

## <a name="enable-optimization-for-x64"></a>X64 iyileştirmesini etkinleştir

Aşağıdaki derleyici seçeneği, uygulamanız için x64 iyileştirmenize yardımcı olur:

- [/favor (Mimari Özellikleri için İyileştirme)](../build/reference/favor-optimize-for-architecture-specifics.md)

## <a name="types-and-storage"></a>Türler ve depolama

Bu bölümde, depolama x64 için veri türleri ve numaralandırma açıklanmaktadır mimarisi.

### <a name="scalar-types"></a>skaler türler

Herhangi bir hizalama ile verilerinize erişmek mümkün olsa da, verilerinizde doğal sınırını ya da performans kaybını önlemek için bazı birden çok hizalamak için önerilir. Sabit listelerinde sabit tamsayı olan ve 32 bit tamsayılar olarak kabul edilir. Aşağıdaki hizalama değerleri kullanarak hizalama ilgili olarak aşağıdaki tabloda tür tanımını ve veriler için önerilen depolama açıklanmaktadır:

- Byte - 8 bit

- Word - 16 bit

- Doubleword - 32 bit

- Quadword - 64 bit

- Octaword - 128 bit

|||||
|-|-|-|-|
|Skalar türü|C veri türü|Depolama boyutu (bayt cinsinden)|Önerilen hizalama|
|**INT8**|**char**|1.|Bayt|
|**UINT8**|**İmzasız char**|1.|Bayt|
|**INT16**|**short**|2|Word|
|**UINT16**|**İmzasız short**|2|Word|
|**INT32**|**int**, **uzun**|4|Doubleword|
|**UINT32**|**işaretsiz int, işaretsiz uzun**|4|Doubleword|
|**INT64**|**__int64**|8|Quadword|
|**UINT64**|**imzalanmamış __int64**|8|Quadword|
|**FP32 (tek duyarlık)**|**float**|4|Doubleword|
|**FP64 (çift duyarlık)**|**double**|8|Quadword|
|**İŞARETÇİ**|__\*__|8|Quadword|
|**__m64**|**Yapı __m64**|8|Quadword|
|**__m128**|**Yapı __m128**|16|Octaword|

### <a name="aggregates-and-unions"></a>Toplamlar ve birleşimler

Diziler, yapılar ve birleşimler, diğer türleri, tutarlı toplama ve birleşim depolama ve veri alımı sağlayan daha sıkı hizalama gereksinimleri vardır. Dizi, yapı ve birleşim tanımlarında şunlardır:

- Dizi

   Bir sıralı bitişik veri nesnelerini içerir. Her bir nesne olarak adlandırılan bir *öğesi*. Bir dizi içindeki tüm öğeleri aynı boyuta ve veri türüne sahip.

- Yapı

   Bir sıralanmış veri nesneleri içerir. Bir dizi öğelerinden farklı olarak, bir yapı içinde veri nesneleri farklı veri türleri ve boyutları olabilir. Bir yapıdaki her veri nesnesi olarak adlandırılan bir *üye*.

- UNION

   Herhangi bir adlandırılmış üyelerin kümesini tutan nesne. Adlandırılmış kümesi üyeleri herhangi bir türde olabilir. Bir birleşimin ayrılan depolama alanı, en büyük hizalama için gerekli tüm doldurma yanı sıra bu birleşim üyesi için gerekli olan depolama eşittir.

Aşağıdaki tablo, skaler üyelerinin birleşimleri ve yapıları için kesin önerilen hizalama gösterir.

||||
|-|-|-|
|Skalar türü|C veri türü|Gerekli hizalama|
|**INT8**|**char**|Bayt|
|**UINT8**|**İmzasız char**|Bayt|
|**INT16**|**short**|Word|
|**UINT16**|**İmzasız short**|Word|
|**INT32**|**int**, **uzun**|Doubleword|
|**UINT32**|**işaretsiz int, işaretsiz uzun**|Doubleword|
|**INT64**|**__int64**|Quadword|
|**UINT64**|**imzalanmamış __int64**|Quadword|
|**FP32 (tek duyarlık)**|**float**|Doubleword|
|**FP64 (çift duyarlık)**|**double**|Quadword|
|**İŞARETÇİ**|<strong>\*</strong>|Quadword|
|**__m64**|**Yapı __m64**|Quadword|
|**__m128**|**Yapı __m128**|Octaword|

Aşağıdaki toplama hizalama kurallar geçerlidir:

- Bir dizinin hizalama, bir dizinin öğelerin hizalamasını ile aynıdır.

- Herhangi bir üyenin en büyük hizalama başına bir yapı veya bir birleşim hizalamadır. Yapı veya birleşim içerisindeki her üye uygun hizalamanın önceki üye bağlı olarak örtük iç doldurma gerektirebilir önceki tabloda tanımlandığı gibi yerleştirilmelidir.

- Yapı boyutu doldurma son üyesinden sonra gerektirebilir, hizalama, tümleşik bir katı olmalıdır. Yapılar ve birleşimler dizilerde gruplandırılabilir olduğundan, yapı veya birleşim her dizi öğesi başlayıp bitmelidir önceden belirlenen uygun hizalaması.

- Verileri önceki kurallar korunduğu sürece hizalama gereksinimlerinden daha büyük olacak şekilde hizalayın mümkündür.

- Ayrı bir derleyici paketleme boyutu nedeniyle bir yapının ayarlayabilirsiniz. Örneğin [/Zp (yapı üyesi hizalama)](../build/reference/zp-struct-member-alignment.md) yapıları paketleme ayarlamak için sağlar.

### <a name="examples-of-structure-alignment"></a>Yapı Hizalama Örnekleri

Hizalanmış bir yapı veya birleşim ve karşılık gelen rakamları, yapı veya birleşim bellekte düzenini gösteren aşağıdaki dört örnek her bildirin. Her sütunda bir şekil bellek baytını temsil eder ve öteleme bu bayt sayısı sütunundaki sayıyı belirtir. Her Şekil ikinci satırındaki adı bir Değişken bildiriminde adını karşılık gelir. Gölgeli sütunlar doldurmayı belirtilen hizalama ulaşmak için gerekli olan gösterir.

#### <a name="example-1"></a>Örnek 1

```C
// Total size = 2 bytes, alignment = 2 bytes (word).

_declspec(align(2)) struct {
    short a;      // +0; size = 2 bytes
}
```

![AMD dönüştürme örnek 1 yapısı Düzen](../build/media/vcamd_conv_ex_1_block.png "AMD dönüştürme örnek 1 yapısı düzeni")

#### <a name="example-2"></a>Örnek 2

```C
// Total size = 24 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) struct {
    int a;       // +0; size = 4 bytes
    double b;    // +8; size = 8 bytes
    short c;     // +16; size = 2 bytes
}
```

![AMD dönüştürme örnek 2 yapısı Düzen](../build/media/vcamd_conv_ex_2_block.png "AMD dönüştürme örnek 2 yapısı düzeni")

#### <a name="example-3"></a>Örnek 3

```C
// Total size = 12 bytes, alignment = 4 bytes (doubleword).

_declspec(align(4)) struct {
    char a;       // +0; size = 1 byte
    short b;      // +2; size = 2 bytes
    char c;       // +4; size = 1 byte
    int d;        // +8; size = 4 bytes
}
```

![AMD dönüştürme örnek 2 yapısı Düzen](../build/media/vcamd_conv_ex_3_block.png "AMD dönüştürme örnek 2 yapısı düzeni")

#### <a name="example-4"></a>Örnek 4

```C
// Total size = 8 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) union {
    char *p;      // +0; size = 8 bytes
    short s;      // +0; size = 2 bytes
    long l;       // +0; size = 4 bytes
}
```

![AMD dönüştürme örnek 4 birleşim layouit](../build/media/vcamd_conv_ex_4_block.png "AMD dönüştürme örnek 4 birleşim layouit")

### <a name="bitfields"></a>Bit Alanları

Yapı bit alanları 64 bit ile sınırlıdır ve türden olabilir imzalı int, işaretsiz int, Int64 veya işaretsiz Int64. Tür sınırını aşan bit alanları bit alanından mantıksal karşılaştırmaya sonraki tür hizalaması için hizalamak için BITS atlar. Örneğin, bir 32-bit sınırını tamsayı bit alanları geçebilir.

### <a name="conflicts-with-the-x86-compiler"></a>X86 çakışıyor derleyici

X86 kullandığınızda 4 bayt yığın üzerinde otomatik olarak hizalanmaz daha büyük olan veri türleri bir uygulama derlemek için derleyici. Çünkü derleyicisidir bir 4 bayt hizalı yığını, örneğin, bir 64-bit tamsayı olan 4 bayt daha büyük bir şey olamaz otomatik olarak hizalanmayacak 8 baytlık adresin x86 mimarisi.

Hizalanmamış veri ile çalışma, iki olası etkilere sahiptir.

- Hizalanmış konumlara erişmek için gereken daha Hizalanmamış konumlara erişmek için daha uzun sürebilir.

- Hizalanmamış konumları birbirine kenetlenmiş işlemler içinde kullanılamaz.

Daha fazla katı hizalama gerektiren kullanırsanız `__declspec(align(N))` , değişken bildirimlerinde. Bu, derleyicinin yığın belirtimleri karşılamak için dinamik olarak hizalamak neden olur. Ancak, yığın çalışma zamanında dinamik olarak ayarlama, uygulamanızın daha yavaş yürütme neden olabilir.

## <a name="register-usage"></a>YAZMAÇ kullanımı

16 XMM/YMM yanı sıra 16 genel amaçlı kayıtları (tamsayı kayıtları olarak bundan sonra anılacaktır) mimarisi sunar x64 kayan nokta kullanıma kaydeder. Geçici kayıtları çağrıyla yok edilecek çağıran tarafından karalama kayıtlardır. Kalıcı kayıtlar arasında bir işlev çağrısı değerlerini korumak için gereklidir ve Aranan tarafından kullanılan kaydedilmesi gerekir.

### <a name="register-volatility-and-preservation"></a>Kayıt geçiciliğine ve korunması

Aşağıdaki tabloda, her kaydın işlev çağrıları arasında nasıl kullanıldığını açıklar:

||||
|-|-|-|
|Yazmaç|Durum|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|RAX|Volatile|Dönüş değeri kaydı|
|RCX|Volatile|İlk tamsayı bağımsız değişkeni|
|RDX|Volatile|İkinci bağımsız değişken|
|R8|Volatile|Üçüncü bağımsız değişken|
|R9|Volatile|Dördüncü tamsayı bağımsız değişkeni|
|R10:R11|Volatile|Çağıran tarafından gerektiği şekilde korunması gerekir; syscall/sysret yönergelerinde kullanılmalıdır|
|R12:R15|Kalıcı|Aranan tarafından korunması gerekir|
|RDI|Kalıcı|Aranan tarafından korunması gerekir|
|RSI|Kalıcı|Aranan tarafından korunması gerekir|
|RBX|Kalıcı|Aranan tarafından korunması gerekir|
|RBP|Kalıcı|Çerçeve işaretçisi olarak kullanılabilir. Aranan tarafından korunması gerekir|
|RSP|Kalıcı|Yığın işaretçisi|
|XMM0, YMM0|Volatile|İlk FP bağımsız değişkeni; ilk vektör türü bağımsız değişken olduğunda `__vectorcall` kullanılır|
|XMM1, YMM1|Volatile|İkinci FP bağımsız değişkeni; vektör türü bağımsız değişken ikinci zaman `__vectorcall` kullanılır|
|XMM2, YMM2|Volatile|Üçüncü FP bağımsız değişkeni; Üçüncü vektör türü bağımsız değişken olduğunda `__vectorcall` kullanılır|
|XMM3, YMM3|Volatile|Dördüncü FP bağımsız değişkeni; Dördüncü vektör türü bağımsız değişken olduğunda `__vectorcall` kullanılır|
|XMM4, YMM4|Volatile|Çağıran tarafından gerektiği şekilde korunması gerekir; Beşinci vektör türü bağımsız değişken olduğunda `__vectorcall` kullanılır|
|XMM5, YMM5|Volatile|Çağıran tarafından gerektiği şekilde korunması gerekir; Altıncı vektör türü bağımsız değişken olduğunda `__vectorcall` kullanılır|
|XMM6:XMM15, YMM6:YMM15|Kalıcı (XMM) Volatile (YMM üst kısmında)|Aranan tarafından korunmalıdır. YMM kayıtları, çağıran tarafından gerektiği şekilde korunmalıdır.|

İşlev çıkmadan ve C çalışma zamanı kitaplığı çağrıları ve Windows sistem çağrıları işlev girişi, CPU yön bayrağı bayrakları kayıt temizlenmesi bekleniyor.

## <a name="stack-usage"></a>Yığın kullanımı

Yığın ayırma, hizalama, işlev türleri ve yığın çerçevelerini x64 hakkında daha fazla bilgi için bkz: [x64 yığın kullanımı](stack-usage.md).

## <a name="prolog-and-epilog"></a>Giriş ve bitiş

Yığın alanı ayırır, diğer işlevleri çağırır, kalıcı Yazmaçları kaydeder veya özel durum işleme kullanan her işlevi geriye doğru izlenen veri ilgili işlevi tablo girişi ve adresindeki başlangıçları ile ilişkili adres sınırları açıklanan bir giriş olmalıdır Her çıkış bir işlev. Gerekli giriş hakkında ayrıntılı bilgi ve epilog kodu x64 bkz [x64 giriş ve bitiş](prolog-and-epilog.md).

## <a name="x64-exception-handling"></a>x64 özel durum işleme

Yapılandırılmış özel durum işleme ve C++ özel durum işleme davranışını x64 uygulamak için kullanılan veri yapılarını ve kuralları hakkında daha fazla bilgi için bkz: [x64 özel durum işleme](exception-handling-x64.md).

## <a name="intrinsics-and-inline-assembly"></a>Yapı içi değerler ve satır içi derleme

Bir x64 için kısıtlamaların derleyici satır içi assembler desteği yok etmektir. İşlevler yani C veya C++ ortamında ya da alt yordamlar veya derleyici tarafından desteklenen iç işlevleri olarak yazılması gerekir yazılamaz. Diğerleri oluşturulmazken belirli performans duyarlı işlevlerdir. Performans açısından duyarlı işlevleri, iç işlev olarak uygulanmalıdır.

Derleyici tarafından desteklenen yapı içlerini açıklanan [derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md).

## <a name="image-format"></a>Görüntü biçimi

X64 yürütülebilir görüntü biçimi olan je typu PE32 +. Yürütülebilir görüntüler (dll ve exe) 2 gigabayt cinsinden maksimum boyutu için kısıtlı olduğundan statik resim verilerini adreslemek için göreli bir 32-bit öteleme ile adresleme kullanılabilir. Bu veriler, içeri aktarma adres tablosunda, dize sabitleri, statik bir genel veri vb. içerir.

## <a name="see-also"></a>Ayrıca Bkz.

[Çağırma Kuralları](../cpp/calling-conventions.md)