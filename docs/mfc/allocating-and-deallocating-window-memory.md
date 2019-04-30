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
ms.openlocfilehash: 60f99c01c7a311c31602269b49efaf434d16827a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394708"
---
# <a name="allocating-and-deallocating-window-memory"></a>Pencere Belleğini Ayırma ve Serbest Bırakma

C++ kullanmayın **Sil** işlecini bir çerçeve penceresinin veya Görünüm yok. Bunun yerine çağrı `CWnd` üye işlevi `DestroyWindow`. Çerçeve pencereleri, bu nedenle, ayrılan işleciyle yığında **yeni**. Çerçeve pencereleri yığın çerçevesinde veya genel olarak ayırırken dikkatli olun. Diğer windows yığın çerçevesi üzerinde mümkün olduğunca ayrılmalıdır.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencereler oluşturma](../mfc/creating-windows.md)

- [Pencere yok etme dizisi](../mfc/window-destruction-sequence.md)

- [Bir cwnd'i hwnd'inden ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Nesnelerini Yok Etme](../mfc/destroying-window-objects.md)
