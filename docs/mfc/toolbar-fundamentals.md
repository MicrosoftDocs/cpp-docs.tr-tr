---
title: "Araç çubuğu temelleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RT_TOOLBAR
dev_langs: C++
helpviewer_keywords:
- embedding toolbar in frame window class [MFC]
- application wizards [MFC], installing default application toolbars
- toolbars [MFC], creating
- resources [MFC], toolbar
- toolbar controls [MFC], toolbars created using Application Wizard
- toolbar controls [MFC], command ID
- RT_TOOLBAR resource [MFC]
- toolbars [MFC], adding default using Application Wizard
- LoadBitmap method [MFC], toolbars
- Toolbar editor [MFC], Application Wizard
- command IDs [MFC], toolbar buttons
- SetButtons method [MFC]
- CToolBar class [MFC], default toolbars in Application Wizard
- frame window classes [MFC], toolbar embedded in
- LoadToolBar method [MFC]
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 55e6df559d6a8365635cea7e94d20bd2576d2273
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="toolbar-fundamentals"></a>Araç Çubuğu Temelleri
Bu makalede, Uygulama Sihirbazı'nda bir seçeneğin uygulamanız için bir varsayılan araç çubuğu eklemenize olanak sağlayan temel MFC uygulaması açıklanmaktadır. Kapsanan konular şunlardır:  
  
