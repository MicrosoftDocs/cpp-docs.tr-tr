---
title: "Ayırma ve pencere belleği serbest bırakma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4933ea9f079a18c4147db2da96b99653c5ddda26
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="allocating-and-deallocating-window-memory"></a>Pencere Belleğini Ayırma ve Serbest Bırakma
C++ kullanmayın **silmek** işleci bir çerçeve penceresi veya Görünüm yok. Bunun yerine, çağrı `CWnd` üye işlevi `DestroyWindow`. Çerçeve pencereleri, bu nedenle, ayrılan işleciyle yığında **yeni**. Çerçeve pencereleri yığın çerçevesinde veya genel olarak ayırırken dikkatli olun. Diğer windows yığın çerçevesi mümkün olduğunca ayrılmalıdır.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Pencereler oluşturma](../mfc/creating-windows.md)  
  
-   [Pencere yok etme dizisi](../mfc/window-destruction-sequence.md)  
  
-   [Bir CWND'i hwnd'inden ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere nesnelerini yok etme](../mfc/destroying-window-objects.md)

