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
ms.openlocfilehash: d4e8793337beb2eed533fe04daf549ec21efc61d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373472"
---
# <a name="toolbar-fundamentals"></a>Araç Çubuğu Temelleri

Bu makalede, Uygulama Sihirbazı'nda bir seçenek seçerek uygulamanız için varsayılan araç çubuğu eklemenize olanak tanıyan temel MFC uygulaması açıklanmaktadır. Ele alınan konular:

- [Uygulama Sihirbazı araç çubuğu seçeneği](#_core_the_appwizard_toolbar_option)

- [Koddaki araç çubuğu](#_core_the_toolbar_in_code)

- [Araç çubuğu kaynağını düzenleme](#_core_editing_the_toolbar_resource)

- [Birden çok araç çubuğu](#_core_multiple_toolbars)

## <a name="the-application-wizard-toolbar-option"></a><a name="_core_the_appwizard_toolbar_option"></a>Uygulama Sihirbazı Araç Çubuğu Seçeneği

Varsayılan düğmeleri içeren tek bir araç çubuğu almak için, Kullanıcı Arabirimi Özellikleri etiketli sayfada Standart Yerleştirme araç çubuğu seçeneğini belirleyin. Bu, uygulamanıza şu kodları ekler:

- Araç çubuğu nesnesini oluşturur.

- Araç çubuğunu, kenetlenme veya yüzdürme yeteneği de dahil olmak üzere yönetir.

## <a name="the-toolbar-in-code"></a><a name="_core_the_toolbar_in_code"></a>Koddaki Araç Çubuğu

Araç çubuğu, uygulamanızın sınıfının veri üyesi olarak bildirilen `CMainFrame` bir [CToolBar](../mfc/reference/ctoolbar-class.md) nesnesidir. Başka bir deyişle, araç çubuğu nesnesi ana çerçeve penceresi nesnesine katıştırılır. Bu, Çerçeve penceresi oluşturduğunda MFC'nin araç çubuğunu oluşturduğu ve çerçeve penceresini yok ettiğinde araç çubuğunu yok ettiği anlamına gelir. Birden çok belge arabirimi (MDI) uygulaması için aşağıdaki kısmi sınıf bildirimi, gömülü bir araç çubuğu ve katıştırılmış durum çubuğu için veri üyelerini gösterir. Ayrıca `OnCreate` üye işlevin geçersiz kılma gösterir.

[!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]

Araç çubuğu oluşturma `CMainFrame::OnCreate`. MFC, çerçeve için pencereyi oluşturduktan sonra ancak görünür hale gelmeden önce [OnCreate'i](../mfc/reference/cwnd-class.md#oncreate) çağırır. Uygulama `OnCreate` Sihirbazı'nın oluşturduğu varsayılan, aşağıdaki araç çubuğu görevlerini yapar:

1. Alttaki `CToolBar` [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesini oluşturmak için nesnenin [Oluştur](../mfc/reference/ctoolbar-class.md#create) üye işlevini çağırır.

1. Araç çubuğu kaynak bilgilerini yüklemek için [LoadToolBar'ı](../mfc/reference/ctoolbar-class.md#loadtoolbar) çağırır.

1. Yerleştirme, kayan ve takım uçlarını etkinleştirmek için işlevleri çağırır. Bu aramalar hakkında ayrıntılı bilgi için, [docking ve Kayan Araç Çubukları](../mfc/docking-and-floating-toolbars.md)makalesine bakın.

> [!NOTE]
> MFC Genel örnek [DOCKTOOL](../overview/visual-cpp-samples.md) hem eski hem de yeni MFC araç çubuklarının çizimlerini içerir. Kullanılan `COldToolbar` araç çubukları, adım 2'deki `LoadBitmap` aramaları `LoadToolBar`(yerine) ve `SetButtons`. Yeni araç çubukları için `LoadToolBar`aramalar gerektirir.

Yerleştirme, kayan ve araç ipuçları aramaları isteğe bağlıdır. `OnCreate` İsterseniz bu satırları kaldırabilirsiniz. Sonuç, sabit kalan, yüzdürülemeyen veya yeniden sabitleyemeyen ve araç ipuçlarını görüntüleyemeyen bir araç çubuğudur.

## <a name="editing-the-toolbar-resource"></a><a name="_core_editing_the_toolbar_resource"></a>Araç Çubuğu Kaynağını Düzenleme

Uygulama Sihirbazı ile elde ettiğiniz varsayılan araç çubuğu, MFC sürüm 4.0'da tanıtılan **RT_TOOLBAR** özel bir kaynağa dayanır. Bu kaynağı araç çubuğu [düzenleyicisi](../windows/toolbar-editor.md)ile birlikte edinebilirsiniz. Düzenleyici, düğmeleri kolayca eklemenizi, silmenizi ve yeniden düzenlemenizi sağlar. Visual C++'daki genel grafik düzenleyicisine çok benzeyen düğmeler için bir grafik düzenleyicisi içerir. Visual C++'ın önceki sürümlerinde araç çubukları düzenlediyseniz, görevi artık çok daha kolay bulacaksınız.

Araç çubuğu düğmesini bir komuta bağlamak için düğmeye bir komut `ID_MYCOMMAND`kimliği verirsiniz. Araç çubuğu düzenleyicisinde düğmenin özellik sayfasında komut kimliğini belirtin. Ardından komut için bir işleyici işlevi oluşturun (daha fazla bilgi için [İşlevlere İletileri Eşleme'ye](../mfc/reference/mapping-messages-to-functions.md) bakın).

Yeni [CToolBar](../mfc/reference/ctoolbar-class.md) üye işlevleri **RT_TOOLBAR** kaynağı ile çalışır. [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) artık araç çubuğu düğme görüntülerinin bit haritasını yüklemek için [LoadBitmap'in](../mfc/reference/ctoolbar-class.md#loadbitmap) yerini alır ve düğme stillerini ayarlamak ve bitmap görüntüleriyle düğmeleri bağlamak için [Düğmeleri Ayarlar.](../mfc/reference/ctoolbar-class.md#setbuttons)

Araç çubuğu düzenleyicisini kullanma hakkında ayrıntılı bilgi için [Araç Çubuğu Düzenleyicisi'ne](../windows/toolbar-editor.md)bakın.

## <a name="multiple-toolbars"></a><a name="_core_multiple_toolbars"></a>Birden Çok Araç Çubuğu

Uygulama Sihirbazı size bir varsayılan araç çubuğu sağlar. Uygulamanızda birden fazla araç çubuğuna ihtiyacınız varsa, varsayılan araç çubuğu için sihirbaz tarafından oluşturulan kodu temel alan ek araç çubukları için kodunuzu modelleyebilirsiniz.

Bir komutun sonucu olarak bir araç çubuğu görüntülemek istiyorsanız, şunları yapmanız gerekir:

- Araç çubuğu düzenleyicisi ile yeni bir araç `OnCreate` çubuğu kaynağı oluşturun ve [LoadToolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar) üye işleviile yükleyin.

- Ana çerçeve pencere sınıfınıza yeni bir [CToolBar](../mfc/reference/ctoolbar-class.md) nesnesi yerleştirin.

- Araç çubuğunu `OnCreate` sabitlemek veya yüzdürmek, stillerini ayarlamak ve benzeri şekilde uygun işlev çağrıları yapın.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [MFC Araç Çubuğu Uygulaması (araç çubuklarına genel bakış bilgileri)](../mfc/mfc-toolbar-implementation.md)

- [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)

- [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları

- [Araç çubuğu denetimiyle çalışma](../mfc/working-with-the-toolbar-control.md)

- [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Araç Çubuğu Uygulaması](../mfc/mfc-toolbar-implementation.md)
