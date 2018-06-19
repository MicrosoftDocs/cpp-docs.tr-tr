---
title: Derleyici Hatası C2432 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2432
dev_langs:
- C++
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8dfbadf2c7d53cce799efbd5f10286b31bb3cd3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196941"
---
# <a name="compiler-error-c2432"></a>Derleyici Hatası C2432
16 bit veri 'tanımlayıcısı' ın geçersiz başvuru  
  
 Bir 16 bit kayıt bir dizin veya temel kayıt kullanılır. Derleyici, 16 bit veri başvuran desteklemez. 16 bit yazmaçlar dizini veya temel kasa için 32 bit kod derleme sırasında kullanılamaz.  
  
 Aşağıdaki örnek C2432 oluşturur:  
  
```  
// C2432.cpp  
// processor: x86  
int main() {  
   _asm mov eax, DWORD PTR [bx]   // C2432  
}  
```