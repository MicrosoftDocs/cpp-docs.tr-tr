---
title: "Derleyici Hatası C2530 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2530
dev_langs:
- C++
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f9ea1b462f2e0b141bdc624d77f548f19c4b71a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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