---
description: 'Hakkında daha fazla bilgi edinin: pencere nesneleriyle çalışma'
title: Pencere Nesneleriyle Çalışma
ms.date: 11/04/2016
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
ms.openlocfilehash: 4a8c6f2c40eadbfe53aa79683bea29847adf684f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172602"
---
# <a name="working-with-window-objects"></a>Pencere Nesneleriyle Çalışma

İki tür etkinlik için Windows çağrıları ile çalışma:

- Windows iletilerini işleme

- Pencerede çizme

Kendi alt pencereleri dahil olmak üzere herhangi bir pencerede Windows iletilerini işlemek için bkz. iletileri C++ pencere sınıfınız ile eşlemek için [Iletileri IŞLEVLERE eşleme](../mfc/reference/mapping-messages-to-functions.md) . Sonra sınıfınıza ileti işleyici üye işlevlerini yazın.

Çerçeve uygulamasındaki çoğu çizim, pencerenin içeriği çizildiğinde [OnDraw](../mfc/reference/cview-class.md#ondraw) üye işlevi çağrılır görünümünde oluşur. Pencereniz görünümün bir alt öğesi ise, `OnDraw` pencerenin üye işlevlerinden birini çağırarak görünümün çiziminin bir kısmını alt pencerenize devredebilirsiniz.

Herhangi bir durumda, çizim için bir cihaz bağlamına ihtiyaç duyarsınız. Kaleminizle ilişkili cihaz bağlamındaki hisse senedi kalemini, fırçayı ve diğer grafik nesnelerini kullanabilirsiniz. Ya da bu nesneleri, ihtiyacınız olan çizim efektlerini almak için değiştirebilirsiniz. Cihaz içeriğiniz istediğiniz gibi ayarlanmış olarak, çizgi, şekil ve metin çizmek için [CDC](../mfc/reference/cdc-class.md) (Device-Context sınıfı) sınıfının üye işlevlerini çağırın; renkleri kullanmak için; ve bir koordinat sistemiyle çalışmak için.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [İleti işleme ve eşleme](../mfc/message-handling-and-mapping.md)

- [Bir görünümde çizim yapma](../mfc/drawing-in-a-view.md)

- [Cihaz bağlamları](../mfc/device-contexts.md)

- [Grafik nesneler](../mfc/graphic-objects.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere nesneleri](../mfc/window-objects.md)
