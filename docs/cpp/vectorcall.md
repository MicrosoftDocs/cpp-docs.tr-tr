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
ms.openlocfilehash: 313a5a1b3620120223fde6ab864dc36284e70fa1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231058"
---
# <a name="__vectorcall"></a>__vectorcall

**Microsoft'a Özgü**

**`__vectorcall`** Çağırma kuralı, işlevler için bağımsız değişkenlerin, mümkün olduğunda yazmaçlara geçirileceğini belirtir. **`__vectorcall`**[`__fastcall`](../cpp/fastcall.md), varsayılan [x64 çağırma kuralı](../build/x64-calling-convention.md) kullanımından veya bu bağımsız değişkenler için daha fazla kayıt kullanır. **`__vectorcall`** Çağırma kuralı yalnızca, Streaming SIMD Extensions 2 (SSE2) ve üstünü içeren x86 ve x64 işlemcilerde yerel kodda desteklenir. **`__vectorcall`** Birkaç kayan noktalı veya SıMD vektör bağımsız değişkenini geçen ve Yazmaçlarda yüklenen bağımsız değişkenlerden faydalanan işlemleri gerçekleştiren işlevleri hızlandırmak için kullanın. Aşağıdaki listede, ' nin x86 ve x64 uygulamaları için ortak olan özellikler gösterilmektedir **`__vectorcall`** . Farklar bu makalenin ilerleyen kısımlarında açıklanmıştır.

|Öğe|Uygulama|
|-------------|--------------------|
|C ad dekorasyon kuralı|İşlev adları iki "at" işaretiyle ( \@ \@ ), ardından parametre listesindeki bayt sayısı (ondalık olarak) ile sonlardır.|
|Durum çevirisi kuralları|Durum çevirisi yapılmaz.|

[`/Gv`](../build/reference/gd-gr-gv-gz-calling-convention.md)Derleyici seçeneğinin kullanılması modüldeki her işlevin olarak derlenmesine neden olur **`__vectorcall`** ; işlev bir üye işlevi değilse, çakışan bir çağırma kuralı özniteliğiyle bildirilirse, `vararg` değişken bağımsız değişken listesini kullanır veya ada sahiptir `main` .

İşlevlerde kayıt yaparak üç tür bağımsız değişken geçirebilirsiniz **`__vectorcall`** : *tamsayı türü* değerleri, *vektör türü* değerleri ve *homojen vektör toplama* (HVA) değerleri.

Bir tamsayı türü iki gereksinimi karşılar: işlemcinin yerel kayıt boyutuna (örneğin, bir x86 makinesinde 4 bayt veya bir x64 makinede 8 bayt) sığar ve bu, kendi bit gösterimini değiştirmeden, kayıt uzunluğuna ve yeniden bir tamsayıya dönüştürülebilir. Örneğin, **`int`** x86 üzerinde (x64 üzerinde) Yükseltilecek herhangi bir tür ( **`long long`** Örneğin, bir veya), veya ' **`char`** a **`short`** **`int`** ( **`long long`** x64 üzerinde) ve değişiklik olmadan özgün türüne geri dönebilir. Tamsayı türleri, işaretçi, başvuru ve **`struct`** ya da **`union`** 4 baytlık (x64 üzerinde 8 bayt) veya daha az tür içerir. X64 platformlarında, daha büyük **`struct`** ve **`union`** türler çağıran tarafından ayrılan belleğe başvuruya göre geçirilir; x86 platformlarında, bu değerler yığındaki değere göre geçirilir.

Vektör türü, örneğin, veya gibi bir kayan nokta türüdür — Örneğin, veya **`float`** **`double`** **`__m128`** **`__m256`** .

HVA türü, aynı vektör türlerine sahip en fazla dört veri üyesini bileşik bir türdür. Bir HVA türü, üyelerinin vektör türüyle aynı hizalama gereksinimine sahiptir. Bu, **`struct`** üç özdeş vektör türü içeren ve 32 baytlık hizalamasına sahip BIR HVA tanımı örneğidir:

```cpp
typedef struct {
   __m256 x;
   __m256 y;
   __m256 z;
} hva3;    // 3 element HVA type on __m256
```

**`__vectorcall`** Ayrı koda derlenmiş kodun hatasız olarak bağlanmasına izin vermek için işlevlerinizi üstbilgi dosyalarındaki anahtar sözcükle birlikte açık olarak bildirin. İşlevlerin kullanılması için prototipsiz olması gerekir **`__vectorcall`** ve `vararg` değişken uzunlukta bağımsız değişken listesi kullanamaz.

Bir üye işlevi, belirtici kullanılarak bildirilemeyebilir **`__vectorcall`** . Gizli **`this`** işaretçi, kayıt tarafından ilk tamsayı türü bağımsız değişkeni olarak geçirilir.

