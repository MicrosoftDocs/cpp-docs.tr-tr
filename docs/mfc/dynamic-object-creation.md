---
title: Dinamik Nesne oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1b8cca1453ef4a044a39853e615c5d0e6c3268f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50051895"
---
# <a name="dynamic-object-creation"></a>Dinamik Nesne Oluşturma

Bu makalede, nesne çalışma zamanında dinamik olarak oluşturmak açıklanmaktadır. Yordam çalışma zamanı sınıf bilgileri makalesinde açıklandığı gibi kullanır [çalışma süresi sınıf bilgilerine erişme](../mfc/accessing-run-time-class-information.md).

#### <a name="to-dynamically-create-an-object-given-its-run-time-class"></a>Dinamik olarak kendi çalışma zamanı sınıfının belirtilen bir nesne oluşturmak için

1. Dinamik olarak kullanarak bir nesne oluşturmak için aşağıdaki kodu kullanın `CreateObject` işlevi `CRuntimeClass`. Hata durumunda unutmayın `CreateObject` döndürür **NULL** yerine bir özel durum oluşturur:

   [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Kullanma](../mfc/using-cobject.md)

