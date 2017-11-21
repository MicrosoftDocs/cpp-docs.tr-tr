---
title: "Derleyici Hatası C2147 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2147
dev_langs: C++
helpviewer_keywords: C2147
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f26a7df3605c01a56e8efcc0f569f9803a0755e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2147"></a>Derleyici Hatası C2147
sözdizimi hatası: ' tanımlayıcısıdır ' yeni bir anahtar sözcüğü  
  
 Tanımlayıcı, şu anda ayrılmış bir anahtar sözcük dilde kullanıldı.  
  
 Aşağıdaki örnek C2147 oluşturur:  
  
```  
// C2147.cpp  
// compile with: /clr  
int main() {  
   int gcnew = 0;   // C2147  
   int i = 0;   // OK  
}  
```