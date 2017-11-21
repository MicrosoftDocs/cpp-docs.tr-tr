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
ms.openlocfilehash: 3db0777c8ac330db747e3376328fe87119407568
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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