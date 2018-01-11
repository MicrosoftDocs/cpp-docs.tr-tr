---
title: "Derleyici Hatası C2467 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2467
dev_langs: C++
helpviewer_keywords: C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a80079c441b1ec76df6d69789d1ca3d4b09fb395
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2467"></a>Derleyici Hatası C2467
Anonim 'kullanıcı tanımlı-tür' geçersiz bildirimi  
  
 İç içe geçmiş bir kullanıcı tanımlı tür bildirildi. Bu ANSI uyumluluğu seçeneğiyle C kaynak kodu derleme sırasında bir hata olduğunu ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) etkinleştirilmiş.  
  
 Aşağıdaki örnek C2467 oluşturur:  
  
```  
//C2467.c  
// compile with: /Za   
int main() {  
   struct X {  
      union { int i; };   // C2467, nested declaration  
   };  
}  
```