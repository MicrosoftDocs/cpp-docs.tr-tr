---
title: Ayırma ve pencere belleği serbest bırakma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1364b4d29e2ccd2c9563359716eba6880df5436
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="allocating-and-deallocating-window-memory"></a>Pencere Belleğini Ayırma ve Serbest Bırakma
C++ kullanmayın **silmek** işleci bir çerçeve penceresi veya Görünüm yok. Bunun yerine, çağrı `CWnd` üye işlevi `DestroyWindow`. Çerçeve pencereleri, bu nedenle, ayrılan işleciyle yığında **yeni**. Çerçeve pencereleri yığın çerçevesinde veya genel olarak ayırırken dikkatli olun. Diğer windows yığın çerçevesi mümkün olduğunca ayrılmalıdır.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Pencereler oluşturma](../mfc/creating-windows.md)  
  
-   [Pencere yok etme dizisi](../mfc/window-destruction-sequence.md)  
  
-   [Bir CWND'i hwnd'inden ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere Nesnelerini Yok Etme](../mfc/destroying-window-objects.md)

