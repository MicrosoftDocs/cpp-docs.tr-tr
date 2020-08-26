---
title: x64 yazılım kuralları
ms.date: 12/17/2018
helpviewer_keywords:
- x64 coding conventions
- Visual C++, x64 calling conventions
ms.assetid: 750f3d97-1706-4840-b2fc-41a007329a08
ms.openlocfilehash: 7c47ec86e80b50bb2b313a2c84a3f375681e2870
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838834"
---
# <a name="x64-software-conventions"></a>x64 yazılım kuralları

Bu bölümde, x86 mimarisinin 64 bitlik uzantısı olan x64 için C++ çağırma kuralı yöntemi açıklanmaktadır.

## <a name="overview-of-x64-calling-conventions"></a>X64 çağırma kurallarına genel bakış

X86 ve x64 arasındaki iki önemli fark, genel kullanıma yönelik olarak 64-bit adresleme özelliğidir ve düz bir 16 64 bit kayıt kümesidir. Genişletilmiş yazmaç kümesi verildiğinde, x64 [__fastcall](../cpp/fastcall.md) çağırma KURALıNı ve RISC tabanlı özel durum işleme modelini kullanır. **`__fastcall`** Kural, ilk dört bağımsız değişken için Yazmaçları ve ek bağımsız değişkenler geçirmek için yığın çerçevesini kullanır. Kullanım kaydetme, yığın parametreleri, dönüş değerleri ve yığın geri sarma dahil olmak üzere x64 çağırma kuralına ilişkin ayrıntılar için bkz. [x64 çağırma kuralı](x64-calling-convention.md).

## <a name="enable-optimization-for-x64"></a>X64 için iyileştirmeyi etkinleştir

Aşağıdaki derleyici seçeneği, uygulamanızı x64 için iyileştirmenize yardımcı olur:

- [/İyileştir (mimari özellikleri için Iyileştirme)](../build/reference/favor-optimize-for-architecture-specifics.md)

## <a name="types-and-storage"></a>Türler ve depolama

Bu bölümde, x64 mimarisine yönelik veri türlerinin numaralandırılması ve depolanması açıklanmaktadır.

### <a name="scalar-types"></a>Skaler türler

Herhangi bir hizalama ile verilere erişmek mümkün olsa da, performans kaybını önlemek için verileri doğal sınırında veya bazı çoklu bir biçimde hizalamak önerilir. Numaralandırmalar sabit tamsayılardır ve 32 bitlik tamsayılar olarak değerlendirilir. Aşağıdaki tabloda, aşağıdaki hizalama değerlerini kullanarak hizalamayla ilgili olarak, veri için tür tanımı ve önerilen depolama alanı açıklanmaktadır:

- Bayt-8 bit

- Sözcük-16 bit

- Doubleword-32 bit

- Quadword-64 bitleri

- Octaword-128 bit

|Skaler tür|C veri türü|Depolama boyutu (bayt)|Önerilen hizalama|
|-|-|-|-|
|**`INT8`**|**`char`**|1|Bayt|
|**`UINT8`**|**`unsigned char`**|1|Bayt|
|**`INT16`**|**`short`**|2|Word|
|**`UINT16`**|**`unsigned short`**|2|Word|
|**`INT32`**|**`int`**, **`long`**|4|Doubleword|
|**`UINT32`**|**`unsigned int`**, **`unsigned long`**|4|Doubleword|
|**`INT64`**|**`__int64`**|8|Dört kelime|
|**`UINT64`**|**`unsigned __int64`**|8|Dört kelime|
|**`FP32`** (tek duyarlık)|**`float`**|4|Doubleword|
|**`FP64`** (çift duyarlık)|**`double`**|8|Dört kelime|
|**`POINTER`**|__\*__|8|Dört kelime|
|**`__m64`**|**`struct __m64`**|8|Dört kelime|
|**`__m128`**|**`struct __m128`**|16|Octaword|

### <a name="aggregates-and-unions"></a>Toplamalar ve birleşimler

Diziler, yapılar ve birleşimler gibi diğer türler, tutarlı toplam ve birleşim depolama ve veri alımı sağlayan daha sıkı hizalama gereksinimlerine sahiptir. Dizi, yapı ve birleşim için tanımlar şunlardır:

