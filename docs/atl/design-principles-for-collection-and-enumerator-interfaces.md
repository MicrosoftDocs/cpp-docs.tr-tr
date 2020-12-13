---
description: 'Hakkında daha fazla bilgi edinin: koleksiyon ve Numaralandırıcı arabirimleri için tasarım Ilkeleri'
title: Koleksiyon ve Numaralandırıcı arabirimlerini tasarlama (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
ms.openlocfilehash: effd2cce775ef926befc89bb6b72a976d85bdf23
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148011"
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Koleksiyon ve Numaralandırıcı arabirimleri için tasarım Ilkeleri

Her bir arabirim türünün arkasında farklı tasarım ilkeleri vardır:

- Bir koleksiyon arabirimi, koleksiyonda *tek* bir öğeye *rastgele* erişim sağlar `Item` . Bu, istemcilerin özellik aracılığıyla koleksiyonda kaç öğe olduğunu bulmasına `Count` ve genellikle istemcilerin öğe eklemesine ve kaldırmasına izin verir.

- Numaralandırıcı arabirimi, bir koleksiyondaki *birden çok* öğeye *seri* erişim sağlar, istemcinin koleksiyonda kaç öğe olduğunu bulmasına izin vermez (Numaralandırıcı öğelerin döndürülmesi durduruluncaya kadar) ve öğe ekleme veya kaldırma yöntemi sağlamaz.

Her arabirim türü, bir koleksiyondaki öğelere erişim sağlamak için farklı bir rol oynar.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar ve Numaralandırıcılar](../atl/atl-collections-and-enumerators.md)
