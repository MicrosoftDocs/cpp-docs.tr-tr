---
title: Toplama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 760a595274ba7a1901138cc0cceceddf97122725
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="aggregation"></a>Toplama
Ne zaman nesnenin uygulayıcıya başka önceden oluşturulmuş nesnesi tarafından sunulan hizmetler yararlanmak istersiniz zamanlar vardır. Ayrıca, bu ikinci nesnenin ilk doğal bir parçası olarak görünmesini ister. COM başarır hem de bu hedeflerinden kapsama ve toplama.  
  
 Toplama içeren (Dış) nesne kapsanan (iç), oluşturma işleminin bir parçası olarak oluşturur ve iç nesneyi arabirimleri dış tarafından sunulan anlamına gelir. Bir nesne veya toplanabilir olması kendisine sağlar. İse, toplama düzgün çalışması için belirli kurallar izlemelisiniz.  
  
 Öncelikle, tüm **IUnknown** kapsanan nesne yöntemi çağrılarını içeren nesneye temsilci gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM giriş](../atl/introduction-to-com.md)   
 [Nesneleri yeniden kullanma](http://msdn.microsoft.com/library/windows/desktop/ms678443)

