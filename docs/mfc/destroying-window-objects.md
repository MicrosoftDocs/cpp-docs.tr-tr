---
description: 'Daha fazla bilgi edinin: pencere nesnelerini yok etme'
title: Pencere Nesnelerini Yok Etme
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
ms.openlocfilehash: c2837ba6b9f568d7f6ab0175ae3ad99c31ccdc7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327823"
---
# <a name="destroying-window-objects"></a>Pencere Nesnelerini Yok Etme

Kullanıcı pencereyle işiniz bittiğinde C++ pencere nesnesini yok etmek için kendi alt pencerenize dikkat edilmelidir. Bu nesneler yok edilmez, uygulamanız belleğini kurtarmaz. Neyse ki Framework pencere yok etme ve çerçeve pencereleri, görünümler ve iletişim kutuları için oluşturma işlemlerini yönetir. Ek pencereler oluşturursanız, bunları yok etmek sizin sorumluluğunuzdadır.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencere yok etme dizisi](window-destruction-sequence.md)

- [Pencere belleğini ayırma ve serbest bırakma](allocating-and-deallocating-window-memory.md)

- [Bir CWnd'i HWND'inden ayırma](detaching-a-cwnd-from-its-hwnd.md)

- [Genel pencere oluşturma sırası](general-window-creation-sequence.md)

- [Çerçeve pencerelerini yok etme](destroying-frame-windows.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere nesneleri](window-objects.md)