ARM makinelerinde, **`__vectorcall`** derleyici tarafından kabul edilir ve yok sayılır.

Statik olmayan sınıf üyesi işlevleri için, işlev satır dışı tanımlanmışsa, çağırma kuralı değiştiricisinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, sınıf statik olmayan üyeler için, bildirim sırasında belirtilen çağırma kuralı, tanım noktasında varsayılır. Bu sınıf tanımını ele alalım:

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

**`__vectorcall`** İşlev işaretçisi oluşturulduğunda çağırma kuralı değiştiricisi belirtilmelidir **`__vectorcall`** . Sonraki örnek, **`typedef`** **`__vectorcall`** dört **`double`** bağımsız değişken alan ve bir değer döndüren bir işlev işaretçisi için bir oluşturur **`__m256`** :

```cpp
typedef __m256 (__vectorcall * vcfnptr)(double, double, double, double);
```

Önceki sürümlerle uyumluluk için, **`_vectorcall`** **`__vectorcall`** derleyici seçeneği [ `/Za` \( dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) ' ın belirtildiği durumlar için bir eş anlamlı olur.

## <a name="__vectorcall-convention-on-x64"></a>x64 üzerinde __vectorcall kuralı

**`__vectorcall`** X64 üzerindeki çağırma kuralı, ek yazmaçların avantajlarından yararlanmak için standart x64 çağırma kuralını genişletir. Hem tamsayı türü bağımsız değişkenleri hem de vektör türü bağımsız değişkenleri, bağımsız değişken listesindeki konuma göre Yazmaçları ile eşleştirilir. HVA bağımsız değişkenleri kullanılmayan vektör kayıtlarına ayrılır.

Soldan sağa sıralı ilk dört bağımsız değişkenlerden biri tamsayı türü bağımsız değişkenleri olduğunda, bunlar o konuma karşılık gelen kasada geçirilir — RCX, RDX, R8 veya R9. Gizli bir **`this`** işaretçi, ilk tamsayı türü bağımsız değişkeni olarak değerlendirilir. İlk dört bağımsız değişkenden birindeki bir HVA bağımsız değişkeni kullanılabilir yazmaçlara geçirilmezse, buna karşılık gelen tamsayı türü kaydına bir çağrı ayrılmış bellek başvurusu geçirilir. Dördüncü parametre konumundan sonra tamsayı türü bağımsız değişkenleri yığına geçirilir.

Soldan sağa sıralı ilk altı bağımsız değişkenden herhangi biri vektör türü bağımsız değişkenleri olduğunda, bağımsız değişken konumuna göre SSE vektör Yazmaçları 0 ile 5 arasında bir değere geçirilir. Kayan nokta ve **`__m128`** türler XMM yazmaçlarında geçirilir ve **`__m256`** türler, KMM yazmaçlarında geçirilir. Bu, standart x64 çağırma kuralından farklıdır, çünkü vektör türleri başvuru yerine değere göre geçirilir ve ek Yazmaçları kullanılır. Vektör türü bağımsız değişkenleri için ayrılan gölge yığın alanı 8 bayt ile düzeltilir ve [`/homeparams`](../build/reference/homeparams-copy-register-parameters-to-stack.md) seçenek uygulanmaz. Yedinci ve sonraki parametre konumlarındaki vektör türü bağımsız değişkenleri, çağıran tarafından ayrılan belleğe başvuruya göre yığına geçirilir.

Kayıt, vektör bağımsız değişkenleri için ayrıldıktan sonra, HVA bağımsız değişkenlerinin veri üyeleri, **`__m256`** Tüm HVA için yeterli sayıda kayıt olduğu sürece, XMM0 to XMM5 (ya da YMM0 ila to YMM5 arasında, türler IÇIN to) için artan düzende ayrılır. Yeterli kayıt yoksa, HVA bağımsız değişkeni çağıran tarafından ayrılan belleğe başvuruya göre geçirilir. Bir HVA bağımsız değişkeni için yığın gölge alanı, tanımsız içerikle 8 bayt ile düzeltilir. HVA bağımsız değişkenleri, kayıt defterlerine, parametre listesinde soldan sağa doğru bir şekilde atanır ve herhangi bir konumda olabilir. Vektör kayıtlarına atanmayan ilk dört bağımsız değişkenden birindeki HVA bağımsız değişkenleri, bu konuma karşılık gelen tamsayı kaydındaki başvuruya göre geçirilir. Dördüncü parametre konumundan sonra başvuruya göre geçirilen HVA bağımsız değişkenleri yığına gönderilir.

İşlevlerin sonuçları **`__vectorcall`** , mümkün olduğunda Yazmaçlarda değer tarafından döndürülür. Yapı veya 8 bayt veya daha az birleşim dahil olmak üzere tamsayı türünün sonuçları, Kx değeri ile döndürülür. Vektör türü sonuçları, boyutuna bağlı olarak XMM0 veya YMM0 Ila içindeki değere göre döndürülür. HVA sonuçlarında, öğe boyutuna bağlı olarak, XMM0: XMM3 veya YMM0 Ila: YMM3 içindeki değer tarafından döndürülen her bir veri öğesi vardır. Karşılık gelen yazmaçlara sığmayan sonuç türleri, çağıran tarafından ayrılan belleğe başvuruya göre döndürülür.

Yığın, ' nin x64 uygulamasında çağıran tarafından korunur **`__vectorcall`** . Çağıran giriş ve bitiş kodu, çağrılan işlev için yığını ayırır ve temizler. Bağımsız değişkenler yığından sağdan sola gönderilir ve kayıt sırasında geçirilen bağımsız değişkenler için gölge yığın alanı ayrılır.

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

## <a name="__vectorcall-convention-on-x86"></a>x86 üzerinde __vectorcall kuralı

**`__vectorcall`** Çağırma kuralı **`__fastcall`** 32 bitlik tamsayı türü bağımsız değişkenlerinin kuralını izler ve vektör türü ve HVA bağımsız DEĞIŞKENLERI için SSE vektör yazmaçlarından yararlanır.

Parametre listesinde soldan sağa bulunan ilk iki tamsayı türü bağımsız değişkeni sırasıyla ECX ve EDX 'e yerleştirilir. Gizli bir **`this`** işaretçi ilk tamsayı türü bağımsız değişkeni olarak değerlendirilir ve ECX 'e geçirilir. İlk altı vektör türü bağımsız değişkeni, bağımsız değişken boyutuna bağlı olarak, XMM veya-mm yazmaçlarında, SSE vektör Yazmaçları 0 ile 5 arasında bir değere göre geçirilir.

Soldan sağa doğru sırada ilk altı vektör türü bağımsız değişkeni, SSE vektör Yazmaçları 0 ile 5 arasında bir değere göre geçirilir. Kayan nokta ve **`__m128`** türler XMM yazmaçlarında geçirilir ve **`__m256`** türler, KMM yazmaçlarında geçirilir. Yazmaç tarafından geçirilen vektör türü bağımsız değişkenleri için bir gölge yığın alanı ayrılmadı. Yedinci ve sonraki vektör türü bağımsız değişkenleri, çağıran tarafından ayrılan belleğe başvuruya göre yığına geçirilir. Derleyici hatası [C2719](../error-messages/compiler-errors-2/compiler-error-c2719.md) kısıtlaması bu bağımsız değişkenler için geçerlidir.

Kayıt, vektör bağımsız değişkenleri için ayrıldıktan sonra, HVA bağımsız değişkenlerinin veri üyeleri, **`__m256`** Tüm HVA için yeterli sayıda kayıt olduğu sürece, XMM0 to XMM5 (veya YMM0 ila to YMM5 arasında, Types IÇIN to) ile artan düzende ayrılır. Yeterli kayıt yoksa, HVA bağımsız değişkeni, çağıran tarafından ayrılan belleğe başvuruya göre yığına geçirilir. Bir HVA bağımsız değişkeni için yığın gölge alanı ayrılmamış. HVA bağımsız değişkenleri, kayıt defterlerine, parametre listesinde soldan sağa doğru bir şekilde atanır ve herhangi bir konumda olabilir.

İşlevlerin sonuçları **`__vectorcall`** , mümkün olduğunda Yazmaçlarda değer tarafından döndürülür. 4 baytlık veya daha az sayıda yapı veya birleşim dahil olmak üzere tamsayı türünün sonuçları EAX içindeki değere göre döndürülür. EDX: EAX içinde değer ile 8 baytlık veya daha az sayıda tamsayı türü oluşturulur. Vektör türü sonuçları, boyutuna bağlı olarak XMM0 veya YMM0 Ila içindeki değere göre döndürülür. HVA sonuçlarında, öğe boyutuna bağlı olarak, XMM0: XMM3 veya YMM0 Ila: YMM3 içindeki değer tarafından döndürülen her bir veri öğesi vardır. Diğer sonuç türleri, çağıran tarafından ayrılan belleğe başvuruya göre döndürülür.

' Nin x86 uygulamasını **`__vectorcall`** çağıran tarafından doğrudan yığına gönderilen bağımsız değişkenlerin kuralını izler ve çağrılan işlev yığının döndürülmeden hemen önce temizlenir. Yalnızca yazmaçlara yerleştirilmez olan bağımsız değişkenler yığına gönderilir.

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

**Son Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız değişken geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
