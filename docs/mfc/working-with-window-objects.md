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
ms.openlocfilehash: 55f3eae10954ee2da1386907f88ae8b594dc8e53
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413640"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere Nesneleri](../mfc/window-objects.md)

