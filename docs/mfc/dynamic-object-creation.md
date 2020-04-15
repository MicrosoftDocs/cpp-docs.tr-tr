---
title: Dinamik Nesne Oluşturma
ms.date: 03/27/2020
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
ms.openlocfilehash: 40a17d3ed458d0634fd5bf27b54d0a36a65e35b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364801"
---
# <a name="dynamic-object-creation"></a>Dinamik Nesne Oluşturma

Bu makalede, çalışma zamanında dinamik olarak bir nesne oluşturmak için nasıl açıklanmaktadır. Yordam, Çalışma Zamanı [Sınıf Bilgilerine Erişim](../mfc/accessing-run-time-class-information.md)makalesinde anlatıldığı gibi çalışma zamanı sınıf bilgilerini kullanır.

#### <a name="dynamically-create-an-object-given-its-run-time-class"></a>Çalışma zamanı sınıfı verilen bir nesneyi dinamik olarak oluşturma

1. Işlevini kullanarak dinamik olarak bir nesne `CreateObject` oluşturmak için `CRuntimeClass`aşağıdaki kodu kullanın. Hata da, `CreateObject` bir özel durum yükseltmek yerine **NULL** döndürür:

   [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Destroying Window Objects](tn017-destroying-window-objects.md)
[CObject kullanarak](using-cobject.md) Pencere Nesneleri Yok
