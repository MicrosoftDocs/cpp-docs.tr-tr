---
title: Birleşime Düzgün Olmayan Erişim
ms.date: 11/04/2016
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
ms.openlocfilehash: a08f2c9aa76d0d2f2370dd45f9eb9ace77ceb76c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642967"
---
# <a name="improper-access-to-a-union"></a>Birleşime Düzgün Olmayan Erişim

**ANSI 3.3.2.3** birleşim nesnenin bir üyesi farklı bir tür üyesi kullanılarak erişilen

İki tür UNION bildirilmiş ve bir değeri depolanan ancak birleşim bir türü ile erişilen, sonuçları güvenilir değil.

Örneğin, bir birleşimini **float** ve `int` bildirilir. A **float** değeri depolanır, ancak bu programı daha sonra değeri olarak erişen bir `int`. Böyle bir durumda iç depolama alanında değer bağlıdır **float** değerleri. Tamsayı değeri güvenilir olmaz.

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Birleşimler, Numaralandırmalar ve Bit Alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)