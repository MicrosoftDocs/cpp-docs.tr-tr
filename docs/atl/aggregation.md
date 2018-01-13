---
title: Toplama | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8dbb0332bc7e55464e5b8af9d0b57e236f23dc86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="aggregation"></a>Toplama
Ne zaman nesnenin uygulayıcıya başka önceden oluşturulmuş nesnesi tarafından sunulan hizmetler yararlanmak istersiniz zamanlar vardır. Ayrıca, bu ikinci nesnenin ilk doğal bir parçası olarak görünmesini ister. COM başarır hem de bu hedeflerinden kapsama ve toplama.  
  
 Toplama içeren (Dış) nesne kapsanan (iç), oluşturma işleminin bir parçası olarak oluşturur ve iç nesneyi arabirimleri dış tarafından sunulan anlamına gelir. Bir nesne veya toplanabilir olması kendisine sağlar. İse, toplama düzgün çalışması için belirli kurallar izlemelisiniz.  
  
 Öncelikle, tüm **IUnknown** kapsanan nesne yöntemi çağrılarını içeren nesneye temsilci gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM giriş](../atl/introduction-to-com.md)   
 [Nesneleri yeniden kullanma](http://msdn.microsoft.com/library/windows/desktop/ms678443)

