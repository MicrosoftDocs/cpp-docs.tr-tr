---
title: Sayısal, Boole ve işaretçi değişmez değerleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- literals, C++
- constants, literals
- literals [C++]
ms.assetid: 17c09fc3-3ad7-47e2-8b48-ba8ae994edc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 178c75efa84ebc7d27c19feb81e81314dc4c5bd7
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948135"
---
# <a name="numeric-boolean-and-pointer-literals--c"></a>Sayısal, Boole ve işaretçi değişmez değerleri (C++)
Bir sabit değer doğrudan bir değeri temsil eden bir program öğesidir. Bu makale türü tamsayı sabit değerleri kapsar kayan nokta, Boole ve işaretçi. Dize ve karakter değişmez değerleri hakkında daha fazla bilgi için bkz. [dize ve karakter değişmez değerleri (C++)](../cpp/string-and-character-literals-cpp.md). Ayrıca, herhangi kategorilerine göre kendi değişmez değerleri tanımlayabilirsiniz; Daha fazla bilgi için [kullanıcı tanımlı değişmez değerler (C++)](../cpp/user-defined-literals-cpp.md)  
  
 biçimindeki telefon numarasıdır. Adlandırılmış değişkenlerini başlatmak ve İşlevler bağımsız değişkenleri geçirmek için yaygın olarak birçok bağlamları, ancak çoğu değişmez değerleri kullanabilirsiniz:  
  
```cpp 
const int answer = 42; // integer literal  
double d = sin(108.87);     //floating point literal passed to sin function  
bool b = true;              // boolean literal  
MyClass* mc = nullptr;      // pointer literal  
  
```  
  
 Bazen derleyicinin bir sabit değer yorumlama ya da ona vermek için belirli ne tür bildirmek önemlidir. Ön eklerin veya soneklerin değişmez değer ekleyerek bunu yapabilirsiniz. Örneğin, önek 0 x bir onaltılık değer, örneğin 0x35 takip eden sayısı olarak yorumlamak üzere söyler. TAM soneki değeri değerlendirilecek derleyiciye bir **işaretsiz long long** 5894345ULL olduğu gibi bir tür. Ön ekleri tam listesi için aşağıdaki bölümlere ve her değişmez değer türü soneklerini bakın.  
  
## <a name="syntax"></a>Sözdizimi  
  
## <a name="integer-literals"></a>Tamsayı sabit değerleri  
 Tamsayı sabit değerlerinde, bir rakam ile başlamalı ve hiç kesirli bölümleri veya üsleri olmayan. Tamsayı sabit değerlerinde ondalık, sekizlik veya onaltılık biçiminde belirtebilirsiniz. İşaretli veya işaretsiz türleri ve uzun veya kısa türleri belirtebilirler.  
  
 Hiçbir ön ek veya sonek varsa, derleyici bir tamsayı değişmez değer türü sunacak **int** (32 bit) değeri alabileceğinden, aksi takdirde, verir, türü **uzun uzun** (64 bit).  
  
 Bir ondalık tamsayı sabit değeri belirtmek için belirtimi sıfır olmayan basamakla başlayın. Örneğin:  
  
```cpp 
int i = 157;   // Decimal literal  
int j = 0198;       // Not a decimal number; erroneous octal literal  
int k = 0365;       // Leading zero specifies octal literal, not decimal  
int m = 36'000'000  // digit separators make large values more readable  
int   
```  
  
 Sekizlik bir tamsayı sabit değeri belirtmek için belirtime 0, 0 ila 7 basamaktan oluşan bir diziyle ardından başlayın. 8 ve 9 basamakları, sekizlik bir sabit değer belirtilirken hatalardır. Örneğin:  
  
```cpp 
int i = 0377;   // Octal literal  
int j = 0397;        // Error: 9 is not an octal digit  
```  
  
 Onaltılık bir tamsayı sabit değeri belirtmek için belirtime başlamak `0x` veya `0X` ("x" durumunda, aralığındaki basamaklardan oluşan bir diziyle ardından önemli değildir) `0` aracılığıyla `9` ve `a` (veya `A`) aracılığıyla `f` (veya `F`). `a` (veya `A`) ile `f` (veya `F`) arasındaki onaltılık basamaklar, 10 ile 15 aralığındaki değerleri temsil eder. Örneğin:  
  
```cpp 
int i = 0x3fff;   // Hexadecimal literal  
int j = 0X3FFF;        // Equal to i  
```  
  
 İşaretsiz bir türü belirtmek için kullanın `u` veya `U` soneki. Uzun bir tür belirtmek için kullanın `l` veya `L` soneki. Bir 64-bit tamsayı türünü belirtmek için LL veya tümünü sonekini kullanın. İ64 sonekini hala desteklenmektedir, ancak Microsoft'a özgüdür ve taşınabilir değildir çünkü kaçınılmalıdır. Örneğin:  
  
