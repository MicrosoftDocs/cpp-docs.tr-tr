---
title: "Derleyici Hatası C2381 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2381
dev_langs:
- C++
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5871a20eb09b11d47200575033f3a67b98864369
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2381"></a>Derleyici Hatası C2381
'function': şemadaki; __declspec(noreturn) farklıdır  
  
 Bir işlev bildirilen ve kullanılan tanımını tanımlanan [noreturn](../../cpp/noreturn.md) `__declspec` değiştiricisi. Kullanımını `noreturn` işlevi şemadaki oluşturduğunu; bildirim ve tanımı kullanılmasına kabul etmeniz `noreturn`.  
  
 Aşağıdaki örnek C2381 oluşturur:  
  
```  
// C2381.cpp  
// compile with: /c  
void f1();  
void __declspec(noreturn) f1() {}   // C2381  
void __declspec(noreturn) f2() {}   // OK  
```