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
ms.openlocfilehash: 259af94958f88643e9c3ce725b25c4e92cc38226
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271131"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Bir CWnd'i HWND'inden Ayırma

Nesne - aşmak gerekiyorsa`HWND` ilişki, MFC başka sağlar `CWnd` üye işlevini [ayırma](../mfc/reference/cwnd-class.md#detach), Windows penceresinden C++ pencere nesnesi keser. Bu, yok edici nesnesi yok edildiğinde Windows penceresini yok etme engeller.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencereler oluşturma](../mfc/creating-windows.md)

- [Pencere yok etme dizisi](../mfc/window-destruction-sequence.md)

- [Pencere belleğini ayırma ve](../mfc/allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Nesneleri](../mfc/window-objects.md)
