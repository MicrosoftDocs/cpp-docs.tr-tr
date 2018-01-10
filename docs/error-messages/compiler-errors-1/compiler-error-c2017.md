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
ms.workload: cplusplus
ms.openlocfilehash: 5d978ebf635f5d042d2cd454581625033c0f306e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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