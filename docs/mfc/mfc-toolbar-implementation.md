---
title: MFC araç çubuğu uygulaması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- toolbars [MFC], creating
- buttons [MFC], MFC toolbars
- toolbars [MFC], docking
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- floating toolbars [MFC]
- toolbars [MFC], floating
- docking toolbars [MFC]
- bitmaps [MFC], toolbar
- toolbar controls [MFC]
- CToolBarCtrl class [MFC], implementing toolbars
- tool tips [MFC], enabling
- toolbars [MFC]
- toolbars [MFC], implementing MFC toolbars
ms.assetid: af3319ad-c430-4f90-8361-e6a2c06fd084
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d21bfa1dcc39e00de852203d05a2eae743b8a2f6
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929238"
---
# <a name="mfc-toolbar-implementation"></a>MFC Araç Çubuğu Uygulaması
Bir araç çubuğu bir [denetim çubuğu](../mfc/control-bars.md) denetimleri bit eşlem görüntülerini içerir. Bu görüntüleri pushbuttons, onay kutusu veya radyo düğmeleri gibi davranabilir. MFC sınıf sağlayan [CToolbar](../mfc/reference/ctoolbar-class.md) araç çubukları yönetmek için.  
  
 Etkinleştirirseniz, MFC araç çubukları kullanıcılarının bir pencere kenarına yerleştirme veya "bunları herhangi bir yerden uygulama penceresi içinde float". MFC geliştirme ortamında gelenler özelleştirilebilir araç çubukları desteklemiyor.  
  
 MFC araç ipuçları da destekler: fare düğmenin üzerine getirdiğinizde, araç düğmenin amacını açıklayan küçük açılır pencereleri. Kullanıcı bir araç çubuğu düğmesi bastığında varsayılan olarak, bir durum dizesi (varsa) durum çubuğunda görünür. "Tarafından yaklaştığında" durum çubuğunda fare düğmesini ' tuşuna basmadan getirildiğinde durum dizesi görüntülemek için güncelleştirme etkinleştirebilirsiniz.  
  
> [!NOTE]
>  MFC sürüm 4. 0'dan sonra araç çubukları ve araç ipuçları için MFC belirli önceki uygulaması yerine Windows 95 ve sonraki işlevselliği kullanılarak uygulanır.  
  
 Geriye dönük uyumluluk için MFC sınıfı eski araç uygulamasında korur `COldToolBar`. MFC önceki sürümleri için belgelere açıklamak `COldToolBar` altında `CToolBar`.  
  
 İlk araç programınızın Uygulama Sihirbazı'nda araç seçeneğini belirterek oluşturun. Ek araç çubukları de oluşturabilirsiniz.  
  
 Bu makalede aşağıdaki yapılmıştır:  
  
-   [Araç çubuğu düğmeleri](#_core_toolbar_buttons)  
  
-   [Yerleşen ve kayan araç çubukları](#_core_docking_and_floating_toolbars)  
  
-   [Araç çubukları ve araç ipuçları](#_core_toolbars_and_tool_tips)  
  
-   [CToolBar ve CToolBarCtrl sınıfları](#_core_the_ctoolbar_and_ctoolbarctrl_classes)  
  
-   [Araç çubuğu bit eşlem](#_core_the_toolbar_bitmap)  
  
##  <a name="_core_toolbar_buttons"></a> Araç çubuğu düğmeleri  
 Araç çubuğu düğmeleri için menü öğeleri benzer. Her iki tür kullanıcı arabirimi nesneleri işleyici işlevleri sağlayarak programınızı işleme komutları oluşturur. Genellikle araç çubuğu düğmeleri aynı işlevselliği için bir alternatif kullanıcı arabirimi sağlayan menü komutlarını işlevlerin birer yinelemesidir. Yalnızca düğme ve menü öğesi aynı kimliğe vererek bu tür çoğaltma düzenlenmiş  
  
 Görünür ve pushbuttons, onay kutusu veya radyo düğmeleri davranır düğmeleri bir araç çubuğu yapabilirsiniz. Daha fazla bilgi için bkz [CToolBar](../mfc/reference/ctoolbar-class.md).  
  
##  <a name="_core_docking_and_floating_toolbars"></a> Yerleşen ve kayan araç çubukları  
 MFC araç çubuğu yapabilirsiniz:  
  
-   Sütunlardan biri kendi üst penceresi sabit kalır.  
  
-   Sürüklenen ve "yerleşik" veya herhangi bir tarafında veya belirttiğiniz pencerenin üst tarafında bir kullanıcı tarafından bağlı.  
  
-   "Kaydırılmış" veya çerçeve penceresinde kullanıcı, uygun bir konuma taşıyabilirsiniz şekilde kendi kısa çerçeve penceresi bulunmuyor.  
  
-   Kayan çalışırken yeniden boyutlandırılabilir.  
  
 Daha fazla bilgi için bkz: [Docking ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md).  
  
##  <a name="_core_toolbars_and_tool_tips"></a> Araç çubukları ve araç ipuçları  
 MFC araç çubukları de yapılabilir "ipuçları aracı" görüntülenecek — küçük açılır pencereleri içeren bir araç düğmenin amacı kısa metin açıklaması. Kullanıcı bir araç çubuğu düğmesi fare taşınırken, araç ipucu penceresi ipucu sunmak için açılır. Daha fazla bilgi için bkz: [araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md).  
  
##  <a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a> CToolBar ve CToolBarCtrl sınıfları  
 Uygulamanızın araç çubukları sınıfı aracılığıyla yönetmek [CToolBar](../mfc/reference/ctoolbar-class.md). MFC sürüm 4.0 itibariyle `CToolBar` araç ortak denetimi Windows 95 altında kullanılabilir veya üstünü ve Windows NT 3.51 veya sonraki bir sürümü kullanmayı reimplemented.  
  
 MFC yaptığından bu yeniden uygulama araç çubukları, daha az MFC kodu sonuçlanır. işletim sistemi desteği kullanın. Yeniden uygulama yeteneği de geliştirir. Kullanabileceğiniz `CToolBar` araç çubukları veya işlemek için üye işlevleri, arka plandaki başvuru edinebilirsiniz [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesne ve araç çubuğunu özelleştirme ve ek işlevsellik için kendi üye işlevlerini çağırın.  
  
> [!TIP]
>  Yoğun eski MFC uygulamasında yatırım yapmış kullanıcılar, `CToolBar`, destek hala mevcuttur. Makalesine bakın [kullanarak bilgisayarınızı eski araç çubukları](../mfc/using-your-old-toolbars.md).  
  
 Ayrıca bkz. MFC genel örnek [DOCKTOOL](../visual-cpp-samples.md).  
  
##  <a name="_core_the_toolbar_bitmap"></a> Araç çubuğu bit eşlem  
 Bir kez oluşturulan bir `CToolBar` nesnesi, her düğme için bir görüntü içeren tek bir bit eşlem yükleyerek araç görüntüsü oluşturur. Uygulama Sihirbazı'nı özelleştirebileceğiniz bir standart araç bit eşlem Visual C++ ile oluşturur [araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md).  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Araç çubuğu temelleri](../mfc/toolbar-fundamentals.md)  
  
-   [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)  
  
-   [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)  
  
-   [Araç Çubuğu Denetimiyle Çalışma](../mfc/working-with-the-toolbar-control.md)  
  
-   [Eski Araç Çubuklarınızı Kullanma](../mfc/using-your-old-toolbars.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araç çubukları](../mfc/toolbars.md)   
 [Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)