- Dizi

   Ardışık veri nesneleri sıralı grubunu içerir. Her nesne bir *öğesi*olarak adlandırılır. Bir dizideki tüm öğeler aynı boyutta ve veri türüne sahiptir.

- Yapı

   Sıralı bir veri nesneleri grubunu içerir. Bir dizinin öğelerinden farklı olarak, bir yapı içindeki veri nesneleri farklı veri türlerine ve boyutlara sahip olabilir. Bir yapıdaki her veri nesnesine *üye*denir.

- Birleşim

   Adlandırılmış üye kümesinden birini tutan nesne. Adlandırılmış küme üyeleri herhangi bir türde olabilir. Bir bileşim için ayrılan depolama alanı, bu birleşimin en büyük üyesi için gereken depolamaya ve hizalama için gereken herhangi bir doldurmaya eşittir.

Aşağıdaki tabloda, birleşimlerin ve yapıların skaler üyeleri için önerilen önerilen hizalama gösterilmektedir.

|Skaler tür|C veri türü|Gerekli hizalama|
|-|-|-|
|**`INT8`**|**`char`**|Bayt|
|**`UINT8`**|**`unsigned char`**|Bayt|
|**`INT16`**|**`short`**|Word|
|**`UINT16`**|**`unsigned short`**|Word|
|**`INT32`**|**`int`**, **`long`**|Doubleword|
|**`UINT32`**|**`unsigned int`**, **`unsigned long`**|Doubleword|
|**`INT64`**|**`__int64`**|Dört kelime|
|**`UINT64`**|**`unsigned __int64`**|Dört kelime|
|**`FP32`** (tek duyarlık)|**`float`**|Doubleword|
|**`FP64`** (çift duyarlık)|**`double`**|Dört kelime|
|**`POINTER`**|<strong>\*</strong>|Dört kelime|
|**`__m64`**|**`struct __m64`**|Dört kelime|
|**`__m128`**|**`struct __m128`**|Octaword|

Aşağıdaki toplam hizalama kuralları geçerlidir:

- Bir dizinin hizalaması, dizinin öğelerinden birinin hizalaması ile aynıdır.

- Bir yapının veya birleşimin başlangıcının hizalaması, herhangi bir üyenin en büyük hizalamasıdır. Yapı veya birleşim içindeki her üyenin, önceki üyeye bağlı olarak örtük iç doldurma gerektirebilecek önceki tabloda tanımlandığı şekilde doğru hizalamasına yerleştirilmesi gerekir.

- Yapı boyutu hizalamasının bir tamsayı katı olmalıdır ve bu, son üyenin sonunda doldurma gerektirebilir. Yapılar ve birleşimler diziler halinde gruplandırılabileceği için bir yapının veya birleşimin her dizi öğesi, daha önce belirlenen uygun hizalamayla başlamalı ve bitmelidir.

- Önceki kuralların çalıştığı sürece verileri, hizalama gereksinimlerinden daha büyük olacak şekilde hizalamak mümkündür.

- Tek bir derleyici, boyut nedenleri için yapının paketlerini ayarlayabilir. Örneğin, [/Zp (struct üye hizalaması)](../build/reference/zp-struct-member-alignment.md) yapıların paketlenmesi için izin verir.

### <a name="examples-of-structure-alignment"></a>Yapı Hizalama Örnekleri

Aşağıdaki dört örnek her biri hizalı bir yapı veya birleşim bildirir ve karşılık gelen rakamlar, bu yapının veya birleşimin bellekteki yerleşimini gösterir. Bir şekildeki her sütun, belleğin bir baytını temsil eder ve sütundaki sayı bu baytın ötelemesi olduğunu gösterir. Her bir şeklin ikinci satırındaki ad, bildirimdeki bir değişkenin adına karşılık gelir. Gölgeli sütunlarda, belirtilen hizalamayı elde etmek için gereken doldurma belirtilir.

#### <a name="example-1"></a>Örnek 1

```C
// Total size = 2 bytes, alignment = 2 bytes (word).

_declspec(align(2)) struct {
    short a;      // +0; size = 2 bytes
}
```

![AMD dönüştürme örnek 1 yapı düzeni](../build/media/vcamd_conv_ex_1_block.png "AMD dönüştürme örnek 1 yapı düzeni")

#### <a name="example-2"></a>Örnek 2

