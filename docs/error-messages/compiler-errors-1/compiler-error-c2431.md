---
title: "Derleyici Hatası C2431 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2431
dev_langs: C++
helpviewer_keywords: C2431
ms.assetid: 88a5b648-c89f-47d1-a20e-63231ab4f0f7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d6c00a8d13739500831e9437c15e3848160183e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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