---
title: Temel Sınıflar
ms.date: 11/19/2018
helpviewer_keywords:
- inheritance, multiple
- base classes [C++], virtual
- derived classes [C++], multiple bases
- multiple inheritance, base classes
- virtual base classes [C++]
- base classes [C++]
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
ms.openlocfilehash: 59c474f54ea439acf83cf6923eba6e167901dd37
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175622"
---
# <a name="base-classes"></a>Temel Sınıflar

Devralma işlemi, temel sınıfların üyelerinden ve türetilmiş sınıf tarafından eklenen yeni üyelerden oluşan yeni bir türetilmiş bir sınıf oluşturur. Bir çoklu devralma işleminde, aynı temel sınıfın birden çok türetilmiş sınıfın parçası olduğu bir devralma grafiği oluşturmak mümkündür. Aşağıdaki şekil bu tür bir grafiği göstermektedir.

![Temel sınıfın birden çok örneği](../cpp/media/vc38xn1.gif "temel sınıfın birden çok örneği") <br/>
Birden çok örneğini tek bir temel sınıf

Şekilde, `CollectibleString` ve `CollectibleSortable` öğesi bileşenlerinin resimsel gösterimleri verilmiştir. Ancak, `Collectible` temel sınıfı, `CollectibleSortableString` yolu ve `CollectibleString` yolu aracılığıyla, `CollectibleSortable` içindedir. Bu artıklığı ortadan kaldırmak için, bu tür sınıflar devralınırlarken sanal temel sınıf olarak bildirilir.