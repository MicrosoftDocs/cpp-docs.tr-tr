---
title: Grafik nesneleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6dfdba311ed13b1ffbd5e1f830d6fa87cfce915d
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="graphic-objects"></a>Grafik Nesneler
Windows cihaz bağlamlarında kullanmak için Araçlar çizim çeşitli sağlar. Çizgiler, dolgu evin içindekiler ve metin çizmek için yazı tiplerini Fırçalar çizmek için Kalem sağlar. MFC Windows çizim araçları eşdeğer grafik nesne sınıfları sağlar. Aşağıdaki tabloda kullanılabilir sınıfların ve eşdeğer Windows grafik cihaz arabirimi (GDI) tanıtıcısı türleri gösterilmektedir.  
  
> [!NOTE]
>  Daha fazla bilgi için GDI + SDK belgelerine bakın: [http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/GDIPlus/GDIPlus.asp](http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/gdiplus/gdiplus.asp).  
  
 Bu makale, bu grafik nesne sınıfları kullanımını açıklar:  
  
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
  
 Sınıf Kitaplığı'nda her grafik nesne sınıfı, ardından uygun oluşturma işleviyle gibi başlatmalıdır o sınıfın grafik nesnelerini oluşturmanıza olanak tanır kurucusunun `CreatePen`.  
  
 Sınıf Kitaplığı'nda her grafik nesnesi sınıf MFC nesneye ilişkili Windows tanıtıcı cast atama işleci sahiptir. İlişkili nesne bu ayırır kadar sonuç tanıtıcı geçerli değil. Nesnenin kullanmak **ayırma** tanıtıcı ayırmak için üye işlevi.  
  
 Aşağıdaki kod atamaları bir `CPen` Windows işlenecek nesne:  
  
 [!code-cpp[NVC_MFCDocViewSDI#5](../mfc/codesnippet/cpp/graphic-objects_1.cpp)]  
  
#### <a name="to-create-a-graphic-object-in-a-device-context"></a>Cihaz bağlamında bir grafik nesnesi oluşturmak için  
  
1.  Grafik nesnesi üzerinde yığın çerçevesi tanımlayın. Nesne türüne özgü oluştur işlevi ile gibi başlatılamıyor `CreatePen`. Alternatif olarak, oluşturucuda nesneyi başlatın. Açıklamalara [tek aşamalı ve iki aşamalı oluşturma](../mfc/one-stage-and-two-stage-construction-of-objects.md), örnek kod sağlar.  
  
2.  [Geçerli cihaz bağlamına nesneyi seçin](../mfc/selecting-a-graphic-object-into-a-device-context.md), eski grafik nesnesi kaydetmeden önce seçilmedi.  
  
3.  Geçerli grafik nesnesi ile işiniz bittiğinde, eski grafik nesnesi durumuna geri yüklemek için geri cihaz bağlamına seçin.  
  
4.  Kapsam çıkıldı olduğunda otomatik olarak silinecek çerçeve ayrılmış grafik nesnesi izin verin.  
  
> [!NOTE]
>  Bir grafik nesnesi sürekli olarak kullanıyorsanız, bir kez ayırabilir ve gerektiğinde her zaman bir cihaz bağlamına seçin. Artık ihtiyacınız olduğunda bu tür bir nesneyi silmek istediğinizden emin olun.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Grafik nesnelerin tek aşamalı ve iki aşamalı yapımı](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Bir ve iki aşamada kalem oluşturma örneği](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Bir Cihaz Bağlamına Grafik Nesnesi Seçme](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [Cihaz bağlamları](../mfc/device-contexts.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere Nesneleri](../mfc/window-objects.md)

