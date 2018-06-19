---
title: Derleyici Uyarısı (düzey 4) C4255 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4255
dev_langs:
- C++
helpviewer_keywords:
- C4255
ms.assetid: 2087b635-4b4c-4182-8a01-c26770d2bb88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff68feb5f926a3c2cf8bbb85acfa18e8e1ecfa29
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296789"
---
# <a name="compiler-warning-level-4-c4255"></a>Derleyici Uyarısı (düzey 4) C4255
'function': verilen hiçbir işlev prototipi: dönüştürme '(void)' için ' (')  
  
 Derleyici bir işlev bağımsız değişkenlerinin açık bir listesi bulunamadı. Bu uyarı için C derleyicisi yalnızca değil.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4255 oluşturur:  
  
```  
// C4255.c  
// compile with: /W4 /WX  
#pragma warning (default : 4255)  
  
void f()  { // C4255  
// try the following line instead  
//void f(void) {  
}  
  
int main(int argc, char *argv[]) {  
   f();  
}  
```