```C
// Total size = 24 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) struct {
    int a;       // +0; size = 4 bytes
    double b;    // +8; size = 8 bytes
    short c;     // +16; size = 2 bytes
}
```

![AMD dönüştürme örneği 2 yapı düzeni](../build/media/vcamd_conv_ex_2_block.png "AMD dönüştürme örneği 2 yapı düzeni")

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

![AMD dönüştürme örneği 2 yapı düzeni](../build/media/vcamd_conv_ex_3_block.png "AMD dönüştürme örneği 2 yapı düzeni")

#### <a name="example-4"></a>Örnek 4

```C
// Total size = 8 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) union {
    char *p;      // +0; size = 8 bytes
    short s;      // +0; size = 2 bytes
    long l;       // +0; size = 4 bytes
}
```

![AMD dönüştürme örneği 4 UNION layouit](../build/media/vcamd_conv_ex_4_block.png "AMD dönüştürme örneği 4 UNION layouit")

### <a name="bitfields"></a>Bit Alanları

Yapı bit alanları 64 bitle sınırlıdır ve işaretli int, işaretsiz int, int64 veya işaretsiz int64 türünde olabilir. Tür sınırını gösteren bit alanları, bit alanından 'ı sonraki tür hizalamasına hizalamak için bitleri atlar. Örneğin, tamsayı biti alanları 32 bitlik bir boundcross olamaz.

### <a name="conflicts-with-the-x86-compiler"></a>X86 derleyicisi ile çakışmalar

Bir uygulamayı derlemek için x86 derleyicisini kullandığınızda 4 bayttan büyük olan veri türleri yığına otomatik olarak hizalanmaz. X86 derleyicisi mimarisi 4 baytlık hizalanmış bir yığın olduğundan, 4 bayttan daha büyük bir değer, örneğin 64 bitlik bir tamsayı, otomatik olarak 8 baytlık bir adrese hizalanamaz.

Hizalanmamış verilerle çalışmanın iki etkileri vardır.

- Hizalanmamış konumlara erişim, hizalanmış konumlara erişime göre daha uzun sürebilir.

- Hizalanmamış konumlar, birbirine kilitli işlemlerde kullanılamaz.

Daha sıkı hizalama gerekiyorsa, `__declspec(align(N))` değişken bildirimlerinde kullanın. Bu, derleyicinin bir yığını belirtimlerinizi karşılayacak şekilde dinamik olarak hizalanmasına neden olur. Ancak, yığın çalışma zamanında dinamik olarak ayarlanarak uygulamanızın daha yavaş yürütülmesine neden olabilir.

## <a name="register-usage"></a>Kullanımı Kaydet

X64 mimarisi, 16 genel amaçlı kayıt (bundan sonra tamsayı Yazmaçları olarak anılacaktır) ve kayan nokta kullanımı için 16 XMM/ıMM yazmaçlarının kullanılmasını sağlar. Geçici Yazmaçları, çağıran tarafından bir çağrıda yok edilmek üzere çağrı yapan karalama yazmalardır. Kalıcı yazmaçları, değerlerini bir işlev çağrısında bekletmek için gereklidir ve kullanılıyorsa aranan tarafından kaydedilmesi gerekir.

### <a name="register-volatility-and-preservation"></a>Vola, ve koruma kaydetme

Aşağıdaki tabloda, her kaydın işlev çağrıları genelinde nasıl kullanıldığı açıklanmaktadır:

