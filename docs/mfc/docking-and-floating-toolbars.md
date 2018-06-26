---
title: Yerleşen ve kayan araç çubukları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CBRS_SIZE_DYNAMIC
- CBRS_SIZE_FIXED
dev_langs:
- C++
helpviewer_keywords:
- size [MFC], toolbars
- size
- frame windows [MFC], toolbar docking
- CBRS_ALIGN_ANY constant [MFC]
- palettes, floating
- toolbars [MFC], docking
- CBRS_SIZE_DYNAMIC constant [MFC]
- floating toolbars
- toolbars [MFC], size
- toolbars [MFC], floating
- fixed-size toolbars
- CBRS_SIZE_FIXED constant [MFC]
- toolbar controls [MFC], wrapping
- toolbars [MFC], wrapping
- floating palettes
ms.assetid: b7f9f9d4-f629-47d2-a3c4-2b33fa6b51e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 317527d87c12a0c140c4a618ec4500dbe12bb003
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931895"
---
# <a name="docking-and-floating-toolbars"></a>Yerleşen ve Kayan Araç Çubukları
Microsoft Foundation Class Kitaplığı dockable araç çubukları destekler. Dockable araç çubuğu bağlı veya, kendi üst penceresi herhangi bir kenarında yerleşik veya ayrılmış veya yükleyebilir, kendi kısa çerçeve penceresinde kaydırılmış. Bu makalede, uygulamalarınızda dockable araç çubukları kullanımı açıklanmaktadır.  
  
 Uygulamanızın çatıyı oluşturmak için Uygulama Sihirbazı'nı kullanırsanız dockable araç çubukları isteyip istemediğinizi seçin istenir. Varsayılan olarak, Uygulama Sihirbazı'nı dockable araç çubuğu uygulamanızda yerleştirmek için gereken üç eylem gerçekleştirir kod oluşturur:  
  
