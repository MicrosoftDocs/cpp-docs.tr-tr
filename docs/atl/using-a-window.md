---
description: 'Hakkında daha fazla bilgi edinin: pencere kullanma'
title: Pencere kullanma (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
ms.openlocfilehash: fb9f1e03a27ad8b637da30eacbd100daf920cdb4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157286"
---
# <a name="using-a-window"></a>Pencere kullanma

Sınıf [CWindow](../atl/reference/cwindow-class.md) , bir pencere kullanmanıza olanak sağlar. Bir nesneye bir pencere iliştirdikten `CWindow` sonra, `CWindow` pencereyi işlemek için yöntemler çağırabilirsiniz. `CWindow` Ayrıca, bir nesneyi HWND 'e dönüştürmek için bir HWND işleci de içerir `CWindow` . Bu nedenle, bir `CWindow` nesneyi bir pencere için işleyici gerektiren herhangi bir işleve geçirebilirsiniz. `CWindow`Geçici nesne oluşturmadan, Yöntem çağrılarını ve Win32 işlev çağrılarını kolayca karıştırabilirsiniz.

`CWindow`Yalnızca iki veri üyesine (bir pencere tutamacı ve varsayılan boyutlar) sahip olduğundan, kodunuzda bir ek yük uygulamaz. Ayrıca, `CWindow` yöntemlerin birçoğu yalnızca karşılık gelen Win32 API işlevlerini sarmalıdır. Kullanarak `CWindow` , HWND üyesi otomatik olarak Win32 işlevine geçirilir.

Doğrudan kullanmanın yanı sıra `CWindow` , sınıfınıza veri veya kod eklemek için de türetebilirsiniz. ATL kendi kendine üç sınıf türetiliyor `CWindow` : [CWindowImpl](../atl/implementing-a-window.md), [Cdialogimpl](../atl/implementing-a-dialog-box.md)ve [CContainedWindowT](../atl/using-contained-windows.md).

## <a name="see-also"></a>Ayrıca bkz.

[Pencere sınıfları](../atl/atl-window-classes.md)
