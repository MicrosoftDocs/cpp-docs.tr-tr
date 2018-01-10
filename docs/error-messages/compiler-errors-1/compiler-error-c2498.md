---
title: "Derleyici Hatası C2498 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2498
dev_langs: C++
helpviewer_keywords: C2498
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9adf1ef6c7ab5b178a054134115162db75771658
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2498"></a>Derleyici Hatası C2498
'function': 'novtable', yalnızca sınıf bildirimleri ya da tanımları uygulanabilir  
  
 Kullanarak bu hata oluşabilir `__declspec(novtable)` işleviyle.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2498 oluşturur:  
  
```  
// C2498.cpp  
// compile with: /c  
void __declspec(novtable) f() {}   // C2498  
class __declspec(novtable) A {};   // OK  
```