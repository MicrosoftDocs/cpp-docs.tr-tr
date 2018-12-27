---
title: __vectorcall
ms.date: 12/17/2018
f1_keywords:
- __vectorcall_cpp
- __vectorcall
- _vectorcall
helpviewer_keywords:
- __vectorcall keyword
- __vectorcall
ms.assetid: 1c95ed59-86c6-4857-b4ed-10519193f851
ms.openlocfilehash: 55c383c4bdf83ddb5fdf1c4990d5f2e47b4d819a
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627459"
---
# <a name="vectorcall"></a>__vectorcall

**Microsoft'a özgü**

**__Vectorcall** çağırma kuralı işlevlere bağımsız değişkenler, mümkün olduğunda kayıtlara geçirilebilir olduğunu belirtir. **__vectorcall** bağımsız değişken için daha fazla kayıtlarını kullanan [__fastcall](../cpp/fastcall.md) veya varsayılan [çağırma kuralı x64](../build/x64-calling-convention.md) kullanın. **__Vectorcall** çağırma kuralı yalnızca desteklenen yerel kodda, Streaming SIMD Extensions 2 (SSE2) içeren x86 ve x64 işlemciler ve üzeri. Kullanım **__vectorcall** defterlerine yüklenen geçmesi birkaç kayan nokta işlevleri veya SIMD vektörü bağımsız değişkenlerini hızlandırmak ve bağımsız değişkenlerden yararlanan işlemleri gerçekleştirmek için. Aşağıdaki liste x86 ve x64 uygulamaları için ortak olan özellikleri gösterir **__vectorcall**. Farklılıklar bu makalenin sonraki bölümlerinde açıklanmıştır.

|Öğe|Uygulama|
|-------------|--------------------|
|C ad düzenleme kuralı|İşlev adları iki "at" işareti soneki (\@\@) parametre listesinde (ondalık) bayt sayısı ardından.|
|Durum çevirisi kuralları|Gerçekleşen durum çevirisi yok.|

