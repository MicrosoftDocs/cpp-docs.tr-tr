---
title: "Derleyici Hatası C2665 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2665
dev_langs: C++
helpviewer_keywords: C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5a349df2c60d746b6b090953362c7c6801e1f2a3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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