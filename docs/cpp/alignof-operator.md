---
title: __alignof işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- alignas_cpp
- __alignof_cpp
- alignof_cpp
dev_langs:
- C++
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a7ab2eb5f33db2a62e745756971ee29f84c25c8
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408538"
---
# <a name="alignof-operator"></a>__alignof İşleci
C ++ 11 tanıtır **alignof** bayt belirtilen türün hizalama döndüren işleci. En fazla taşınabilirlik için Microsoft'a özgü __alignof işleci yerine alignof işleci kullanmanız gerekir.  
  
 **Microsoft'a özgü**  
  
 Türünde bir değer döndürür `size_t` hizalama gereksinimi olan türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  __alignof( type )
```  
  
## <a name="remarks"></a>Açıklamalar  
 Örneğin:  
  
|İfade|Değer|  
|----------------|-----------|  
|**__alignof (karakter)**|1.|  
|**__alignof (kısa)**|2|  
|**__alignof (int)**|4|  
|**__alignof ( \__int64)**|8|  
|**__alignof (kayan nokta)**|4|  
|**__alignof (çift)**|8|  
|**__alignof (char\* )**|4|  
  
 **__Alignof** değerdir aynı değeri olarak `sizeof` temel türleri için. , Ancak bu örneği göz önünde bulundurun:  
  
```cpp 
typedef struct { int a; double b; } S;  
// __alignof(S) == 8  
```  
  
 Bu durumda, **__alignof** yapısındaki en büyük öğenin hizalama gereksinimi değerdir.  
  
 Benzer şekilde,  
  
```cpp 
typedef __declspec(align(32)) struct { int a; } S;  
```  
  
 `__alignof(S)` eşittir `32`.  
  
 Bir kullanımı **__alignof** kendi bellek ayırma yordamlarınızın birine bir parametre olarak olacaktır. Yapı aşağıdaki ' gibi tanımlı `S`, adlı bir bellek ayırma yordam çağırabilir `aligned_malloc` belirli hizalama sınırındaki bellek ayrılamadı.  
  
```cpp 
typedef __declspec(align(32)) struct { int a; double b; } S;  
int n = 50; // array size  
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));  
```  
  
 Hizalama değiştirme hakkında daha fazla bilgi için bkz:  
  
-   [pack](../preprocessor/pack.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [__unaligned](../cpp/unaligned.md)  
  
-   [/Zp (Yapı Üyesi Hizalama)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Yapı hizalama örnekleri](../build/examples-of-structure-alignment.md) (x64 belirli)  
  
 Hizalama x86 ve x64 kodda farklılıklar hakkında daha fazla bilgi için bkz:  
  
-   [x86 Derleyicisi ile Çakışma](../build/conflicts-with-the-x86-compiler.md)  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)