Kullanarak [GV](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneği olarak derlemek için modüldeki her işlevin neden **__vectorcall** işlevi bir üye işlev olmadığı sürece, çakışan çağrı kuralı özniteliğiyle bildirilen, kullanır bir `vararg` bağımsız değişken listesi ya da adına sahip `main`.

Kaydına göre üç tür bağımsız değişkeni geçirebilirsiniz **__vectorcall** işlevleri: *tamsayı türü* değerleri *vektör türü* değerleri ve *homojen vektör Toplama* (HVA) değerleri.

Bir tamsayı türü, iki gereksinimi karşılar: işlemcinin yerel kayıt boyutuna uyan — Örneğin, 4 baytlık bir x86 makine veya 8 bayt x x64 makine — ve yeniden kendi bit değişiklik yapmadan tamsayıya kayıt uzunluğu ve geri dönüştürülemez temsili. Örneğin yükseltilebilir türlü **int** x86 (**uzun uzun** x64) — Örneğin, bir **char** veya **kısa**— veya için yayımlanabilir **int** (**uzun uzun** x64) ve orijinal türe geri için değişiklik olmayan bir tamsayı türü. Tamsayı türleri, işaretçi, başvuru içerir ve **yapı** veya **birleşim** 4 baytlık (x64 8 bayt) veya daha az. X64 platformlarda, daha büyük **yapı** ve **birleşim** türleri x86; çağırıcı tarafından ayrılan belleğe başvuruyla geçirilir platformlar, bunlar değerine göre geçirilir yığında.

Vektör türü olan bir kayan nokta türü — örneğin, bir **float** veya **çift**— veya SIMD vektör türü olabilir — örneğin, **__m128** veya **__m256**.

HVA türü, aynı vektör türlerine sahip en fazla dört veri üyeleri bileşik türüdür. HVA türü, üyelerinin vektör türüyle aynı hizalama gereksinimine sahiptir. Bir örnek bir hva **yapı** üç özdeş vektör türü içeren ve 32 baytlık hizalaması olan tanımı:

```cpp
typedef struct {
   __m256 x;
   __m256 y;
   __m256 z;
} hva3;    // 3 element HVA type on __m256
```

İşlevlerinizi açıkça bildirin **__vectorcall** üst bilgi dosyaları, ayrı olarak izin vermek için bir anahtar sözcük hatasız kodu derlenmiş. İşlevleri kullanmak için prototipli olmalıdır **__vectorcall**ve bir `vararg` değişken uzunlukta bağımsız değişken listesi.

Üye işlevi kullanılarak bildirilebilir **__vectorcall** tanımlayıcısı. Gizli **bu** işaretçisi ilk tamsayı türü bağımsız değişkeni olarak kayıt tarafından geçirilir.

ARM makinelerde **__vectorcall** kabul edilir ve derleyici tarafından yok sayılır.

Tanımlanan çıkış satır dışı, işlev ise, statik olmayan sınıf üyesi işlevleri için çağırma kuralı değiştiricinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, sınıfı statik olmayan üyeler için bildirim sırasında belirtilen çağırma kuralı tanımı kabul edilir. Bu sınıf tanımını ele alalım:

```cpp
struct MyClass {
   void __vectorcall mymethod();
};
```

bu:

```cpp
void MyClass::mymethod() { return; }
```

şuna eşdeğerdir:

```cpp
void __vectorcall MyClass::mymethod() { return; }
```

**__Vectorcall** çağırma kuralı değiştiricisi belirtilmelidir işaretçisi olduğunda bir **__vectorcall** işlevi oluşturulur. Sonraki örnek, oluşturur bir **typedef** işaretçisi için bir **__vectorcall** dört alan işlev **çift** bağımsız değişkenleri ve döndürür bir **__m256**değeri:

```cpp
typedef __m256 (__vectorcall * vcfnptr)(double, double, double, double);
```

Önceki sürümlerle uyumluluk için **_vectorcall** eşanlamlıdır **__vectorcall** sürece derleyici seçeneği [/Za \(dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md)belirtilir.

## <a name="vectorcall-convention-on-x64"></a>x64 __vectorcall kuralı

**__Vectorcall** üzerinde x64 çağırma kuralı, ek yazmaçların yararlanmak için çağırma kuralını standard x64 genişletir. Hem tamsayı türü bağımsız değişkenleri ve vektör türü bağımsız değişken listesindeki konumu temel alan kayıtlarla eşlenir. HVA bağımsız değişkenleri kullanılmayan vektör kayıtları için ayrılır.

Sırayla soldan sağa doğru ilk dört bağımsız değişken tamsayı türü bağımsız değişken olduğunda, bunlar karşılık gelen kayıt defterinde, geçirilirler — RCX, RDX, R8 ve R9. Gizli **bu** işaretçisi ilk tamsayı türü bağımsız değişken olarak kabul edilir. İlk dört bağımsız değişken biriyle HVA bağımsız değişkeni kullanılabilir kayıtlara geçirilemez, arayana ayrılan belleğe başvuru bunun yerine karşılık gelen bir tamsayı türü kayıttaki geçirilir. Tamsayı türü bağımsız değişkenleri dördüncü parametre konumunda sonra yığına geçirilir.

Sırayla soldan sağa ilk altı bağımsız değişken vektör türü bağımsız değişken, arası SSE vektör kayıtlarında göre bağımsız değişken konumu 0-5 değere göre geçirilir. Kayan nokta ve **__m128** türleri geçirilir XMM yazmaçlarında ve **__m256** türleri YMM geçirilir kaydeder. Bu çağırma kuralı, vektör türleri başvuruya göre değere göre geçirilir ve ek kayıtlar kullanıldığından çünkü standart x64 farklıdır. Vektör türü bağımsız değişkenleri için ayrılan gölge yığın alanı 8 bayt ile sabittir ve [/homeparams](../build/reference/homeparams-copy-register-parameters-to-stack.md) seçeneği geçerli değildir. Vektör türü bağımsız değişken yedinci ve sonraki parametresi konumları yığında çağırıcı tarafından ayrılan bellek başvurusu tarafından geçirilir.

Yazmaçları vektör bağımsız değişkenleri için ayrılmasından sonra HVA bağımsız değişkenlerinin veri üyeleri, kullanılmayan vektör kayıtlarına XMM0 ila XMM5 arasında artan sırada ayrılır (veya YMM0 ila ymm5 arasında için **__m256** türleri), yeterli yazmaç var olduğu sürece Tüm HVA için kullanılabilir. Aksi durumda yeterli yazmaç, HVA bağımsız değişkeni çağırıcı tarafından ayrılan bellek başvurusu tarafından geçirilir. Bir HVA bağımsız değişkeninin yığın gölge alanı tanımlanmamış içerikle 8 bayt düzeltildi. HVA bağımsız değişkenleri atanır sırayla soldan sağa parametre listesinde ve herhangi bir konumda olabilir. Vektör atanmaz konumları o konuma karşılık gelen tam sayı kayıt başvuruya göre iletilir HVA bağımsız bir ilk dört bağımsız değişken. Dördüncü parametre konumunda sonra başvuru tarafından geçirilen HVA bağımsız değişkenleri yığın üzerine itilir.

Sonuçları **__vectorcall** işlevleri, mümkün olduğunda yazmaçlardaki değer tarafından döndürülür. Yapılar veya 8 bayt veya daha az birleşimler dahil tamsayı türü sonuçları RAX'daki değer tarafından döndürülür. Vektör türü sonuçları, boyutuna bağlı olarak XMM0 veya YMM0, değer tarafından döndürülür. HVA sonuçları kayıtları XMM0:XMM3 veya YMM0:YMM3, öğe boyutuna bağlı olarak değeri tarafından döndürülen her veri öğesini içerir. İlgili kayıtlara uygun olmayan sonuç türleri, çağırıcı tarafından ayrılan belleğe başvuru tarafından döndürülür.

Yığın x64 çağrı yapan tarafından korunur uygulaması **__vectorcall**. Çağıran prolog ve epilog kodu ayırır ve çağrılan işlev için yığını temizler. Bağımsız değişkenleri sağdan sola yığın üzerine itilir ve gölge yığın alanı kayıtlara geçirilen bağımsız değişkenler için ayrılır.

Örnekler:

```cpp
// crt_vc64.c
// Build for amd64 with: cl /arch:AVX /W3 /FAs crt_vc64.c
// This example creates an annotated assembly listing in
// crt_vc64.asm.

#include <intrin.h>
#include <xmmintrin.h>

typedef struct {
   __m128 array[2];
} hva2;    // 2 element HVA type on __m128

typedef struct {
   __m256 array[4];
} hva4;    // 4 element HVA type on __m256

// Example 1: All vectors
// Passes a in XMM0, b in XMM1, c in YMM2, d in XMM3, e in YMM4.
// Return value in XMM0.
__m128 __vectorcall
example1(__m128 a, __m128 b, __m256 c, __m128 d, __m256 e) {
   return d;
}

// Example 2: Mixed int, float and vector parameters
// Passes a in RCX, b in XMM1, c in R8, d in XMM3, e in YMM4,
// f in XMM5, g pushed on stack.
// Return value in YMM0.
__m256 __vectorcall
example2(int a, __m128 b, int c, __m128 d, __m256 e, float f, int g) {
   return e;
}

// Example 3: Mixed int and HVA parameters
// Passes a in RCX, c in R8, d in R9, and e pushed on stack.
// Passes b by element in [XMM0:XMM1];
// b's stack shadow area is 8-bytes of undefined value.
// Return value in XMM0.
__m128 __vectorcall example3(int a, hva2 b, int c, int d, int e) {
   return b.array[0];
}

// Example 4: Discontiguous HVA
// Passes a in RCX, b in XMM1, d in XMM3, and e is pushed on stack.
// Passes c by element in [YMM0,YMM2,YMM4,YMM5], discontiguous because
// vector arguments b and d were allocated first.
// Shadow area for c is an 8-byte undefined value.
// Return value in XMM0.
float __vectorcall example4(int a, float b, hva4 c, __m128 d, int e) {
   return b;
}

// Example 5: Multiple HVA arguments
// Passes a in RCX, c in R8, e pushed on stack.
// Passes b in [XMM0:XMM1], d in [YMM2:YMM5], each with
// stack shadow areas of an 8-byte undefined value.
// Return value in RAX.
int __vectorcall example5(int a, hva2 b, int c, hva4 d, int e) {
   return c + e;
}

// Example 6: HVA argument passed by reference, returned by register
// Passes a in [XMM0:XMM1], b passed by reference in RDX, c in YMM2,
// d in [XMM3:XMM4].
// Register space was insufficient for b, but not for d.
// Return value in [YMM0:YMM3].
hva4 __vectorcall example6(hva2 a, hva4 b, __m256 c, hva2 d) {
   return b;
}

int __cdecl main( void )
{
   hva4 h4;
   hva2 h2;
   int i;
   float f;
   __m128 a, b, d;
   __m256 c, e;

   a = b = d = _mm_set1_ps(3.0f);
   c = e = _mm256_set1_ps(5.0f);
   h2.array[0] = _mm_set1_ps(6.0f);
   h4.array[0] = _mm256_set1_ps(7.0f);

   b = example1(a, b, c, d, e);
   e = example2(1, b, 3, d, e, 6.0f, 7);
   d = example3(1, h2, 3, 4, 5);
   f = example4(1, 2.0f, h4, d, 5);
   i = example5(1, h2, 3, h4, 5);
   h4 = example6(h2, h4, c, h2);
}
```

## <a name="vectorcall-convention-on-x86"></a>x86 __vectorcall kuralı

**__Vectorcall** takip çağırma **__fastcall** 32-bit tamsayı türü bağımsız değişkenleri ve vektör türü ve HVA bağımsız değişkenleri için SSE vektör yazmaçlarının avantajlarından kuralı.

Parametre listesinde soldan sağa yerleştirilir doğru ECX ve EDX içine sırasıyla bulunan ilk iki tamsayı türü bağımsız değişkenler. Gizli **bu** işaretçisi ilk tamsayı türü bağımsız değişken olarak kabul edilir ve ECX'e geçirilir. İlk altı vektör türü bağımsız SSE vektör yazmaçlarının 0-5, bağımsız değişken boyutuna bağlı olarak XMM veya YMM kayıtlarında değere göre geçirilir.

Sırasıyla soldan sağa geçirilir için değer arası SSE vektör kayıtlarında 0-5 v argumentech typu ilk altı vektör. Kayan nokta ve **__m128** türleri geçirilir XMM yazmaçlarında ve **__m256** türleri YMM geçirilir kaydeder. Hiçbir gölge yığın alanı, kayıt tarafından geçirilen vektör türü bağımsız değişkenler için ayrılır. Yedinci ve sonraki vektör türü bağımsız değişkenler, yığında çağırıcı tarafından ayrılan bellek başvurusu tarafından geçirilir. Derleyici Hatası SORUMLULUĞUN [C2719](../error-messages/compiler-errors-2/compiler-error-c2719.md) bu bağımsız değişkenler için geçerli değildir.

Yazmaçları vektör bağımsız değişkenleri için ayrılmasından sonra veri üyeleri, HVA bağımsız değişkenleri kullanılmayan vektör kayıtlarına artan düzende ayrılır XMM0 ila XMM5 arasında kaydeder (veya YMM0 ila ymm5 arasında için **__m256** türleri), yeterli yazmaç var olduğu sürece Tüm HVA için kullanılabilir. Aksi durumda yeterli yazmaç, HVA bağımsız değişkeni çağırıcı tarafından ayrılan bellek başvurusu tarafından yığına geçirilir. HVA bağımsız değişkeni için hiçbir yığın gölge boşluğu ayrılmaz. HVA bağımsız değişkenleri atanır sırayla soldan sağa parametre listesinde ve herhangi bir konumda olabilir.

Sonuçları **__vectorcall** işlevleri, mümkün olduğunda yazmaçlardaki değer tarafından döndürülür. Yapılar veya 4 bayt veya daha az birleşimler dahil tamsayı türü sonuçları EAX'daki değer tarafından döndürülür. Tamsayı türü yapılar veya 8 bayt veya daha az birleşimler edx: eax içindeki değer tarafından döndürülür. Vektör türü sonuçları, boyutuna bağlı olarak XMM0 veya YMM0, değer tarafından döndürülür. HVA sonuçları kayıtları XMM0:XMM3 veya YMM0:YMM3, öğe boyutuna bağlı olarak değeri tarafından döndürülen her veri öğesini içerir. Diğer sonuç türleri, çağırıcı tarafından ayrılan belleğe başvuru tarafından döndürülür.

X86 uygulaması **__vectorcall** aşağıdaki çağıran ve çağrılan işlev tarafından yığında sağdan sola taşınan bağımsız değişkenlerle ilgili kuralı yığını temizler hemen önce. Yazmaçlarda yerleştirilmez yalnızca bağımsız değişkenler yığına itilir.

Örnekler:

```cpp
// crt_vc86.c
// Build for x86 with: cl /arch:AVX /W3 /FAs crt_vc86.c
// This example creates an annotated assembly listing in
// crt_vc86.asm.

#include <intrin.h>
#include <xmmintrin.h>

typedef struct {
   __m128 array[2];
} hva2;    // 2 element HVA type on __m128

typedef struct {
   __m256 array[4];
} hva4;    // 4 element HVA type on __m256

// Example 1: All vectors
// Passes a in XMM0, b in XMM1, c in YMM2, d in XMM3, e in YMM4.
// Return value in XMM0.
__m128 __vectorcall
example1(__m128 a, __m128 b, __m256 c, __m128 d, __m256 e) {
   return d;
}

// Example 2: Mixed int, float and vector parameters
// Passes a in ECX, b in XMM0, c in EDX, d in XMM1, e in YMM2,
// f in XMM3, g pushed on stack.
// Return value in YMM0.
__m256 __vectorcall
example2(int a, __m128 b, int c, __m128 d, __m256 e, float f, int g) {
   return e;
}

// Example 3: Mixed int and HVA parameters
// Passes a in ECX, c in EDX, d and e pushed on stack.
// Passes b by element in [XMM0:XMM1].
// Return value in XMM0.
__m128 __vectorcall example3(int a, hva2 b, int c, int d, int e) {
   return b.array[0];
}

// Example 4: HVA assigned after vector types
// Passes a in ECX, b in XMM0, d in XMM1, and e in EDX.
// Passes c by element in [YMM2:YMM5].
// Return value in XMM0.
float __vectorcall example4(int a, float b, hva4 c, __m128 d, int e) {
   return b;
}

// Example 5: Multiple HVA arguments
// Passes a in ECX, c in EDX, e pushed on stack.
// Passes b in [XMM0:XMM1], d in [YMM2:YMM5].
// Return value in EAX.
int __vectorcall example5(int a, hva2 b, int c, hva4 d, int e) {
   return c + e;
}

// Example 6: HVA argument passed by reference, returned by register
// Passes a in [XMM1:XMM2], b passed by reference in ECX, c in YMM0,
// d in [XMM3:XMM4].
// Register space was insufficient for b, but not for d.
// Return value in [YMM0:YMM3].
hva4 __vectorcall example6(hva2 a, hva4 b, __m256 c, hva2 d) {
   return b;
}

int __cdecl main( void )
{
   hva4 h4;
   hva2 h2;
   int i;
   float f;
   __m128 a, b, d;
   __m256 c, e;

   a = b = d = _mm_set1_ps(3.0f);
   c = e = _mm256_set1_ps(5.0f);
   h2.array[0] = _mm_set1_ps(6.0f);
   h4.array[0] = _mm256_set1_ps(7.0f);

   b = example1(a, b, c, d, e);
   e = example2(1, b, 3, d, e, 6.0f, 7);
   d = example3(1, h2, 3, 4, 5);
   f = example4(1, 2.0f, h4, d, 5);
   i = example5(1, h2, 3, h4, 5);
   h4 = example6(h2, h4, c, h2);
}
```

**End Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)