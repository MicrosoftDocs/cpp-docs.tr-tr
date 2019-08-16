---
title: Cihaz Bağlamları
ms.date: 11/04/2016
helpviewer_keywords:
- OnPrepareDC method [MFC]
- windows [MFC], and device context
- drawing [MFC], device context
- CClientDC class [MFC], and GetDC method [MFC]
- drawing [MFC], in mouse and device contexts
- CDC class [MFC], objects
- device contexts [MFC]
- client areas
- CMetaFileDC class [MFC], and OnPrepareDC method [MFC]
- GDI objects [MFC], device contexts
- graphic objects [MFC], device contexts
- frame windows [MFC], device contexts
- metafiles and device contexts
- EndPaint method [MFC]
- printers [MFC], device contexts
- mouse [MFC], drawing and device contexts
- BeginPaint method, CPaintDC
- CPaintDC class [MFC], device context for painting
- windows [MFC], drawing directly into
- client areas, and device context
- device contexts [MFC], CDC class [MFC]
- user interface [MFC], device contexts
- device-independent drawing
- GetDC method and CClientDC class [MFC]
- CClientDC class [MFC], and ReleaseDC method [MFC]
- ReleaseDC method [MFC]
- device contexts [MFC], about device contexts
- drawing [MFC], directly into windows
- painting and device context
ms.assetid: d0cd51f1-f778-4c7e-bf50-d738d10433c7
ms.openlocfilehash: d5337e8d8b83a641458a15612803feeec3b6361c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508662"
---
# <a name="device-contexts"></a>Cihaz Bağlamları

Cihaz bağlamı, bir cihazın görüntü veya yazıcı gibi çizim öznitelikleri hakkında bilgi içeren bir Windows veri yapısıdır. Tüm çizim çağrıları, çizgi, şekil ve metin çizmek için Windows API 'Lerini kapsülleyen bir cihaz bağlamı nesnesi aracılığıyla yapılır. Cihaz bağlamları Windows 'da cihazdan bağımsız çizime izin verir. Cihaz bağlamları, ekrana, yazıcıya veya bir dosya dosyasına çizim yapmak için kullanılabilir.

[CPaintDC](../mfc/reference/cpaintdc-class.md) nesneleri, Windows 'un ortak deyim sayısını kapsüllemek, `BeginPaint` işlevi çağırmak, sonra cihaz bağlamında çizim yapmak ve sonra `EndPaint` işlevi çağırmak. Oluşturucu sizin için ve yok edicisi çağırır `EndPaint`. `CPaintDC` `BeginPaint` Basitleştirilmiş işlem, [CDC](../mfc/reference/cdc-class.md) nesnesini oluşturmak, çizmek ve sonra `CDC` nesneyi yok etmek. Çerçevesinde, bu işlem de otomatikleştirilmiştir. Özellikle, işleviniz `OnDraw` `CPaintDC` zaten hazırlanmış (aracılığıyla `OnPrepareDC`) olarak geçirilir ve yalnızca içine çizersiniz. Framework tarafından yok edilir ve işlevinizin `OnDraw` çağrısından geri dönerek temeldeki cihaz bağlamı Windows 'ta serbest bırakılır.

[CClientDC](../mfc/reference/cclientdc-class.md) nesneleri, yalnızca bir pencerenin istemci alanını temsil eden bir cihaz bağlamı ile çalışmayı kapsüller. `CClientDC` Oluşturucu işlevini`GetDC` çağırır`ReleaseDC` ve yıkıcı işlevi çağırır. [CWindowDC](../mfc/reference/cwindowdc-class.md) nesneleri, çerçevesini dahil olmak üzere tüm pencereyi temsil eden bir cihaz bağlamını kapsüller.

[CMetaFileDC](../mfc/reference/cmetafiledc-class.md) nesneleri, çizimi bir Windows meta dosyasına kapsüller. `CPaintDC` Geçirilen öğesine`OnDraw`karşılık olarak, bu örnekte, [onhazırlık EDC](../mfc/reference/cview-class.md#onpreparedc) çağrısı yapmanız gerekir.

## <a name="mouse-drawing"></a>Fare çizimi

Çerçeve programında çoğu çizim — ve bu nedenle çoğu cihaz bağlamı işi — görünümün `OnDraw` üye işlevinde yapılır. Ancak, diğer amaçlar için hala cihaz bağlamı nesnelerini kullanabilirsiniz. Örneğin, bir görünümde fare hareketiyle ilgili izleme geri bildirimi sağlamak için, çağrılabilir olmadan `OnDraw` doğrudan görünüme bir çizim yapmanız gerekir.

Böyle bir durumda, bir [CClientDC](../mfc/reference/cclientdc-class.md) cihaz bağlamı nesnesini kullanarak doğrudan görünüme çizim yapabilirsiniz.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Cihaz bağlamları (tanım)](/windows/win32/gdi/device-contexts)

- [Bir Görünümde Çizim Yapma](../mfc/drawing-in-a-view.md)

- [Bir Görünümü Kullanarak Kullanıcı Girişini Yorumlama](../mfc/interpreting-user-input-through-a-view.md)

- [Çizgiler ve eğriler](/windows/win32/gdi/lines-and-curves)

- [Doldurulmuş şekiller](/windows/win32/gdi/filled-shapes)

- [Yazı tipleri ve metin](/windows/win32/gdi/fonts-and-text)

- [Renkler](/windows/win32/gdi/colors)

- [Boşluk ve dönüştürmeleri koordinat](/windows/win32/gdi/coordinate-spaces-and-transformations)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Nesneleri](../mfc/window-objects.md)
