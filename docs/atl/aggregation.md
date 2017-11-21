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
ms.openlocfilehash: b98caeedd99199f7d286a4d8ab12c976fffd073c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="aggregation"></a>Toplama
Ne zaman nesnenin uygulayıcıya başka önceden oluşturulmuş nesnesi tarafından sunulan hizmetler yararlanmak istersiniz zamanlar vardır. Ayrıca, bu ikinci nesnenin ilk doğal bir parçası olarak görünmesini ister. COM başarır hem de bu hedeflerinden kapsama ve toplama.  
  
 Toplama içeren (Dış) nesne kapsanan (iç), oluşturma işleminin bir parçası olarak oluşturur ve iç nesneyi arabirimleri dış tarafından sunulan anlamına gelir. Bir nesne veya toplanabilir olması kendisine sağlar. İse, toplama düzgün çalışması için belirli kurallar izlemelisiniz.  
  
 Öncelikle, tüm **IUnknown** kapsanan nesne yöntemi çağrılarını içeren nesneye temsilci gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM giriş](../atl/introduction-to-com.md)   
 [Nesneleri yeniden kullanma](http://msdn.microsoft.com/library/windows/desktop/ms678443)

