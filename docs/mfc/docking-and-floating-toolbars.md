---
title: Yerleşen ve Kayan Araç Çubukları
ms.date: 11/04/2016
f1_keywords:
- CBRS_SIZE_DYNAMIC
- CBRS_SIZE_FIXED
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
ms.openlocfilehash: 30113565167b96b0df84a65768a1dfabe92ceffe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369768"
---
# <a name="docking-and-floating-toolbars"></a>Yerleşen ve Kayan Araç Çubukları

Microsoft Foundation Class Kitaplığı takılabilir araç çubuklarını destekler. Takılabilir araç çubuğu, ana penceresinin herhangi bir tarafına eklenebilir veya sabitlenebilir veya kendi mini çerçeve penceresinde ayrılabilir veya yüzdürülebilir. Bu makalede, uygulamalarınızda takılabilir araç çubuklarının nasıl kullanılacağı açıklanmaktadır.

Uygulamanızın iskeletini oluşturmak için Uygulama Sihirbazı'nı kullanırsanız, takılabilir araç çubuklarını isteyip istemediğinizi seçmeniz istenir. Varsayılan olarak, Uygulama Sihirbazı, uygulamanıza takılabilir bir araç çubuğu yerleştirmek için gereken üç eylemi gerçekleştiren kodu oluşturur:

