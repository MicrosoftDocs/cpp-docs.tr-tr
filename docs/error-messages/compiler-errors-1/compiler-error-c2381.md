---
title: Derleyici Hatası C2381 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2381
dev_langs:
- C++
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bd5f5edcf95144333524c41b803c24b728a621f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225283"
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