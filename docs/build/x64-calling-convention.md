---
title: x64 çağırma kuralı
description: Varsayılan x64 ABI arama kuralının ayrıntıları.
ms.date: 12/17/2018
ms.assetid: 41ca3554-b2e3-4868-9a84-f1b46e6e21d9
ms.openlocfilehash: caf22172ea5e9c20280bce8e508d72fd30c00c5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335125"
---
# <a name="x64-calling-convention"></a>x64 çağırma kuralı

Bu bölümde, bir işlevin (arayan) x64 kodunda başka bir işleve (callee) çağrı yapmak için kullandığı standart işlemler ve kurallar açıklanmaktadır.

## <a name="calling-convention-defaults"></a>Çağırma kuralı varsayılanları

x64 Uygulama İkili Arabirimi (ABI), varsayılan olarak dört kayıtlı hızlı arama çağrı kuralı kullanır. Alan çağrı yığınına, bu kayıtları kaydetmek için çağrı verenler için gölge deposu olarak ayrılır. Bir işlev çağrısıiçin bağımsız değişkenler ve bu bağımsız değişkenler için kullanılan kayıtlar arasında sıkı birbire bir yazışma var. 8 bayta sığmayacak veya 1, 2, 4 veya 8 bayt olmayan tüm bağımsız değişkenler başvuru yla geçirilmelidir. Tek bir bağımsız değişken hiçbir zaman birden çok kayıt ta yayılmaz. x87 kayıt yığını kullanılmaz ve callee tarafından kullanılabilir, ancak işlev çağrıları arasında geçici olarak kabul edilmelidir. Tüm kayan nokta işlemleri 16 XMM kayıtları kullanılarak yapılır. Karşıcı bağımsız değişkenler RCX, RDX, R8 ve R9 kayıtlarında geçirilir. Kayan nokta bağımsız değişkenleri XMM0L, XMM1L, XMM2L ve XMM3L'de geçirilir. 16 bayt bağımsız değişkenler başvuru ile geçirilir. Parametre [geçişi, Parametre Geçişi'nde](#parameter-passing)ayrıntılı olarak açıklanmıştır. Bu kayıtlara ek olarak, RAX, R10, R11, XMM4 ve XMM5 geçici olarak kabul edilir. Diğer tüm kayıtlar geçici değildir. [Kayıt kullanımı, Register Kullanımı](../build/x64-software-conventions.md#register-usage) ve [Arayan/Callee Kayıtlı Kayıtlar'da](#callercallee-saved-registers)ayrıntılı olarak belgelenmiştir.

Prototip işlevleri için, tüm bağımsız değişkenler geçmeden önce beklenen çağrı türlerine dönüştürülür. Arayan, parametreler için alan ayırmakla yükümlüdür ve callee bu kadar çok parametre almasa bile, her zaman dört kayıt parametresini depolamak için yeterli alan ayırmalıdır. Bu kural, prototiplenmemiş C dili işlevleri ve vararg C/C++ işlevleri için desteği basitleştirir. Vararg veya prototiplenmemiş işlevler için, kayan nokta değerlerinin ilgili genel amaçlı kayıtta çoğaltılması gerekir. İlk dört ötesindeki parametreler, aramadan önce gölge deposundan sonra yığında depolanmalıdır. Vararg fonksiyon ayrıntıları [Varargs](#varargs)bulunabilir. Prototipsiz işlev bilgileri [Prototipsiz Fonksiyonlar'da](#unprototyped-functions)ayrıntılı olarak açıklanır.

## <a name="alignment"></a>Hizalama

Çoğu yapı doğal hizalarına göre hizalanır. Birincil özel durumlar, performansa `malloc` `alloca` yardımcı olmak için 16 bayt'a hizalanmış yığın işaretçisi ve bellektir. 16 baytın üzerindeki hizalama el ile yapılmalıdır, ancak 16 bayt XMM işlemleri için ortak bir hizalama boyutu olduğundan, bu değer çoğu kod için çalışmalıdır. Yapı düzeni ve hizalama hakkında daha fazla bilgi için [Bkz. Türleri ve Depolama.](../build/x64-software-conventions.md#types-and-storage) Yığın düzeni hakkında bilgi için [bkz.](../build/stack-usage.md)

## <a name="unwindability"></a>Gevşeme

Yaprak işlevleri, geçici olmayan kayıtları değiştirmeyen işlevlerdir. Yaprak sız bir işlev, örneğin, bir işlevi çağırarak veya yerel değişkenler için ek yığın alanı ayırarak geçici olmayan RSP'yi değiştirebilir. Bir özel durum işlendiğinde geçici olmayan kayıtları kurtarmak için, yaprak olmayan işlevler, rasgele bir yönergede işlevin nasıl düzgün bir şekilde gevşeteceğini açıklayan statik verilerle ek açıklama lı olmalıdır. Bu veriler *pdata*veya yordam verileri olarak depolanır, bu da *xdata*,özel durum işleme verileri anlamına gelir. Xdata gevşeme bilgilerini içerir ve ek pdata veya bir özel durum işleyicisi işlevine işaret edebilir. Prologs ve epilogs xdata düzgün açıklanabilir böylece son derece sınırlıdır. Yığın işaretçisi, yaprak işlevleri dışında, bir epilog veya prolog parçası olmayan herhangi bir kod bölgesinde 16 bayt olarak hizalanmalıdır. Yaprak işlevleri sadece bir dönüş simüle ederek çözülebilir, bu nedenle pdata ve xdata gerekli değildir. Fonksiyon prologları ve epilogların uygun yapısı hakkında ayrıntılı bilgi için [x64 prolog ve epilog'a](../build/prolog-and-epilog.md)bakın. Özel durum işleme ve pdata ve xdata'nın özel durum işleme ve gevşemesi hakkında daha fazla bilgi için [bkz.](../build/exception-handling-x64.md)

## <a name="parameter-passing"></a>Parametre geçişi

İlk dört karşım bağımsız değişkeni kayıtlarda geçirilir. Tamsayı değerleri sırasıyla RCX, RDX, R8 ve R9'da soldan sağa sırayla geçirilir. Bağımsız değişkenler beş ve daha yüksek yığına aktarılır. Tüm bağımsız değişkenler kayıtlarda haklıdır, böylece callee kaydın üst bitlerini yoksayabilir ve yalnızca kaydın gerekli kısmına erişebilir.

İlk dört parametredeki kayan nokta ve çift duyarlıklı bağımsız değişkenler konuma bağlı olarak XMM0 - XMM3'te geçirilir. Tamsayı, varargs bağımsız değişkenleri dışında normalde bu konumlar için kullanılacak olan RCX, RDX, R8 ve R9'u kaydeder. Ayrıntılar için Bkz. [Varargs.](#varargs) Benzer şekilde, karşılık gelen bağımsız değişken bir sonda veya işaretçi türü olduğunda XMM0 - XMM3 kayıtları yoksayılır.

[__m128](../cpp/m128.md) türleri, diziler ve dizeleri hemen değer tarafından geçirilir asla. Bunun yerine, bir işaretçi arayan tarafından ayrılan belleğe geçirilir. 8, 16, 32 veya 64 bit ve __m64 türdeki yapı ve birlikler, aynı boyuttaki tamsayılar gibi geçirilir. Diğer boyutlardaki structs veya birliş, arayan tarafından ayrılan belleğe işaretçi olarak geçirilir. _m128 da dahil \_olmak üzere işaretçi olarak geçirilen bu toplam türleri için, arayanın ayıran geçici belleği 16 bayt hizalanmış olmalıdır.

Yığın alanı ayırmayen ve diğer işlevleri çağırmayen içsel işlevler, bazen ek kayıt bağımsız değişkenlerini geçmek için diğer geçici kayıtları kullanır. Bu optimizasyon derleyici ve içsel fonksiyon uygulaması arasındaki sıkı bağlama ile mümkün hale getirilir.

Callee gerekirse kendi gölge uzaya kayıt parametreleri damping sorumludur.

Aşağıdaki tabloparametrelerin nasıl geçirildiğini özetler:

|Parametre türü|Nasıl geçti|
|--------------------|----------------|
|Kayan nokta|İlk 4 parametre - XMM0 ile XMM3. Diğerleri yığın geçti.|
|Tamsayı|İlk 4 parametre - RCX, RDX, R8, R9. Diğerleri yığın geçti.|
|Toplamlar (8, 16, 32 veya 64 bit) ve __m64|İlk 4 parametre - RCX, RDX, R8, R9. Diğerleri yığın geçti.|
|Toplamlar (diğer)|İşaretçiye göre. RCX, RDX, R8 ve R9'da işaretçi olarak geçirilen ilk 4 parametre|
|__m128|İşaretçiye göre. RCX, RDX, R8 ve R9'da işaretçi olarak geçirilen ilk 4 parametre|

### <a name="example-of-argument-passing-1---all-integers"></a>1 geçen bağımsız değişken örneği - tüm tüm tüm insalar

```cpp
func1(int a, int b, int c, int d, int e);
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack
```

### <a name="example-of-argument-passing-2---all-floats"></a>2 geçen argüman örneği - tüm yüzer

```cpp
func2(float a, double b, float c, double d, float e);
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack
```

### <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>3 geçen argüman örneği - karışık ints ve floats

```cpp
func3(int a, double b, int c, float d);
// a in RCX, b in XMM1, c in R8, d in XMM3
```

### <a name="example-of-argument-passing-4--__m64-__m128-and-aggregates"></a>4 -__m64, \__m128 ve toplamları geçen bağımsız değişken örneği

```cpp
func4(__m64 a, _m128 b, struct c, float d);
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3
```

## <a name="varargs"></a>Varargs

Parametreler varargs (örneğin, elips bağımsız değişkenleri) aracılığıyla aktarılırsa, beşinci ve sonraki bağımsız değişkenlerin yığına dökülmesi de dahil olmak üzere normal kayıt parametresi geçiş kuralı uygulanır. Adreslerini alan argümanları çöpe atmak callee'nin sorumluluğundadır. Yalnızca kayan nokta değerleri için, callee'nin sonda kayıtlarındaki değeri beklemesi durumunda, hem sonda kaydı hem de kayan nokta kaydının değeri içermesi gerekir.

## <a name="unprototyped-functions"></a>Prototiplenmemiş işlevler

Tam olarak prototiplenmeyen işlevler için, arayan tamsayı değerlerini tamsayılar ve kayan nokta değerleri çift duyarlık olarak geçirir. Yalnızca kayan nokta değerleri için, callee'nin sonda kayıtlarındaki değeri beklemesi durumunda hem yüzer kaydı hem de kayan nokta kaydı float değerini içerir.

```cpp
func1();
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7
   func1(2, 1.0, 7);
}
```

## <a name="return-values"></a>Döndürülen değerler

64 bit sığabilecek skaler dönüş değeri RAX ile döndürülür; bu __m64 türleri içerir. Kayan, çift ve vektör türleri gibi [__m128,](../cpp/m128.md) [__m128i,](../cpp/m128i.md) [__m128d](../cpp/m128d.md) gibi skaler olmayan türler XMM0'da döndürülür. RAX veya XMM0'de döndürülen değerdeki kullanılmayan bitlerin durumu tanımsızdır.

Kullanıcı tanımlı türler, global işlevlerden ve statik üye işlevlerden değer olarak döndürülebilir. Kullanıcı tanımlı bir türü RAX'teki değere göre döndürmek için 1, 2, 4, 8, 16, 32 veya 64 bit uzunluğunda olması gerekir. Ayrıca kullanıcı tanımlı oluşturucu, yıkıcı veya kopya atama işleci olmamalıdır; özel veya korumalı statik olmayan veri üyeleri; referans türünden statik olmayan veri üyeleri yok; temel sınıf yok; sanal fonksiyonlar yok; ve bu gereksinimleri karşılamayan hiçbir veri üyesi. (Bu aslında c++03 POD tipinin tanımıdır. C++11 standardında tanım değiştiğinden, bu test için `std::is_pod` kullanmanızı önermiyoruz.) Aksi takdirde, arayan bellek ayırma ve ilk bağımsız değişken olarak döndürme değeri için bir işaretçi geçirme sorumluluğunu üstlenir. Sonraki bağımsız değişkenler daha sonra sağa bir bağımsız değişken kaydırılır. Aynı işaretçi RAX'taki callee tarafından döndürülmelidir.

Bu örnekler, parametrelerin ve iade değerlerinin belirtilen bildirimlere sahip işlevler için nasıl geçirildiğini gösterir:

### <a name="example-of-return-value-1---64-bit-result"></a>İade değeri 1 - 64 bit sonuç örneği

```Output
__int64 func1(int a, float b, int c, int d, int e);
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,
// callee returns __int64 result in RAX.
```

### <a name="example-of-return-value-2---128-bit-result"></a>İade değeri 2 - 128 bitlik sonuç örneği

```Output
__m128 func2(float a, double b, int c, __m64 d);
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,
// callee returns __m128 result in XMM0.
```

### <a name="example-of-return-value-3---user-type-result-by-pointer"></a>İade değeri örneği 3 - işaretçiye göre kullanıcı türü sonucu

```Output
struct Struct1 {
   int j, k, l;    // Struct1 exceeds 64 bits.
};
Struct1 func3(int a, double b, int c, float d);
// Caller allocates memory for Struct1 returned and passes pointer in RCX,
// a in RDX, b in XMM2, c in R9, d pushed on the stack;
// callee returns pointer to Struct1 result in RAX.
```

### <a name="example-of-return-value-4---user-type-result-by-value"></a>İade değeri örneği 4 - değere göre kullanıcı türü sonucu

```Output
struct Struct2 {
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.
};
Struct2 func4(int a, double b, int c, float d);
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;
// callee returns Struct2 result by value in RAX.
```

## <a name="callercallee-saved-registers"></a>Arayan/Callee kaydedilen kayıtları

RAX, RCX, RDX, R8, R9, R10, R11, XMM0-5 ve YMM0-15 ve ZMM0-15'in üst kısımları uçucu olarak kabul edilir ve işlev çağrılarında imha edilmiş olarak kabul edilmelidir (tüm program optimizasyonu gibi analizlerle aksi takdirde güvenlik kanıtlanamaz sayılmadığı sürece). AVX512VL'de ZMM, YMM ve XMM kayıtları 16-31 değişkendir.

RBX, RBP, RDI, RSI, RSP, R12, R13, R14, R15 ve XMM6-15 kayıtları geçici olmayan olarak kabul edilir ve bunları kullanan bir işlev tarafından kaydedilip geri yüklenmelidir.

## <a name="function-pointers"></a>İşlev işaretçileri

İşlev işaretçileri yalnızca ilgili işlevin etiketine işaretçilerdir. İşlev işaretçileri için içerik tablosu (TOC) gereksinimleri yoktur.

## <a name="floating-point-support-for-older-code"></a>Eski kod için kayan nokta desteği

MMX ve kayan nokta lı yığın kayıtları (MM0-MM7/ST0-ST7) bağlam anahtarları arasında korunur. Bu kayıtlar için açık bir çağrı sözleşmesi yoktur. Çekirdek modu kodunda bu kayıtların kullanımı kesinlikle yasaktır.

## <a name="fpcsr"></a>FpCsr

Kayıt durumu da x87 FPU denetim sözcüğü içerir. Arama sözleşmesi, bu kaydın geçici olmamasını emreder.

x87 FPU denetim sözcük kaydı, program yürütmenin başlangıcında aşağıdaki standart değerlere ayarlanır:

| Bitleri kaydedin]\[ | Ayar |
|-|-|
| FPCSR\[0:6] | Özel durum maskeleri tüm 1's (tüm özel durumlar maskeli) |
| FPCSR\[7] | Ayrılmış - 0 |
| FPCSR\[8:9] | Hassas Kontrol - 10B (çift hassasiyet) |
| FPCSR\[10:11] | Yuvarlama kontrolü - 0 (en yakına yuvarlama) |
| FPCSR\[12] | Sonsuzluk kontrolü - 0 (kullanılmaz) |

FPCSR içindeki alanlardan herhangi birini değiştiren bir callee, arayana dönmeden önce bunları geri yüklemelidir. Ayrıca, bu alanlardan herhangi birini değiştiren bir arayanın, callee'nin değiştirilen değerleri beklemediği sürece, bir callee'yi çağırmadan önce bunları standart değerlerine geri yüklemesi gerekir.

Denetim bayraklarının oynaklığı olmamasıyla ilgili kuralların iki istisnası vardır:

1. Verilen işlevin belgelenen amacının geçici olmayan FpCsr bayraklarını değiştirmek olduğu işlevlerde.

1. Bu kuralların ihlalinin, örneğin tüm program çözümlemesi yoluyla, bu kuralların ihlal edilmediği bir programla aynı şekilde görünen bir programla sonuçlandığı kanıtlanabilir şekilde doğru olduğunda.

## <a name="mxcsr"></a>MxCsr

Kayıt durumu da MxCsr içerir. Çağrı kuralı, bu kaydı geçici bir bölüme ve geçici olmayan bir bölüme böler. Geçici kısım, MXCSR\[0:5]'deki altı durum bayrağından oluşurken, kaydın geri\[kalanı, MXCSR 6:15] geçici olmayan olarak kabul edilir.

Geçici olmayan kısım, program yürütmenin başlangıcında aşağıdaki standart değerlere ayarlanır:

| Bitleri kaydedin]\[ | Ayar |
|-|-|
| MXCSR\[6] | Denormals sıfırlar - 0 |
| MXCSR\[07:12] | Özel durum maskeleri tüm 1's (tüm özel durumlar maskeli) |
| MXCSR\[13:14] | Yuvarlama kontrolü - 0 (en yakına yuvarlama) |
| MXCSR\[15] | Maskeli alt akış için sıfıra flush - 0 (kapalı) |

MXCSR içindeki geçici olmayan alanlardan herhangi birini değiştiren bir callee, arayana dönmeden önce bunları geri yüklemelidir. Ayrıca, bu alanlardan herhangi birini değiştiren bir arayanın, callee'nin değiştirilen değerleri beklemediği sürece, bir callee'yi çağırmadan önce bunları standart değerlerine geri yüklemesi gerekir.

Denetim bayraklarının oynaklığı olmamasıyla ilgili kuralların iki istisnası vardır:

- Verilen işlevin belgelenen amacının geçici olmayan MxCsr bayraklarını değiştirmek olduğu işlevlerde.

- Bu kuralların ihlalinin, örneğin tüm program çözümlemesi yoluyla, bu kuralların ihlal edilmediği bir programla aynı şekilde görünen bir programla sonuçlandığı kanıtlanabilir şekilde doğru olduğunda.

Bir işlevin belgelerinde özel olarak belirtilmediği sürece, MXCSR'nin geçici bölümünün bir işlev sınırı boyunca durumu hakkında hiçbir varsayımda bulunulamaz.

## <a name="setjmplongjmp"></a>setjmp/longjmp

Eğer setjmpex.h veya setjmp.h eklediğinizde, yıkıcılar ve `__finally` aramalar çağırır bir gevşeme [setjmp](../c-runtime-library/reference/setjmp.md) veya [longjmp](../c-runtime-library/reference/longjmp.md) sonuç tüm aramalar.  Bu x86 farklıdır, burada setjmp.h `__finally` yan tümceleri ve yıkıcılar çağrılmadı sonuçları da dahil olmak üzere.

Geçerli yığın `setjmp` işaretçisini, geçici olmayan kayıtları ve MxCsr kayıtları korur için bir çağrı.  En `longjmp` son `setjmp` arama sitesine dönmek için yapılan çağrılar ve yığın işaretçisini, geçici olmayan kayıtları ve MxCsr kayıtları sıfırlanır ve en son `setjmp` arama tarafından korunduğu şekilde duruma geri döner.

## <a name="see-also"></a>Ayrıca bkz.

[x64 yazılım kuralları](../build/x64-software-conventions.md)
