---
title: Derleyici Hatası C2665 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2665
dev_langs:
- C++
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18cc99d6ea0a45e7c096a13cfe57dc841ca351bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2665"></a>Derleyici Hatası C2665
'function': Sayı1 aşırı hiçbiri parametre sayı2 'type' türünden dönüştürülemiyor.  
  
 Aşırı yüklenmiş işlevinin parametresi gerekli türüne dönüştürülemiyor.  Olası çözümler:  
  
-   Bir dönüşüm işleci sağlayın.  
  
-   Açık dönüşüm kullanın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2665 oluşturur.  
  
```  
// C2665.cpp  
void func(short, char*){}  
void func(char*, char*){}  
  
int main() {  
   func(0, 1);   // C2665  
   func((short)0, (char*)1);   // OK  
}  
```