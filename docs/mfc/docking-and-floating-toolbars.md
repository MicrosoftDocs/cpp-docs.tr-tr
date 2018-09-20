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
ms.openlocfilehash: 95990ef4f1d2b1c6eb4278f645226e57b67e15e8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399034"
---
# <a name="docking-and-floating-toolbars"></a>Yerleşen ve Kayan Araç Çubukları

Microsoft Foundation Class Kitaplığı yerleştirilebilir araç çubukları destekler. Yerleştirilebilir bir araç çubuğu bağlı olabileceği gibi herhangi bir kenarında üst pencereye sabitlenmiş veya ayrılmış veya yükleyebilir, kendi Mini çerçeve penceresinde kaydırıldı. Bu makalede, uygulamalarınızda yerleştirilebilir araç çubukları kullanmayı açıklar.

Uygulamanızın çatıyı oluşturmak için Uygulama Sihirbazı'nı kullanırsanız yerleştirilebilir araç çubukları isteyip istemediğinizi seçin istenir. Varsayılan olarak, uygulamanızda yerleştirilebilir bir araç çubuğu yerleştirmek için gereken üç eylem gerçekleştiren kod Uygulama Sihirbazı oluşturur:

- [Bir çerçeve penceresinde yerleştirme etkinleştirme](#_core_enabling_docking_in_a_frame_window).

- [Etkinleştirmek için bir araç çubuğu yerleştirme](#_core_enabling_docking_for_a_toolbar).

- [Araç çubuğu (Çerçeve penceresine) sabitlemek](#_core_docking_the_toolbar).

Bu adımlardan herhangi biri eksikse, uygulamanızın bir standart araç çubuğu görüntülenir. Son iki adımı, uygulamanızdaki her yerleştirilebilir araç için gerçekleştirilmelidir.

Bu makalede ele alınan diğer konular şunlardır:

- [Kayan araç çubuğu](#_core_floating_the_toolbar)

- [Araç çubuğunda dinamik olarak yeniden boyutlandırma](#_core_dynamically_resizing_the_toolbar)

- [Bir sabit stili araç çubuğu için ayar kaydırma konumları](#_core_setting_wrap_positions_for_a_fixed_style_toolbar)

MFC genel örnek görmek [DOCKTOOL](../visual-cpp-samples.md) örnekler.

##  <a name="_core_enabling_docking_in_a_frame_window"></a> Bir çerçeve penceresinde yerleştirme etkinleştirme

Araç çubukları için bir çerçeve pencere sabitlemek için çerçeve penceresinin (veya hedef) yerleştirme izin vermek için etkinleştirilmesi gerekir. Bu yapılır kullanarak [CFrameWnd::EnableDocking](../mfc/reference/cframewnd-class.md#enabledocking) bir alan işlevi *DWORD* stili bir dizi parametre bit belirten yerleştirme hangi tarafta çerçeve penceresinin kabul eder. Araç hakkında yerleştirilemediğinde ve için yerleştirilmiş birden çok kenarı vardır, yüz belirtilen parametre geçirilen `EnableDocking` şu sırayla kullanılır: üst, alt, sol, sağ. Mümkün olmasını istiyorsanız denetimi yerleştirmek için herhangi bir yere çubukları, geçirin **cbrs_alıgn_any** için `EnableDocking`.

##  <a name="_core_enabling_docking_for_a_toolbar"></a> İçin bir araç çubuğu yerleştirme etkinleştirme

Yerleştirme hedefi hazırladıktan sonra araç çubuğu (veya kaynak) benzer şekilde hazırlamanız gerekir. Çağrı [CControlBar::EnableDocking](../mfc/reference/ccontrolbar-class.md#enabledocking) sabitlemek istediğiniz her araç için hedef belirleme kenarlara araç çubuğu yerleştirme. Çağrısında belirtilen yüz hiçbiri `CControlBar::EnableDocking` çerçeve penceresinde yerleştirme için etkin yüz eşleşmiyor, araç sabitleyemezsiniz — bunu kayar. Kaydırılmış olan sonra dolaştırılabilir araç kutusu, çerçeve penceresine sabitlemek oluşturulamıyor kalır.

Efekti kalıcı olarak dolaştırılabilir araç kutusu ise, çağrı `EnableDocking` parametresi 0. Ardından çağırın [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar). Araç, kayan, herhangi bir yerleştirme kurulamıyor kalıcı olarak kalır.

##  <a name="_core_docking_the_toolbar"></a> Araç çubuğu yerleştirme

Framework çağrıları [CFrameWnd::DockControlBar](../mfc/reference/cframewnd-class.md#dockcontrolbar) çalıştığında kullanıcı araç çubuğu yerleştirme sağlayan çerçeve penceresi tarafında bırakın.

Ayrıca, Denetim çubuklarını çerçeve penceresine sabitlemek için herhangi bir zamanda bu işlevi çağırın. Bu, normalde başlatma sırasında gerçekleştirilir. Birden çok araç, belirli bir çerçeve penceresi tarafına sabitlenebilir.

##  <a name="_core_floating_the_toolbar"></a> Kayan araç çubuğu

Çerçeve penceresinde yerleştirilebilir bir araç çubuğu ayırma kayan araç çubuğu adı verilir. Çağrı [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar) Bunu yapmak için. Kaydırılmış için araç çubuğunda, nereye yerleştirileceğini noktası ve kayan araç yatay veya dikey olup olmadığını belirleyen bir hizalama stilini belirtin.

Bir kullanıcı bir araç çubuğu sabitlenmiş konumuna sürüklediğinde ve burada yerleştirme etkin bir konumda keser framework bu işlevi çağırır. Bu herhangi bir çerçeve penceresinin içinde veya dışında olabilir. Olduğu gibi `DockControlBar`, başlatma sırasında da bu işlevi çağırabilirsiniz.

MFC uygulaması yerleştirilebilir araç çubuklarının yerleştirilebilir araç çubukları destekleyen bazı uygulamalarda genişletilmiş özelliklerinden bazıları sağlamaz. Özelleştirilebilir araç çubukları gibi özellikleri sağlanmadı.

##  <a name="_core_dynamically_resizing_the_toolbar"></a> Araç çubuğunda dinamik olarak yeniden boyutlandırma

Visual C++ sürüm 4.0 itibariyle bunu kayan araç çubukları dinamik olarak yeniden boyutlandırmak için uygulamanızın kullanıcıları için olası bir duruma getirebilirsiniz. Genellikle, yatay olarak uzun, doğrusal bir şekli bir araç vardır. Ancak, araç çubuğunun yönünü ve nesnenin şeklini değiştirebilirsiniz. Örneğin, kullanıcı bir araç çubuğu bir çerçeve penceresinin dikey tarafının karşı docks, dikey düzene şeklini değiştirir. Araç çubuğu düğmelerinin birden çok satır içeren bir dikdörtgen içine şekillendirmek mümkündür.

Şunları yapabilirsiniz:

- Araç çubuğu özelliği olarak dinamik boyutlandırma belirtin.

- Sabit boyutlandırma araç özelliği olarak belirtin.

Bu desteği sağlamak için iki yeni araç çubuğu stili vardır, çağrılarında kullanılmak [CToolBar::Create](../mfc/reference/ctoolbar-class.md#create) üye işlevi. Bunlar:

- **Cbrs_sıze_dynamıc** dinamik denetim çubuğu.

- **Cbrs_sıze_fıxed** denetim çubuğu sabittir.

Boyutunun dinamik stili araç, kayan ancak değil takılıyken, yeniden boyutlandırma, kullanıcı sağlar. Araç çubuğu "kenarlarını kullanıcının sürüklediği şekil değiştirmek için gerektiğinde sarmalar".

Bir araç çubuğu düğmeleri konumunu her sütunda düzeltme, kaydırma durumları Style sabit boyutu korur. Uygulamanızın kullanıcı araç çubuğunu şeklini değiştiremezsiniz. Düğmeler arasındaki ayırıcı konumları gibi belirtilen yerlerde araç sarmalar. Yerleşik veya kayan araç olup olmadığını Bu şeklin tutar. Düğme birden çok sütun içeren sabit bir palet etkisidir.

Ayrıca [CToolBar::GetButtonStyle](../mfc/reference/ctoolbar-class.md#getbuttonstyle) durumu ve stili düğme için araç çubuklarında döndürülecek. Düğme nasıl göründüğünü ve nasıl kullanıcı girişine yanıt veren bir düğmenin stilini belirler; durumu düğme Sarmalanan bir durumda olup olmadığını söyler.

##  <a name="_core_setting_wrap_positions_for_a_fixed_style_toolbar"></a> Bir sabit stili araç çubuğu için ayar kaydırma konumları

Style sabit boyutlu bir araç için araç çubuğu düğmesi dizinleri, araç kaydırılır belirleyin. Aşağıdaki kod, ana çerçeve penceresinin bunun nasıl yapılacağını gösterir `OnCreate` geçersiz kıl:

[!code-cpp[NVC_MFCDocViewSDI#10](../mfc/codesnippet/cpp/docking-and-floating-toolbars_1.cpp)]

MFC genel örnek [DOCKTOOL](../visual-cpp-samples.md) sınıfının üye fonksiyonları kullanmayı gösterir [CControlBar](../mfc/reference/ccontrolbar-class.md) ve [CToolBar](../mfc/reference/ctoolbar-class.md) dinamik bir araç çubuğu yerleşimini yönetmek için. EDITBAR dosyasına bakın. CPP DOCKTOOL içinde.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Araç çubuğu temelleri](../mfc/toolbar-fundamentals.md)

- [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)

- [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Araç Çubuğu Uygulaması](../mfc/mfc-toolbar-implementation.md)

