---
title: Bir CWnd'i HWND'inden Ayırma
ms.date: 11/04/2016
f1_keywords:
- CWnd
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
ms.openlocfilehash: fe4d9efa6adcec51d5944755e4a8abb1cc0784e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653979"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Bir CWnd'i HWND'inden Ayırma

Nesne - aşmak gerekiyorsa`HWND` ilişki, MFC başka sağlar `CWnd` üye işlevini [ayırma](../mfc/reference/cwnd-class.md#detach), Windows penceresinden C++ pencere nesnesi keser. Bu, yok edici nesnesi yok edildiğinde Windows penceresini yok etme engeller.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencereler oluşturma](../mfc/creating-windows.md)

- [Pencere yok etme dizisi](../mfc/window-destruction-sequence.md)

- [Pencere belleğini ayırma ve](../mfc/allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere Nesneleri](../mfc/window-objects.md)

