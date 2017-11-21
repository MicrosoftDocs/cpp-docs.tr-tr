---
title: "Derleyici Hatası C2086 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2086
dev_langs: C++
helpviewer_keywords: C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 36270e50049889e5c6819a22b6b6e35d4c7d2caf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2086"></a>Derleyici Hatası C2086
'tanımlayıcısı': yeniden tanımlama  
  
 Tanımlayıcısı birden çok kez tanımlı değil veya önceki bir sonraki bildirimi farklıdır.  
  
 C2086 de başvuruda bulunulan bir C# derleme için artımlı derleme sonucu olabilir. Bu hatayı gidermek için C# derleme yeniden oluşturun.  
  
 Aşağıdaki örnek C2086 oluşturur:  
  
```  
// C2086.cpp  
main() {  
  int a;  
  int a;   // C2086 not an error in ANSI C  
}  
```