```cpp 
unsigned val_1 = 328u;             // Unsigned value  
long val_2 = 0x7FFFFFL;                 // Long value specified   
                                        //  as hex literal  
unsigned long val_3 = 0776745ul;        // Unsigned long value  
auto val_4 = 108LL;                           // signed long long  
auto val_4 = 0x8000000000000000ULL << 16;     // unsigned long long   
```  
  
 **Rakam ayırıcıları**: bunları insanlar okunmasını kolaylaştırmak için daha büyük sayılar değerlerde yer ayırmak için tek tırnak işareti karakteri (kesme işareti) kullanabilirsiniz. Ayırıcılar derleme üzerinde etkisi yoktur.  
  
```cpp 
long long i = 24'847'458'121  
```  
  
## <a name="floating-point-literals"></a>Kayan nokta değişmez değerleri  
 Kayan noktalı sabit değerleri kesirli bir kısmı gereken değerleri belirtin. Bu değerler ondalık noktası içerir (**.**) ve Üstel sayı içerebilir.  
  
 Kayan noktalı sabit değerleri "sayısı,"sayı büyüklüğünü belirten bir üs"ve değişmez değerin alacağı türünü belirten isteğe bağlı bir sonek değeri belirten bir Mantis," vardır. Mantis bir nokta, isteğe bağlı bir sayının kesirli kısmını temsil eden bir basamak dizisi tarafından izlediği bir basamak dizisi olarak belirtilir. Örneğin:  
  
```cpp 
18.46  
38.  
```  
  
 Üs varsa, büyüklük sayının 10 üssü aşağıdaki örnekte gösterildiği gibi belirtir:  
  
```cpp 
18.46e0      // 18.46  
18.46e1           // 184.6  
```  
  
 Üs kullanırken belirtilebilir `e` veya `E`, bir isteğe bağlı işaretiyle birlikte aynı anlama sahiptir (+ veya -) ve bir basamak dizisi.  Sondaki ondalık gibi bir üs varsa, tam sayı olarak gerekli değildir. `18E0`.  
  
 Kayan noktalı sabit değerleri türü varsayılan **çift**. Sonekleri kullanarak `f` veya `l` (veya `F` veya `L` — soneki büyük küçük harfe duyarlı değil), değişmez değer olarak belirtilen **float** veya **uzun çift**, sırasıyla.  
  
 Ancak **uzun çift** ve **çift** aynı gösterimi vardır, bunlar aynı türde değil. Örneğin, sizin gibi işlevleri aşırı yüklenmiş  
  
```cpp 
void func( double );  
```  
  
 and  
  
```cpp 
void func( long double );  
```  
  
## <a name="boolean-literals"></a>Boole sabit değerleri  
 Boole sabit değerler **true** ve **false**.  
  
## <a name="pointer-literal-c11"></a>İşaretçi sabit değeri (C ++ 11)  
 C++'ı tanıtır [nullptr](../cpp/nullptr.md) literal sıfır başlatılmayan bir işaretçi belirtin. Taşınabilir kodda **nullptr** integral türünden sıfır ya da NULL gibi makrolar yerine kullanılmalıdır.  
  
## <a name="binary-literals-c14"></a>İkili sabit dizeler (C ++ 14)  
 Bir ikili sabit değerinin kullanımı tarafından belirtilebilir `0B` veya `0b` 1 ve 0'ın bir dizi tarafından izlenen öneki:  
  
```cpp 
  
auto x = 0B001101 ; // int  
auto y = 0b000001 ; // int  
```  
  
## <a name="avoid-using-literals-as-magic-constants"></a>Sabit değerleri "Sihirli sabitler" kullanmaktan kaçının  
 Her zaman iyi bir programlama olmamasına karşın, doğrudan ifadeleri ve deyimlerini'deki değişmez değerleri kullanabilirsiniz:  
  
```cpp 
if (num < 100)  
    return "Success";  
  
```  
  
 Önceki örnekte, düz bir anlamı, örneğin "MAXIMUM_ERROR_THRESHOLD" ileten bir adlandırılmış sabiti kullanmak daha iyi olabilir. Ve "Başarılı", son kullanıcılar, ardından tarafından görülür. döndürülen değer, burada diğer dile yerelleştirilebilen bir dosyadan tek bir konumda depolanan bir adlandırılmış dize sabit kullanılması daha iyidir. Adlandırılmış sabitler kullanmak, diğerlerinin yanı sıra kodun amacı anlamak için kendinize yardımcı olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sözcük kuralları](../cpp/lexical-conventions.md)   
 [C++ dize değişmez değerleri](../cpp/string-and-character-literals-cpp.md)   
 [C++ kullanıcı tanımlı değişmez değerler](../cpp/user-defined-literals-cpp.md)