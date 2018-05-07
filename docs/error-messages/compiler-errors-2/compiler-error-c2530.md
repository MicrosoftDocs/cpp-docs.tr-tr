---
title: Derleyici Hatası C2530 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2530
dev_langs:
- C++
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b226ef5ca0e839c745e13d4118264a69ca408db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2530"></a>Derleyici Hatası C2530
'tanımlayıcısı': başvuruları başlatılmalı  
  
 Bunu bildirildi, zaten bildirilir sürece bir başvuru başlatması gerekir:  
  
-   Anahtar sözcüğüyle [extern](../../cpp/using-extern-to-specify-linkage.md).  
  
-   Sınıf, yapı veya birleşim üyesi olarak (ve oluşturucuda başlatılır).  
  
-   İşlevi bildiriminde ya da tanımı bir parametre olarak.  
  
-   Bir işlevin dönüş türü olarak.  
  
 Aşağıdaki örnek C2530 oluşturur:  
  
```  
// C2530.cpp  
int main() {  
   int i = 0;  
   int &j;   // C2530  
   int &k = i;   // OK  
}  
```