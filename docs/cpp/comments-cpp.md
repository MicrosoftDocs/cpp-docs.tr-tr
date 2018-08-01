---
title: Açıklamaları (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a412c2b4dd87bc3e8e3e1b77a524d2a5925aaf60
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405064"
---
# <a name="comments-c"></a>Açıklamaları (C++)
Açıklama, derleyicinin yoksaydığı ancak programcılar için yararlı bir metindir. Açıklamalar normalde daha sonra başvurmak üzere koda açıklama eklemek için kullanılır. Derleyici bunları boşluk olarak işler. Kodun belirli satırlarını etkin hale getirmek için test açıklamaları kullanabilirsiniz; Ancak, `#if` / `#endif` önişlemci yönergeleri çalışması daha iyi bu çünkü açıklamaları içeren kodu çevreleyebilirsiniz ancak açıklamaları iç içe olamaz.  
  
 Bir C++ açıklaması aşağıdaki yollardan biriyle yazılır:  
  
-   `/*` (eğik çizgi, yıldız işareti) karakterleri, ardından bir dizi karakter (yeni satırlar dahil) ve onun da ardından `*/` karakterleri gelir. Bu sözdizimi ANSI C ile aynıdır.  
  
-   `//` (iki eğik çizgi) karakterlerinin ardından bir dizi karakter gelir. Hemen öncesinde bir ters eğik çizginin gelmediği yeni bir çizgi, bu açıklama formunu sonlandırır. Bu nedenle, buna genellikle "tek çizgilik açıklama" denir.  
  
 Açıklama karakterleri (`/*`, `*/` ve `//`); karakter sabiti, dize sabiti veya açıklama içinde herhangi bir özel anlama sahip değildir. Bundan dolayı, ilk sözdizimini kullanan açıklamalar iç içe yerleştirilemez.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Sözcük Temelli Kurallar](../cpp/lexical-conventions.md)