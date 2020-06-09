---
title: Dinamik Nesne Oluşturma
ms.date: 03/27/2020
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
ms.openlocfilehash: 00e627e6d73e510ca694966291e2ef518fef18b5
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619543"
---
# <a name="dynamic-object-creation"></a>Dinamik Nesne Oluşturma

Bu makalede, çalışma zamanında dinamik olarak bir nesne oluşturma açıklanır. Yordam, çalışma zamanı sınıf [bilgilerine erişme](accessing-run-time-class-information.md)makalesinde açıklandığı gibi çalışma zamanı sınıf bilgilerini kullanır.

#### <a name="dynamically-create-an-object-given-its-run-time-class"></a>Çalışma zamanı sınıfı verilen bir nesneyi dinamik olarak oluşturma

1. İşlevini kullanarak bir nesneyi dinamik olarak oluşturmak için aşağıdaki kodu kullanın `CreateObject` `CRuntimeClass` . Hata durumunda, `CreateObject` bir özel durum tetikme yerine **null** döndürür:

   [!code-cpp[NVC_MFCCObjectSample#6](codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Pencere nesnelerini](tn017-destroying-window-objects.md) 
 yok etme [CObject kullanma](using-cobject.md)
