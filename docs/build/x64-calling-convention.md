---
title: çağırma kuralı x64
description: Varsayılan x64 ABI çağrı kuralı ayrıntıları.
ms.date: 12/17/2018
ms.assetid: 41ca3554-b2e3-4868-9a84-f1b46e6e21d9
ms.openlocfilehash: 02bf4719766366049b600b148ad88fc238f4e54e
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415792"
---
# <a name="x64-calling-convention"></a>çağırma kuralı x64

Bu bölümde standart süreçler ve içinde x64 (çağrılan) başka bir işleve çağrı yapmak için bir işlev (arayan) kullanan kurallar açıklanmaktadır kod.

## <a name="calling-convention-defaults"></a>Çağırma kuralı Varsayılanları

Varsayılan olarak x64 dört kaydını bir hızlı arama çağırma kuralı tarafından uygulama ikili arabirimi (ABI) kullanır. Çağrı yığınındaki bir gölge depolama için bu kayıtları kaydetmek çağrılanlar olarak ayrılmış alanı. Bir işlev çağrısı için bağımsız değişkenler ve bu bağımsız değişkenler için kullanılan kasalar arasında katı bire bir ilişkisi yoktur. 8 baytlık sığmayan ya da 1, 2, 4 veya 8 bayt değil herhangi bir bağımsız değişken başvuruyla geçirildi gerekir. Tek bir bağımsız değişken hiçbir zaman birden çok kayıt arasında yayılır. Yığın x87 kaydetme kullanılmayan ve Aranan tarafından kullanılabilir, ancak işlev çağrıları arasında geçici olarak düşünülmelidir. Tüm kayan nokta işlemleri gerçekleştirilir XMM 16 kullanarak kaydeder. Tamsayı bağımsız değişkenleri RCX, RDX, R8 ve R9 yazmaçlarında geçirilir. Kayan nokta bağımsız değişkenler XMM0L, XMM1L, XMM2L ve XMM3L geçirilir. 16 bayt bağımsız değişkenleri başvuruya göre iletilir. Parametre geçirme ayrıntılı olarak açıklanan [parametre geçirerek](#parameter-passing). Bu kayıtları yanı sıra RAX'daki, R10 R11 XMM4 ve XMM5 geçici olarak kabul edilir. Geçici olmayan diğer tüm kayıtlar. YAZMAÇ kullanımı ayrıntılı olarak belgelenmiştir [kaydetme kullanım](../build/x64-software-conventions.md#register-usage) ve [çağıran/çağrılan kaydedilmiş kayıtları](#callercallee-saved-registers).

Prototipi oluşturulmuş işlevler için bağımsız değişkenlerin tümü geçirilmeden önce beklenen çağrılan türleri dönüştürülür. Çağıranın alanı parametreleri için çağrılanın sorumlu olan ve çağrılan diğer birçok bir parametre almasa bile her zaman dört kayıt parametreleri depolamak için yeterli alan ayırmanız gerekir. Bu kural, prototipi oluşturulmamış C dili işlevler ve vararg C/C++ işlevleri için destek basitleştirir. Vararg veya prototipi oluşturulmamış işlevler için herhangi bir kayan nokta değerleri gereken yinelenen karşılık gelen genel amaçlı kayıt defterinde. Gölge depolama sonra çağrıdan önce ilk dört ötesinde herhangi bir parametre yığında depolanmış olması gerekir. Vararg işlev ayrıntıları bulunabilir [Varargs](#varargs). Prototipi oluşturulmamış işlevi bilgileri ayrıntılı olarak [prototipi oluşturulmamış işlevler](#unprototyped-functions).

## <a name="alignment"></a>Hizalama

Çoğu yapıları, doğal hizalama hizalanır. Birincil özel durumlar ve yığın işaretçisi olan ve `malloc` veya `alloca` bellek, performansa yardımcı olmak için 16 bayt ile hizalanır. 16 bayt üzerindeki hizalama el ile yapılması gerekir, ancak 16 bayt XMM işlemleri için ortak bir hizalama boyutu olduğundan, bu değer için çoğu kod çalışması gerekir. Yapı düzeni ve hizalama hakkında daha fazla bilgi için bkz: [türler ve depolama](../build/x64-software-conventions.md#types-and-storage). Yığın düzeni hakkında daha fazla bilgi için bkz. [x64 yığın kullanımı](../build/stack-usage.md).

## <a name="unwindability"></a>Unwindability

Yaprak, geçici olmayan bir kaydı değiştirme işlevleri işlevlerdir. Bir yaprak olmayan işlev geçici olmayan RSP, örneğin, bir işlev çağırmanın veya yerel değişkenler için ek yığın alanı ayırma değişebilir. Bir özel durum işlendiğinde geçici olmayan kayıtları kurtarmak için yaprak olmayan işlevler düzgün rastgele bir yönerge işlevi geriye doğru izleme işlemini açıklamaktadır statik veriler ile Açıklama eklenmelidir. Bu veri olarak depolanır *pdata*, veya sırayla başvuran yordamı veri *xdata*, veri işleme özel durum. Xdata geriye doğru izleme bilgileri içerir ve ek pdata veya bir özel durum işleyici işlevine işaret edebilir. Açıklanabilmeleri başlangıçları xdata içinde düzgün bir şekilde açıklandığı gibi olması için ileri derecede kısıtlı. Yığın işaretçisi yaprak işlevlerinde dışında bir bitiş veya giriş parçası olmayan kod herhangi bir bölgedeki 16 bayt hizalı olmalıdır. Yaprak işlevleri pdata ve xdata gerekli değildir, dolayısıyla yalnızca bir dönüş benzetimini yaparak sapmasına. İşlev açıklanabilmeleri ve sonuç uygun yapısı hakkında daha fazla ayrıntı için bkz: [x64 giriş ve bitiş](../build/prolog-and-epilog.md). Özel durum işleme ve özel durum işleme ve pdata xdata ve geriye doğru izleme hakkında daha fazla bilgi için bkz. [x64 özel durum işleme](../build/exception-handling-x64.md).

## <a name="parameter-passing"></a>Parametre geçirme

İlk dört tamsayı bağımsız değişkeni kayıtlara geçirilir. Tamsayı değerleri sırayla soldan sağa RCX, RDX, R8 ve R9, sırasıyla geçirilir. Bağımsız değişkenler 5 ve üzeri yığına geçirilir. Aranan üst bitlerini yoksay ve yalnızca gerekli kayıt bölümüne erişmek için kayıtlara sağa yaslanmış tüm bağımsız değişkenler.

Tüm kayan nokta ve çift duyarlıklı bağımsız değişkenler ilk dört parametrelerinde konumuna bağlı olarak XMM0 - XMM3, geçirilir. RCX, RDX, R8 ve R9 normalde bu konumları için kullanılan tamsayı kayıtlara göz ardı edilir, söz konusu olduğunda varargs bağımsız değişkenler hariç. Ayrıntılar için bkz [Varargs](#varargs). Benzer şekilde, XMM0 - XMM3 karşılık gelen bağımsız değişken bir tamsayı veya işaretçi türünde olduğunda kayıtlara göz ardı edilir.

[__m128](../cpp/m128.md) türleri, diziler ve dizeleri hiçbir zaman hemen değerine göre geçirilir. Bunun yerine, bir işaretçi çağırıcı tarafından ayrılan bellek geçirilir. Aynı boyutta tamsayı değilmiş gibi yapılar ve birleşimler boyutu 8, 16, 32 veya 64 bit m64 türleri ve geçirilir. Yapılar veya diğer boyutlarda birleşimler çağırıcı tarafından ayrılan bellek işaretçisi olarak geçirilir. Bir işaretçi olarak geçirilen bu toplam değer türleri için de dahil olmak üzere \__m128, arayana ayrılan geçici bellek 16 bayt hizalı olmalıdır.

Yığın alanı ayırmayın ve diğer işlevleri iç işlevleri, diğer geçici kayıtları bazen ek yazmaç bağımsız değişkenleri geçirmek için kullanın. Bu iyileştirme derleyici ve iç işlev uygulaması arasında sıkı bağlama tarafından gerçekleştirilir.

Gerekirse, gölge alanına kayıt parametreleri dökme için Aranan sorumludur.

Parametrelerin nasıl geçirildiğini aşağıdaki tabloda özetlenmiştir:

|Parametre türü|Nasıl geçti|
|--------------------|----------------|
|Kayan nokta|İlk 4 parametre - XMM0 ila XMM3. Diğerleri, yığın olarak geçirilir.|
|Tamsayı|İlk 4 parametre - RCX, RDX, R8'de, R9. Diğerleri, yığın olarak geçirilir.|
|Toplamlar (8, 16, 32 veya 64 bit) ve __m64|İlk 4 parametre - RCX, RDX, R8'de, R9. Diğerleri, yığın olarak geçirilir.|
|Toplamlar (diğer)|İşaretçi tarafından. İlk 4 parametre RCX, RDX, R8 ve R9 işaretçi olarak geçirildi|
|__m128|İşaretçi tarafından. İlk 4 parametre RCX, RDX, R8 ve R9 işaretçi olarak geçirildi|

### <a name="example-of-argument-passing-1---all-integers"></a>Bağımsız değişken geçirme 1 - tüm tamsayıların örneği

```cpp
func1(int a, int b, int c, int d, int e);
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack
```

### <a name="example-of-argument-passing-2---all-floats"></a>Bağımsız değişken 2 - tüm float'lar geçirme örneği

```cpp
func2(float a, double b, float c, double d, float e);
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack
```

### <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>Bağımsız değişken 3 - karma tamsayılar ve float'lar geçirme örneği

```cpp
func3(int a, double b, int c, float d);
// a in RCX, b in XMM1, c in R8, d in XMM3
```

### <a name="example-of-argument-passing-4--m64-m128-and-aggregates"></a>Bağımsız değişken geçirme 4 örneği-__m64, \__m128 ve toplamlar

```cpp
func4(__m64 a, _m128 b, struct c, float d);
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3
```

## <a name="varargs"></a>Varargs

Parametreler (örneğin, üç nokta bağımsız değişkenler) varargs geçirilir, ardından kuralı geçirme normal kayıt parametresi, beşinci ve sonraki bağımsız değişkenler yığına taşma dahil olmak üzere uygular. Bu çağrıyı yapanın adresleri alınıp döküm bağımsız değişkenlere sorumluluğundadır. Aranan değer tamsayı kayıtlara bekliyor durumunda yalnızca kayan nokta değerleri için hem tamsayı kaydı ve kayan nokta kaydı değer içermesi gerekir.

## <a name="unprototyped-functions"></a>Prototipi oluşturulmamış İşlevler

Değil tam prototipi oluşturulmuş işlevler için çağırana tamsayı değerleri tamsayı ve kayan nokta değerleri çift duyarlık olarak geçirir. Aranan değer tamsayı kayıtlara bekliyor durumunda yalnızca kayan nokta değerleri için hem tamsayı kaydı ve kayan nokta kaydı float değeri içerir.

```cpp
func1();
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7
   func1(2, 1.0, 7);
}
```

## <a name="return-values"></a>Döndürülen değerler

64 bit'e sığabilen skaler bir dönüş değeri dahil RAX üzerinden döndürülür; Bu, m64 türleri içerir. Float, double ve vektör türleri gibi dahil olmayan skaler türleri [__m128](../cpp/m128.md), [__m128i](../cpp/m128i.md), [__m128d](../cpp/m128d.md) XMM0'da döndürülür. Kullanılmayan RAX'daki veya XMM0 döndürülen değerdeki bitler durumu tanımsızdır.

Kullanıcı tanımlı türler genel işlevleri ve statik üye işlevleri, değere göre döndürülebilir. Kullanıcı tanımlı bir tür RAX'daki değer döndürmek için 1, 2, 4, 8, 16, 32 veya 64 bit uzunluğu olmalıdır. Ayrıca, kullanıcı tanımlı oluşturucusu yok, yok Edicisi veya kopya atama işleci olmalıdır; hiçbir özel veya korumalı statik olmayan veri üyesi; hiçbir başvuru türü statik olmayan veri üyesi; temel olmayan sınıflar; sanal işlev yok; ve ayrıca bu gereksinimleri karşılamayan veri üye yok. (Bu aslında C ++ 03 tanımı, POD türü. C ++ 11'de standart tanımı değiştiğinden, kullanımı önerilmemektedir `std::is_pod` bu test için.) Aksi takdirde, arayanın bellek ayırma ve işaretçi dönüş değeri için ilk bağımsız değişken olarak geçirme sorumluluğu üstlenir. İzleyen bağımsız değişkenler, tek bir bağımsız değişken sağa doğru kayar. Aynı işaretçi RAX'daki Aranan tarafından iade edilmesi gerekir.

Bu örnekler, parametreler ve dönüş değerleri için işlevleri belirtilen bildirimleri ile nasıl geçirilir gösterir:

### <a name="example-of-return-value-1---64-bit-result"></a>Dönüş değeri 1 - 64 bit sonuç örneği

```Output
__int64 func1(int a, float b, int c, int d, int e);
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,
// callee returns __int64 result in RAX.
```

### <a name="example-of-return-value-2---128-bit-result"></a>Dönüş değeri 2 - 128-bit sonuç örneği

```Output
__m128 func2(float a, double b, int c, __m64 d);
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,
// callee returns __m128 result in XMM0.
```

### <a name="example-of-return-value-3---user-type-result-by-pointer"></a>Dönüş değeri 3 - işaretçi tarafından kullanıcı türü sonuç örneği

```Output
struct Struct1 {
   int j, k, l;    // Struct1 exceeds 64 bits.
};
Struct1 func3(int a, double b, int c, float d);
// Caller allocates memory for Struct1 returned and passes pointer in RCX,
// a in RDX, b in XMM2, c in R9, d pushed on the stack;
// callee returns pointer to Struct1 result in RAX.
```

### <a name="example-of-return-value-4---user-type-result-by-value"></a>Dönüş değeri 4 - değere göre kullanıcı türü sonuç örneği

```Output
struct Struct2 {
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.
};
Struct2 func4(int a, double b, int c, float d);
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;
// callee returns Struct2 result by value in RAX.
```

## <a name="callercallee-saved-registers"></a>Çağıran/Çağrılan Kaydedilmiş Yazmaçlar

İşlev çağrılarında RAX'daki, RCX, RDX, R8, R9, R10, R11 geçici olarak kabul edilir ve dikkate alınması gereken kayıtları yok (sürece Aksi durumda güvenlik-kanıtlanabilir bütün program iyileştirmesi gibi analiz tarafından).

Yazmaçları RBX, RBP, RDI, RSI, RSP, R12, R13, R14 ve R15 kayıtları kalıcı olarak kabul edilir ve kaydedilmesi gerekir ve bir işlev tarafından geri, bunları kullanır.

## <a name="function-pointers"></a>İşlev işaretçileri

İşlev işaretçileri, yalnızca ilgili işlevi etiketini işaretçileri olan. İşlev işaretçileri için içeriği (TOC) gereksinimleri tablosu vardır.

## <a name="floating-point-support-for-older-code"></a>Eski kod için kayan nokta desteği

Kayan nokta yığın kayıtları (MM0-MM7/ST0-ST7) ve MMX bağlam geçişleri boyunca korunur. Bu kayıtlar için açık bir çağrı kuralı yok. Bu yazmaçların kullanımı kesinlikle çekirdek modu kodu içinde kullanılamaz.

## <a name="fpcsr"></a>FpCsr

Kayıt durumu x87 yöntemlerine FPU denetim sözcüğü. Çağırma kuralı, bu kayıt kalıcı olmasını belirler.

Program yürütmesini x87 FPU denetim sözcük kaydı başlangıcında standart aşağıdaki değerlere ayarlanır:

| Kayıt\[BITS] | Ayar |
|-|-|
| FPCSR\[0:6] | Özel durum tüm 1 (maskelenmiş tüm özel durumlar) maskeleri |
| FPCSR\[7] | Ayrılmış - 0 |
| FPCSR\[8:9] | Duyarlık denetimi - 10B (çift duyarlık) |
| FPCSR\[10:11] | Yuvarlama denetimi - 0 (YUVARLA en yakın) |
| FPCSR\[12] | Sonsuzluk denetimi - 0 (kullanılmaz) |

Herhangi bir alanı olamayan FPCSR içinde değiştiren bir çağrılan çağırana döndürülmeden önce bunları geri yüklemelisiniz. Ayrıca, bu alanların değiştirdiği bir çağıranın bunları standart değerlerine sözleşmesiyle çağrılan değiştirilen değerlerin bekliyor sürece çağrılan çağırmadan önce geri yüklemeniz gerekir.

Denetim bayrakları, olmayan-volatility hakkında kuralları iki istisna mevcuttur:

1. Verilen işlevin amacı belgelenmiş geçici olamayan FpCsr değiştirmek için olduğu işlevlerde işaretler.

1. Bu kural ihlalini burada bu kurallar, örneğin, tüm program Analizi ile ihlal olmayan bir program gibi davranır bir programda sonuçları kanıtlanabilir geldiğinde düzeltin.

## <a name="mxcsr"></a>MxCsr

Kayıt durumu MxCsr de içerir. Çağırma kuralı bu kayıt, geçici ve kalıcı bir bölümü böler. Altı durumu bayrakları MXCSR geçici bölümü oluşan\[0:5], while MXCSR kasanızın geri kalanı\[6:15], kalıcı olarak kabul edilir.

Kalıcı bölümü, program yürütme başlangıcında standart aşağıdaki değerlere ayarlanır:

| Kayıt\[BITS] | Ayar |
|-|-|
| MXCSR\[6] | Denormals sıfır - 0 olan |
| MXCSR\[7:12] | Özel durum tüm 1 (maskelenmiş tüm özel durumlar) maskeleri |
| MXCSR\[13:14] | Yuvarlama denetimi - 0 (YUVARLA en yakın) |
| MXCSR\[15] | Sıfıra maskelenmiş yetersiz kalması - 0 (Kapalı) için temizleme |

Kalıcı alanlar MXCSR içinde değiştiren bir çağrılan çağırana döndürülmeden önce bunları geri yüklemelisiniz. Ayrıca, bu alanların değiştirdiği bir çağıranın bunları standart değerlerine sözleşmesiyle çağrılan değiştirilen değerlerin bekliyor sürece çağrılan çağırmadan önce geri yüklemeniz gerekir.

Denetim bayrakları, olmayan-volatility hakkında kuralları iki istisna mevcuttur:

- Kalıcı MxCsr değiştirmek için verilen işlevi belgelenen amacı olduğu işlevlerde işaretler.

- Bu kural ihlalini burada bu kurallar, örneğin, tüm program Analizi ile ihlal olmayan bir program gibi davranır bir programda sonuçları kanıtlanabilir geldiğinde düzeltin.

Hiçbir varsayım özellikle bir işlevin belgelerinde açıklanan sürece MXCSR geçici kısmı bir işlev sınırı arasında durumuyla ilgili yapılabilir.

## <a name="setjmplongjmp"></a>setjmp/longjmp

Setjmpex.h veya setjmp.h eklediğinizde, tüm çağrılar [setjmp](../c-runtime-library/reference/setjmp.md) veya [longjmp](../c-runtime-library/reference/longjmp.md) neden yıkıcıları bir geriye doğru ve `__finally` çağırır.  Bu x86, burada dahil olmak üzere setjmp.h sonuçlanıyor farklıdır `__finally` yan tümceleri ve yıkıcı çağrılmasını değil.

Bir çağrı `setjmp` geçerli yığın işaretçisi, geçici olmayan kayıtlar ve MxCsr kayıtları korur.  Çağrılar `longjmp` dönün en son `setjmp` site ve sıfırlar yığın işaretçisi, geçici olmayan kayıtlar ve MxCsr kaydeder, duruma göre en güncel korunduğu çağırmak `setjmp` çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[x64 yazılım kuralları](../build/x64-software-conventions.md)
