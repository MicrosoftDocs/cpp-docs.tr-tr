---
title: "Pencere nesneleriyle çalışma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3061787d4be2b85cb1b3776d499e53df83128387
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="working-with-window-objects"></a>Pencere Nesneleriyle Çalışma
Windows çağrıları iki tür etkinlik için çalışma:  
  
-   Windows iletilerini işleme  
  
-   Penceresinde çizme  
  
 Tüm penceresinde, kendi alt pencereleri dahil olmak üzere Windows iletilerini işlemek için bkz: [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md) , C++ pencere sınıfı için ileti eşlemesi için. Ardından ileti işleyicisi sınıfınızda üye işlevleri yazın.  
  
 Çoğu framework uygulamasında çizim görünümünde oluşur, [OnDraw](../mfc/reference/cview-class.md#ondraw) Pencere içeriklerini çizilmesi gerektiğinde her üye işlevi çağrılır. Pencerenizi görünümünün bir alt ise, görünümün çizim bazıları alt pencerenizi sağlayarak temsilci `OnDraw` , pencerenin üye işlevleri birini çağırın.  
  
 Herhangi bir durumda, bir cihaz bağlamı çizim için gerekir. Stok Kalem, fırça ve pencerenizi ile ilişkili cihaz bağlamı içinde yer alan diğer grafik nesnelerini kullanabilirsiniz. Veya gereksinim duyduğunuz çizim etkileri almak için bu nesneler değişiklik yapabilirsiniz. Cihaz bağlamı istediğiniz olarak ayarlamak, üye sınıfının işlevlerini [CDC](../mfc/reference/cdc-class.md) (cihaz bağlamı) satırları, Şekil ve metinler çizmek için; renkleri; kullanacak şekilde ve sınıfı bir koordinat sistemi ile çalışmak için.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [İleti işleme ve eşleme](../mfc/message-handling-and-mapping.md)  
  
-   [Bir görünümde çizim yapma](../mfc/drawing-in-a-view.md)  
  
-   [Cihaz bağlamları](../mfc/device-contexts.md)  
  
-   [Grafik nesneleri](../mfc/graphic-objects.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere nesneleri](../mfc/window-objects.md)

