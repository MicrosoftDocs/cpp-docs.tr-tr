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
ms.openlocfilehash: 8ce5f2c6703b18747dd4a2c51fe540d01370b38b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="numeric-boolean-and-pointer-literals--c"></a>Sayısal, Boole ve işaretçi değişmez değerleri (C++)
Bir hazır değer doğrudan bir değeri temsil eden bir program öğedir. Bu makale değişmez değerleri tamsayı türünde kapsamaktadır kayan nokta, Boole ve işaretçi. Dize ve karakter değişmez değerleri hakkında daha fazla bilgi için bkz: [dize ve karakter değişmez değerleri (C++)](../cpp/string-and-character-literals-cpp.md). Ayrıca, tüm Bu kategoriler göre kendi değişmez değerleri tanımlayabilirsiniz; Daha fazla bilgi için bkz: [kullanıcı tanımlı değişmez değerler (C++)](../cpp/user-defined-literals-cpp.md)  
  
 biçimindeki telefon numarasıdır. Değişmez değerler birçok bağlamları, ancak en yaygın olarak adlandırılmış değişkenleri başlatılamadı ve işleve bağımsız değişkenler geçirmek için kullanabilirsiniz:  
  
```  
const int answer = 42; // integer literal  
double d = sin(108.87);     //floating point literal passed to sin function  
bool b = true;              // boolean literal  
MyClass* mc = nullptr;      // pointer literal  
  
```  
  
 Bazen bir hazır değer yorumlama ya da ona vermek için belirli ne tür derleyici bildirmek önemlidir. Bunun için önekleri veya sonekleri için sabit ekleyerek. Örneğin, önek 0 x derleyici 0x35 onaltılık değer olarak, örneğin izleyen sayısını yorumlayabilir söyler. TAM soneki değeri kabul et bildirir bir `unsigned long long` 5894345ULL olduğu gibi türü. Önekleri tam listesi için aşağıdaki bölümleri ve sonekleri her değişmez değer türü için bkz.  
  
## <a name="syntax"></a>Sözdizimi  
  
## <a name="integer-literals"></a>Tamsayı değişmez değerleri  
 Tamsayı değişmez değerleri bir rakamla başlamalı ve hiç kesirli bölümleri veya üs. Ondalık, sekizlik ve onaltılık biçimde tamsayı değişmez değerler belirtebilirsiniz. İşaretli veya işaretsiz türleri ve uzun veya kısa türleri belirtebilirler.  
  
 Derleyici hiçbir önek veya sonek mevcut olduğunda, bir tam sayı değişmez değer türü verecektir `int` (32 bit), değerini uygun değilse, aksi takdirde, verir, türü `long long` (64 bit).  
  
 Ondalık bir tam sayı sabit değeri belirtmek için sıfır olmayan bir basamak belirtimiyle başlayın. Örneğin:  
  
```  
int i = 157;   // Decimal literal  
int j = 0198;       // Not a decimal number; erroneous octal literal  
int k = 0365;       // Leading zero specifies octal literal, not decimal  
int m = 36'000'000  // digit separators make large values more readable  
int   
```  
  
 Sekizlik tam sayı sabit değeri belirtmek için 0, 0 ile 7 arasındaki aralığı basamak dizisi arkasından belirtimiyle başlayın. 8 ve 9 basamak sekizlik değişmez değeri belirterek hataları var. Örneğin:  
  
```  
int i = 0377;   // Octal literal  
int j = 0397;        // Error: 9 is not an octal digit  
```  
  
 Onaltılık bir tam sayı sabit değeri belirtmek için belirtimiyle başlamak `0x` veya `0X` ("x" durumunda, bir aralıktaki rakam dizisini arkasından önemli değildir) `0` aracılığıyla `9` ve `a` (veya `A`) aracılığıyla `f` (veya `F`). `a` (veya `A`) ile `f` (veya `F`) arasındaki onaltılık basamaklar, 10 ile 15 aralığındaki değerleri temsil eder. Örneğin:  
  
```  
int i = 0x3fff;   // Hexadecimal literal  
int j = 0X3FFF;        // Equal to i  
```  
  
 İşaretsiz tür belirtmek için kullanın ya da **u** veya **U** soneki. Uzun türünü belirtmek için kullanın ya da **l** veya **L** soneki. 64 bit tam sayı türünü belirtmek için ÜM veya üm sonekini kullanın. I64 soneki hala desteklenmektedir ancak Microsoft'a özgüdür ve taşınabilir değil çünkü kaçınılmalıdır. Örneğin:  
  
