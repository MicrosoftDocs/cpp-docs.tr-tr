---
title: Derleyici Hatası C3120 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3120
dev_langs:
- C++
helpviewer_keywords:
- C3120
ms.assetid: 9b6b210f-9948-4517-a4cc-b4aaadebde68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e27d066d7d0a3c34adbbfe10cc7b4e39e563830
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247207"
---
# <a name="compiler-error-c3120"></a>Derleyici Hatası C3120
'method_name': arabirim yöntemleri değişken bağımsız değişken listesi alamaz  
  
 Arabirim yöntemi bir değişken bağımsız değişken listesi alınamıyor. Örneğin, aşağıdaki arabirim tanımı C3120 oluşturur:  
  
```  
// C3120.cpp  
__interface A {  
int X(int i, ...);    // C3120  
};  
  
int main(void) { return(0); }  
```