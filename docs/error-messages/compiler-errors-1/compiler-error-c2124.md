---
title: "Derleyici Hatası C2124 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2124
dev_langs: C++
helpviewer_keywords: C2124
ms.assetid: 93392aaa-5582-4d68-8cc5-bd9c62a0ae7e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 773cb5b9e2e6a7d52bfb75d64ebf5af7f88e3805
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2124"></a>Derleyici Hatası C2124
bölme ya da sıfıra mod  
  
 Bir sabit ifadesine bir sıfır payda sahiptir. Hatayı gidermek için sıfıra bölünme değil.  
  
 Aşağıdaki örnek C2124 oluşturur:  
  
```  
// C2124.cpp  
int main() {  
  int i = 1 / 0;   // C2124  do not divide by zero  
  int i2 = 12 / 2;   // OK  
}  
```