```  
unsigned val_1 = 328u;             // Unsigned value  
long val_2 = 0x7FFFFFL;                 // Long value specified   
                                        //  as hex literal  
unsigned long val_3 = 0776745ul;        // Unsigned long value  
auto val_4 = 108LL;                           // signed long long  
auto val_4 = 0x8000000000000000ULL << 16;     // unsigned long long   
```  
  
 **Basamak ayırıcıları**: Yerleştir değerleri okumaya insanlar için kolaylaştırmak için büyük sayılar ayırmak için tek tırnak karakteri (kesme) kullanabilirsiniz. Ayırıcılar derleme üzerinde hiçbir etkisi yoktur.  
  
```  
long long i = 24'847'458'121  
```  
  
## <a name="floating-point-literals"></a>Kayan nokta değişmez değerleri  
 Kayan nokta değişmez değerleri ondalık bir bölümü olmalıdır değerlerini belirtin. Bu değerleri ondalık basamak içeren (**.**) ve üs içerebilir.  
  
 Kayan nokta değişmez değerler "sayısı,"sayının büyüklük belirten bir üs"ve sabit 's türünü belirten isteğe bağlı bir sonek değeri belirten bir Mantis," vardır. Mantis bir noktayla isteğe bağlı bir sayının kesirli kısmını temsil eden basamak dizisi tarafından izlediği basamak dizisi olarak belirtilir. Örneğin:  
  
```  
18.46  
38.  
```  
  
 Üs varsa, sayının büyüklük 10 gücünü aşağıdaki örnekte gösterildiği gibi belirtir:  
  
```  
18.46e0      // 18.46  
18.46e1           // 184.6  
```  
  
 Üs kullanılarak belirtilebilir **e** veya **E**, isteğe bağlı bir işaretiyle birlikte aynı anlamı olan (+ veya -) ve bir rakam dizisini.  Sondaki ondalık gibi bir üs varsa, tam sayı olarak gerekli değildir. `18E0`.  
  
 Kayan nokta değişmez değerler varsayılan yazmak için **çift**. Sonekleri kullanarak **f** veya **l** (veya **F** veya **L** — soneki büyük küçük harfe duyarlı değil), sabit değer olarak belirtilen  **float** veya `long double`sırasıyla.  
  
 Ancak `long double` ve **çift** aynı gösterimi vardır, bunlar aynı türde değil. Örneğin, size gibi işlevler aşırı  
  
```  
void func( double );  
```  
  
 and  
  
```  
void func( long double );  
```  
  
## <a name="boolean-literals"></a>Boole değişmez değerleri  
 Boole sabit değerleri olan `true` ve `false`.  
  
## <a name="pointer-literal-c11"></a>İşaretçi değişmez değer (C ++ 11)  
 C++ tanıtır [nullptr](../cpp/nullptr.md) sıfır başlatılmış bir işaretçi belirtmek için hazır. Taşınabilir kodda `nullptr` integral türü sıfır ya da NULL gibi makroları yerine kullanılmalıdır.  
  
## <a name="binary-literals-c14"></a>İkili değişmez değerleri (C ++ 14)  
 İkili bir hazır değer tarafından kullanımını belirtilebilir `0B` veya `0b` bir dizi 1 ve 0'ın tarafından izlenen öneki:  
  
```  
  
auto x = 0B001101 ; // int  
auto y = 0b000001 ; // int  
```  
  
## <a name="avoid-using-literals-as-magic-constants"></a>Değişmez değerler "Sihirli sabitleri" kullanmaktan kaçının  
 Her zaman uygulama programlama iyi olmasa da değişmez değerlerine doğrudan ifadeleri ve deyimleri kullanabilirsiniz:  
  
```  
if (num < 100)  
    return "Success";  
  
```  
  
 Önceki örnekte, örneğin "MAXIMUM_ERROR_THRESHOLD" net bir anlamı ilettiği adlandırılmış bir constant kullanmak daha iyi olabilir. Ve "Başarılı" son kullanıcılar, sonra da tarafından görülen dönüş değeri olabilir, daha iyi bir dosyadan diğer dillere burada yerelleştirilebilir tek bir konumda depolanan bir adlandırılmış dize sabiti kullanın. Adlı sabitler kullanarak, diğerlerinin yanı sıra kendiniz kod amacı anlamak için yardımcı olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sözcük kuralları](../cpp/lexical-conventions.md)   
 [C++ dize değişmez değerleri](../cpp/string-and-character-literals-cpp.md)   
 [C++ kullanıcı tanımlı değişmez değerler](../cpp/user-defined-literals-cpp.md)