|Kaydol|Durum|Kullanın|
|-|-|-|
|RAX|Katılımcıdan|Dönüş değeri kaydı|
|RCX|Katılımcıdan|İlk tamsayı bağımsız değişkeni|
|RDX|Katılımcıdan|İkinci tamsayı bağımsız değişkeni|
|R8|Katılımcıdan|Üçüncü tamsayı bağımsız değişkeni|
|R9|Katılımcıdan|Dördüncü tamsayı bağımsız değişkeni|
|R10:R11|Katılımcıdan|Çağıranın gerektirdiği şekilde korunması gerekir; syscall/sysret yönergelerinde kullanılır|
|R12:R15|X|Çağrılan tarafından korunması gerekir|
|RDı|X|Çağrılan tarafından korunması gerekir|
|RSı|X|Çağrılan tarafından korunması gerekir|
|RBX|X|Çağrılan tarafından korunması gerekir|
|RBP|X|, Bir çerçeve işaretçisi olarak kullanılabilir; çağrılan tarafından korunması gerekir|
|RSP|X|Yığın işaretçisi|
|XMM0, YMM0 ILA|Katılımcıdan|İlk FP bağımsız değişkeni; İlk vektör türü bağımsız değişken **`__vectorcall`** kullanıldığında|
|XMM1, YMM1|Katılımcıdan|İkinci FP bağımsız değişkeni; kullanıldığında ikinci vektör türü bağımsız değişken **`__vectorcall`**|
|XMM2, YMM2|Katılımcıdan|Üçüncü FP bağımsız değişkeni; kullanıldığında üçüncü vektör türü bağımsız değişkeni **`__vectorcall`**|
|XMM3, YMM3|Katılımcıdan|Dördüncü FP bağımsız değişkeni; kullanıldığında dördüncü vektör türü bağımsız değişkeni **`__vectorcall`**|
|XMM4, YMM4|Katılımcıdan|Çağıranın gerektirdiği şekilde korunması gerekir; kullanıldığında beşinci vektör türü bağımsız değişkeni **`__vectorcall`**|
|XMM5, YMM5 ARASıNDA|Katılımcıdan|Çağıranın gerektirdiği şekilde korunması gerekir; kullanıldığı zaman altıncı vektör türü bağımsız değişkeni **`__vectorcall`**|
|XMM6:XMM15, YMM6:YMM15|Kalıcı olmayan (XMM), geçici (en büyük yarı yarım yarısı)|Aranan tarafından korunması gerekir. -MM kayıtları, çağıran tarafından gerektiği şekilde korunmalıdır.|

İşlev çıkışta ve C çalışma zamanı kitaplığı çağrılarına ve Windows Sistem çağrılarına işlev girdisinde, CPU bayrakları kaydındaki yön bayrağının temizlenmesi beklenir.

## <a name="stack-usage"></a>Yığın kullanımı

X64 üzerindeki yığın ayırma, hizalama, işlev türleri ve yığın çerçeveleri hakkında daha fazla bilgi için bkz. [x64 Stack kullanımı](stack-usage.md).

## <a name="prolog-and-epilog"></a>Giriş ve bitiş

Yığın alanı ayıran, diğer işlevleri çağıran, kalıcı kayıtları kaydeden veya özel durum işlemenin kullanıldığı her işlev, adres limitlerinin ilgili işlev tablosu girdisiyle ilişkili geriye doğru izleme verilerinde açıklanan bir giriş ve her çıkışta bir işleve çıkış olması gerekir. X64 üzerindeki gerekli giriş ve bitiş kodu hakkında daha fazla bilgi için bkz. [x64 giriş ve bitiş](prolog-and-epilog.md).

## <a name="x64-exception-handling"></a>x64 özel durum işleme

X64 üzerinde yapılandırılmış özel durum işleme ve C++ özel durum işleme davranışını uygulamak için kullanılan kurallar ve veri yapıları hakkında daha fazla bilgi için, bkz. [x64 özel durum işleme](exception-handling-x64.md).

## <a name="intrinsics-and-inline-assembly"></a>İç bilgiler ve satır içi derleme

X64 derleyicisi kısıtlamalarından biri, satır içi assembler desteğine sahip değildir. Bu, C veya C++ dilinde yazılamayacağını gösteren işlevlerin alt yordamlar olarak yazılması ya da derleyici tarafından desteklenen iç işlevler olması anlamına gelir. Bazı işlevler, diğerleri olmasa da performansa duyarlıdır. Performansa duyarlı işlevler, iç işlevler olarak uygulanmalıdır.

Derleyici tarafından desteklenen iç bilgiler, [derleyici iç](../intrinsics/compiler-intrinsics.md)bilgileri içinde açıklanmıştır.

## <a name="image-format"></a>Görüntü biçimi

X64 yürütülebilir görüntü biçimi PE32 + ' dır. Yürütülebilir görüntüler (hem dll 'Ler hem de exe 'Ler) en yüksek boyut olan 2 gigabayt ile kısıtlanır, bu nedenle 32 bitlik bir yer değiştirme ile göreli adresleme statik görüntü verilerini adreslemek için kullanılabilir. Bu veriler içeri aktarma adresi tablosunu, dize sabitlerini, statik genel verileri vb. içerir.

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma kuralları](../cpp/calling-conventions.md)
