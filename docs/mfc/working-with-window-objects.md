---
title: Pencere nesneleriyle çalışma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4c00649c51e34bbbac7adbf7aa5f3c7d04790ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
 [Pencere Nesneleri](../mfc/window-objects.md)

