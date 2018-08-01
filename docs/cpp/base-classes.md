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
ms.openlocfilehash: f1375cee34266b8d751e9c8d88fb22ce56f6c044
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407994"
---
# <a name="base-classes"></a>Temel Sınıflar
Devralma işlemi, temel sınıfların üyelerinden ve türetilmiş sınıf tarafından eklenen yeni üyelerden oluşan yeni bir türetilmiş bir sınıf oluşturur. Bir çoklu devralma işleminde, aynı temel sınıfın birden çok türetilmiş sınıfın parçası olduğu bir devralma grafiği oluşturmak mümkündür. Aşağıdaki şekil bu tür bir grafiği göstermektedir.  
  
 ![Temel sınıfın birden çok örneği](../cpp/media/vc38xn1.gif "vc38XN1")  
Tek Temel Sınıfın Birden Çok Örneği  
  
 Şekilde, `CollectibleString` ve `CollectibleSortable` öğesi bileşenlerinin resimsel gösterimleri verilmiştir. Ancak, `Collectible` temel sınıfı, `CollectibleSortableString` yolu ve `CollectibleString` yolu aracılığıyla, `CollectibleSortable` içindedir. Bu artıklığı ortadan kaldırmak için, bu tür sınıflar devralınırlarken sanal temel sınıf olarak bildirilir.  