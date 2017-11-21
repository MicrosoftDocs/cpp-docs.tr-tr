---
title: "Derleyici Hatası C3131 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3131
dev_langs: C++
helpviewer_keywords: C3131
ms.assetid: 38f20fac-83c9-4cd9-b7b5-74ca8f650ea6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 53b42516687d34b7eeb92ee46becf9afa99ef592
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3131"></a>Derleyici Hatası C3131
Proje 'module' öznitelik 'name' özelliğine sahip olması gerekir  
  
 [Modülü](../../windows/module-cpp.md) özniteliği name parametresi olması gerekir.  
  
 Aşağıdaki örnek C3131 oluşturur:  
  
```  
// C3131.cpp  
[emitidl];  
[module];   // C3131  
// try the following line instead  
// [module (name="MyLib")];  
  
[public]  
typedef long int LongInt;  
```