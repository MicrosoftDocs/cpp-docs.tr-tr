---
title: Derleyici Uyarısı (düzey 4) C4125 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4125
dev_langs:
- C++
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af7fdd16925f080137be386cb3d2dd0dd3d8b446
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293851"
---
# <a name="compiler-warning-level-4-c4125"></a>Derleyici Uyarısı (düzey 4) C4125
sekizli çıkış dizisi ondalık basamak sonlandırır  
  
 Derleyici sekizli sayı ondalık basamak olmadan değerlendirir ve bir karakter ondalık basamak olduğunu varsayar.  
  
## <a name="example"></a>Örnek  
  
```  
// C4125a.cpp  
// compile with: /W4  
char array1[] = "\709"; // C4125  
int main()  
{  
}  
```  
  
 9 basamak karakter olarak amaçlanıyorsa, örnek şu şekilde düzeltin:  
  
```  
// C4125b.cpp  
// compile with: /W4  
char array[] = "\0709";  // C4125 String containing "89"  
int main()  
{  
}  
```