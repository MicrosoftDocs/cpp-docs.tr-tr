---
description: 'Daha fazla bilgi edinin: dinamik nesne oluşturma'
title: Dinamik Nesne Oluşturma
ms.date: 03/27/2020
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
ms.openlocfilehash: b39c0561a98807030c471b3de4cd5921883f9f0e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290979"
---
# <a name="dynamic-object-creation"></a>Dinamik Nesne Oluşturma

Bu makalede, çalışma zamanında dinamik olarak bir nesne oluşturma açıklanır. Yordam, [Run-Time sınıfı bilgilerine erişme](accessing-run-time-class-information.md)makalesinde açıklandığı gibi çalışma zamanı sınıf bilgilerini kullanır.

#### <a name="dynamically-create-an-object-given-its-run-time-class"></a>Çalışma zamanı sınıfı verilen bir nesneyi dinamik olarak oluşturma

1. İşlevini kullanarak bir nesneyi dinamik olarak oluşturmak için aşağıdaki kodu kullanın `CreateObject` `CRuntimeClass` . Hata durumunda, `CreateObject` bir özel durum tetikme yerine **null** döndürür:

   [!code-cpp[NVC_MFCCObjectSample#6](codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Pencere nesnelerini](tn017-destroying-window-objects.md) 
 yok etme [CObject kullanma](using-cobject.md)
