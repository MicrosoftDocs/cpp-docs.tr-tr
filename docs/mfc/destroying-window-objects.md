---
title: Pencere nesnelerini yok etme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 704122f028cd744f0ce064f0153825830144d5b7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401647"
---
# <a name="destroying-window-objects"></a>Pencere Nesnelerini Yok Etme

Bakım penceresiyle kullanıcı tamamlandığında C++ pencere nesnesi yok etmek için kendi alt pencereleri ile alınması gerekir. Bu nesneler yok edilmez, uygulamanızı kendi bellek kurtarılmaz. Neyse ki, çerçeve pencere yok etme, hem de çerçeve pencereleri, görünümler ve iletişim kutuları için oluşturma yönetir. Ek windows oluşturursanız, bu yok etme için sorumlu olursunuz.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencere yok etme dizisi](../mfc/window-destruction-sequence.md)

- [Pencere belleğini ayırma ve](../mfc/allocating-and-deallocating-window-memory.md)

- [Bir cwnd'i hwnd'inden ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)

- [Genel Pencere Oluşturma Dizisi](../mfc/general-window-creation-sequence.md)

- [Çerçeve pencerelerini yok etme](../mfc/destroying-frame-windows.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere Nesneleri](../mfc/window-objects.md)

