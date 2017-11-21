---
title: "Derleyici Hatası C2040 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2040
dev_langs: C++
helpviewer_keywords: C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3504c8e18637ef907d5ab9c941ef7ad550daedf0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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