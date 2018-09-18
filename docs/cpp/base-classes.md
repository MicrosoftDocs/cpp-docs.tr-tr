---
title: Temel sınıflar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- inheritance, multiple
- base classes [C++], virtual
- derived classes [C++], multiple bases
- multiple inheritance, base classes
- virtual base classes [C++]
- base classes [C++]
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a6d6494cc1ef371cfeb51647bc310a74ac68bfb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059218"
---
# <a name="base-classes"></a>Temel Sınıflar

Devralma işlemi, temel sınıfların üyelerinden ve türetilmiş sınıf tarafından eklenen yeni üyelerden oluşan yeni bir türetilmiş bir sınıf oluşturur. Bir çoklu devralma işleminde, aynı temel sınıfın birden çok türetilmiş sınıfın parçası olduğu bir devralma grafiği oluşturmak mümkündür. Aşağıdaki şekil bu tür bir grafiği göstermektedir.

![Temel sınıfın birden çok örneği](../cpp/media/vc38xn1.gif "vc38XN1") birden çok örneğini tek bir temel sınıf

Şekilde, `CollectibleString` ve `CollectibleSortable` öğesi bileşenlerinin resimsel gösterimleri verilmiştir. Ancak, `Collectible` temel sınıfı, `CollectibleSortableString` yolu ve `CollectibleString` yolu aracılığıyla, `CollectibleSortable` içindedir. Bu artıklığı ortadan kaldırmak için, bu tür sınıflar devralınırlarken sanal temel sınıf olarak bildirilir.