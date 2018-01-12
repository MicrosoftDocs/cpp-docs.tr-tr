---
title: "Derleyici Uyarısı (düzey 1) C4518 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4518
dev_langs: C++
helpviewer_keywords: C4518
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 187967bee0523529c71343fb04bc8793f44f7f0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4518"></a>Derleyici Uyarısı (düzey 1) C4518
'tanımlayıcısı': depolama sınıfı veya specifier(s) beklenmeyen burada; yazın göz ardı  
  
 Aşağıdaki örnek C4518 oluşturur:  
  
```  
// C4518.cpp  
// compile with: /c /W1  
_declspec(dllexport) extern "C" void MyFunction();   // C4518  
  
extern "C" void MyFunction();   // OK  
```