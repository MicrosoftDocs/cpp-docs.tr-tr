---
title: __vectorcall | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 1c95ed59-86c6-4857-b4ed-10519193f851
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e61efe58ae718e7381d6404f54c0887f556ac34c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vectorcall"></a>__vectorcall
**Microsoft özel**  
  
 `__vectorcall` Çağırma bağımsız değişkenlerinin işlevlere Yazmaçları, mümkün olduğunda geçirilecek olduğunu belirtir. `__vectorcall`' den bağımsız değişkenler için daha fazla kayıtlarını kullanır [__fastcall](../cpp/fastcall.md) veya varsayılan [çağırma x64](../build/overview-of-x64-calling-conventions.md) kullanın. `__vectorcall` Çağırma yalnızca desteklenen yerel kodda Streaming SIMD Extensions 2 (SSE2) dahil x86 hem x64 işlemciler ve üstü. Kullanım `__vectorcall` Yazmaçları yüklenen geçmesi birkaç kayan nokta işlevleri veya SIMD vektör bağımsız hızlandırmak ve bağımsız değişkenler yararlanmak işlemleri gerçekleştirmek için. Aşağıdaki liste x86 hem x64 uygulamalar için ortak olan özellikleri gösterir `__vectorcall`. Farkları bu makalenin sonraki bölümlerinde açıklanmıştır.  
  
|Öğe|Uygulama|  
|-------------|--------------------|  
|C ad düzenlemesi kuralı|İşlev adları, iki "at" işareti (@@) parametre listesinde (ondalık) bayt sayısı ve ardından sonekine.|  
|Durum çevirisi kuralları|Servis talebi çeviri gerçekleştirilir.|  
  
 Kullanarak [/GV](../build/reference/gd-gr-gv-gz-calling-convention.md) derleyici seçeneği olarak derlemek için modüldeki her işlevi neden `__vectorcall` üye işlevi işlevi olmadığı sürece, çakışan arama kuralı özniteliğiyle bildirilmiş, kullanan bir `vararg` değişken bağımsız değişken listesi ya da adına sahip `main`.  
  
 Kayıttaki tarafından üç tür bağımsız değişkenler geçirebilirsiniz `__vectorcall` işlevleri: *tamsayı türü* değerleri, *vektör türü* değerleri ve *homojen vektör toplama* (HVA ) değerleri.  
  
 Bir tamsayı türü iki gereksinimlerini karşılayan: işlemci yerel kayıt boyutunu uygun — Örneğin, 4 bayt x x86 makine ya da x x64 8 bayt makine — ve yeniden kendi bit değiştirmeden kayıt uzunluğu ve geri tamsayıya dönüştürülebilir gösterimi. Örneğin, yükseltilebilir hiçbir türü `int` x86 üzerinde (`long long` x64 üzerinde) — Örneğin, bir `char` veya `short`— veya, dönüştürülür için `int` (`long long` x64 üzerinde) ve değişikliği bir tamsayıdır olmadan özgün türüne yeniden geri yazın. Tamsayı türleri işaretçi, başvuru içerir ve `struct` veya `union` türleri 4 bayt (x64 8 bayt) veya daha az. X64 üzerinde platformları, büyük `struct` ve `union` türleri, çağıran tarafından; x86 ayrılmış bellek referansı tarafından geçirilir platformları, bunlar geçirilir değeriyle yığında.  
  
 Bir kayan nokta türlerinden vektör türüdür — Örneğin, bir `float` veya `double`— veya SIMD vektör türü — örneğin, `__m128` veya `__m256`.  
  
 Aynı vektör türlerine sahip en fazla dört veri üyeleri bileşik bir tür bir HVA türüdür. Bir HVA türü üyeleri vektör türü olarak aynı hizalama gereksinimi vardır. Bu, bir HVA örneğidir `struct` aynı vektör üç içerir ve 32-bayt hizalama tanımı:  
  
