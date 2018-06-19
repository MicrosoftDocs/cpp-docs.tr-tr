---
title: Derleyici Hatası C3207 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3207
dev_langs:
- C++
helpviewer_keywords:
- C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0973b929e9feafeed3c2cde0b2b6e9e30996855
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251464"
---
# <a name="compiler-error-c3207"></a>Derleyici Hatası C3207
'function': 'arg', beklenen sınıf şablonu için geçersiz şablon bağımsız değişken  
  
 Bir şablon işlevi şablonu şablon bağımsız değişken alan olarak tanımlanır. Ancak, bir şablon türü bağımsız değişken geçirildi.  
  
 Aşağıdaki örnek C3207 oluşturur:  
  
```  
// C3207.cpp  
template <template <class T> class TT>  
void f(){}  
  
template <class T>  
struct S  
{  
};  
  
void f1()  
{  
   f<S<int> >();   // C3207  
   // try the following line instead  
   // f<S>();  
}  
```