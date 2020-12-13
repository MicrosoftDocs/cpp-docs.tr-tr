---
description: 'Daha fazla bilgi edinin: pencere belleğini ayırma ve ayırmayı kaldırma'
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
ms.openlocfilehash: 7648914289babffdfb5195f1ec53cd736e26892c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343724"
---
# <a name="allocating-and-deallocating-window-memory"></a>Pencere Belleğini Ayırma ve Serbest Bırakma

**`delete`** Bir çerçeve penceresini veya görünümünü yok etmek Için C++ işlecini kullanmayın. Bunun yerine, `CWnd` üye işlevini çağırın `DestroyWindow` . Bu nedenle, çerçeve pencereleri işleçle yığın üzerinde ayrılmalıdır **`new`** . Yığın çerçevesinde veya küresel olarak çerçeve pencereleri ayrılırken dikkatli olun. Diğer pencereler mümkün olduğunda yığın çerçevesine ayrılmalıdır.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencereler oluşturma](creating-windows.md)

- [Pencere yok etme dizisi](window-destruction-sequence.md)

- [Bir CWnd'i HWND'inden ayırma](detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere nesnelerini yok etme](destroying-window-objects.md)
