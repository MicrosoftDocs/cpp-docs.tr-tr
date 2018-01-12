---
title: "Derleyici Uyarısı (Düzey 3) C4359 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4359
dev_langs: C++
helpviewer_keywords: C4359
ms.assetid: d8fe993c-ef82-45a0-a43d-c29f9d1bacdb
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 654e58be8f70717d724c8cce1287629d2a396886
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4359"></a>Derleyici Uyarısı (Düzey 3) C4359
'type': Gerçek hizalama (8) __declspec(align()) içinde belirtilen değerden daha büyük  
  
 Türü için belirtilen hizalama veri üyelerine birinin türü hizalamasını küçüktür.  Daha fazla bilgi için bkz: [Hizala](../../cpp/align-cpp.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4359 oluşturur.  
  
```  
// C4359.cpp  
// compile with: /W3 /c  
struct __declspec(align(8)) C8 { __int64 i; };  
struct __declspec(align(4)) C4  { C8 m8; };   // C4359  
struct __declspec(align(8)) C8_b  { C8 m8; };   // OK  
struct __declspec(align(16)) C16  { C8 m8; };   // OK  
```