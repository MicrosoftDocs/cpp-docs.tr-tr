---
title: Pencere nesnelerini yok etme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 67d2df7d72de079a0408847c433000a652ac6aaa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="destroying-window-objects"></a>Pencere Nesnelerini Yok Etme
Bakım penceresiyle kullanıcı tamamlandığında C++ pencere nesnesi yok etmek için kendi alt windows ile alınması gerekir. Bu nesneler yok edilmez, uygulamanız kendi bellek kurtarma değil. Neyse ki, çerçeve pencere yok etme ve bunun yanı sıra oluşturma çerçeve pencereleri, görünümleri ve iletişim kutuları için yönetir. Ek windows oluşturursanız, yok etme için sorumludur.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Pencere yok etme dizisi](../mfc/window-destruction-sequence.md)  
  
-   [Ayırma ve pencere belleği serbest bırakma](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Bir CWND'i hwnd'inden ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [Genel pencere oluşturma dizisi](../mfc/general-window-creation-sequence.md)  
  
-   [Çerçeve pencerelerini yok etme](../mfc/destroying-frame-windows.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere nesneleri](../mfc/window-objects.md)

