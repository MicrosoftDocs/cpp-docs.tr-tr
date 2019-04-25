---
title: Pencere Yok Etme Dizisi
ms.date: 11/04/2016
helpviewer_keywords:
- destruction, windows
- destroying windows
- sequence [MFC], window destruction
- CWnd objects [MFC], destruction sequence
- sequence [MFC]
- windows [MFC], destroying
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
ms.openlocfilehash: d4592e6ac0077d6bc335b50f2d67b140402b4fe2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167653"
---
# <a name="window-destruction-sequence"></a>Pencere Yok Etme Dizisi

Kullanıcı, pencerenin varsayılan çerçeve penceresi kapandığında MFC çerçevesi içinde [OnClose](../mfc/reference/cwnd-class.md#onclose) işleyicisi çağrılarını [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Windows penceresini yok edildiğinde adlı son bir üye işlevidir [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), bazı temizleme işlemleri yapar, çağıran [varsayılan](../mfc/reference/cwnd-class.md#default) üye Windows temizleme işlemini gerçekleştirmek için işlevi ve son olarak çağırır sanal üye işlevi [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). [CFrameWnd](../mfc/reference/cframewnd-class.md) uygulaması `PostNcDestroy` C++ pencere nesnesi siler.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencere belleğini ayırma ve](../mfc/allocating-and-deallocating-window-memory.md)

- [Bir cwnd'i hwnd'inden ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Nesnelerini Yok Etme](../mfc/destroying-window-objects.md)
