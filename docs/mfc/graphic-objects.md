---
title: Grafik nesneler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- HRGN
- HFONT
- HBITMAP
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd8fc67f7cdc11328c4da9643f57b65a1cc6bfd0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197191"
---
# <a name="graphic-objects"></a>Grafik Nesneler
Çizim Araçları, cihaz bağlamlarında kullanmak için çeşitli Windows sağlar. Bu, kalemler, çizgiler, Fırçalar dolgu evin içindekiler ve metin çizmek için yazı tiplerini çizmek için sağlar. MFC Windows de çizim araçlarından eşdeğer grafik nesne sınıfları sağlar. Aşağıdaki tabloda kullanılabilir sınıflar ve eşdeğer Windows grafik cihaz arabirimi (GDI) tanıtıcı türlerine gösterir.  
  
> [!NOTE]
>  Daha fazla bilgi için GDI +'da SDK belgelerine bakın: [ https://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/GDIPlus/GDIPlus.asp ](https://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/gdiplus/gdiplus.asp).  
  
 Bu makalede, bu grafik nesne sınıfları kullanımını açıklar:  
  
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
>  Sınıf [Cımage](../atl-mfc-shared/reference/cimage-class.md) Gelişmiş bit eşlem desteği sağlar.  
  
 Sınıf Kitaplığı'nda her grafik nesne sınıfı, ardından uygun Oluştur işleviyle gibi başlatmalıdır söz konusu sınıfın grafik nesneleri oluşturma olanak tanıyan bir oluşturucusu vardır `CreatePen`.  
  
 Sınıf Kitaplığı'nda her grafik nesne sınıfı, ilişkili Windows işlenecek bir MFC nesne başvurusuna bir atama işleci vardır. İlişkili nesneyi ayırır kadar elde edilen tanıtıcısı geçerli değil. Nesnenin kullanın `Detach` tanıtıcısı ayrılamadı üye işlevi.  
  
 Aşağıdaki kod yayınları bir `CPen` Windows işlemek için nesne:  
  
 [!code-cpp[NVC_MFCDocViewSDI#5](../mfc/codesnippet/cpp/graphic-objects_1.cpp)]  
  
#### <a name="to-create-a-graphic-object-in-a-device-context"></a>Bir cihaz bağlamında grafik nesnesi oluşturmak için  
  
1.  Grafik nesnesi yığın çerçevesini tanımlar. Nesne türü-özel oluştur işlevi ile gibi başlatmak `CreatePen`. Alternatif olarak, oluşturucuda nesnesini başlatır. Açıklamalara [tek aşamalı ve iki aşamalı oluşturmayı](../mfc/one-stage-and-two-stage-construction-of-objects.md), kod örneği sağlar.  
  
2.  [Geçerli cihaz bağlamına nesneyi seçin](../mfc/selecting-a-graphic-object-into-a-device-context.md), eski grafik nesnesi, kaydetmeden önce seçilmiştir.  
  
3.  Geçerli grafik nesnesi ile işiniz bittiğinde, eski grafik nesnesinin durumunu geri yüklemek için geri cihaz bağlamına seçin.  
  
4.  Kapsam çıkıldı olduğunda otomatik olarak silinmesi çerçeve tarafından ayrılmış grafik nesnesi sağlar.  
  
> [!NOTE]
>  Grafik nesnesi sürekli olarak kullanacağınız bir kez ayırın ve her zaman gerekli bir cihaz bağlamına seçin. Artık ihtiyacınız olmadığında, böyle bir nesnenin silmek istediğinizden emin olun.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Grafik nesnelerin tek aşamalı ve iki aşamalı yapımı](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Bir ve iki aşamada kalem oluşturma örneği](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Bir Cihaz Bağlamına Grafik Nesnesi Seçme](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [Cihaz bağlamları](../mfc/device-contexts.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere Nesneleri](../mfc/window-objects.md)

