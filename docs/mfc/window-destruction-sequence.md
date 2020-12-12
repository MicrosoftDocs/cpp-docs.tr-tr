---
description: 'Daha fazla bilgi edinin: pencere yok etme sırası'
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
ms.openlocfilehash: 2ba60f1dcd3668a754bbe4384a6c8cf6b4d541d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207689"
---
# <a name="window-destruction-sequence"></a>Pencere Yok Etme Dizisi

MFC çerçevesinde, Kullanıcı çerçeve penceresini kapattığında, pencerenin varsayılan [OnClose](../mfc/reference/cwnd-class.md#onclose) Işleyicisi, [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)'u çağırır. Windows penceresi yok edildiğinde çağrılan son üye işlevi [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), bazı temizleme işlemleri yapar, Windows CleanUp işlemini gerçekleştirmek için [varsayılan](../mfc/reference/cwnd-class.md#default) üye işlevini çağırır ve son olarak [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy)sanal üye işlevini çağırır. ' In [CFrameWnd](../mfc/reference/cframewnd-class.md) uygulamasının `PostNcDestroy` C++ pencere nesnesini silmesi.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencere belleğini ayırma ve serbest bırakma](../mfc/allocating-and-deallocating-window-memory.md)

- [Bir CWnd'i HWND'inden ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere nesnelerini yok etme](../mfc/destroying-window-objects.md)
