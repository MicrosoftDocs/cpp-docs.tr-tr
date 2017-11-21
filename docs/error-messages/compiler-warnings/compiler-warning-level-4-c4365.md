---
title: "Derleyici Uyarısı (düzey 4) C4365 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4365
dev_langs: C++
helpviewer_keywords: C4365
ms.assetid: af4b4191-bdfd-4dbb-8229-3ba4405df257
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7d2c54e6761edf95ece06b5cad79374566e296b5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4365"></a>Derleyici Uyarısı (düzey 4) C4365
'action': 'type_1' dönüştürmeye 'type_2', imzalı ve imzasız uyuşmazlığı  
  
 Örneğin, bir işaretsiz değer imzalı değerine dönüştürmek çalıştı.  
  
 Varsayılan olarak C4365 kapalıdır.  Daha fazla bilgi için bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4365 oluşturur.  
  
```  
// C4365.cpp  
// compile with: /W4  
#pragma warning(default:4365)  
  
int f(int) { return 0; }  
void Test(size_t i) {}  
  
int main() {  
   unsigned int n = 10;  
   int o = 10;  
   n++;  
   f(n);   // C4365  
   f(o);   // OK  
  
   Test( -19 );   // C4365  
}  
```