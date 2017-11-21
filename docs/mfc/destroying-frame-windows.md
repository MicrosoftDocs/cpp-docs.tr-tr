---
title: "Çerçeve pencerelerini yok etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PostNcDestroy
dev_langs: C++
helpviewer_keywords:
- Default method [MFC]
- DestroyWindow method [MFC]
- frame windows [MFC], destroying
- OnNcDestroy method, and frame windows
- document frame windows [MFC], destroying
- destroying frame windows
- MFC, frame windows
- windows [MFC], destroying
- OnClose method [MFC]
- PostNcDestroy method [MFC]
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0ab4e9999b46bc005f377b51c691f6947519143e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="destroying-frame-windows"></a>Çerçeve Pencerelerini Yok Etme
MFC çerçevesi pencere yok etme ve bunun yanı sıra oluşturma framework belgeler ve görünümler ile ilişkili bu Windows yönetir. Ek windows oluşturursanız, yok etme için sorumludur.  
  
 Kullanıcı pencerenin varsayılan çerçeve penceresi kapatıldığında Framework'teki [OnClose](../mfc/reference/cwnd-class.md#onclose) işleyicisi çağrılarını [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Windows penceresi bozulduğunda adlı son üye işlevi [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), hangi bazı temizleme mu çağırır [varsayılan](../mfc/reference/cwnd-class.md#default) üye Windows temizlenmesini işlev ve son olarak çağırır sanal üye işlevi [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). [CFrameWnd](../mfc/reference/cframewnd-class.md) uyarlamasını `PostNcDestroy` C++ pencere nesnesi siler. C++ hiçbir zaman kullanması gereken **silme** bir çerçeve penceresinde işleci. Bunun yerine `DestroyWindow` kullanın.  
  
 Ana penceresi kapatıldığında uygulamayı kapatır. Var. kaydedilmemiş belgeleri değiştirilirse framework belgeleri kaydedilmiş sormak için bir ileti kutusu görüntüler ve ilgili belgelere gerekirse kaydedilir sağlar.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve pencerelerini kullanma](../mfc/using-frame-windows.md)

