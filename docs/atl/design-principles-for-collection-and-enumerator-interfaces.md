---
title: Koleksiyon ve Numaralandırıcı arabirimleri (ATL) tasarlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ffe40b583a9dabeb14ce5347de6ae3d14dae724
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751491"
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Koleksiyon ve Numaralandırıcı arabirimleri için tasarım ilkeleri

Her tür arabirimin arkasına farklı tasarım ilkeleri vardır:

- Bir koleksiyon arabirimidir *rastgele* erişimi bir *tek* koleksiyondaki öğe `Item` yöntemi koleksiyondaki öğe sayısını olduğunu öğrenmek istemciler sağlar `Count` özellik ve genellikle öğeleri eklemek ve kaldırmak etmesine olanak tanır.

- Numaralandırıcı arabirimi sağlayan *seri* erişim *birden çok* bir koleksiyondaki öğelerin, istemci (numaralandırıcıyı döndürmek durdurur kadar kaç öğe koleksiyonda yer alan bulmak izin vermez öğeleri) ve öğe ekleme veya kaldırma, herhangi bir şekilde sağlamaz.

Her arabirimin türü bir koleksiyondaki öğelere erişim sağlayan bir farklı rol oynar.

## <a name="see-also"></a>Ayrıca Bkz.

[Koleksiyonlar ve numaralandırmalar](../atl/atl-collections-and-enumerators.md)

