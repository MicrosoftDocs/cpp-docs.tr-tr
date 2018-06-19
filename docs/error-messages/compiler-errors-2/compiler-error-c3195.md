---
title: Derleyici Hatası C3195 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3195
dev_langs:
- C++
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ce3c51da68b971c34d651826a9c84974957ac46
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33256897"
---
# <a name="compiler-error-c3195"></a>Derleyici Hatası C3195
'işleci': ayrılmıştır ve ref sınıfı veya değer türünün bir üyesi olarak kullanılamaz. CLR veya WinRT işleçleri 'işleci' anahtar sözcüğünü kullanarak tanımlanmış olması gerekir  
  
Derleyici Yönetilen Uzantılar için C++ söz dizimini kullanarak bir işleç tanımı algıladı. C++ söz dizimini işleçler için kullanmanız gerekir.  
  
Aşağıdaki örnek C3195 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C3195.cpp  
// compile with: /clr /LD  
#using <mscorlib.dll>  
value struct V {  
   static V op_Addition(V v, int i);   // C3195  
   static V operator +(V v, char c);   // OK for new C++ syntax   
};  
```