---
title: Pencere (ATL) kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
ms.openlocfilehash: 7446196e9eec4b9d9236d4ab55afd9fcf859254b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568668"
---
# <a name="using-a-window"></a>Pencere kullanma

Sınıf [CWindow](../atl/reference/cwindow-class.md) pencere kullanmanıza olanak tanır. Bir pencereye eklediğiniz sonra bir `CWindow` nesnesi, ardından çağırabilirsiniz `CWindow` penceresi işlemek için yöntemler. `CWindow` Ayrıca dönüştürmek için bir HWND işleci içeren bir `CWindow` HWND için nesne. Bu nedenle geçirebilirsiniz bir `CWindow` bir pencere için işleme gerektiren herhangi bir işlev nesnesi. Kolayca karıştırabilirsiniz `CWindow` yöntem çağrıları ve herhangi bir geçici nesne oluşturmadan Win32 işlev çağrıları.

Çünkü `CWindow` bunu değil zorunlu tuttukları kodunuzu bir iş yükünü yalnızca iki veri üyesi (bir pencere tutucu ve varsayılan boyutları) sahiptir. Ayrıca, birçok `CWindow` yöntemleri karşılık gelen Win32 API işlevleri yalnızca kaydır. Kullanarak `CWindow`, HWND üye otomatik olarak Win32 işleve geçirilir.

Kullanmanın yanı sıra `CWindow` doğrudan da veriler veya kod sınıfı eklemek için türetebilirsiniz. ATL kendisini üç sınıflarından türetilen `CWindow`: [Cwindowımpl](../atl/implementing-a-window.md), [Cdialogımpl](../atl/implementing-a-dialog-box.md), ve [CContainedWindowT](../atl/using-contained-windows.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere sınıfları](../atl/atl-window-classes.md)

