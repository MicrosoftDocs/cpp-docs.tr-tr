---
title: Koleksiyon ve Numaralandırıcı arabirimleri (ATL) tasarlama
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
ms.openlocfilehash: f40c86d3bc8d9b4e4c752fe6657f6a5a14f19e0c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269943"
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Koleksiyon ve Numaralandırıcı arabirimleri için tasarım ilkeleri

Her tür arabirimin arkasına farklı tasarım ilkeleri vardır:

- Bir koleksiyon arabirimidir *rastgele* erişimi bir *tek* koleksiyondaki öğe `Item` yöntemi koleksiyondaki öğe sayısını olduğunu öğrenmek istemciler sağlar `Count` özellik ve genellikle öğeleri eklemek ve kaldırmak etmesine olanak tanır.

- Numaralandırıcı arabirimi sağlayan *seri* erişim *birden çok* bir koleksiyondaki öğelerin, istemci (numaralandırıcıyı döndürmek durdurur kadar kaç öğe koleksiyonda yer alan bulmak izin vermez öğeleri) ve öğe ekleme veya kaldırma, herhangi bir şekilde sağlamaz.

Her arabirimin türü bir koleksiyondaki öğelere erişim sağlayan bir farklı rol oynar.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar ve numaralandırmalar](../atl/atl-collections-and-enumerators.md)
