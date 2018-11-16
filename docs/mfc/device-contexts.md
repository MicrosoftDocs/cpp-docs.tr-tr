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
ms.openlocfilehash: 105e438a9ed3e8f7de7edc813fec516c0e99700a
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694692"
---
# <a name="device-contexts"></a>Cihaz Bağlamları

Bir cihaz bağlamı, bir cihazın bir görüntü veya yazıcı gibi çizim öznitelikleri hakkında bilgi içeren Windows bir veri yapısıdır. Tüm çizim çağrıları çizim çizgiler, şekiller ve metin için Windows API'ları kapsülleyen bir cihaz bağlamındaki nesne ile yapılır. Cihaz bağlamları Windows CİHAZDAN bağımsız çizim izin verir. Cihaz bağlamları ekran, yazıcı veya bir meta dosyası çizmek için kullanılabilir.

[CPaintDC](../mfc/reference/cpaintdc-class.md) nesneleri kapsülleyen çağırma Windows, ortak deyimidir `BeginPaint` işlevi, ardından cihaz bağlamında çizmek ardından çağırma `EndPaint` işlevi. `CPaintDC` Oluşturucu çağrıları `BeginPaint` ve yıkıcı çağrıları için `EndPaint`. Oluşturmak için Basitleştirilmiş işlemidir [CDC](../mfc/reference/cdc-class.md) nesne çizin ve ardından yok `CDC` nesne. Framework'te bile bu işlemin otomatikleştirildi. Özellikle, `OnDraw` işlevi geçirilen bir `CPaintDC` önceden hazırlanmış (aracılığıyla `OnPrepareDC`), ve yalnızca içine çizin. Framework tarafından yok edilir ve temel alınan cihaz bağlamı için Windows return çağrısından sonra serbest bırakılır, `OnDraw` işlevi.

[CClientDC](../mfc/reference/cclientdc-class.md) nesneleri kapsülleyen yalnızca bir pencerenin istemci alanını temsil eden bir cihaz bağlamı ile çalışma. `CClientDC` Oluşturucu çağrıları `GetDC` işlevi ve yok edici çağrıları `ReleaseDC` işlevi. [CWindowDC](../mfc/reference/cwindowdc-class.md) nesneleri kapsülleyen çerçevesini dahil olmak üzere tüm pencereyi temsil eden bir cihaz bağlamı.

[CMetaFileDC](../mfc/reference/cmetafiledc-class.md) nesneleri çizim bir Windows Meta dosyası halinde kapsüller. Tersine `CPaintDC` geçirilen `OnDraw`, bu durumda çağırmalıdır [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) kendiniz.

## <a name="mouse-drawing"></a>Fare çizim

Çoğu bir çerçeve programında çizim — ve böylece çoğu cihaz bağlamı iş — görünümün içinde yapılır `OnDraw` üye işlevi. Ancak, cihaz bağlamı nesnesinin diğer amaçlar için kullanmaya devam edebilirsiniz. Örneğin, bir görünümde fare hareketini izleme geri bildirim sağlamak için doğrudan görünüme beklemeden çizmek ihtiyacınız `OnDraw` çağrılabilir.

Böyle bir durumda, kullandığınız bir [CClientDC](../mfc/reference/cclientdc-class.md) doğrudan görünüme çizmek için cihaz bağlamındaki nesne.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Cihaz bağlamları (tanım)](/windows/desktop/gdi/device-contexts)

- [Bir Görünümde Çizim Yapma](../mfc/drawing-in-a-view.md)

- [Bir Görünümü Kullanarak Kullanıcı Girişini Yorumlama](../mfc/interpreting-user-input-through-a-view.md)

- [Çizgiler ve eğriler](/windows/desktop/gdi/lines-and-curves)

- [Doldurulmuş şekiller](/windows/desktop/gdi/filled-shapes)

- [Yazı tipleri ve metin](/windows/desktop/gdi/fonts-and-text)

- [Renkler](/windows/desktop/gdi/colors)

- [Koordinat ve dönüştürmeler](/windows/desktop/gdi/coordinate-spaces-and-transformations)

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere Nesneleri](../mfc/window-objects.md)

