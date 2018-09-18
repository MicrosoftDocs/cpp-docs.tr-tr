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
ms.openlocfilehash: ce2fbe4a2dd566541a637459510ec8422b318c47
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070925"
---
# <a name="aggregation"></a>Toplama

Bir nesnenin uygulamacının başka bir, önceden oluşturulmuş bir nesne tarafından sunulan hizmetler yararlanmak için ne zaman istediğiniz zamanlar vardır. Ayrıca, bu ikinci nesne ilk doğal bir parçası olarak görünmesini istediğiniz. COM, her ikisi de elde eder, bu hedefleri kapsama ve toplama.

Toplama içeren (Dış) nesnenin içerdiği (iç), oluşturma işleminin bir parçası olarak oluşturur ve arabirimler iç nesne dış tarafından sunulan anlamına gelir. Bir nesne kendisine veya bir araya toplanabilir olmasını sağlar. İse, düzgün çalışması Toplama için belirli kuralları izlemelidir.

Öncelikle, tüm `IUnknown` kapsanan nesne üzerinde yöntem çağrılarını içeren nesneye temsilci gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[Nesneleri yeniden kullanma](/windows/desktop/com/reusing-objects)

