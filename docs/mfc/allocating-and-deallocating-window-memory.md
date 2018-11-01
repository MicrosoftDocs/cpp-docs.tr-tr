---
title: Pencere Belleğini Ayırma ve Serbest Bırakma
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
ms.openlocfilehash: a9bbf92a586a910dfa4e81774ce4817c9cf458e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582502"
---
# <a name="allocating-and-deallocating-window-memory"></a>Pencere Belleğini Ayırma ve Serbest Bırakma

C++ kullanmayın **Sil** işlecini bir çerçeve penceresinin veya Görünüm yok. Bunun yerine çağrı `CWnd` üye işlevi `DestroyWindow`. Çerçeve pencereleri, bu nedenle, ayrılan işleciyle yığında **yeni**. Çerçeve pencereleri yığın çerçevesinde veya genel olarak ayırırken dikkatli olun. Diğer windows yığın çerçevesi üzerinde mümkün olduğunca ayrılmalıdır.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencereler oluşturma](../mfc/creating-windows.md)

- [Pencere yok etme dizisi](../mfc/window-destruction-sequence.md)

- [Bir cwnd'i hwnd'inden ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere Nesnelerini Yok Etme](../mfc/destroying-window-objects.md)

