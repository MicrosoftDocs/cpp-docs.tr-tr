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
ms.openlocfilehash: f40d8860f2e514bf3c9e9364a664326250c9627a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615833"
---
# <a name="docking-and-floating-toolbars"></a>Yerleşen ve Kayan Araç Çubukları

Microsoft Foundation Class Kitaplığı, yerleştirilebilir araç çubuklarını destekler. Bir yerleştirilebilir araç çubuğu, üst penceresinin herhangi bir tarafına iliştirilebilir veya yerleştirilebilir ya da kendi mini kare penceresinde ayrılabilir veya kaydırılmış olabilir. Bu makalede, uygulamalarınızda yerleştirilebilir araç çubuklarının nasıl kullanılacağı açıklanmaktadır.

Uygulamanızın iskeklerini oluşturmak için uygulama Sihirbazı 'nı kullanırsanız, yerleştirilebilir araç çubuklarının isteyip istemediğinizi seçmeniz istenir. Varsayılan olarak, uygulama Sihirbazı uygulamanıza bir yerleştirilebilir araç çubuğu yerleştirmek için gereken üç eylemi gerçekleştiren kodu üretir:

- [Bir çerçeve penceresinde yerleştirmeyi etkinleştirin](#_core_enabling_docking_in_a_frame_window).

- [Bir araç çubuğu için yerleştirmeyi etkinleştirin](#_core_enabling_docking_for_a_toolbar).

- [Araç çubuğunu (çerçeve penceresine) Yerleştir](#_core_docking_the_toolbar).

Bu adımlardan herhangi biri eksikse, uygulamanız standart bir araç çubuğu görüntüler. Uygulamanızdaki her bir yerleştirilebilir araç çubuğu için son iki adım gerçekleştirilmelidir.

Bu makalede ele alınan diğer konular şunlardır:

- [Araç çubuğunu kayan](#_core_floating_the_toolbar)

- [Araç çubuğunu dinamik olarak yeniden boyutlandırma](#_core_dynamically_resizing_the_toolbar)

- [Sabit stil araç çubuğu için kaydırılabilir konumları ayarlama](#_core_setting_wrap_positions_for_a_fixed_style_toolbar)

Örnekler için bkz. MFC genel örnek [docktool](../overview/visual-cpp-samples.md) .

## <a name="enabling-docking-in-a-frame-window"></a><a name="_core_enabling_docking_in_a_frame_window"></a>Çerçeve penceresinde yerleştirmeyi etkinleştirme

Araç çubuklarını bir çerçeve penceresine sabitlemek için, çerçeveye izin vermek için çerçeve penceresi (veya hedefi) etkinleştirilmelidir. Bu, çerçeve penceresinin hangi tarafının yerleştirmeyi kabul ettiğini gösteren bir dizi stil bitleri olan bir *DWORD* parametresi alan [CFrameWnd:: EnableDocking](reference/cframewnd-class.md#enabledocking) işlevi kullanılarak yapılır. Bir araç çubuğu yerleştirilme ve üzerine yerleştirilme gibi birden çok kenar varsa, geçirilen parametrede belirtilen kenarlar `EnableDocking` Şu sırada kullanılır: üst, alt, sol, sağ. Denetim çubuklarını her yere sabitlemek istiyorsanız **CBRS_ALIGN_ANY** ' ye geçirin `EnableDocking` .

## <a name="enabling-docking-for-a-toolbar"></a><a name="_core_enabling_docking_for_a_toolbar"></a>Araç çubuğu için yerleştirmeyi etkinleştirme

Hedefi sabitleme için hazırladıktan sonra, araç çubuğunu (veya kaynağı) benzer bir biçimde hazırlamanız gerekir. Sabitlemek istediğiniz her bir araç çubuğu için [CControlBar:: EnableDocking](reference/ccontrolbar-class.md#enabledocking) ' ı çağırın, böylece araç çubuğunun hangi hedef yüzlerini yerleştirmeyi belirtin. `CControlBar::EnableDocking`Çerçevede, çerçeve penceresinde yerleştirme için etkinleştirilen taraflardan hiçbiri için belirtilen taraflardan hiçbiri, kaydırma çubuğunu sabitlemez, float olur. Kaydırıldıktan sonra, kayan bir araç çubuğu kalır, çerçeve penceresine yuva yapılamıyor.

İstediğiniz efekt kalıcı olarak kayan bir araç çubuğudur, `EnableDocking` 0 parametresiyle çağırın. Sonra [CFrameWnd:: FloatControlBar](reference/cframewnd-class.md#floatcontrolbar)öğesini çağırın. Araç çubuğu kayan kalır ve kalıcı olarak her yere sabitleyebilir.

## <a name="docking-the-toolbar"></a><a name="_core_docking_the_toolbar"></a>Araç çubuğunu sabitleme

Framework, Kullanıcı araç çubuğunu yerleştirmeye izin veren çerçeve penceresinin bir tarafında bırakmaya çalıştığında [CFrameWnd::D ockControlBar](reference/cframewnd-class.md#dockcontrolbar) çağırır.

Ayrıca, bu işlevi herhangi bir zamanda çağırabilirsiniz ve denetim çubuklarının kenarlığını çerçeve penceresine yerleştirebilirsiniz. Bu işlem genellikle başlatma sırasında yapılır. Çerçeve penceresinin belirli bir tarafına birden fazla araç çubuğu yerleştirilebilir.

## <a name="floating-the-toolbar"></a><a name="_core_floating_the_toolbar"></a>Araç çubuğunu kayan

Çerçeve penceresinden bir yerleştirilebilir araç çubuğunu ayırmak, araç çubuğunu yüzer olarak adlandırılır. Bunu yapmak için [CFrameWnd:: FloatControlBar](reference/cframewnd-class.md#floatcontrolbar) öğesini çağırın. Kaydırılan araç çubuğunu, yerleştirilmesi gereken noktayı ve kayan araç çubuğunun yatay mı yoksa dikey mi olduğunu belirleyen bir hizalama stilini belirtin.

Bir Kullanıcı bir araç çubuğunu sabitlenmiş konumundan sürüklediğinde ve bu işlevi yerleştirme özelliğinin etkinleştirilmediği bir konuma bırakdığında çerçeve bu işlevi çağırır. Bu, çerçeve penceresinin içinde veya dışında bir yerde olabilir. İle olduğu gibi `DockControlBar` , başlatma sırasında bu işlevi de çağırabilirsiniz.

Yerleştirilebilir araç çubuklarının MFC uygulaması, bazı uygulamalarda bulunan bazı genişletilmiş özelliklerden, yerleştirilebilir araç çubuklarını destekleyen bazı özellikler sağlamaz. Özelleştirilebilir araç çubukları gibi özellikler sağlanmaz.

## <a name="dynamically-resizing-the-toolbar"></a><a name="_core_dynamically_resizing_the_toolbar"></a>Araç çubuğunu dinamik olarak yeniden boyutlandırma

Visual C++ sürüm 4,0 itibariyle, uygulamanızın kullanıcılarının kayan araç çubuklarını dinamik olarak yeniden boyutlandırmasını olanaklı hale getirebilirsiniz. Genellikle, bir araç çubuğu uzun, doğrusal bir şekle sahiptir ve yatay olarak gösterilir. Ancak araç çubuğunun yönünü ve şeklini değiştirebilirsiniz. Örneğin, Kullanıcı çerçeve penceresinin dikey taraflarından birine karşı bir araç çubuğu oluştururken, şekil dikey düzende değişir. Araç çubuğunu birden çok düğme satırı içeren bir dikdörtgende yeniden şekillendirmek mümkündür.

Seçenekleriniz şunlardır:

- Dinamik boyutlandırmayı bir araç çubuğu özelliği olarak belirtin.

- Sabit boyutlandırmayı bir araç çubuğu özelliği olarak belirtin.

Bu desteği sağlamak için, [CToolBar:: Create](reference/ctoolbar-class.md#create) üye işlevine yönelik çağrılarınız için kullanabileceğiniz iki yeni araç çubuğu stili vardır. Bunlar:

- **CBRS_SIZE_DYNAMIC** Denetim çubuğu dinamiktir.

- **CBRS_SIZE_FIXED** Denetim çubuğu düzeltildi.

Boyut dinamik stili, kullanıcının kayan nokta, yerleştirilmiş durumdayken araç çubuğunu yeniden boyutlandırmasına izin verir. Araç çubuğu, Kullanıcı kenarlarını sürüklediği şekilde şekli değiştirmek için gereken yerlerde "kaydırılır".

Sabit stil boyutu, her bir sütundaki düğmelerin konumunu düzelterek bir araç çubuğunun sarması durumlarını korur. Uygulamanızın kullanıcısı araç çubuğunun şeklini değiştiremiyor. Araç çubuğu, düğmeler arasındaki ayırıcıların konumları gibi belirlenen yerlerde kaydırılır. Araç çubuğunun yerleştirilmiş veya kayan olup olmadığı bu şekli korur. Efekt, birden çok düğme sütununu içeren sabit bir palettir.

Ayrıca, araç çubuklarınızdaki düğmelere yönelik bir durum ve stil döndürmek için [CToolBar:: GetButtonStyle](reference/ctoolbar-class.md#getbuttonstyle) ' i de kullanabilirsiniz. Düğmenin stili, düğmenin nasıl göründüğünü ve kullanıcı girişine nasıl yanıt vereceğini belirler; durum, düğmenin sarmalanmış durumda olup olmadığını söyler.

## <a name="setting-wrap-positions-for-a-fixed-style-toolbar"></a><a name="_core_setting_wrap_positions_for_a_fixed_style_toolbar"></a>Sabit stil araç çubuğu için kaydırılabilir konumları ayarlama

Sabit boyutlu bir araç çubuğu için, Toolbar 'ın kaydırabileceği araç çubuğu düğme dizinlerini belirleyin. Aşağıdaki kod, bunu ana çerçeve pencerenizin `OnCreate` geçersiz kılmada nasıl yapılacağını gösterir:

[!code-cpp[NVC_MFCDocViewSDI#10](codesnippet/cpp/docking-and-floating-toolbars_1.cpp)]

MFC genel örnek [Dockaracı](../overview/visual-cpp-samples.md) , bir araç çubuğunun dinamik yerleşimini yönetmek Için [CControlBar](reference/ccontrolbar-class.md) ve [CToolBar](reference/ctoolbar-class.md) sınıfının üye işlevlerinin nasıl kullanılacağını gösterir. Bkz. dosya EDITBAR. DOCKTOOL 'da CPP.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Araç çubuğu temelleri](toolbar-fundamentals.md)

- [Araç çubuğu araç ipuçları](toolbar-tool-tips.md)

- [Eski araç çubuklarınızı kullanma](using-your-old-toolbars.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC araç çubuğu uygulama](mfc-toolbar-implementation.md)
