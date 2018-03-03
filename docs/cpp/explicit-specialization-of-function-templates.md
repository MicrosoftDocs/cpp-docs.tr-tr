---
title: "İşlev şablonlarının açık alt Uzmanlaşması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58480c4f118a083dc7c9f97f3a0014e9d0cc294a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
