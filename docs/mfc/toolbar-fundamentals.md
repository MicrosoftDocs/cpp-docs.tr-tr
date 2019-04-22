---
title: Araç Çubuğu Temelleri
ms.date: 11/04/2016
f1_keywords:
- RT_TOOLBAR
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
ms.openlocfilehash: 9c784db2e1a482b313147e6837d6bbbd16d0ecb4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58775497"
---
# <a name="toolbar-fundamentals"></a>Araç Çubuğu Temelleri

Bu makalede Uygulama Sihirbazı'nda bir seçenek belirleyerek varsayılan araç uygulamanıza eklemenize olanak sağlayan temel MFC uygulaması. Kapsanan konular şunlardır:

- [Uygulama Sihirbazı araç seçeneği](#_core_the_appwizard_toolbar_option)

- [Kod bir araç çubuğu](#_core_the_toolbar_in_code)

- [Araç çubuğu kaynağı düzenleme](#_core_editing_the_toolbar_resource)

- [Birden çok araç çubukları](#_core_multiple_toolbars)

##  <a name="_core_the_appwizard_toolbar_option"></a> Uygulama Sihirbazı araç seçeneği

Varsayılan düğme ile tek bir araç almak için kullanıcı arabirimi özellikleri etiketli sayfasında standart yerleştirme araç seçeneği seçin. Bu kodu uygulamanıza ekler:

- Araç çubuğu nesnesi oluşturur.

- Sabitlemek veya kaydırmak için kendi yeteneği de dahil olmak üzere araç çubuğunda yönetir.

##  <a name="_core_the_toolbar_in_code"></a> Kod bir araç çubuğu

Araç çubuğu bir [CToolBar](../mfc/reference/ctoolbar-class.md) nesne, uygulamanızın veri üyesi olarak bildirilen `CMainFrame` sınıfı. Diğer bir deyişle, araç çubuğu nesnesi ana çerçeve penceresi nesnesinde katıştırılır. Başka bir deyişle, çerçeve penceresi oluşturur ve çerçeve penceresini yok eder, araç yok eder MFC araç çubuğu oluşturur. Aşağıdaki kısmi sınıf bildirimi, birden çok belge arabirimi (MDI) uygulaması için veri üyeleri için bir gömülü araç ve bir katıştırılmış durum çubuğunu gösterir. Ayrıca geçersiz kılmasını gösterir `OnCreate` üye işlevi.

[!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]

Araç çubuğu oluşturma oluşuyor `CMainFrame::OnCreate`. MFC çağrıları [OnCreate](../mfc/reference/cwnd-class.md#oncreate) pencerenin çerçevesinin ancak görünür duruma gelir önce oluşturduktan sonra. Varsayılan `OnCreate` Uygulama Sihirbazı'nın ürettiği aşağıdaki araç görevleri gerçekleştirir:

1. Çağrıları `CToolBar` nesnenin [Oluştur](../mfc/reference/ctoolbar-class.md#create) üye işlevi temel alınan [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesne.

1. Çağrıları [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) araç çubuğu kaynak bilgileri yüklenemedi.

1. Yerleştirme, kayan ve araç ipuçlarını etkinleştirme işlevleri çağırır. Bu çağrılar hakkında daha fazla ayrıntı için bkz [Docking ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md).

> [!NOTE]
>  MFC genel örnek [DOCKTOOL](../overview/visual-cpp-samples.md) eski ve yeni MFC araç çubukları çizimleri içerir. Kullandığınız araç çubuklarını `COldToolbar` çağrılar için 2. adımda gerektirir `LoadBitmap` (yerine `LoadToolBar`) ve `SetButtons`. Çağrılar yeni araç çubukları gerektiren `LoadToolBar`.

Yerleştirme, kayan ve araç ipuçları çağrıları isteğe bağlıdır. Bu satırlardan kaldırabilirsiniz `OnCreate` tercih ederseniz. Sonuç, sabit, float veya redock yapılamıyor ve araç ipuçları görüntülenemiyor kalan bir araç çubuğudur.

##  <a name="_core_editing_the_toolbar_resource"></a> Araç çubuğu kaynağı düzenleme

Uygulama Sihirbazı'nı al varsayılan araç dayalı bir **RT_TOOLBAR** MFC sürüm 4.0 içinde sunulan özel kaynak. Bu kaynakla düzenleyebileceğiniz [araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md). Düzenleyici, kolayca ekleme, silme ve düğmeleri yeniden olanak tanır. Bu, Visual C++ genel grafik düzenleyicisinde çok benzer düğmeleri için bir grafik Düzenleyicisi içerir. Önceki sürümlerinde Visual C++ araç çubukları düzenlediyseniz, görev çok daha kolay artık bulabilirsiniz.

Araç çubuğu düğmesi için bir komut bağlanmak için düğmeyi bir komut kimliği gibi size `ID_MYCOMMAND`. Düğmenin özellik sayfası araç çubuğu düzenleyicisinde komut kimliği belirtin. Ardından bir komut işleyici işlevi oluşturun (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md) daha fazla bilgi için).

Yeni [CToolBar](../mfc/reference/ctoolbar-class.md) üye işlevleri çalışın **RT_TOOLBAR** kaynak. [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) artık yerini alır [LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap) araç çubuğu düğmesi görüntü bit eşlem yüklenemiyor ve [SetButtons](../mfc/reference/ctoolbar-class.md#setbuttons) düğme stilleri ve düğme bit eşlem görüntülerle bağlama.

Araç çubuğu Düzenleyicisi'ni kullanma hakkında daha fazla ayrıntı için bkz. [araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md).

##  <a name="_core_multiple_toolbars"></a> Birden çok araç çubukları

Uygulama Sihirbazı ile bir varsayılan araç sağlar. Uygulamanızda birden fazla araç gerekiyorsa, kodunuz için varsayılan araç çubuğu için sihirbazın ürettiği kod göre ek araç çubukları modelleyebilirsiniz.

Bir komutun sonucu olarak bir araç çubuğunu görüntülemek istiyorsanız, yapmanız gerekir:

- Düzenleyici araç çubuğu ile yeni bir araç çubuğu kaynağı oluşturma ve bunu yük `OnCreate` ile [LoadToolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar) üye işlevi.

- Yeni bir ekleme [CToolBar](../mfc/reference/ctoolbar-class.md) ana çerçeve penceresi sınıfında nesne.

- Uygun işlev çağrıları yapma `OnCreate` sabitlemek veya araç float, stillerini ayarlama ve benzeri.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [MFC araç çubuğu uygulaması (araç çubuklarında genel bakış bilgileri)](../mfc/mfc-toolbar-implementation.md)

- [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)

- [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları

- [Araç çubuğu denetimiyle çalışma](../mfc/working-with-the-toolbar-control.md)

- [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Araç Çubuğu Uygulaması](../mfc/mfc-toolbar-implementation.md)
