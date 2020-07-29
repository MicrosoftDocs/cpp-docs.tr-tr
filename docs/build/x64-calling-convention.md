---
title: x64 çağırma kuralı
description: Varsayılan x64 çağırma kuralının ayrıntıları.
ms.date: 07/06/2020
ms.assetid: 41ca3554-b2e3-4868-9a84-f1b46e6e21d9
ms.openlocfilehash: b615d2e4473fed1d090b7411211c08b0b824bc8f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87200861"
---
# <a name="x64-calling-convention"></a>x64 çağırma kuralı

Bu bölümde, bir işlevin (çağıran) x64 kodundaki başka bir işleve (aranan) çağrı yapmak için kullandığı standart süreçler ve kurallar açıklanmaktadır.

## <a name="calling-convention-defaults"></a>Çağırma kuralı Varsayılanları

X64 uygulama Ikili arabirimi (ABı), varsayılan olarak dört yazmaç hızlı çağrı çağırma kuralını kullanır. Çağrı yığınında, bu kayıtları kaydetmek üzere Callet 'ler için bir gölge depolama alanı olarak tahsis edilir.

Bir işlev çağrısının bağımsız değişkenleri ve bu bağımsız değişkenler için kullanılan Yazmaçları arasında katı bire bir yazışmalar vardır. 8 bayta uymayan veya 1, 2, 4 veya 8 bayt olmayan bağımsız değişkenler başvuruya göre geçirilmelidir. Tek bir bağımsız değişken hiçbir şekilde birden çok kayıt arasında yayılmaz.

X87 kayıt yığını kullanılmıyor. Bu, aranan tarafından kullanılabilir, ancak işlev çağrıları arasında geçici olarak ele alalım. Tüm kayan nokta işlemleri 16 XMM Yazmaçları kullanılarak yapılır.

