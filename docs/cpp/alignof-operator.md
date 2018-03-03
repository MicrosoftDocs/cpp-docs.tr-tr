---
title: "__alignof işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: faceca31928d9c49f3c1cf5b933a65767ece7453
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="alignof-operator"></a>__alignof İşleci
C ++ 11 tanıtır `alignof` uyumu, belirtilen türdeki bayt cinsinden döndürür işleci. En fazla taşınabilirlik için Microsoft'a özgü __alignof işleci yerine alignof işleci kullanmanız gerekir.  
  
 **Microsoft Specific**  
  
 Türünde bir değer döndürür **size_t** diğer bir deyişle hizalama gereksinim türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  __alignof( type )
```  
  
## <a name="remarks"></a>Açıklamalar  
 Örneğin:  
  
|İfade|Değer|  
|----------------|-----------|  
|**__alignof (karakter)**|1.|  
|**__alignof (kısa)**|2|  
|**__alignof (int)**|4|  
|**__alignof( \__int64 )**|8|  
|**__alignof (kayan nokta)**|4|  
|**__alignof( double )**|8|  
|**__alignof (char\* )**|4|  
  
 `__alignof` Değerdir değeri ile aynı `sizeof` temel türleri için. , Ancak bu örnek göz önünde bulundurun:  
  
```  
typedef struct { int a; double b; } S;  
// __alignof(S) == 8  
```  
  
 Bu durumda, `__alignof` yapısındaki en büyük öğesinin hizalama gereksinim bir değerdir.  
  
 Benzer şekilde,  
  
```  
typedef __declspec(align(32)) struct { int a; } S;  
```  
  
 `__alignof(S)`eşittir `32`.  
  
 Bir kullanım için `__alignof` kendi bellek ayırma yordamları birine bir parametre olarak olacaktır. Yapısı aşağıdaki ' Örneğin, tanımlı `S`, adlandırılmış bir bellek ayırma yordam çağırabilirsiniz `aligned_malloc` belirli hizalama sınırında bellek ayıramadı.  
  
```  
typedef __declspec(align(32)) struct { int a; double b; } S;  
int n = 50; // array size  
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));  
```  
  
 Hizalama değiştirme hakkında daha fazla bilgi için bkz:  
  
-   [pack](../preprocessor/pack.md)  
  
-   [Hizalama](../cpp/align-cpp.md)  
  
-   [__unaligned](../cpp/unaligned.md)  
  
-   [/Zp (Yapı Üyesi Hizalama)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Yapı hizalama örnekleri](../build/examples-of-structure-alignment.md) (x64 belirli)  
  
 Hizalama x86 hem x64 ilişkin kodda farklar hakkında daha fazla bilgi için bkz:  
  
-   [x86 Derleyicisi ile Çakışma](../build/conflicts-with-the-x86-compiler.md)  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)