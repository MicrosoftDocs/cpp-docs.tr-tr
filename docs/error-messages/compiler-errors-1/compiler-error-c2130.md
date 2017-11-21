---
title: "Derleyici Hatası C2130 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2130
dev_langs: C++
helpviewer_keywords: C2130
ms.assetid: c6fd5a7e-8f28-4f67-99d1-95a13b0dff90
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b510d68a1434f1c82c7d327391d9c7a34b954724
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2130"></a>Derleyici Hatası C2130
\#satırından 'belirteci' bulunan dosya adını içeren bir dize bekleniyor  
  
 İsteğe bağlı bir dosya adı belirteci aşağıdaki [#line](../../preprocessor/hash-line-directive-c-cpp.md) `linenumber` bir dize olmalıdır.  
  
 Aşağıdaki örnek C2130 oluşturur:  
  
```  
// C2130.cpp  
int main() {  
   #line 1000 test   // C2130  
   #line 1000 "test"   // OK  
}  
```