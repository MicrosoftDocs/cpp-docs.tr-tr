---
title: Pencere Nesneleriyle Çalışma
ms.date: 11/04/2016
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
ms.openlocfilehash: c696d880ffa69b0a0399c5282621546c5783ebe4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399492"
---
# <a name="working-with-window-objects"></a>Pencere Nesneleriyle Çalışma

İki tür etkinlik için windows çağrıları ile çalışma:

- Windows iletilerini işleme

- Pencerede çizme

Kendi alt pencereleri de dahil olmak üzere herhangi bir pencerede, Windows iletileri işlemek için bkz. [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md) C++ pencere sınıfa ileti eşlemesi için. Ardından ileti işleyicisi sınıfınızda üye işlevleri yazın.

Çoğu bir framework uygulamasında çizim Görünümü'nde gerçekleşir, [OnDraw](../mfc/reference/cview-class.md#ondraw) pencerenin içeriği çizilmesi her üye işlevi çağrılır. Pencerenizin görünüm alt varsa, görünümün çizim bazıları alt pencerenizi sağlayarak temsilci `OnDraw` , pencerenin üye işlevleri birini çağırın.

Çizim için herhangi bir durumda, bir cihaz bağlamı ihtiyacınız olacak. Stok Kalem ve fırça pencereniz ile ilişkili cihaz bağlamı içinde yer alan diğer grafik nesneleri kullanabilirsiniz. Veya gereksinim duyduğunuz çizim etkileri almak için bu nesneleri değiştirebilirsiniz. Cihaz bağlamı istediğiniz olarak ayarlamak, üye işlevleri sınıfı çağırın [CDC](../mfc/reference/cdc-class.md) (cihaz bağlamı) metin satırlar ve şekiller çizmek için; renkleri; kullanılacak ve sınıfı bir koordinat sistemiyle çalışmak için.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [İleti işleme ve eşleme](../mfc/message-handling-and-mapping.md)

- [Bir görünümde çizim yapma](../mfc/drawing-in-a-view.md)

- [Cihaz bağlamları](../mfc/device-contexts.md)

- [Grafik nesneler](../mfc/graphic-objects.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Nesneleri](../mfc/window-objects.md)
