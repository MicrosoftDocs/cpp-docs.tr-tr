---
title: Pencere Nesnelerini Yok Etme
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
ms.openlocfilehash: 22b483c1005931b229453ae229935c0e716ab726
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621857"
---
# <a name="destroying-window-objects"></a>Pencere Nesnelerini Yok Etme

Kullanıcı pencereyle işiniz bittiğinde C++ pencere nesnesini yok etmek için kendi alt pencerenize dikkat edilmelidir. Bu nesneler yok edilmez, uygulamanız belleğini kurtarmaz. Neyse ki Framework pencere yok etme ve çerçeve pencereleri, görünümler ve iletişim kutuları için oluşturma işlemlerini yönetir. Ek pencereler oluşturursanız, bunları yok etmek sizin sorumluluğunuzdadır.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencere yok etme sırası](window-destruction-sequence.md)

- [Pencere belleğini ayırma ve serbest bırakma](allocating-and-deallocating-window-memory.md)

- [Bir CWnd'i HWND'inden ayırma](detaching-a-cwnd-from-its-hwnd.md)

- [Genel Pencere Oluşturma Dizisi](general-window-creation-sequence.md)

- [Çerçeve pencerelerini yok etme](destroying-frame-windows.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere nesneleri](window-objects.md)
