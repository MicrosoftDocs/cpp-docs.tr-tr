---
title: Derleyici Hatası C2017 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2017
dev_langs:
- C++
helpviewer_keywords:
- C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 019c166b1945bee26c11115000fae3c2f3f99968
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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