---
title: Pencere (ATL) kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
ms.openlocfilehash: 3a1843bfedc30e7d3b47c2916af08c8b53aaa965
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342077"
---
# <a name="using-a-window"></a>Pencere kullanma

Sınıf [CWindow](../atl/reference/cwindow-class.md) pencere kullanmanıza olanak tanır. Bir pencereye eklediğiniz sonra bir `CWindow` nesnesi, ardından çağırabilirsiniz `CWindow` penceresi işlemek için yöntemler. `CWindow` Ayrıca dönüştürmek için bir HWND işleci içeren bir `CWindow` HWND için nesne. Bu nedenle geçirebilirsiniz bir `CWindow` bir pencere için işleme gerektiren herhangi bir işlev nesnesi. Kolayca karıştırabilirsiniz `CWindow` yöntem çağrıları ve herhangi bir geçici nesne oluşturmadan Win32 işlev çağrıları.

Çünkü `CWindow` bunu değil zorunlu tuttukları kodunuzu bir iş yükünü yalnızca iki veri üyesi (bir pencere tutucu ve varsayılan boyutları) sahiptir. Ayrıca, birçok `CWindow` yöntemleri karşılık gelen Win32 API işlevleri yalnızca kaydır. Kullanarak `CWindow`, HWND üye otomatik olarak Win32 işleve geçirilir.

Kullanmanın yanı sıra `CWindow` doğrudan da veriler veya kod sınıfı eklemek için türetebilirsiniz. ATL kendisini üç sınıflarından türetilen `CWindow`: [Cwindowımpl](../atl/implementing-a-window.md), [Cdialogımpl](../atl/implementing-a-dialog-box.md), ve [CContainedWindowT](../atl/using-contained-windows.md).

## <a name="see-also"></a>Ayrıca bkz.

[Pencere sınıfları](../atl/atl-window-classes.md)
