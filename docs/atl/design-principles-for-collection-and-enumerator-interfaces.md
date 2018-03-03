---
title: "Koleksiyon ve Numaralandırıcı arabirimleri (ATL) tasarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8709274e1b95816dee01b4457993521dde5d5213
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Tasarım ilkeleri toplama ve Numaralandırıcı arabirimleri
Her tür arabirimi arkasında farklı tasarım ilkeleri vardır:  
  
-   Bir koleksiyon arabirim sağlayan *rastgele* erişim bir *tek* koleksiyondaki öğe **öğesi** yöntemi, koleksiyondaki öğe sayısını olduğunu öğrenmek istemcileri sağlar aracılığıyla **sayısı** özelliği ve genellikle istemcilerin öğeleri eklemek ve kaldırmak olanak sağlar.  
  
-   Bir numaralandırıcı arabirim sağlar *seri* erişim *birden çok* bir koleksiyondaki öğelerin (Numaralandırıcı döndürme durdurur kadar kaç öğe koleksiyonda yer alan keşfetmek istemci izin vermez öğeleri) ve öğe ekleme veya kaldırma, herhangi bir şekilde sağlamaz.  
  
 Her tür arabiriminin bir koleksiyondaki öğelerin erişim sağlayan, farklı bir rol oynar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyonlar ve numaralandırmalar](../atl/atl-collections-and-enumerators.md)

