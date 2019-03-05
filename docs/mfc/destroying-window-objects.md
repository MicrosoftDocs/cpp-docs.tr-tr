---
title: Pencere Nesnelerini Yok Etme
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
ms.openlocfilehash: f50d198f9868a70d25370f6c1399b66efaa5490b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289851"
---
# <a name="destroying-window-objects"></a>Pencere Nesnelerini Yok Etme

Bakım penceresiyle kullanıcı tamamlandığında C++ pencere nesnesi yok etmek için kendi alt pencereleri ile alınması gerekir. Bu nesneler yok edilmez, uygulamanızı kendi bellek kurtarılmaz. Neyse ki, çerçeve pencere yok etme, hem de çerçeve pencereleri, görünümler ve iletişim kutuları için oluşturma yönetir. Ek windows oluşturursanız, bu yok etme için sorumlu olursunuz.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencere yok etme dizisi](../mfc/window-destruction-sequence.md)

- [Pencere belleğini ayırma ve](../mfc/allocating-and-deallocating-window-memory.md)

- [Bir cwnd'i hwnd'inden ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)

- [Genel Pencere Oluşturma Dizisi](../mfc/general-window-creation-sequence.md)

- [Çerçeve pencerelerini yok etme](../mfc/destroying-frame-windows.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Nesneleri](../mfc/window-objects.md)
