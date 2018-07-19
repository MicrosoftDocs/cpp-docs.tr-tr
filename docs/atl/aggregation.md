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
ms.openlocfilehash: 2457d6e94677c43985cadf8ca49a176a82566b6a
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37847875"
---
# <a name="aggregation"></a>Toplama
Bir nesnenin uygulamacının başka bir, önceden oluşturulmuş bir nesne tarafından sunulan hizmetler yararlanmak için ne zaman istediğiniz zamanlar vardır. Ayrıca, bu ikinci nesne ilk doğal bir parçası olarak görünmesini istediğiniz. COM, her ikisi de elde eder, bu hedefleri kapsama ve toplama.  
  
 Toplama içeren (Dış) nesnenin içerdiği (iç), oluşturma işleminin bir parçası olarak oluşturur ve arabirimler iç nesne dış tarafından sunulan anlamına gelir. Bir nesne kendisine veya bir araya toplanabilir olmasını sağlar. İse, düzgün çalışması Toplama için belirli kuralları izlemelidir.  
  
 Öncelikle, tüm `IUnknown` kapsanan nesne üzerinde yöntem çağrılarını içeren nesneye temsilci gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM'a giriş](../atl/introduction-to-com.md)   
 [Nesneleri yeniden kullanma](http://msdn.microsoft.com/library/windows/desktop/ms678443)

