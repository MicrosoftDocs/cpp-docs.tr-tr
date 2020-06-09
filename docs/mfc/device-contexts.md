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
ms.openlocfilehash: a5be2e57302e597e9c65b7bc966a5ff0ecaf855a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620360"
---
# <a name="device-contexts"></a>Cihaz Bağlamları

Cihaz bağlamı, bir cihazın görüntü veya yazıcı gibi çizim öznitelikleri hakkında bilgi içeren bir Windows veri yapısıdır. Tüm çizim çağrıları, çizgi, şekil ve metin çizmek için Windows API 'Lerini kapsülleyen bir cihaz bağlamı nesnesi aracılığıyla yapılır. Cihaz bağlamları Windows 'da cihazdan bağımsız çizime izin verir. Cihaz bağlamları, ekrana, yazıcıya veya bir dosya dosyasına çizim yapmak için kullanılabilir.

[CPaintDC](reference/cpaintdc-class.md) nesneleri, Windows 'un ortak deyim sayısını kapsüllemek, `BeginPaint` işlevi çağırmak, sonra cihaz bağlamında çizim yapmak ve sonra `EndPaint` işlevi çağırmak. `CPaintDC`Oluşturucu `BeginPaint` sizin için ve yok edicisi çağırır `EndPaint` . Basitleştirilmiş işlem, [CDC](reference/cdc-class.md) nesnesini oluşturmak, çizmek ve sonra nesneyi yok etmek `CDC` . Çerçevesinde, bu işlem de otomatikleştirilmiştir. Özellikle, `OnDraw` işleviniz `CPaintDC` zaten hazırlanmış (aracılığıyla `OnPrepareDC` ) olarak geçirilir ve yalnızca içine çizersiniz. Framework tarafından yok edilir ve işlevinizin çağrısından geri dönerek temeldeki cihaz bağlamı Windows 'ta serbest bırakılır `OnDraw` .

[CClientDC](reference/cclientdc-class.md) nesneleri, yalnızca bir pencerenin istemci alanını temsil eden bir cihaz bağlamı ile çalışmayı kapsüller. `CClientDC`Oluşturucu `GetDC` işlevini çağırır ve yıkıcı işlevi çağırır `ReleaseDC` . [CWindowDC](reference/cwindowdc-class.md) nesneleri, çerçevesini dahil olmak üzere tüm pencereyi temsil eden bir cihaz bağlamını kapsüller.

[CMetaFileDC](reference/cmetafiledc-class.md) nesneleri, çizimi bir Windows meta dosyasına kapsüller. Geçirilen öğesine karşılık olarak `CPaintDC` `OnDraw` , bu örnekte, [Onhazırlık EDC](reference/cview-class.md#onpreparedc) çağrısı yapmanız gerekir.

## <a name="mouse-drawing"></a>Fare çizimi

Çerçeve programında çoğu çizim — ve bu nedenle çoğu cihaz bağlamı işi — görünümün `OnDraw` üye işlevinde yapılır. Ancak, diğer amaçlar için hala cihaz bağlamı nesnelerini kullanabilirsiniz. Örneğin, bir görünümde fare hareketiyle ilgili izleme geri bildirimi sağlamak için, çağrılabilir olmadan doğrudan görünüme bir çizim yapmanız gerekir `OnDraw` .

Böyle bir durumda, bir [CClientDC](reference/cclientdc-class.md) cihaz bağlamı nesnesini kullanarak doğrudan görünüme çizim yapabilirsiniz.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Cihaz bağlamları (tanım)](/windows/win32/gdi/device-contexts)

- [Bir görünümde çizim yapma](drawing-in-a-view.md)

- [Bir görünüm aracılığıyla Kullanıcı girişini yorumlama](interpreting-user-input-through-a-view.md)

- [Çizgiler ve eğriler](/windows/win32/gdi/lines-and-curves)

- [Doldurulmuş şekiller](/windows/win32/gdi/filled-shapes)

- [Yazı tipleri ve metin](/windows/win32/gdi/fonts-and-text)

- [Renkler](/windows/win32/gdi/colors)

- [Boşluk ve dönüştürmeleri koordinat](/windows/win32/gdi/coordinate-spaces-and-transformations)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere nesneleri](window-objects.md)
