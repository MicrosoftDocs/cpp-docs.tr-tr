---
title: "Derleyici Hatası C2094 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2094
dev_langs: C++
helpviewer_keywords: C2094
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f20930a38a429aba3e3959f57f937bbfa9962da9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2094"></a>Derleyici Hatası C2094
Etiket 'tanımlayıcısı' tanımlanmamış  
  
Tarafından kullanılan etiketi bir [goto](../../cpp/goto-statement-cpp.md) deyimi işlevinde yok.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C2094 oluşturur:  
  
```cpp  
// C2094.c  
int main() {  
   goto test;  
}   // C2094  
```  
  
 Olası çözüm:  
  
```cpp  
// C2094b.c  
int main() {  
   goto test;  
   test:   
   {  
   }  
}  
```