Tamsayı bağımsız değişkenleri, RCX, RDX, R8 ve R9 yazmaçlarında geçirilir. Kayan nokta bağımsız değişkenleri XMM0L, XMM1L, XMM2L ve XMM3L içinde geçirilir. 16 baytlık bağımsız değişkenler başvuruya göre geçirilir. Parametre geçirme, [parametre geçirme](#parameter-passing)bölümünde ayrıntılı olarak açıklanmıştır. Bu Yazmaçları ve KıX, R10, R11, XMM4 ve XMM5, geçici olarak değerlendirilir. Kayıt kullanımı, kullanımı ve [arayan/çağrılan kaydedilmiş Yazmaçları](#callercallee-saved-registers) [kaydetme](../build/x64-software-conventions.md#register-usage) bölümünde ayrıntılı olarak belgelenmiştir.

Prototipi oluşturulmuş işlevlerde, geçirmeden önce tüm bağımsız değişkenler beklenen aranan türlerine dönüştürülür. Çağıranın, aranan parametreleri için alan ayırmaktan sorumludur. Çağıran bu sayıda parametreyi almasa bile, çağıranın dört kayıt parametresini depolaması için her zaman yeterli alan ayırması gerekir. Bu kural, prototipi oluşturulmamış C dili işlevleri ve vararg C/C++ işlevleri için desteği basitleştirir. Vararg veya prototipi oluşturulmamış işlevlerde, tüm kayan nokta değerleri karşılık gelen genel amaçlı kasada yinelenmelidir. İlk dört dışındaki tüm parametrelerin, çağrıdan önce gölge depodan sonra yığına depolanması gerekir. Vararg işlev ayrıntıları [varargs](#varargs)içinde bulunabilir. Prototipi oluşturulmamış işlev bilgileri [prototipi oluşturulmamış işlevlerde](#unprototyped-functions)ayrıntılı olarak açıklanmıştır.

## <a name="alignment"></a>Hizalama

Çoğu yapı doğal hizalamasına hizalanır. Birincil özel durumlar, `malloc` `alloca` performansa yardımcı olmak için 16 baytlık hizalanmış yığın işaretçisi ve veya bellektir. 16 baytın üzerinde hizalama el ile yapılmalıdır. 16 bayt, XMM işlemleri için ortak bir hizalama boyutu olduğundan, bu değer çoğu kod için çalışmalıdır. Yapı düzeni ve hizalama hakkında daha fazla bilgi için bkz. [türler ve depolama](../build/x64-software-conventions.md#types-and-storage). Yığın düzeni hakkında daha fazla bilgi için bkz. [x64 Stack kullanımı](../build/stack-usage.md).

## <a name="unwindability"></a>Unwınbir

Yaprak işlevleri, geçici olmayan kayıtları değiştirmeyen işlevlerdir. Yaprak olmayan bir işlev, örneğin bir işlev çağırarak geçici olmayan RSP 'yi değiştirebilir. Ya da yerel değişkenler için ek yığın alanı ayırarak RSP 'yi değiştirebilir. Bir özel durum işlendiği zaman geçici olmayan kayıtları kurtarmak için, yaprak olmayan işlevlere statik verilerle açıklama eklenir. Veriler, işlevin rastgele bir yönergede nasıl düzgün bir şekilde geriye doğru şekilde geri alınacağını açıklar. Bu veriler *pData*olarak, veri işleme verileri de *XData*' a karşılık gelen yordam verileri olarak depolanır. XData, geriye doğru izleme bilgilerini içerir ve ek PDATA veya bir özel durum işleyici işlevine işaret edebilir.

Prologs 'lar ve epiteler, XData 'da doğru şekilde açıklanabilmeleri için yüksek oranda kısıtlıdır. Yığın işaretçisi, yaprak işlevleri dışında bir bitiş veya giriş bölümünün parçası olmayan herhangi bir kod bölgesinde 16 baytlık hizalanmış olmalıdır. Yaprak işlevleri bir dönüşün benzetimini yaparak, PDATA ve XData gerekli değildir. İşlev progünlükleri ve epıde 'ın doğru yapısı hakkında daha fazla bilgi için bkz. [x64 giriş ve bitiş](../build/prolog-and-epilog.md). Özel durum işleme hakkında daha fazla bilgi ve pData ve XData 'ların özel durum işleme ve geri alma hakkında daha fazla bilgi için bkz. [x64 özel durum işleme](../build/exception-handling-x64.md)

## <a name="parameter-passing"></a>Parametre geçirme

Varsayılan olarak, x64 çağırma kuralı kayıt içindeki bir işleve ilk dört bağımsız değişkeni geçirir. Bu bağımsız değişkenler için kullanılan Yazmaçları bağımsız değişkenin konumuna ve türüne bağlıdır. Kalan bağımsız değişkenler yığına sağdan sola doğru sırada gönderilir.

En soldaki dört konumda bulunan tamsayı değerli bağımsız değişkenler, sırasıyla RCX, RDX, R8 ve R9 içinde soldan sağa sırada geçirilir. Beşinci ve daha yüksek bağımsız değişkenler, daha önce açıklandığı gibi yığına geçirilir. Yazmaçlardaki tüm tamsayı bağımsız değişkenleri sağa yaslanır, bu nedenle aranan, kaydın üst bitlerini yoksayabilir ve yalnızca kaydın gerekli kısmına erişebilir.

İlk dört parametrede herhangi bir kayan nokta ve çift duyarlıklı bağımsız değişken, konuma göre XMM0-XMM3 ile geçirilir. Kayan nokta değerleri yalnızca vararg bağımsız değişkenleri olduğunda RCX, RDX, R8 ve R9 tamsayı kayıtlarına yerleştirilir. Ayrıntılar için bkz. [varargs](#varargs). Benzer şekilde, XMM0-XMM3 Yazmaçları karşılık gelen bağımsız değişken bir tamsayı veya işaretçi türü olduğunda yoksayılır.

[`__m128`](../cpp/m128.md)türler, diziler ve dizeler hiçbir şekilde anında değer tarafından geçirilmez. Bunun yerine, çağıran tarafından ayrılan belleğe bir işaretçi geçirilir. 8, 16, 32 veya 64 bit ve tür yapılar ve birleşimler **`__m64`** aynı boyutta tamsayılar gibi geçirilir. Diğer boyutlardaki yapılar veya birleşimler, çağıran tarafından ayrılan belleğe bir işaretçi olarak geçirilir. Bir işaretçi olarak geçirilen bu toplama türleri için, **`__m128`** arayan tarafından ayrılan geçici bellek, 16 baytlık hizalı olmalıdır.

Yığın alanı içermeyen ve diğer işlevleri çağırmadığı iç işlevler, bazen ek yazmaç bağımsız değişkenlerini geçirmek için diğer geçici Yazmaçları kullanır. Bu iyileştirme, derleyici ile iç işlev uygulamasıyla sıkı bağlama mümkün hale getirilir.

Aranan, kayıt parametrelerini, gerekirse gölge alanına dökten sorumludur.

Aşağıdaki tablo, parametrelerin türe ve konuma göre nasıl geçtiğini özetler:

| Parametre türü | Beşinci ve daha yüksek | diğerini | şirketlerin | saniye | Soldaki |
|-|-|-|-|-|-|
| kayan nokta | yığın | XMM3 | XMM2 | XMM1 | XMM0 |
| integer | yığın | R9 | R8 | RDX | RCX |
| Toplamlar (8, 16, 32 veya 64 bit) ve**`__m64`** | yığın | R9 | R8 | RDX | RCX |
| Diğer toplamalar, işaretçiler olarak | yığın | R9 | R8 | RDX | RCX |
| **`__m128`**, bir işaretçi olarak | yığın | R9 | R8 | RDX | RCX |

### <a name="example-of-argument-passing-1---all-integers"></a>Bağımsız değişken geçen bir örnek 1-tüm tamsayılar

```cpp
func1(int a, int b, int c, int d, int e, int f);
// a in RCX, b in RDX, c in R8, d in R9, f then e pushed on stack
```

### <a name="example-of-argument-passing-2---all-floats"></a>Bağımsız değişken geçen 2-tüm float örnekleri

```cpp
func2(float a, double b, float c, double d, float e, float f);
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, f then e pushed on stack
```

### <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>3-karışık litre ve float bağımsız değişken örneği

```cpp
func3(int a, double b, int c, float d, int e, float f);
// a in RCX, b in XMM1, c in R8, d in XMM3, f then e pushed on stack
```

### <a name="example-of-argument-passing-4---__m64-__m128-and-aggregates"></a>4- `__m64` , `__m128` , ve toplamları geçen bağımsız değişken örneği

```cpp
func4(__m64 a, __m128 b, struct c, float d, __m128 e, __m128 f);
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3,
// ptr to f pushed on stack, then ptr to e pushed on stack
```

## <a name="varargs"></a>Varargs

Parametreler varargs aracılığıyla (örneğin, üç nokta bağımsız değişkeni) geçirilirse, normal kayıt parametresi geçirme kuralı uygulanır. Bu kural, yığına beşinci ve üzeri bağımsız değişkenlerin atıştırılması içerir. Adresinin alındığı bağımsız değişkenlerin dökümünü almak için aranan sorumluluğudur. Yalnızca kayan nokta değerleri için, çağrılan tamsayı Yazmaçlarda değeri beklediği durumlarda tamsayı kaydı ve kayan nokta kaydı değeri içermelidir.

## <a name="unprototyped-functions"></a>Prototipi oluşturulmamış işlevler

Tam prototipi bulunmayan işlevler için, çağıran tam sayı değerlerini tamsayı ve kayan nokta değerleri olarak çift duyarlıklı geçirir. Yalnızca kayan nokta değerleri için, hem tamsayı kaydı hem de kayan nokta kaydı, çağrılan değerin tamsayı Yazmaçlarda değer beklediği durumda float değerini içerir.

```cpp
func1();
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7
   func1(2, 1.0, 7);
}
```

## <a name="return-values"></a>Dönüş değerleri

Türü de dahil olmak üzere 64 bite uyaabilecek skaler bir dönüş değeri **`__m64`** , Kx aracılığıyla döndürülür. ; Gibi float, Double değerleri ve vektör türlerini içeren skalar olmayan türler, [`__m128`](../cpp/m128.md) [`__m128i`](../cpp/m128i.md) [`__m128d`](../cpp/m128d.md) XMM0 içinde döndürülür. IX veya XMM0 içinde döndürülen değer içindeki kullanılmayan bitlerin durumu tanımsız.

Kullanıcı tanımlı türler, genel işlevlerden ve statik üye işlevlerdeki değere göre döndürülebilir. Bir Kullanıcı tanımlı türü, bir GREX değerine göre döndürmek için, 1, 2, 4, 8, 16, 32 veya 64 bit uzunluğunda olmalıdır. Ayrıca, Kullanıcı tanımlı Oluşturucusu, yok edicisi veya kopya atama operatörünün olması gerekir. Özel veya korumalı statik olmayan veri üyelerine sahip olamaz ve başvuru türündeki statik olmayan veri üyesi olamaz. Temel sınıflar veya sanal işlevlere sahip olamaz. Ayrıca, bu gereksinimleri karşılayan veri üyelerine de sahip olabilir. (Bu tanım temelde bir C++ 03 POD türü ile aynıdır. Tanım C++ 11 standardında değiştiğinden, `std::is_pod` Bu test için kullanılması önerilmez.) Aksi takdirde, çağıran dönüş değeri için bellek ayırmayı ve ilk bağımsız değişken olarak ona bir işaretçi iletmelidir. Kalan bağımsız değişkenler daha sonra sağa bir bağımsız değişken kaydıralınır. Aynı işaretçi, RAMPAIÇINDEKI çağrılan tarafından döndürülmelidir.

Bu örnekler, belirtilen bildirimlere sahip işlevler için parametrelerin ve dönüş değerlerinin nasıl geçtiğini gösterir:

### <a name="example-of-return-value-1---64-bit-result"></a>Dönüş değeri 1-64-bit sonucu örneği

```Output
__int64 func1(int a, float b, int c, int d, int e);
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,
// callee returns __int64 result in RAX.
```

### <a name="example-of-return-value-2---128-bit-result"></a>Dönüş değeri 2-128-bit sonucu örneği

```Output
__m128 func2(float a, double b, int c, __m64 d);
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,
// callee returns __m128 result in XMM0.
```

### <a name="example-of-return-value-3---user-type-result-by-pointer"></a>Dönüş değeri 3-işaretçiye göre Kullanıcı türü sonucu

```Output
struct Struct1 {
   int j, k, l;    // Struct1 exceeds 64 bits.
};
Struct1 func3(int a, double b, int c, float d);
// Caller allocates memory for Struct1 returned and passes pointer in RCX,
// a in RDX, b in XMM2, c in R9, d pushed on the stack;
// callee returns pointer to Struct1 result in RAX.
```

### <a name="example-of-return-value-4---user-type-result-by-value"></a>Dönüş değeri 4-Kullanıcı türü sonucu değere göre örnek

```Output
struct Struct2 {
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.
};
Struct2 func4(int a, double b, int c, float d);
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;
// callee returns Struct2 result by value in RAX.
```

## <a name="callercallee-saved-registers"></a>Çağıran/çağrılan kayıtlı Yazmaçları

X64 ABı, KıX, RCX, RDX, R8, R9, R10, R11 ve XMM0-XMM5 volatile yazmaçlarını dikkate alır. Varsa, YMM0 Ila-YMM15 ve ZMM0-ZMM15 ' nin üst bölümleri de geçici bir şekilde bulunur. AVX512VL 'de ZMM, YıMM ve XMM Yazmaçları 16-31 de geçici bir durum olabilir. Aksi takdirde, tüm program iyileştirmesi gibi Analize güvenlik altına alınmadıkça, işlev çağrılarında geçici Yazmaçları yok edin.

X64 ABı, Yazmaçları RBX, RBP, RDı, RSı, RSP, R12, R13, R14, R15 ve XMM6-XMM15 kalıcı olarak değerlendirir. Bunların kendilerini kullanan bir işlev tarafından kaydedilmesi ve geri yüklenmesi gerekir.

## <a name="function-pointers"></a>İşlev işaretçileri

İşlev işaretçileri, yalnızca ilgili işlevin etiketine yönelik işaretçilerdir. İşlev işaretçileri için içindekiler tablosu (TOC) gereksinimi yoktur.

## <a name="floating-point-support-for-older-code"></a>Eski kod için kayan nokta desteği

MMX ve kayan nokta yığın Yazmaçları (MM0-MM7/ST0-ST7) bağlam anahtarları arasında korunur. Bu Yazmaçları için açık bir çağırma kuralı yoktur. Bu yazmaçların kullanımı, çekirdek modu kodunda kesinlikle yasaktır.

## <a name="fpcsr"></a>FPCSR

Kayıt durumu Ayrıca x87 FPU denetim sözcüğünü de içerir. Çağırma kuralı, bu kaydın kalıcı olmasını belirler.

X87 FPU denetimi sözcük kaydı, program yürütme başlangıcında aşağıdaki standart değerleri kullanarak ayarlanır:

| \[Bitleri Kaydet] | Ayar |
|-|-|
| FPCSR \[ 0:6] | Özel durum maskeleri hepsi 1 ' dir (tüm özel durumlar maskelenir) |
| FPCSR \[ 7] | Ayrılmış-0 |
| FPCSR \[ 8:9] | Duyarlık denetimi-10B (çift duyarlık) |
| FPCSR \[ 10:11] | Yuvarlama denetimi-0 (en yakın) |
| FPCSR \[ 12] | Infinity denetimi-0 (kullanılmaz) |

FPCSR içindeki alanlardan herhangi birini değiştiren bir çağrılan, çağıranına dönmeden önce bunları geri yüklemesi gerekir. Ayrıca, bu alanlardan herhangi birini değiştiren bir çağıran, çağrı yapılmadan önce bu alanları standart değerlerine geri yüklemesi gerekir, çünkü çağrılan, çağrılan değerler bekler.

Denetim bayraklarının listesi oluşturulmamış kurallarla ilgili kuralların iki özel durumu vardır:

- Verilen işlevin belgelenmiş amacının kalıcı FPCSR bayraklarını değiştirmesi durumunda olduğu işlevlerde.

- Provably olduğunda, bu kuralların ihlali, kuralları ihlal eden bir programla aynı şekilde davranan bir programla (örneğin, tüm program analizinden) neden olur.

## <a name="mxcsr"></a>MXCSR

Kayıt durumu MXCSR de içerir. Çağırma kuralı, bu kaydı geçici bir bölüme ve kalıcı bölüme böler. Geçici bölüm, MXCSR 0:5] içindeki altı durum bayraklarından oluşur ve \[ kaydın geri kalanı, mxcsr \[ 6:15] kalıcı olarak kabul edilir.

Kalıcı olmayan bölüm, program yürütme başlangıcında aşağıdaki standart değerlere ayarlanır:

| \[Bitleri Kaydet] | Ayar |
|-|-|
| MXCSR \[ 6] | Denormaller sıfırlardır-0 |
| MXCSR \[ 7:12] | Özel durum maskeleri hepsi 1 ' dir (tüm özel durumlar maskelenir) |
| MXCSR \[ 13:14] | Yuvarlama denetimi-0 (en yakın) |
| MXCSR \[ 15] | Maskelenmiş sınırın üzerinde sıfıra kadar temizle-0 (kapalı) |

MXCSR içindeki kalıcı olmayan alanlardan herhangi birini değiştiren bir çağrılan, çağıranına dönmeden önce onları geri yüklemesi gerekir. Ayrıca, bu alanlardan herhangi birini değiştiren bir çağıran, çağrı yapılmadan önce bu alanları standart değerlerine geri yüklemesi gerekir, çünkü çağrılan, çağrılan değerler bekler.

Denetim bayraklarının listesi oluşturulmamış kurallarla ilgili kuralların iki özel durumu vardır:

- Verilen işlevin belgelenmiş amacının, kalıcı MXCSR bayraklarını değiştirmek olduğu işlevlerde.

- Provably olduğunda, bu kuralların ihlali, kuralları ihlal eden bir programla aynı şekilde davranan bir programla (örneğin, tüm program analizinden) neden olur.

İşlev belgelerinin açıkça açıklamadığı durumlar dışında, bir işlev sınırının tamamında MXCSR yazmacın geçici bölüm durumuyla ilgili varsayımsız yapmayın.

## <a name="setjmplongjmp"></a>setjmp/longjmp

Setjmpex. h veya setjmp. h dahil ettiğinizde, tüm çağrıları [`setjmp`](../c-runtime-library/reference/setjmp.md) [`longjmp`](../c-runtime-library/reference/longjmp.md) ve yıkıcıları ve çağrıları çağıran bir geriye doğru çağırır **`__finally`** .  Bu davranış, setjmp. h dahil olmak üzere, **`__finally`** yan tümcelerde ve yıkıcılarda çağrılan x86 'dan farklıdır.

`setjmp`Geçerli yığın işaretçisini, geçici olmayan kayıtları ve MXCSR yazmaçlarını koruyan bir çağrı.  `longjmp`En son `setjmp` çağrı sitesine geri dönmek ve yığın işaretçisi, geçici olmayan Yazmaçları ve MXCSR yazmaçlarını en son çağrıya göre korunan duruma geri döndürecek şekilde çağırır `setjmp` .

## <a name="see-also"></a>Ayrıca bkz.

[x64 yazılım kuralları](../build/x64-software-conventions.md)
