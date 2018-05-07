---
title: Derleyici Hatası C2431 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2431
dev_langs:
- C++
helpviewer_keywords:
- C2431
ms.assetid: 88a5b648-c89f-47d1-a20e-63231ab4f0f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94a3f94163e02b953a4739b56a04f92f2499d27f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2431"></a>Derleyici Hatası C2431
'tanımlayıcısı' ın geçersiz dizin Kaydet  
  
 ESP kaydının ölçeklendirilmiş veya dizin ve temel kayıt kullanılır. İşlemci ya da izin verme x86 için kodlama SIB.  
  
 Aşağıdaki örnek C2431 oluşturur:  
  
```  
// C2431.cpp  
// processor: x86  
int main() {  
   _asm mov ax, [ESI + 2*ESP]   // C2431  
   _asm mov ax, [esp + esp]   // C2431  
}  
```