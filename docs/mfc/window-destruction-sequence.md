---
title: Pencere yok etme dizisi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- destruction, windows
- destroying windows
- sequence [MFC], window destruction
- CWnd objects [MFC], destruction sequence
- sequence [MFC]
- windows [MFC], destroying
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8b873d51f585336425537756064582eb709988f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="window-destruction-sequence"></a>Pencere Yok Etme Dizisi
MFC Framework'teki kullanıcı pencerenin varsayılan çerçeve penceresi kapatıldığında [OnClose](../mfc/reference/cwnd-class.md#onclose) işleyicisi çağrılarını [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Windows penceresi bozulduğunda adlı son üye işlevi [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), hangi bazı temizleme mu çağırır [varsayılan](../mfc/reference/cwnd-class.md#default) üye Windows temizlenmesini işlev ve son olarak çağırır sanal üye işlevi [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). [CFrameWnd](../mfc/reference/cframewnd-class.md) uyarlamasını `PostNcDestroy` C++ pencere nesnesi siler.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Ayırma ve pencere belleği serbest bırakma](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Bir CWND'i hwnd'inden ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere Nesnelerini Yok Etme](../mfc/destroying-window-objects.md)

