---
title: Dinamik Nesne Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
ms.openlocfilehash: 75d4a055f047abfcac4451c04bcd1cc75650c89a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563732"
---
# <a name="dynamic-object-creation"></a>Dinamik Nesne Oluşturma

Bu makalede, nesne çalışma zamanında dinamik olarak oluşturmak açıklanmaktadır. Yordam çalışma zamanı sınıf bilgileri makalesinde açıklandığı gibi kullanır [çalışma süresi sınıf bilgilerine erişme](../mfc/accessing-run-time-class-information.md).

#### <a name="to-dynamically-create-an-object-given-its-run-time-class"></a>Dinamik olarak kendi çalışma zamanı sınıfının belirtilen bir nesne oluşturmak için

1. Dinamik olarak kullanarak bir nesne oluşturmak için aşağıdaki kodu kullanın `CreateObject` işlevi `CRuntimeClass`. Hata durumunda unutmayın `CreateObject` döndürür **NULL** yerine bir özel durum oluşturur:

   [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Kullanma](../mfc/using-cobject.md)

