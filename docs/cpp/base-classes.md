---
title: "Temel sınıflar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- inheritance, multiple
- base classes [C++], virtual
- derived classes [C++], multiple bases
- multiple inheritance, base classes
- virtual base classes [C++]
- base classes [C++]
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0a83507d89c17aab363f986dab3ff4d84c4c916
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="base-classes"></a>Temel Sınıflar
Devralma işlemi, temel sınıfların üyelerinden ve türetilmiş sınıf tarafından eklenen yeni üyelerden oluşan yeni bir türetilmiş bir sınıf oluşturur. Bir çoklu devralma işleminde, aynı temel sınıfın birden çok türetilmiş sınıfın parçası olduğu bir devralma grafiği oluşturmak mümkündür. Aşağıdaki şekil bu tür bir grafiği göstermektedir.  
  
 ![Bir taban sınıfın birden çok örneği](../cpp/media/vc38xn1.gif "vc38XN1")  
Tek Temel Sınıfın Birden Çok Örneği  
  
 Şekilde, `CollectibleString` ve `CollectibleSortable` öğesi bileşenlerinin resimsel gösterimleri verilmiştir. Ancak, `Collectible` temel sınıfı, `CollectibleSortableString` yolu ve `CollectibleString` yolu aracılığıyla, `CollectibleSortable` içindedir. Bu artıklığı ortadan kaldırmak için, bu tür sınıflar devralınırlarken sanal temel sınıf olarak bildirilir.  
  
