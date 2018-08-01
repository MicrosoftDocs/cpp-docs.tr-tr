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
ms.openlocfilehash: d8b6a56a0a1dce5d07007898dec486d0e3b080c4
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407695"
---
# <a name="explicit-specialization-of-function-templates"></a>İşlev Şablonlarının Açık Alt Uzmanlaşması
Bir işlev şablonu ile bu tür için işlev şablonunun açık uzmanlığı (geçersiz kılma) sağlayarak, belirli bir tür için özel bir davranış tanımlayabilirsiniz. Örneğin:  
  
```cpp
template<> void MySwap(double a, double b);  
```  
  
 Bu bildirim için farklı bir işlev tanımlamanızı sağlayan **çift** değişkenleri. Gibi şablon olmayan işlevlere, standart tür dönüştürmeleri (türünde bir değişken yükseltme gibi **float** için **çift**) uygulanır.  
  
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İşlev Şablonları](../cpp/function-templates.md)