---
title: Birleşime düzgün olmayan erişim | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ac723ed80eaebc4b3f245ef56b761600007cd2d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028382"
---
# <a name="improper-access-to-a-union"></a>Birleşime Düzgün Olmayan Erişim

**ANSI 3.3.2.3** birleşim nesnenin bir üyesi farklı bir tür üyesi kullanılarak erişilen

İki tür UNION bildirilmiş ve bir değeri depolanan ancak birleşim bir türü ile erişilen, sonuçları güvenilir değil.

Örneğin, bir birleşimini **float** ve `int` bildirilir. A **float** değeri depolanır, ancak bu programı daha sonra değeri olarak erişen bir `int`. Böyle bir durumda iç depolama alanında değer bağlıdır **float** değerleri. Tamsayı değeri güvenilir olmaz.

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Birleşimler, Numaralandırmalar ve Bit Alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)