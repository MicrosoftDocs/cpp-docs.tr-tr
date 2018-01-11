---
title: Bir pencere (ATL) kullanarak | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a2be573e10190b385274de9afab498c77a094550
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-window"></a>Bir penceresini kullanma
Sınıf [CWindow](../atl/reference/cwindow-class.md) bir pencere kullanmanıza olanak sağlar. Bir pencere ekleme sonra bir `CWindow` nesnesi, ardından çağırabilir `CWindow` pencereyi denetlemek için yöntemler. `CWindow`Ayrıca içeren bir `HWND` dönüştürmek için işleci bir `CWindow` nesnesine bir `HWND`. Bu nedenle geçirebilirsiniz bir `CWindow` nesnesine bir pencere için bir tanıtıcı gerektiren herhangi bir işlev. Kolayca karıştırabilirsiniz `CWindow` yöntem çağrılarını ve geçici nesneleri oluşturmadan Win32 işlev çağrıları.  
  
 Çünkü `CWindow` onu değil zorunlu tuttukları kodunuzu bir iş yükünü yalnızca iki veri üyesi (bir pencere tanıtıcının ve varsayılan boyutları) sahiptir. Ayrıca, birçok `CWindow` yöntemleri yalnızca karşılık gelen Win32 API işlevleri sarmalayın. Kullanarak `CWindow`, `HWND` üye Win32 işlev için otomatik olarak geçirilir.  
  
 Kullanmanın yanı sıra `CWindow` doğrudan, ayrıca, verileri veya kod sınıfınıza eklemek için türetilen. ATL kendisini türetilen üç sınıflardan `CWindow`: [CWindowImpl](../atl/implementing-a-window.md), [Cdialogımpl](../atl/implementing-a-dialog-box.md), ve [CContainedWindowT](../atl/using-contained-windows.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere sınıfları](../atl/atl-window-classes.md)

