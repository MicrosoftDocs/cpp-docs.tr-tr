---
title: Bir Cwnd'i hwnd'inden ayırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWnd
dev_langs:
- C++
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c69703d8c528d82a696fc94be76ac4a569628b4e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392655"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Bir CWnd'i HWND'inden Ayırma

Nesne - aşmak gerekiyorsa`HWND` ilişki, MFC başka sağlar `CWnd` üye işlevini [ayırma](../mfc/reference/cwnd-class.md#detach), Windows penceresinden C++ pencere nesnesi keser. Bu, yok edici nesnesi yok edildiğinde Windows penceresini yok etme engeller.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencereler oluşturma](../mfc/creating-windows.md)

- [Pencere yok etme dizisi](../mfc/window-destruction-sequence.md)

- [Pencere belleğini ayırma ve](../mfc/allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere Nesneleri](../mfc/window-objects.md)