```cpp  
typedef struct {  
   __m256 x;  
   __m256 y;  
   __m256 z;  
} hva3;    // 3 element HVA type on __m256  
  
```  
  
 İşlevlerinizi açıkça ile bildirme `__vectorcall` ayrı olarak izin vermek için üst bilgi dosyaları'nın anahtar sözcüğü derlenmiş hatasız bağlamak için kod. İşlevleri kullanmak için örneklenmiş olmalıdır `__vectorcall`ve kullanılamayan bir `vararg` değişken uzunlukta bağımsız değişken listesi.  
  
 Üye işlevi kullanılarak bildirilmelidir `__vectorcall` tanımlayıcısı. Gizli `this` işaretçi tarafından register ilk tamsayı tür bağımsız değişkeni olarak geçirilir.  
  
 ARM makinelerde `__vectorcall` kabul edilir ve derleyici tarafından yoksayıldı.  
  
 Tanımlanan çıkış satır sonu, işlevi ise, statik olmayan sınıf üyesi işlevleri için arama kuralı değiştiricisi satır dışı tanımında belirtilen yok. Diğer bir deyişle, sınıfı statik olmayan üyeler için bildirim sırasında belirtilen çağırma noktasında tanımı varsayılır. Bu sınıf tanımını ele alalım:  
  
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
  
 `__vectorcall` Kuralı değiştiricisi çağırma belirtilmelidir gösteren bir işaretçi olduğunda bir `__vectorcall` işlevi oluşturulur. Sonraki örnekte bir `typedef` için bir işaretçi bir `__vectorcall` dört isteyen işlevi `double` bağımsız değişkenleri ve döndürür bir `__m256` değeri:  
  
```cpp  
typedef __m256 (__vectorcall * vcfnptr)(double, double, double, double);  
```  
  
## <a name="vectorcall-convention-on-x64"></a>x64 __vectorcall kuralına  
 `__vectorcall` Üzerinde x64 çağırma ek kayıtları yararlanmak için çağırma standart x64 genişletir. Tamsayı tür bağımsız değişkenleri ve vektör tür bağımsız değişkenleri bağımsız değişken listesinde konuma göre kayıtları eşlenir. HVA bağımsız değişkenleri kullanılmayan vektör kayıtları için ayrılır.  
  
 Soldan sağa doğru sırayla ilk dört bağımsız değişkenlerden biri tamsayı tür bağımsız değişkenleri olduğunuzda, bunlar bu konuma karşılık gelen kayıt defterinde geçirilen — RCX, RDX, R8 veya R9. Gizli `this` işaretçi ilk tamsayı tür bağımsız değişkeni olarak değerlendirilir. Bir HVA değişkeninde ilk dört bağımsız değişkenlerden biri kullanılabilir kasalar geçirilemez, çağıran ayrılmış bellek başvuru bunun yerine karşılık gelen tamsayı türü kayıttaki geçirilir. Tamsayı türü olan bağımsız değişkenlerden sonra dördüncü parametre konumunda yığında geçirilir.  
  
 Sırayla soldan doğru olan ilk altı bağımsız değişkenlerden biri tür bağımsız değişkenleri vektör, değer SSE vektör yazmaçlar 0 ile 5 arasında bağımsız değişken konuma göre olarak geçirilir. Kayan nokta ve `__m128` türleri geçirilir XMM kayıtları içinde ve `__m256` türleri YMM içinde geçirilen kaydeder. Bu, vektör türleri başvuruya göre yerine değeriyle geçirilir ve ek kayıtları kullanılır çünkü çağırma standart x64 farklıdır. Vektör tür bağımsız değişkenleri için ayrılan gölge yığın alanı 8 bayt sabittir ve [/homeparams](../build/reference/homeparams-copy-register-parameters-to-stack.md) seçeneği geçerli değildir. Yedinci ve üzeri parametre konumlarda vektör tür bağımsız değişkenleri, çağıran tarafından ayrılan bellek başvuruya yığında geçirilir.  
  
 Yazmaçları vektör bağımsız değişkenler için ayrılan sonra HVA bağımsız değişkenlerinin veri üyeleri, kullanılmayan vektör kayıtları XMM0 XMM5 için için artan sırada ayrılmış (veya YMM5, YMM0 için `__m256` türleri), var olduğu sürece yeterli kayıtları için kullanılabilir Tüm HVA. Aksi takdirde yeterli yazmaçlar kullanılabilen, HVA bağımsız değişken başvuru çağıran tarafından ayrılan bellek olarak geçirilir. HVA bağımsız değişken için yığın gölge alanı 8 bayt tanımsız içerikle düzeltilmiştir. HVA bağımsız değişkenleri Atanana kasalar sırayla soldan sağa parametre listesinde ve herhangi bir konuma olabilir. Yazmaçları vektör atanmayan konumlar bu konuma karşılık gelen tamsayı kaydını başvuruya göre geçirilir HVA bağımsız değişkenler ilk dört bağımsız değişkeni birinde. Yığına sonra dördüncü parametre konumunda başvuruya göre geçirilen HVA bağımsız değişkenleri.  
  
 Sonuçlarını `__vectorcall` işlevleri yazmaçlar mümkün olduğunda değeri döndürülür. Yapılar ve birleşimleri 8 bayt veya daha az, de dahil Tamsayı türünde sonuçlar RAX değeri döndürülür. Vektör türü sonuçları XMM0 veya YMM0, değer boyutuna bağlı olarak döndürülür. HVA sonuçları kayıtları XMM0:XMM3 veya öğesi boyutuna bağlı olarak YMM0:YMM3 değeri tarafından döndürülen her veri öğesi var. Karşılık gelen kasalar uymayan sonuç türleri, çağıran tarafından ayrılan bellek referansı tarafından döndürülür.  
  
 Yığın x64 çağrı yapan tarafından korunur uyarlamasını `__vectorcall`. Arayan giriş ve bitiş kodu ayırır ve çağrılan işlev yığını temizler. Bağımsız değişkenler sağdan sola yığına ve gölge yığın alanı Yazmaçları geçirilen bağımsız değişkenler için ayrılır.  
  
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
  
