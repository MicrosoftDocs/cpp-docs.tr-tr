---
title: Windows | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- objects [MFC], window
- windows [MFC]
- MFC, windows
- window objects [MFC], MFC Framework
ms.assetid: dd92bf34-842e-40fe-8aea-3028b55314d5
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 55b1445675762bb715e7b879e8336b7ccf73c7eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="windows"></a>Windows
Bu makaleler ailesi MFC çerçevesi pencere nesneleri kapsar. Tüm MFC windows sınıfından türetilen [CWnd](../mfc/reference/cwnd-class.md)çerçeve pencereleri, görünümler, iletişim kutuları ve denetimleri dahil olmak üzere.  
  
 Makalelerin ilk grubu tanımlayan [pencere nesneleri](../mfc/window-objects.md) genel. C++ pencere nesneleri, nasıl bunlar HWND kapsüllemek ve bunları alt windows gibi kendi windows oluştururken kullanma hakkında genel bilgi için bu gruba başvurun.  
  
 Makalelerin ikinci grubu tanımlayan [çerçeve windows](../mfc/frame-windows.md)— içeriğin etrafında bir çerçeve put windows — özellikle. MFC çerçevesi çerçeve pencereleri ve bunlar, Denetim çubuklarını ve görünümleri de dahil olmak üzere, çerçeve içeriği nasıl yönettiği hakkında bilgi için bu grubu bakın.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
 *Genel pencere nesnelerde konuları*  
  
-   [Pencere nesneleri](../mfc/window-objects.md)  
  
-   [C++ arasındaki ilişki pencere nesneleri ve HWND işleme](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)  
  
-   [Türetilen pencere sınıfları](../mfc/derived-window-classes.md)  
  
-   [Pencere nesneleri oluşturma](../mfc/creating-windows.md)  
  
-   [Pencere nesnelerini yok etme](../mfc/destroying-window-objects.md)  
  
-   [Pencere "sınıflarını" kaydetme](../mfc/registering-window-classes.md)  
  
-   [Pencere nesneleriyle çalışma](../mfc/working-with-window-objects.md)  
  
-   [Cihaz bağlamları](../mfc/device-contexts.md): aygıttan bağımsız Windows çizim yapmak nesneleri  
  
-   [Grafik nesneleri](../mfc/graphic-objects.md): kalemler, Fırçalar, yazı tipleri, bit eşlemler, paletler, bölgeler  
  
 *Çerçeve penceresi konuları*  
  
-   [Çerçeve windows](../mfc/frame-windows.md): çerçeve sağlamak pencere nesneleri  
  
-   [Çerçeve pencereleri ve görünümler](../mfc/frame-windows.md)  
  
-   [Çerçeve penceresi sınıfları](../mfc/frame-window-classes.md)  
  
-   [Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)  
  
-   [MFC tarafından oluşturulan pencerenin stillerini değiştirme](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [Çerçeve pencerelerinin görevi](../mfc/what-frame-windows-do.md)  
  
-   [Çerçeve pencerelerini kullanma](../mfc/using-frame-windows.md)  
  
-   [(MDICLIENT penceresi) MD/alt öğe pencerelerini yönetme](../mfc/managing-mdi-child-windows.md)  
  
-   [Menüleri, Denetim çubuklarını ve Hızlandırıcıları yönetme](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [CFrameWnd](../mfc/reference/cframewnd-class.md)  
  
-   [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
  
-   [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md)  
  
-   [Görünümleri kullanma](../mfc/using-views.md)  
  
-   [Birden çok belge türü, görünümler ve çerçeve pencereleri (Bölümlendirici pencereler)](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [İletiler (eşlemeleri ve işleyici işlevleri)](../mfc/messages.md)  
  
 *Oluşturma ve Windows yok*  
  
-   [Genel pencere oluşturma dizisi](../mfc/general-window-creation-sequence.md)  
  
-   [Pencere nesneleri yok](../mfc/destroying-window-objects.md)  
  
-   [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)  
  
-   [Çerçeve pencerelerini yok](../mfc/destroying-frame-windows.md)  
  
 *Bölümlendirici pencereler oluşturma*  
  
-   [Bölümlendirici pencereler oluşturma](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
 *Alt pencereler ve geçerli görünümü yönetme*  
  
-   [MDI alt öğe pencerelerini yönetme](../mfc/managing-mdi-child-windows.md)  
  
-   [Geçerli görünümü yönetme](../mfc/managing-the-current-view.md)  
  
-   [Menüleri, Denetim çubuklarını ve Hızlandırıcıları yönetme](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
 *Cihaz bağlamları ve pencere stilleri ile çalışma*  
  
-   [Cihaz bağlamında kalemler ve diğer grafik nesnelerini kullanın](../mfc/graphic-objects.md)  
  
-   [MFC tarafından oluşturulan pencerenin stillerini değiştirme](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)   
 [İletişim kutuları](../mfc/dialog-boxes.md)   
 [Araç çubukları](../mfc/toolbars.md)   
 [Durum çubukları](../mfc/status-bars.md)   
 [İletişim kutusu çubukları](../mfc/dialog-bars.md)

