---
title: İşlev şablonlarının açık alt Uzmanlaşması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, functions
- function templates, specialization
- explicit specialization of function templates
- declaring functions [C++], specialization of function template
- specialization of function templates
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e35eda35a7d2474826ce151292121be224955420
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410739"
---
# <a name="explicit-specialization-of-function-templates"></a>İşlev Şablonlarının Açık Alt Uzmanlaşması
İşlev şablonu ile bu tür için bir açık alt uzmanlaşması (geçersiz kılma) işlevi şablonu sağlayarak belirli bir tür için özel bir davranış tanımlayabilirsiniz. Örneğin:  
  
```cpp
template<> void MySwap(double a, double b);  
```  
  
 Bu bildirim için farklı bir işlevi tanımlamanızı sağlar **çift** değişkenleri. Şablon olmayan işlevler, standart tür dönüşümleri gibi (türünde bir değişken yükseltme gibi **float** için **çift**) uygulanır.  
  
## <a name="example"></a>Örnek  
  
```cpp
// explicit_specialization.cpp  
template<class T> void f(T t)  
{  
};  
  
// Explicit specialization of f with 'char' with the  
// template argument explicitly specified:  
//  
template<> void f<char>(char c)  
{  
}  
  
// Explicit specialization of f with 'double' with the  
// template argument deduced:  
//  
template<> void f(double d)  
{  
}  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlev Şablonları](../cpp/function-templates.md)
