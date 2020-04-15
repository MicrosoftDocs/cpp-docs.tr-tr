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
ms.openlocfilehash: 0201e53114b71c02877762f89cc65fc46d17700c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370521"
---
# <a name="graphic-objects"></a>Grafik Nesneler

Windows, aygıt bağlamlarında kullanılacak çeşitli çizim araçları sağlar. Çizgiler çizmek için kalemler, iç mekanları doldurmak için fırçalar ve metin çizmek için yazı tipleri sağlar. MFC, Windows'daki çizim araçlarına eşdeğer grafik nesnesınıfları sağlar. Aşağıdaki tabloda kullanılabilir sınıflar ve eşdeğer Windows grafik aygıtı arabirimi (GDI) tutamacı türleri gösterilmektedir.

> [!NOTE]
> Daha fazla bilgi için [GDI+ SDK belgelerine](/windows/win32/gdiplus/-gdiplus-gdi-start)bakın.

Bu makalede, bu grafik nesnesınıflarının kullanımı açıklanmaktadır:

### <a name="classes-for-windows-gdi-objects"></a>Windows GDI Nesneleri için sınıflar

|Sınıf|Windows tutamacı türü|
|-----------|-------------------------|
|[Cpen](../mfc/reference/cpen-class.md)|`HPEN`|
|[Cbrush](../mfc/reference/cbrush-class.md)|`HBRUSH`|
|[Cfont](../mfc/reference/cfont-class.md)|**HFONT**|
|[Cbitmap](../mfc/reference/cbitmap-class.md)|`HBITMAP`|
|[Cpalette](../mfc/reference/cpalette-class.md)|`HPALETTE`|
|[Crgn](../mfc/reference/crgn-class.md)|**HRGN**|

> [!NOTE]
> [CImage](../atl-mfc-shared/reference/cimage-class.md) sınıfı gelişmiş bit map desteği sağlar.

Sınıf kitaplığındaki her grafik nesne sınıfı, bu sınıfın grafik nesnelerini oluşturmanıza olanak tanıyan bir oluşturucuya sahiptir `CreatePen`ve bu nesneleri daha sonra .

Sınıf kitaplığındaki her grafik nesnesi sınıfı, ilişkili Windows tanıtıcısına bir MFC nesnesi atan bir döküm işleci vardır. Elde edilen tutamaç, ilişkili nesne onu ayırana kadar geçerlidir. Tutamacı ayırmak `Detach` için nesnenin üye işlevini kullanın.

Aşağıdaki kod bir `CPen` nesneyi Windows tanıtıcısına atar:

[!code-cpp[NVC_MFCDocViewSDI#5](../mfc/codesnippet/cpp/graphic-objects_1.cpp)]

#### <a name="to-create-a-graphic-object-in-a-device-context"></a>Aygıt bağlamında grafik nesneoluşturmak için

1. Yığın çerçevesi üzerinde bir grafik nesnesi tanımlayın. Türüne özgü oluşturma işlevi ile nesneyi `CreatePen`başlatma. Alternatif olarak, oluşturucudaki nesneyi başharfe aktarın. Örnek kod sağlayan [tek aşamalı ve iki aşamalı oluşturma](../mfc/one-stage-and-two-stage-construction-of-objects.md)tartışmasına bakın.

1. [Nesneyi geçerli aygıt bağlamına seçin](../mfc/selecting-a-graphic-object-into-a-device-context.md)ve daha önce seçili olan eski grafik nesnesini kaydedin.

1. Geçerli grafik nesnesi ile yapıldığında, durumunu geri yüklemek için eski grafik nesnesini aygıt bağlamına geri seçin.

1. Kapsam çıkarıldığında çerçeve ye ayrılan grafik nesnesinin otomatik olarak silinmesine izin verin.

> [!NOTE]
> Bir grafik nesnesi art arda kullanacaksanız, bir kez ayırabilir ve her gerektiğinde aygıt bağlamına seçebilirsiniz. Artık ihtiyacınız olmadığında böyle bir nesneyi sildiğinizi unutmayın.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Grafik nesnelerin tek aşamalı ve iki aşamalı yapısı](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [Bir ve iki aşamada kalem oluşturma örneği](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [Aygıt Bağlamına Grafik Nesne seçme](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [Cihaz bağlamları](../mfc/device-contexts.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Nesneleri](../mfc/window-objects.md)
