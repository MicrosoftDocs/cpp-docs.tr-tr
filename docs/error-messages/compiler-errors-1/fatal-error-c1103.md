---
title: "Önemli hata C1103 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1103
dev_langs: C++
helpviewer_keywords: C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 41759b75db078d4f689b12cc71d502ec907b56a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1103"></a>Önemli hata C1103
önemli hata ProgID içeri aktarma: 'iletisi  
  
 Derleyici tür kitaplığını içeri aktarma bir sorun algıladı.  Örneğin, olamaz bir tür kitaplığı ile ProgID belirtin ve ayrıca belirtin `no_registry`.  
  
 Daha fazla bilgi için bkz: [#import yönergesi](../../preprocessor/hash-import-directive-cpp.md).  
  
 Aşağıdaki örnek C1103 üretir:  
  
```  
// C1103.cpp  
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103  
```