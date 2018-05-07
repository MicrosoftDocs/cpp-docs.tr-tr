---
title: Derleyici Hatası C2094 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2094
dev_langs:
- C++
helpviewer_keywords:
- C2094
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4db86a805118cbdbf74f21737b4a331fc59237c3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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