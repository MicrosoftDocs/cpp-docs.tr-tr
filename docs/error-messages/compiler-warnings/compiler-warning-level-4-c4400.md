---
title: "Derleyici Uyarısı (düzey 4) C4400 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4400
dev_langs: C++
helpviewer_keywords: C4400
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 975127c09a44448c5589edfd3b63323caa23f942
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4400"></a>Derleyici Uyarısı (düzey 4) C4400
'type': const/volatile niteleyicileri bu türü desteklenmiyor  
  
 [Const](../../cpp/const-cpp.md)ve [volatile](../../cpp/volatile-cpp.md)niteleyicileri ortak dil çalışma zamanı türleri değişkenlerle çalışmaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4400 oluşturur.  
  
```  
// C4400.cpp  
// compile with: /clr /W4  
// C4401 expected  
using namespace System;  
#pragma warning (disable : 4101)  
int main() {  
   const String^ str;   // C4400  
   volatile String^ str2;   // C4400  
}  
```