-   [Bir çerçeve penceresinde yerleştirme etkinleştirmek](#_core_enabling_docking_in_a_frame_window).  
  
-   [Etkinleştirmek için bir araç çubuğu yerleştirme](#_core_enabling_docking_for_a_toolbar).  
  
-   [Araç çubuğu yerleştirme (çerçeve penceresi için)](#_core_docking_the_toolbar).  
  
 Bu adımlardan herhangi birini eksikse, uygulamanızın standart bir araç çubuğu görüntülenir. Son iki adımı, her dockable araç çubuğu, uygulamanızda için gerçekleştirilmelidir.  
  
 Bu makalede ele alınan diğer konular şunlardır:  
  
-   [Kayan araç çubuğu](#_core_floating_the_toolbar)  
  
-   [Araç çubuğu dinamik olarak yeniden boyutlandırma](#_core_dynamically_resizing_the_toolbar)  
  
-   [Ayarı kaydırma konumlar için sabit stil araç çubuğu](#_core_setting_wrap_positions_for_a_fixed_style_toolbar)  
  
 MFC genel örnek bkz [DOCKTOOL](../visual-cpp-samples.md) örnekleri için.  
  
##  <a name="_core_enabling_docking_in_a_frame_window"></a> Bir çerçeve penceresinde yerleştirme etkinleştirme  
 Araç çubukları için bir çerçeve pencere sabitlemek için çerçeve penceresi (veya hedef) yerleştirme izin vermek için etkinleştirilmesi gerekir. Bu yapılır kullanarak [CFrameWnd::EnableDocking](../mfc/reference/cframewnd-class.md#enabledocking) alır işlevi *DWORD* stil bir dizi parametre BITS yerleştirme çerçeve penceresi hangi tarafının kabul belirten. Bir araç hakkında yerleşik için ise ve için yerleşik birden fazla kenara vardır, yanları belirtilen geçirilen parametre `EnableDocking` aşağıdaki sırayla kullanılır: üst, alt, sol, sağ. Kullanabilmek isterseniz, Denetim sabitlemek için herhangi bir yere çubuklarını, geçirmek **cbrs_alıgn_any** için `EnableDocking`.  
  
##  <a name="_core_enabling_docking_for_a_toolbar"></a> İçin bir araç çubuğu yerleştirme etkinleştirme  
 Yerleştirme için hedef hazırladıktan sonra araç çubuğu (veya kaynak) benzer bir şekilde hazırlamanız gerekir. Çağrı [CControlBar::EnableDocking](../mfc/reference/ccontrolbar-class.md#enabledocking) sabitlemek istediğiniz her araç için hedef belirleme kenarlara araç çubuğu yerleştirme. Yapılan çağrıda belirtilen yanları hiçbiri `CControlBar::EnableDocking` çerçeve penceresinde yerleştirme için etkin yanları eşleşmiyor, araç sabitleyemezsiniz — float. Kaydırılmış olan sonra çerçeve penceresi yerleştirme kuramıyor kayan araç kalır.  
  
 İstediğiniz efekti kalıcı olarak kayan araç çubuğunu çağırır `EnableDocking` bir parametre 0 ile. ' I çağırın [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar). Araç çubuğu kayan, herhangi bir yere yerleştirme kurulamıyor kalıcı olarak kalır.  
  
##  <a name="_core_docking_the_toolbar"></a> Araç çubuğu yerleştirme  
 Framework çağrıları [CFrameWnd::DockControlBar](../mfc/reference/cframewnd-class.md#dockcontrolbar) çalıştığında kullanıcı araç çubuğu yerleştirme verir çerçeve penceresi tarafında bırakın.  
  
 Buna ek olarak, Denetim çubuklarını çerçeve pencere sabitlemek için herhangi bir zamanda bu işlevini çağırın. Bu, başlatma sırasında normal olarak gerçekleştirilir. Birden çok araç, belirli bir çerçeve penceresi kenarına yerleştirilmiş.  
  
##  <a name="_core_floating_the_toolbar"></a> Kayan araç çubuğu  
 Çerçeve penceresinden dockable araç ayırma kayan araç çubuğu adı verilir. Çağrı [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar) Bunu yapmak için. Kaydırılmış için araç çubuğunda, nereye yerleştirileceğini noktası ve kayan araç yatay veya dikey olup olmadığını belirleyen bir hizalama stili belirtin.  
  
 Bir kullanıcı bir araç çubuğu sabitlendiği konumdan sürüklediği ve burada yerleştirme etkin bir konumda bırakır framework bu işlevi çağırır. Bu herhangi bir yere çerçeve penceresinin içinde veya dışında olabilir. İle `DockControlBar`, bu işlev başlatma sırasında çağırabilirsiniz.  
  
 MFC uygulaması dockable araç çubukları, bazı dockable araç çubukları destekleyen bazı uygulamalarda bulunan genişletilmiş özellikler sağlamaz. Özelleştirilebilir araç çubukları gibi özellikleri sağlanmadı.  
  
##  <a name="_core_dynamically_resizing_the_toolbar"></a> Araç çubuğu dinamik olarak yeniden boyutlandırma  
 Visual C++ sürüm 4.0 itibariyle bunu kayan araç çubukları dinamik olarak yeniden boyutlandırmak için uygulamanızı kullanıcılar için olası duruma getirebilirsiniz. Genellikle, bir araç çubuğu yatay olarak bir uzun, doğrusal şekli vardır. Ancak, araç çubuğunun yönlendirmesini ve şeklini değiştirebilirsiniz. Örneğin, kullanıcı bir çerçeve penceresi dikey tarafının karşı bir araç çubuğu docks, Şekil dikey bir düzene değiştirir. Araç çubuğu düğmelerini birden çok satır ile dikdörtgenin içine yeniden şekillendirmek mümkündür.  
  
 Şunları yapabilirsiniz:  
  
-   Dinamik boyutlandırma araç özelliği olarak belirtin.  
  
-   Sabit boyutlandırma araç özelliği olarak belirtin.  
  
 Bu destek sağlamak için vardır aramalarınız kullanmak için iki yeni araç çubuğu stilleri [CToolBar::Create](../mfc/reference/ctoolbar-class.md#create) üye işlevi. Bunlar:  
  
-   **Cbrs_sıze_dynamıc** denetim çubuğu dinamik.  
  
-   **Cbrs_sıze_fıxed** denetim çubuğu sabittir.  
  
 Boyutu dinamik stili kayan sırada ancak değil takılıyken araç çubuğunu yeniden boyutlandırmak, kullanıcının izin verir. Araç çubuğu "kendi kenarları kullanıcının sürüklediği gibi şeklini değiştirmek için gerektiğinde sarmalar".  
  
 Stil sabit boyutu düğmeleri konumunu her sütunda düzelttikten bir araç çubuğu kaydırma durumlarını korur. Uygulamanızın kullanıcı araç şeklini değiştiremezsiniz. Araç çubuğu düğmeleri arasındaki ayırıcıları konumlarını gibi belirlenmiş bir yerde sarmalar. Araç yerleşik kayan olup bu şeklin tutar. Sabit palet düğmelerinin birden fazla sütunlu etkisidir.  
  
 Aynı zamanda [CToolBar::GetButtonStyle](../mfc/reference/ctoolbar-class.md#getbuttonstyle) durumu ve stil düğmelerinin çubuklarınızı üzerinde dönün. Düğmenin stilini düğmesi nasıl göründüğünü ve nasıl kullanıcı girişine yanıt vereceğini belirler; Durum düğmesi Sarmalanan bir durumda olup olmadığını bildirir.  
  
##  <a name="_core_setting_wrap_positions_for_a_fixed_style_toolbar"></a> Ayarı kaydırma konumlar için sabit stil araç çubuğu  
 Stil sabit boyutu olan bir araç için araç çubuğu düğmesi dizinleri, araç kaydırılır belirleyin. Aşağıdaki kod, ana çerçeve penceresinin nasıl yapılacağı gösterilmektedir `OnCreate` geçersiz kıl:  
  
 [!code-cpp[NVC_MFCDocViewSDI#10](../mfc/codesnippet/cpp/docking-and-floating-toolbars_1.cpp)]  
  
 MFC genel örnek [DOCKTOOL](../visual-cpp-samples.md) sınıfların üye işlevlerinin nasıl kullanılacağı gösterilmektedir [CControlBar](../mfc/reference/ccontrolbar-class.md) ve [CToolBar](../mfc/reference/ctoolbar-class.md) dinamik bir araç çubuğu yerleşimini yönetmek için. EDITBAR dosyasına bakın. CPP DOCKTOOL içinde.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Araç çubuğu temelleri](../mfc/toolbar-fundamentals.md)  
  
-   [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)  
  
-   [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Araç Çubuğu Uygulaması](../mfc/mfc-toolbar-implementation.md)

