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
ms.openlocfilehash: 2e0484698654cd14f22a92be76a80f71c0f9adf5
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621851"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Bir CWnd'i HWND'inden Ayırma

Nesne ilişkisini atlatmaya ihtiyacınız varsa `HWND` , MFC `CWnd` C++ pencere nesnesinin Windows penceresinden bağlantısını kesten başka bir üye işlevi sağlar. [Detach](reference/cwnd-class.md#detach) Bu, nesne yok edilirken yok edicinin Windows penceresini yok etmesini engeller.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencereler oluşturma](creating-windows.md)

- [Pencere yok etme sırası](window-destruction-sequence.md)

- [Pencere belleğini ayırma ve serbest bırakma](allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere nesneleri](window-objects.md)
