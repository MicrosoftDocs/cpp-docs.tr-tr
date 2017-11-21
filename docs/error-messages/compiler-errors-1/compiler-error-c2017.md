---
title: "Derleyici Hatası C2017 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2017
dev_langs: C++
helpviewer_keywords: C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7170fa404cba6cab3a0fcf3eec3e1d02c11271bb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2017"></a>Derleyici Hatası C2017
Geçersiz kaçış sırası  
  
 \T gibi bir kaçış sırası karakteri veya dize dışında görünür sabit.  
  
 Aşağıdaki örnek C2017 oluşturur:  
  
```  
// C2017.cpp  
int main() {  
   char test1='a'\n;   // C2017  
   char test2='a\n';   // ok  
}  
```  
  
 Kaçış dizileri içeren dizelerle stringize işleci kullanıldığında C2017 ortaya çıkabilir.  
  
 Aşağıdaki örnek C2017 oluşturur:  
  
```  
// C2017b.cpp  
#define TestDfn(x) AfxMessageBox(#x)  
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017  
```