---
title: Grafik Nesneler
ms.date: 11/04/2016
f1_keywords:
- HRGN
- HFONT
- HBITMAP
helpviewer_keywords:
- CRgn class [MFC], HRGN handle type
- HPEN [MFC]
- objects [MFC], graphic
- palettes [MFC], creating in device context
- pens [MFC], creating in device context
- bitmaps [MFC], creating in device contexts
- palette objects [MFC]
- memory [MFC], display contexts
- MFC, graphic objects
- regions [MFC], creating in device context
- CPen class [MFC], HPEN handle type
- GDI objects [MFC]
- HRGN [MFC]
- graphic objects [MFC]
- GDI objects [MFC], graphic-object classes
- CFont class [MFC], HFONT handle type
- HFONT and class CFont [MFC]
- HBITMAP and class CBitmap [MFC]
- fonts [MFC], creating in device context
- images [MFC], graphic objects [MFC]
- CBitmap class [MFC], HBITMAP handle type
- HPALETTE and class CPalette [MFC]
- CBrush class [MFC], HBRUSH handle type
- objects [MFC], graphic objects
- drawing [MFC], in device contexts
- device contexts [MFC], graphic objects [MFC]
- brushes [MFC], creating in device context
- region objects [MFC]
- pen objects [MFC]
- GDI [MFC], graphic-object classes
- graphic objects [MFC], creating in device context
- HBRUSH and class CBrush [MFC]
- painting and device context [MFC]
- CPalette class [MFC], HPALETTE handle type
ms.assetid: 41963b25-34b7-4343-8446-34ba516b83ca
ms.openlocfilehash: 4abc2764abd0f31b83253f37b8cb459be638ae5a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508533"
---
# <a name="graphic-objects"></a>Grafik Nesneler

Windows, cihaz bağlamlarında kullanmak için çeşitli çizim araçları sağlar. Çizgi çizme, türleri dolduracak fırçalar ve yazı tiplerinin metin çizmek için kalem sağlar. MFC, Windows 'daki çizim araçlarına eşdeğer grafik nesnesi sınıfları sağlar. Aşağıdaki tabloda kullanılabilir sınıflar ve eşdeğer Windows grafik cihaz arabirimi (GDI) tanıtıcı türleri gösterilmektedir.

> [!NOTE]
>  Daha fazla bilgi için bkz. [GDI+ SDK belgeleri](/windows/win32/gdiplus/-gdiplus-gdi-start).

Bu makalede, bu grafik nesnesi sınıflarının kullanımı açıklanmaktadır:

### <a name="classes-for-windows-gdi-objects"></a>Windows GDI nesneleri için sınıflar

|örneği|Windows tanıtıcı türü|
|-----------|-------------------------|
|[CPen](../mfc/reference/cpen-class.md)|`HPEN`|
|[CBrush](../mfc/reference/cbrush-class.md)|`HBRUSH`|
|[CFont](../mfc/reference/cfont-class.md)|**HFONT**|
|[CBitmap](../mfc/reference/cbitmap-class.md)|`HBITMAP`|
|[CPalette](../mfc/reference/cpalette-class.md)|`HPALETTE`|
|[CRgn](../mfc/reference/crgn-class.md)|**HRGN**|

> [!NOTE]
>  [CImage](../atl-mfc-shared/reference/cimage-class.md) sınıfı gelişmiş bit eşlem desteği sağlar.

Sınıf kitaplığındaki her bir grafik nesnesi sınıfı, bu sınıfın grafik nesneleri oluşturmanızı sağlayan bir oluşturucuya sahiptir `CreatePen`. Bu, daha sonra, gibi uygun oluşturma işleviyle başlatılmalıdır.

Sınıf kitaplığındaki her bir grafik nesnesi sınıfının, bir MFC nesnesini ilişkili Windows tanıtıcısına saçan bir atama işleci vardır. Elde edilen tutamaç, ilişkili nesne tarafından bölünene kadar geçerlidir. Tutamacı ayırmak için nesnenin `Detach` üye işlevini kullanın.

Aşağıdaki kod bir Windows tanıtıcısına `CPen` bir nesnesi yayınlar:

[!code-cpp[NVC_MFCDocViewSDI#5](../mfc/codesnippet/cpp/graphic-objects_1.cpp)]

#### <a name="to-create-a-graphic-object-in-a-device-context"></a>Bir cihaz bağlamında grafik nesnesi oluşturmak için

1. Yığın çerçevesinde bir grafik nesnesi tanımlayın. Nesnesini, `CreatePen`gibi türe özgü oluşturma işleviyle başlatın. Alternatif olarak, oluşturucudaki nesneyi başlatın. Örnek kod sağlayan [tek aşamalı ve iki aşamalı oluşturma](../mfc/one-stage-and-two-stage-construction-of-objects.md)tartışmalarına bakın.

1. Daha önce seçilmiş olan eski grafik nesnesini kaydederek [geçerli cihaz bağlamında nesneyi seçin](../mfc/selecting-a-graphic-object-into-a-device-context.md).

1. Geçerli grafik nesnesiyle işiniz bittiğinde, durumunu geri yüklemek için eski grafik nesnesini cihaz bağlamına geri doğru seçin.

1. Kapsamda çıkış yapıldığında çerçeveye ayrılan grafik nesnesinin otomatik olarak silinmesine izin verin.

> [!NOTE]
>  Art arda bir grafik nesnesi kullanacaksanız, onu bir kez ayırabilir ve gerektiğinde bir cihaz bağlamına seçebilirsiniz. Artık ihtiyaç kalmadığında bu tür bir nesneyi sildiğinizden emin olun.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Grafik nesnelerinin tek aşamalı ve iki aşamalı yapımı](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [Bir ve iki aşamada kalem oluşturma örneği](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [Bir Cihaz Bağlamına Grafik Nesnesi Seçme](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [Cihaz bağlamları](../mfc/device-contexts.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Nesneleri](../mfc/window-objects.md)
