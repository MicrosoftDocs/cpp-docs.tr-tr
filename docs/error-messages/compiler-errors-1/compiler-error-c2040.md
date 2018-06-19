---
title: Derleyici Hatası C2040 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2040
dev_langs:
- C++
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6b19a5dd647e51efb46ef9798b7f7cdff5339b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167547"
---
# <a name="compiler-error-c2040"></a>Derleyici Hatası C2040
'işleci': 'identifier1' farklı 'identifier2' den yöneltme düzeylerinde  
  
 Belirtilen işlenenler içeren bir ifade uyumsuz işlenen türleri olan veya örtük olarak işlenen türleri dönüştürülür. Her iki işlenen aritmetik veya her ikisi de (dizi veya işaretçi gibi) nonarithmetic, bunlar değişiklik kullanılır. Bir işlenen aritmetik ise ve diğer değil, nonarithmetic işlenen türü için aritmetik işleç dönüştürülür.  
  
 Bu örnek C2040 oluşturur ve nasıl düzeltileceği gösterir.  
  
```  
// C2040.cpp  
// Compile by using: cl /c /W3 C2040.cpp  
bool test() {  
   char c = '3';  
   return c == "3"; // C2446, C2040  
   // return c == '3'; // OK  
}  
```