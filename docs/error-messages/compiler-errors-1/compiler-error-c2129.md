---
title: "Derleyici Hatası C2129 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2129
dev_langs: C++
helpviewer_keywords: C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e2c5bd1b79960f83ef6effeb064375d6b49e8f20
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2129"></a>Derleyici Hatası C2129
statik işlevi 'function' bildirildi, ancak tanımlı değil  
  
 İleriye doğru bir başvuru yapılan bir `static` hiçbir zaman tanımlanan işlevi.  
  
 A `static` işlevi dosya kapsamı içinde tanımlanması gerekir. İşlevin başka bir dosyaya tanımlanmışsa bildirilmelidir `extern`.