---
title: Derleyici Hatası C2762 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2762
dev_langs:
- C++
helpviewer_keywords:
- C2762
ms.assetid: 8b81a801-fd48-40a1-8bee-0748795b12e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb2ab9324639cb4f1e47858f9601c314b25fb96f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234074"
---
# <a name="compiler-error-c2762"></a>Derleyici Hatası C2762
'class': 'bağımsız değişkeni' için bir şablon bağımsız değişken olarak geçersiz bir ifade  
  
 Kullanırken [/Za](../../build/reference/za-ze-disable-language-extensions.md), derleyici gösteren bir işaretçi bir integral biçimine dönüştürmez.  
  
 Aşağıdaki örnek C2762 oluşturur:  
  
```  
// C2762.cpp  
// compile with: /Za  
template<typename T, T *pT>  
class X2 {};  
  
void f2() {  
   X2<int, 0> x21;   // C2762  
   // try the following line instead  
   // X2<int, static_cast<int *>(0)> x22;  
}  
```