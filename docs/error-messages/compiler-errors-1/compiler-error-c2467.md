---
title: Derleyici Hatası C2467 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2467
dev_langs:
- C++
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ed9b1b50c63852ed830c2072d7cd8fce668a671
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225649"
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