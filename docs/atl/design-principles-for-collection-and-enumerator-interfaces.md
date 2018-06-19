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
ms.openlocfilehash: 05649cce0e80af6f54327545cef7b663d69babf9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354925"
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Tasarım ilkeleri toplama ve Numaralandırıcı arabirimleri
Her tür arabirimi arkasında farklı tasarım ilkeleri vardır:  
  
-   Bir koleksiyon arabirim sağlayan *rastgele* erişim bir *tek* koleksiyondaki öğe **öğesi** yöntemi, koleksiyondaki öğe sayısını olduğunu öğrenmek istemcileri sağlar aracılığıyla **sayısı** özelliği ve genellikle istemcilerin öğeleri eklemek ve kaldırmak olanak sağlar.  
  
-   Bir numaralandırıcı arabirim sağlar *seri* erişim *birden çok* bir koleksiyondaki öğelerin (Numaralandırıcı döndürme durdurur kadar kaç öğe koleksiyonda yer alan keşfetmek istemci izin vermez öğeleri) ve öğe ekleme veya kaldırma, herhangi bir şekilde sağlamaz.  
  
 Her tür arabiriminin bir koleksiyondaki öğelerin erişim sağlayan, farklı bir rol oynar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyonlar ve numaralandırmalar](../atl/atl-collections-and-enumerators.md)