-   [Uygulama Sihirbazı araç seçeneği](#_core_the_appwizard_toolbar_option)  
  
-   [Kod araç çubuğu](#_core_the_toolbar_in_code)  
  
-   [Araç çubuğu kaynağı düzenleme](#_core_editing_the_toolbar_resource)  
  
-   [Birden çok araç çubukları](#_core_multiple_toolbars)  
  
##  <a name="_core_the_appwizard_toolbar_option"></a>Uygulama Sihirbazı araç seçeneği  
 Tek bir araç varsayılan düğmeleri ile almak için kullanıcı arabirimi özellikleri etiketli sayfasında standart yerleştirme araç seçeneğini seçin. Bu kodu uygulamanıza ekler:  
  
-   Araç çubuğu nesnesi oluşturur.  
  
-   Yerleştirme veya float için kendi yeteneği dahil olmak üzere araç yönetir.  
  
##  <a name="_core_the_toolbar_in_code"></a>Kod araç çubuğu  
 Araç çubuğu bir [CToolBar](../mfc/reference/ctoolbar-class.md) nesne uygulamanızın veri üye olarak bildirilen **CMainFrame** sınıfı. Diğer bir deyişle, araç çubuğu nesnesi ana çerçeve penceresi nesnesinde katıştırılır. Başka bir deyişle, çerçeve penceresi oluşturduğunda ve çerçeve penceresi yok eder, araç bozar MFC araç oluşturur. Veri üyeleri katıştırılmış bir araç çubuğu ve katıştırılmış durum çubuğu için birden çok belge arabirimi (MDI) uygulaması aşağıdaki parçalı sınıf bildirimi gösterir. Ayrıca bir geçersiz kılma gösterir `OnCreate` üye işlevi.  
  
 [!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]  
  
 Araç çubuğu oluşturma oluşuyor **CMainFrame::OnCreate**. MFC çağrıları [OnCreate](../mfc/reference/cwnd-class.md#oncreate) pencere çerçevesi için ancak görünür duruma gelmesi oluşturduktan sonra. Varsayılan `OnCreate` Uygulama Sihirbazı'nın ürettiği aşağıdaki araç görevleri yapar:  
  
1.  Çağrıları `CToolBar` nesnenin [oluşturma](../mfc/reference/ctoolbar-class.md#create) arka plandaki oluşturmak için üye işlevi [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesi.  
  
2.  Çağrıları [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) araç çubuğu kaynak bilgileri yüklenemedi.  
  
3.  Yerleştirme, kayan ve araç ipuçları etkinleştirmek için işlevlerini çağırır. Makaleyi bu çağrıları hakkında daha fazla bilgi için bkz [Docking ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md).  
  
> [!NOTE]
>  MFC genel örnek [DOCKTOOL](../visual-cpp-samples.md) eski ve yeni MFC araç çubukları çizimleri içerir. Araç çubuklarını kullanın **COldToolbar** çağrıları için 2. adımda gerektiren `LoadBitmap` (yerine `LoadToolBar`) ve `SetButtons`. Yeni araç çubukları çağrıları gerektiren `LoadToolBar`.  
  
 Yerleştirme, kayan ve araç ipuçları çağrıları isteğe bağlıdır. Bu satırlarından kaldırabilirsiniz `OnCreate` tercih ederseniz. Sabit, kayan veya redock yapılamıyor ve araç ipuçları görüntülenemiyor kalır bir araç çubuğu sonucudur.  
  
##  <a name="_core_editing_the_toolbar_resource"></a>Araç çubuğu kaynağı düzenleme  
 Uygulama Sihirbazı'nı alma varsayılan araç dayalı bir **RT_TOOLBAR** özel kaynak, MFC sürüm 4.0 sunmuştur. Bu kaynakla düzenleyebilirsiniz [araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md). Düzenleyici kolayca ekleme, silme ve düğmeleri yeniden olanak sağlar. Visual C++'ta genel grafik Düzenleyicisi için çok benzer düğmeleri için grafik bir düzenleyici içerir. Araç çubukları Visual C++'ın önceki sürümlerinde düzenlediyseniz, görev çok daha kolay şimdi bulabilirsiniz.  
  
 Araç çubuğu düğmesi için bir komut bağlanmak için düğmeyi komut kimliği gibi size `ID_MYCOMMAND`. Araç çubuğu düzenleyicisinde düğmenin özellik sayfasındaki komut Kimliğini belirtin. Komutu için bir işleyici işlevi oluşturma (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md) daha fazla bilgi için).  
  
 Yeni [CToolBar](../mfc/reference/ctoolbar-class.md) üye işlevleri çalışabilirsiniz **RT_TOOLBAR** kaynak. [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) şimdi yerini alır [LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap) araç çubuğu düğmesi görüntüler, bit eşlem yüklemeye ve [SetButtons](../mfc/reference/ctoolbar-class.md#setbuttons) düğmesi stilleri ayarlama ve bit eşlem görüntülerle düğmeleri bağlanın.  
  
 Araç çubuğu Düzenleyicisi'ni kullanma hakkında daha fazla bilgi için bkz: [araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md).  
  
##  <a name="_core_multiple_toolbars"></a>Birden çok araç çubukları  
 Uygulama Sihirbazı ile bir varsayılan araç sağlar. Birden çok araç, uygulamanızda gerekiyorsa, kodunuzu varsayılan araç çubuğu için sihirbaz tarafından oluşturulan kodu göre ek araç çubukları için model oluşturabilirsiniz.  
  
 Bir komutu sonucu olarak bir araç çubuğu görüntülemek istiyorsanız, bunu yapmanız gerekir:  
  
-   Yeni bir araç çubuğu Kaynak Düzenleyicisi araç çubuğunu oluşturun ve içine yük `OnCreate` ile [LoadToolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar) üye işlevi.  
  
-   Yeni bir katıştırmak [CToolBar](../mfc/reference/ctoolbar-class.md) ana çerçeve penceresi sınıfında nesne.  
  
-   Uygun işlev çağrıları yapma `OnCreate` yerleştirme veya araç float, kendi stilleri ayarlama ve benzeri.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [MFC araç çubuğu uygulaması (çubuklarında genel bakış bilgileri)](../mfc/mfc-toolbar-implementation.md)  
  
-   [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)  
  
-   [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları  
  
-   [Araç çubuğu denetimiyle çalışma](../mfc/working-with-the-toolbar-control.md)  
  
-   [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC araç çubuğu uygulaması](../mfc/mfc-toolbar-implementation.md)

