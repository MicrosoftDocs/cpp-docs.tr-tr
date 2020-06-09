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
ms.openlocfilehash: 02546559183d0e14973bc2e5ccb26a4570a39b1e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623262"
---
# <a name="allocating-and-deallocating-window-memory"></a>Pencere Belleğini Ayırma ve Serbest Bırakma

Bir çerçeve penceresini veya görünümünü yok etmek için C++ **Delete** işlecini kullanmayın. Bunun yerine, `CWnd` üye işlevini çağırın `DestroyWindow` . Bu nedenle, çerçeve pencereleri **Yeni**işleçle yığında ayrılmalıdır. Yığın çerçevesinde veya küresel olarak çerçeve pencereleri ayrılırken dikkatli olun. Diğer pencereler mümkün olduğunda yığın çerçevesine ayrılmalıdır.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencereler oluşturma](creating-windows.md)

- [Pencere yok etme sırası](window-destruction-sequence.md)

- [Bir CWnd'i HWND'inden ayırma](detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere nesnelerini yok etme](destroying-window-objects.md)
