---
title: Bir CWnd'i HWND'inden Ayırma
ms.date: 11/04/2016
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
ms.openlocfilehash: f7a6f97ba9f1dd3a928a5450c1a899ce09a4ac5f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446966"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Bir CWnd'i HWND'inden Ayırma

Nesne`HWND` ilişkisini atlatmaya ihtiyacınız varsa, MFC, C++ pencere nesnesinin Windows penceresinden bağlantısını kesten başka bir `CWnd` üye Işlevi ( [Ayır](../mfc/reference/cwnd-class.md#detach)) sağlar. Bu, nesne yok edilirken yok edicinin Windows penceresini yok etmesini engeller.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Windows oluşturma](../mfc/creating-windows.md)

- [Pencere yok etme sırası](../mfc/window-destruction-sequence.md)

- [Pencere belleğini ayırma ve ayırmayı kaldırma](../mfc/allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Nesneleri](../mfc/window-objects.md)
