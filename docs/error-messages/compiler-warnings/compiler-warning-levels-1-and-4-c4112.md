---
title: "Derleyici Uyarısı (düzey 1 ve 4) C4112 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4112
dev_langs:
- C++
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e82b2425aef840d8da7a0d0ad4dc4b81bd2a812
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Derleyici Uyarısı (düzey 1 ve 4) C4112
\#Satırı 1 ve sayı arasında bir tamsayı gerektirir  
  
 [#Line](../../preprocessor/hash-line-directive-c-cpp.md) yönergesi izin verilen aralığın dışında bir tamsayı parametre belirtir.  
  
 Belirtilen parametre 1'den az ise, satır sayacı 1 olarak sıfırlanır. Belirtilen parametre büyükse *numarası*sınırı derleyici tanımlı olduğundan, satır sayaç değiştirilmez. Bu düzey 1 uyarı ANSI Uyumluluğu altında değil ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ve düzey 4 uyarı Microsoft Uzantıları ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 Aşağıdaki örnek C4112 oluşturur:  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```