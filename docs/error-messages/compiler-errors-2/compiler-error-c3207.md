---
title: "Derleyici Hatası C3207 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3207
dev_langs:
- C++
helpviewer_keywords:
- C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04aecf7f37d7e631a9dc07c7f029257c274f6538
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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