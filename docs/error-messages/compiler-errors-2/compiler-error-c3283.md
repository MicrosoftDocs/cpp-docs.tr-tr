---
title: Derleyici Hatası C3283 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3283
dev_langs:
- C++
helpviewer_keywords:
- C3283
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bc23270d70a2fec1c0ac9cc5f6b96541085cfc6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249110"
---
# <a name="compiler-error-c3283"></a>Derleyici Hatası C3283
'type': arabirim örnek oluşturucu olamaz  
  
 Bir CLR [arabirimi](../../windows/interface-class-cpp-component-extensions.md) örnek oluşturucu sahip olamaz.  Statik Oluşturucu izin verilir.  
  
 Aşağıdaki örnek C3283 oluşturur:  
  
```  
// C3283.cpp  
// compile with: /clr  
interface class I {  
   I();   // C3283  
};  
```  
  
 Olası çözüm:  
  
```  
// C3283b.cpp  
// compile with: /clr /c  
interface class I {  
   static I(){}  
};  
```