---
description: Daha fazla bilgi için bkz. araç çubuğu temelleri
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
ms.openlocfilehash: ed52c5878482f2ff0fa1c31a133fd2948d21a76e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264394"
---
# <a name="toolbar-fundamentals"></a>Araç Çubuğu Temelleri

Bu makalede, uygulama sihirbazında bir seçenek belirleyerek uygulamanıza varsayılan bir araç çubuğu eklemenize olanak sağlayan temel MFC uygulaması açıklanmaktadır. Ele alınan konular:

- [Uygulama Sihirbazı araç çubuğu seçeneği](#_core_the_appwizard_toolbar_option)

- [Koddaki araç çubuğu](#_core_the_toolbar_in_code)

- [Araç çubuğu kaynağını Düzenle](#_core_editing_the_toolbar_resource)

- [Birden çok araç çubuğu](#_core_multiple_toolbars)

## <a name="the-application-wizard-toolbar-option"></a><a name="_core_the_appwizard_toolbar_option"></a> Uygulama Sihirbazı araç çubuğu seçeneği

Varsayılan düğmelerle tek bir araç çubuğu almak için, Kullanıcı arabirimi özellikleri etiketli sayfada Standart yerleştirme araç çubuğu seçeneğini belirleyin. Bu, uygulamanıza kod ekler:

- Araç çubuğu nesnesini oluşturur.

- Araç çubuğunu, kayan nokta veya kaydırma özelliği de dahil olmak üzere yönetir.

## <a name="the-toolbar-in-code"></a><a name="_core_the_toolbar_in_code"></a> Koddaki araç çubuğu

Araç çubuğu, uygulamanızın sınıfının veri üyesi olarak belirtilen bir [CToolBar](../mfc/reference/ctoolbar-class.md) nesnesidir `CMainFrame` . Diğer bir deyişle, araç çubuğu nesnesi ana çerçeve pencere nesnesine katıştırılır. Bu, MFC 'nin çerçeve penceresini oluşturduğunda araç çubuğunu oluşturduğu ve çerçeve penceresini yok etmek için araç çubuğunu yok eden bir anlamına gelir. Birden çok belge arabirimi (MDI) uygulaması için aşağıdaki kısmi sınıf bildirimi, katıştırılmış bir araç çubuğu ve katıştırılmış durum çubuğu için veri üyelerini gösterir. Ayrıca üye işlevin geçersiz kılmasını gösterir `OnCreate` .

[!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]

Araç çubuğu oluşturma içinde oluşur `CMainFrame::OnCreate` . MFC, çerçeve için pencere oluşturduktan sonra, ancak görünür hale gelmeden önce [OnCreate](../mfc/reference/cwnd-class.md#oncreate) yöntemini çağırır. `OnCreate`Uygulama Sihirbazı 'nın oluşturduğu varsayılan değer aşağıdaki araç çubuğu görevlerini yapar:

1. `CToolBar`Temel [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesini oluşturmak Için nesnenin üye [Oluştur](../mfc/reference/ctoolbar-class.md#create) işlevini çağırır.

1. Araç çubuğu kaynak bilgilerini yüklemek için [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) 'ı çağırır.

1. Yerleştirme, kayan ve araç ipuçlarını etkinleştirmek için işlevleri çağırır. Bu çağrılar hakkında daha fazla bilgi için, bkz. [yerleştirme ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md).

> [!NOTE]
> MFC genel örnek [Dockaracı](../overview/visual-cpp-samples.md) hem eski hem de yeni MFC araç çubuklarının çizimlerini içerir. Kullanan araç çubukları, `COldToolbar` Adım 2 ' de `LoadBitmap` (yerine) ve ile çağrı gerektirir `LoadToolBar` `SetButtons` . Yeni araç çubukları için çağrılar gerektirir `LoadToolBar` .

Yerleştirme, kayan ve araç ipuçları çağrıları isteğe bağlıdır. İsterseniz bu satırları kaldırabilirsiniz `OnCreate` . Sonuç düzeltilmeyen, kaydırma yapılamıyor veya yeniden yuvaya yerleştirilemiyor ve araç ipuçları gösterilemiyor.

## <a name="editing-the-toolbar-resource"></a><a name="_core_editing_the_toolbar_resource"></a> Araç çubuğu kaynağını Düzenle

Uygulama Sihirbazı ile aldığınız varsayılan araç, MFC sürüm 4,0 ' de tanıtılan **rt_toolbar** özel bir kaynağı temel alır. Bu kaynağı [Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)ile düzenleyebilirsiniz. Düzenleyici, düğmeleri kolayca eklemenizi, silmenizi ve yeniden düzenlemenizi sağlar. Visual C++, genel grafik düzenleyicisine çok benzer düğmeler için bir grafik düzenleyici içerir. Önceki Visual C++ sürümlerindeki araç çubuklarını düzenlediyseniz, görevi daha kolay bulacaksınız.

Bir araç çubuğu düğmesini komuta bağlamak için, düğme gibi bir komut KIMLIĞI verirsiniz `ID_MYCOMMAND` . Araç çubuğu düzenleyicisindeki düğme Özellik sayfasında komut KIMLIĞINI belirtin. Ardından komut için bir işleyici işlevi oluşturun (daha fazla bilgi için bkz. [Iletileri IŞLEVLERE eşleme](../mfc/reference/mapping-messages-to-functions.md) .).

Yeni [CToolBar](../mfc/reference/ctoolbar-class.md) üye işlevleri **rt_toolbar** kaynağıyla çalışır. [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) artık, araç çubuğu düğme görüntülerinin bit eşlemini yüklemek Için [LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap) 'in yerini [alır ve düğme](../mfc/reference/ctoolbar-class.md#setbuttons) stillerini ve bağlama düğmelerini bit eşlem görüntülerle bağlayın.

Araç çubuğu düzenleyicisini kullanma hakkında ayrıntılı bilgi için bkz. [Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md).

## <a name="multiple-toolbars"></a><a name="_core_multiple_toolbars"></a> Birden çok araç çubuğu

Uygulama Sihirbazı size bir varsayılan araç çubuğu sağlar. Uygulamanızda birden fazla araç çubuğuna ihtiyacınız varsa, varsayılan araç çubuğunun sihirbaz tarafından oluşturulan koduna bağlı olarak kodunuzu ek araç çubukları için modelleyebilirsiniz.

Bir komut çubuğunu bir komutun sonucu olarak göstermek istiyorsanız şunları yapmanız gerekir:

- Araç Çubuğu Düzenleyicisi ile yeni bir araç çubuğu kaynağı oluşturun ve bunu `OnCreate` [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) üye işleviyle birlikte yükleyin.

- Ana çerçeve pencere sınıfınıza yeni bir [CToolBar](../mfc/reference/ctoolbar-class.md) nesnesi ekleyin.

- `OnCreate`Araç çubuğunu sabitlemek veya kayan hale getirmek, stillerini ayarlamak vb. için, içinde uygun işlevi çağırır.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [MFC araç çubuğu uygulama (araç çubuklarında genel bakış bilgileri)](../mfc/mfc-toolbar-implementation.md)

- [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)

- [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları

- [Araç çubuğu denetimiyle çalışma](../mfc/working-with-the-toolbar-control.md)

- [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC araç çubuğu uygulama](../mfc/mfc-toolbar-implementation.md)
