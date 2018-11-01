---
title: Koleksiyon ve Numaralandırıcı arabirimleri (ATL) tasarlama
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
ms.openlocfilehash: 8c7f782f52391b162a8b32a97961269178999ee0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538209"
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Koleksiyon ve Numaralandırıcı arabirimleri için tasarım ilkeleri

Her tür arabirimin arkasına farklı tasarım ilkeleri vardır:

- Bir koleksiyon arabirimidir *rastgele* erişimi bir *tek* koleksiyondaki öğe `Item` yöntemi koleksiyondaki öğe sayısını olduğunu öğrenmek istemciler sağlar `Count` özellik ve genellikle öğeleri eklemek ve kaldırmak etmesine olanak tanır.

- Numaralandırıcı arabirimi sağlayan *seri* erişim *birden çok* bir koleksiyondaki öğelerin, istemci (numaralandırıcıyı döndürmek durdurur kadar kaç öğe koleksiyonda yer alan bulmak izin vermez öğeleri) ve öğe ekleme veya kaldırma, herhangi bir şekilde sağlamaz.

Her arabirimin türü bir koleksiyondaki öğelere erişim sağlayan bir farklı rol oynar.

## <a name="see-also"></a>Ayrıca Bkz.

[Koleksiyonlar ve numaralandırmalar](../atl/atl-collections-and-enumerators.md)

