---
title: "Açıklamaları (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 482b9f2f3d9917466becff3f2c9bf9fea6f599f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comments-c"></a>Açıklamaları (C++)
Açıklama, derleyicinin yoksaydığı ancak programcılar için yararlı bir metindir. Açıklamalar normalde daha sonra başvurmak üzere koda açıklama eklemek için kullanılır. Derleyici bunları boşluk olarak işler. Belirli kod satırlarını devre dışı yapma için sınama sırasında açıklamaları kullanabilirsiniz; Ancak, `#if` / `#endif` önişlemci yönergeleri çalışmak daha iyi bu açıklamaları içeren kodu çevreleyen ancak açıklamaları iç içe yerleştirilemez.  
  
 Bir C++ açıklaması aşağıdaki yollardan biriyle yazılır:  
  
-   `/*` (eğik çizgi, yıldız işareti) karakterleri, ardından bir dizi karakter (yeni satırlar dahil) ve onun da ardından `*/` karakterleri gelir. Bu sözdizimi ANSI C ile aynıdır.  
  
-   `//` (iki eğik çizgi) karakterlerinin ardından bir dizi karakter gelir. Hemen öncesinde bir ters eğik çizginin gelmediği yeni bir çizgi, bu açıklama formunu sonlandırır. Bu nedenle, buna genellikle "tek çizgilik açıklama" denir.  
  
 Açıklama karakterleri (`/*`, `*/` ve `//`); karakter sabiti, dize sabiti veya açıklama içinde herhangi bir özel anlama sahip değildir. Bundan dolayı, ilk sözdizimini kullanan açıklamalar iç içe yerleştirilemez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sözcük Temelli Kurallar](../cpp/lexical-conventions.md)