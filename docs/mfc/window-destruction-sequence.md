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
ms.openlocfilehash: 07312d6c7bba219cebcfa2c73a8d66c9c97ec08e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571359"
---
# <a name="window-destruction-sequence"></a>Pencere Yok Etme Dizisi

Kullanıcı, pencerenin varsayılan çerçeve penceresi kapandığında MFC çerçevesi içinde [OnClose](../mfc/reference/cwnd-class.md#onclose) işleyicisi çağrılarını [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Windows penceresini yok edildiğinde adlı son bir üye işlevidir [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), bazı temizleme işlemleri yapar, çağıran [varsayılan](../mfc/reference/cwnd-class.md#default) üye Windows temizleme işlemini gerçekleştirmek için işlevi ve son olarak çağırır sanal üye işlevi [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). [CFrameWnd](../mfc/reference/cframewnd-class.md) uygulaması `PostNcDestroy` C++ pencere nesnesi siler.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencere belleğini ayırma ve](../mfc/allocating-and-deallocating-window-memory.md)

- [Bir cwnd'i hwnd'inden ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere Nesnelerini Yok Etme](../mfc/destroying-window-objects.md)