## <a name="vectorcall-convention-on-x86"></a>x86 __vectorcall kuralına  
 `__vectorcall` Kuralı aşağıdaki çağırma `__fastcall` kuralı 32 bit tamsayı tür bağımsız değişkenleri ve vektör türü ve HVA bağımsız değişkenler için SSE vektör kaydeder yararlanır.  
  
 Soldan sağa yerleştirilir doğru ECX ve EDX, sırasıyla parametre listesinde bulunan ilk iki tamsayı tür bağımsız değişkeni. Gizli `this` işaretçi ilk tamsayı tür bağımsız değişkeni olarak kabul edilir ve ECX geçirilir. İlk altı vektör tür bağımsız değişkenleri SSE vektör yazmaçlar 0 ile 5 arasında bağımsız değişken boyutuna bağlı olarak XMM veya YMM yazmaçlar içinde aracılığıyla değeriyle geçirilir.  
  
 İlk altı tür bağımsız değişkenleri soldan sağa geçirilir için SSE vektör yazmaçlar 0 ile 5 arasında değeriyle yan sırada vektör. Kayan nokta ve `__m128` türleri geçirilir XMM kayıtları içinde ve `__m256` türleri YMM içinde geçirilen kaydeder. Hiçbir gölge yığın alanı kaydı tarafından geçirilen vektör tür bağımsız değişkenleri için ayrılır. Yedinci ve sonraki vektör tür bağımsız değişkenleri, çağıran tarafından ayrılan bellek başvuruya yığında geçirilir. Derleyici Hatası sınırlandırılmasıdır [C2719](../error-messages/compiler-errors-2/compiler-error-c2719.md) bu bağımsız değişkenler için geçerli değildir.  
  
 Yazmaçları vektör bağımsız değişkenler için ayrılan sonra HVA bağımsız değişkenleri üyeleri için kullanılmayan vektör artan düzende ayrılır veri XMM5 XMM0 kaydeder (veya YMM5, YMM0 için `__m256` türleri), var olduğu sürece yeterli kayıtları için tüm kullanılabilir HVA. Değilse yeterli yazmaçlar kullanılabilen, HVA bağımsız değişken çağıran tarafından ayrılan bellek başvuruya yığında geçirilir. Yığın gölge boşluk HVA bağımsız değişken için ayrılır. HVA bağımsız değişkenleri Atanana kasalar sırayla soldan sağa parametre listesinde ve herhangi bir konuma olabilir.  
  
 Sonuçlarını `__vectorcall` işlevleri yazmaçlar mümkün olduğunda değeri döndürülür. Yapılar ve birleşimleri 4 bayt veya daha az, de dahil Tamsayı türünde sonuçlar EAX değeri döndürülür. Tamsayı türü yapılar veya birleşimler 8 bayt veya daha az EDX:EAX değeri döndürülür. Vektör türü sonuçları XMM0 veya YMM0, değer boyutuna bağlı olarak döndürülür. HVA sonuçları kayıtları XMM0:XMM3 veya öğesi boyutuna bağlı olarak YMM0:YMM3 değeri tarafından döndürülen her veri öğesi var. Diğer sonuç türleri, çağıran tarafından ayrılan bellek referansı tarafından döndürülür.  
  
 X86 uygulaması `__vectorcall` aşağıdaki sağdan sola çağıran ve çağrılan işlev yığına bağımsız değişkenleri kuralı temizler yığın yalnızca döndürmeden önce. Yazmaçları yerleştirilmez yalnızca bağımsız değişken yığına.  
  
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
  
 **Son Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız değişkeni geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)