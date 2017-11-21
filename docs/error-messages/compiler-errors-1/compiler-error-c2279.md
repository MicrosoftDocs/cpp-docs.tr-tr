---
title: "Derleyici Hatası C2279 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2279
dev_langs: C++
helpviewer_keywords: C2279
ms.assetid: 1b5c88ef-2336-49b8-9ddb-d61f97c73e14
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c6523db90f1d934c6c7cd715ed5fbd3b7d8ab64c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2279"></a>Derleyici Hatası C2279
özel durum belirtimi typedef bildiriminde görünemez.  
  
 Altında **/Za**, [özel durum belirtimleri](../../cpp/exception-specifications-throw-cpp.md) typedef bildiriminde izin verilmiyor.  
  
 Aşağıdaki örnek C2279 oluşturur:  
  
```  
// C2279.cpp  
// compile with: /Za /c  
typedef int (*xy)() throw(...);   // C2279  
typedef int (*xyz)();   // OK  
```