- [Çerçeve penceresine yerleştirmeyi etkinleştirin.](#_core_enabling_docking_in_a_frame_window)

- [Araç çubuğu için yerleştirmeyi etkinleştirin.](#_core_enabling_docking_for_a_toolbar)

- [Araç çubuğunu (çerçeve penceresine) sabitle.](#_core_docking_the_toolbar)

Bu adımlardan herhangi biri eksikse, uygulamanız standart bir araç çubuğu görüntüler. Son iki adım, uygulamanızdaki her takılabilir araç çubuğu için gerçekleştirilmelidir.

Bu makalede ele alınan diğer konular şunlardır:

- [Araç çubuğunu yüzdürme](#_core_floating_the_toolbar)

- [Araç çubuğunu dinamik olarak yeniden boyutlandırma](#_core_dynamically_resizing_the_toolbar)

- [Sabit stil araç çubuğu için kaydırma konumlarını ayarlama](#_core_setting_wrap_positions_for_a_fixed_style_toolbar)

Örnekler için MFC Genel örnek [DOCKTOOL'a](../overview/visual-cpp-samples.md) bakın.

## <a name="enabling-docking-in-a-frame-window"></a><a name="_core_enabling_docking_in_a_frame_window"></a>Çerçeve Penceresine Yerleştirmeyi Etkinleştirme

Araç çubuklarını çerçeve penceresine yerleştirmek için, yerleştirmeye izin vermek için çerçeve penceresinin (veya hedefin) etkinleştirilmesi gerekir. Bu, çerçeve penceresinin hangi tarafının yerleştirmeyi kabul ettiğini belirten bir stil biti kümesi olan bir *DWORD* parametresi alan [CFrameWnd::EnableDocking](../mfc/reference/cframewnd-class.md#enabledocking) işlevi kullanılarak yapılır. Bir araç çubuğu kenetlenmek üzereyse ve üzerine sabitlenebileceği birden çok taraf varsa, parametrede belirtilen `EnableDocking` kenarlar aşağıdaki sırada kullanılır: üst, alt, sol, sağ. Kontrol çubuklarını herhangi bir yere sabitleyebilmek `EnableDocking`istiyorsanız, **CBRS_ALIGN_ANY'** ye geçirin.

## <a name="enabling-docking-for-a-toolbar"></a><a name="_core_enabling_docking_for_a_toolbar"></a>Araç Çubuğu için Yerleştirmeyi Etkinleştirme

Yerleştirme için varış noktasını hazırladıktan sonra, araç çubuğunu (veya kaynağı) benzer bir şekilde hazırlamanız gerekir. [CControlBar'ı arayın::Yerleştirmek](../mfc/reference/ccontrolbar-class.md#enabledocking) istediğiniz her araç çubuğu için, araç çubuğunun yanaşması gereken hedef taraflarını belirterek Etkinleştirme. Çağrıda belirtilen tarafların hiçbiri çerçeve `CControlBar::EnableDocking` penceresine yerleştirme için etkinleştirilen tarafları eşleştirmezse, araç çubuğu sabitlenemez — yüzer. Yüzdürüldünden sonra, çerçeve penceresine sabitleyemeyen kayan bir araç çubuğu olarak kalır.

İstediğinizin etkisi kalıcı olarak kayan bir araç `EnableDocking` çubuğuysa, 0 parametresi ile arayın. Sonra [CFrameWnd arayın::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar). Araç çubuğu kayan kalır, kalıcı olarak herhangi bir yere sabitleyemiyor.

## <a name="docking-the-toolbar"></a><a name="_core_docking_the_toolbar"></a>Araç Çubuğunu Yerleştirme

Kullanıcı araç çubuğunu yerleştirmeye izin veren çerçeve penceresinin bir tarafına düşürmeye çalıştığında çerçeve [CFrameWnd::DockControlBar'ı](../mfc/reference/cframewnd-class.md#dockcontrolbar) çağırır.

Ayrıca, denetim çubuklarını çerçeve penceresine yerleştirmek için istediğiniz zaman bu işlevi arayabilirsiniz. Bu normalde başlatma sırasında yapılır. Birden fazla araç çubuğu çerçeve penceresinin belirli bir tarafına sabitlenebilir.

## <a name="floating-the-toolbar"></a><a name="_core_floating_the_toolbar"></a>Araç Çubuğunu Yüzdürme

Çerçeve penceresinden takılabilir bir araç çubuğunu ayırmak, araç çubuğunu yüzdürme olarak adlandırılır. Bunu yapmak için [CFrameWnd'i arayın::FloatControlBar'ı](../mfc/reference/cframewnd-class.md#floatcontrolbar) arayın. Yüzdürülecek araç çubuğunu, yerleştirilmesi gereken noktayı ve kayan araç çubuğunun yatay mı yoksa dikey mi olduğunu belirleyen bir hizalama stilini belirtin.

Bir kullanıcı bir araç çubuğunu kenetlenmiş konumundan sürüklüyor ve yerleştirmenin etkinleştirilen olmadığı bir konuma attığında çerçeve bu işlevi çağırır. Bu, çerçeve penceresinin içinde veya dışında herhangi bir yerde olabilir. Olduğu `DockControlBar`gibi, ayrıca başlatma sırasında bu işlevi arayabilirsiniz.

Takılabilir araç çubuklarının MFC uygulaması, bazı uygulamalarda bulunan ve takılabilir araç çubuklarını destekleyen genişletilmiş özelliklerden bazılarını sağlamaz. Özelleştirilebilir araç çubukları gibi özellikler sağlanmaz.

## <a name="dynamically-resizing-the-toolbar"></a><a name="_core_dynamically_resizing_the_toolbar"></a>Araç Çubuğunu Dinamik Olarak Yeniden Boyutlandırma

Visual C++ sürüm 4.0'dan itibaren, uygulamanızın kullanıcılarının kayan araç çubuklarını dinamik olarak yeniden boyutlandırmalarını mümkün kullanabilirsiniz. Genellikle, bir araç çubuğu yatay olarak görüntülenen uzun, doğrusal bir şekle sahiptir. Ancak araç çubuğunun yönünü ve şeklini değiştirebilirsiniz. Örneğin, kullanıcı bir araç çubuğunu çerçeve penceresinin dikey kenarlarından birine dockladığında, şekil dikey düzene dönüşür. Araç çubuğunu birden çok düğme satırıyla dikdörtgen şeklinde yeniden şekillendirmek de mümkündür.

Şunları yapabilirsiniz:

- Araç çubuğu özelliği olarak dinamik boyutlandırmayı belirtin.

- Araç çubuğu özelliği olarak sabit boyutlandırmayı belirtin.

Bu desteği sağlamak için, CToolBar'a yapılan çağrılarda kullanılmak üzere iki yeni araç çubuğu stili [vardır::Üye](../mfc/reference/ctoolbar-class.md#create) işlevi oluşturun. Bunlar:

- **CBRS_SIZE_DYNAMIC** Kontrol çubuğu dinamiktir.

- **CBRS_SIZE_FIXED** Kontrol çubuğu sabittir.

Boyut dinamik stili, kullanıcınızın araç çubuğunu yüzerken yeniden boyutlandırmasına olanak tanır, ancak kenetlenirken değil. Araç çubuğu, kullanıcı kenarlarını sürüklerken şekli değiştirmek için gereken yeri "sarar".

Sabit stil boyutu, her sütundaki düğmelerin konumunu düzelten bir araç çubuğunun kaydırma durumlarını korur. Uygulamanızın kullanıcısı araç çubuğunun şeklini değiştiremez. Araç çubuğu, düğmeler arasındaki ayırıcıların konumları gibi belirlenmiş yerlerde sarar. Araç çubuğunun kenetlenip kenetlenmediği veya kayan olması bu şekli korur. Efekt, birden çok düğme sütunlu sabit bir palettir.

Ayrıca [cToolBar kullanabilirsiniz::GetButtonStyle](../mfc/reference/ctoolbar-class.md#getbuttonstyle) araç çubuklarınızdaki düğmeler için bir durum ve stil döndürmek için. Düğmenin stili, düğmenin nasıl görünüp kullanıcı girişine nasıl yanıt veriyi belirler; durum, düğmenin sarılmış durumda olup olmadığını söyler.

## <a name="setting-wrap-positions-for-a-fixed-style-toolbar"></a><a name="_core_setting_wrap_positions_for_a_fixed_style_toolbar"></a>Sabit Stil Araç Çubuğu için Kaydırma Konumlarını Ayarlama

Boyutu sabit stili olan bir araç çubuğu için, araç çubuğunun kaydıracağı araç çubuğu düğmesi dizinlerini belirleyin. Aşağıdaki kod, ana çerçeve pencerenizin `OnCreate` geçersiz kılınmasında bunu nasıl yapacağınızı gösterir:

[!code-cpp[NVC_MFCDocViewSDI#10](../mfc/codesnippet/cpp/docking-and-floating-toolbars_1.cpp)]

MFC Genel örnek [DOCKTOOL,](../overview/visual-cpp-samples.md) bir araç çubuğunun dinamik düzenini yönetmek için [CControlBar](../mfc/reference/ccontrolbar-class.md) ve [CToolBar](../mfc/reference/ctoolbar-class.md) sınıflarının üye işlevlerinin nasıl kullanılacağını gösterir. EDITBAR dosyasına bakın. DOCKTOOL cpp.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Araç çubuğu temelleri](../mfc/toolbar-fundamentals.md)

- [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)

- [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Araç Çubuğu Uygulaması](../mfc/mfc-toolbar-implementation.md)
