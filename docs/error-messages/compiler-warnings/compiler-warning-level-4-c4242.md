---
title: Derleyici Uyarısı (düzey 4) C4242 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4242
dev_langs:
- C++
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 623183e5ee54c995d624f47461c724ee8f4befae
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217404"
---
# <a name="compiler-warning-level-4-c4242"></a>Derleyici Uyarısı (düzey 4) C4242
'identifier': 'type1' öğesinden 'type2', olası veri kaybı dönüştürme  
  
 Farklı türleridir. Tür dönüşümü, veri kaybına neden olabilir. Derleyici, tür dönüştürme sağlar.  
  
 Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 C4242 hakkında ek bilgi için bkz. [Genel derleyici hataları](/windows/desktop/WinProg64/common-compiler-errors).  
  
 Aşağıdaki örnek, C4242 oluşturur:  
  
```  
// C4242.cpp  
// compile with: /W4  
#pragma warning(4:4242)  
int func() {  
   return 0;  
}  
  
int main() {  
   char a;  
   a = func();   // C4242, return type and variable type do not match  
}  
```