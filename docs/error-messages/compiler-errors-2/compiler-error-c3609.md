---
title: "Derleyici Hatası C3609 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3609
dev_langs: C++
helpviewer_keywords: C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86436a87c266fd21735f5afd5c7976fcb19f5e0d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3609"></a>Derleyici Hatası C3609
'member': korumalı veya son bir işlev sanal olmalıdır  
  
 [Korumalı](../../windows/sealed-cpp-component-extensions.md) ve [son](../../cpp/final-specifier.md) anahtar sözcükler yalnızca bir sınıf, yapı veya üye işlevi işaretlenmiş izin `virtual`.  
  
 Aşağıdaki örnek C3609 oluşturur:  
  
```  
// C3609.cpp  
// compile with: /clr /c  
ref class C {  
   int f() sealed;   // C3609  
   virtual int f2() sealed;   // OK  
};  
```  
