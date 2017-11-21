---
title: "Derleyici Hatası C2430 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2430
dev_langs: C++
helpviewer_keywords: C2430
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f5491d998b9c93fc2041c09c19f8b175d319e4d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2430"></a>Derleyici Hatası C2430
birden fazla dizin 'tanımlayıcısı' kaydetme  
  
 Birden fazla kayıt ölçeklendirilir. Ölçeklendirilmiş dizin oluşturma derleyici destekler, ancak yalnızca bir kasa ölçeklendirebilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2430 oluşturur.  
  
```  
// C2430.cpp  
// processor: x86  
int main() {  
   _asm mov eax, [ebx*2+ecx*4] // C2430  
}  
```