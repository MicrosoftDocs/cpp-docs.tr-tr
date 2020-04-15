---
title: MFC Araç Çubuğu Uygulaması
ms.date: 11/04/2016
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
ms.openlocfilehash: 38811be765d4427c4083b8f142b54fb67b9076a0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359315"
---
# <a name="mfc-toolbar-implementation"></a>MFC Araç Çubuğu Uygulaması

Araç çubuğu, denetimlerin bit eşlemi görüntülerini içeren bir [denetim çubuğudur.](../mfc/control-bars.md) Bu görüntüler düğmeler, onay kutuları veya radyo düğmeleri gibi olabilir. MFC, araç çubuklarını yönetmek için sınıf [CToolbar'ı](../mfc/reference/ctoolbar-class.md) sağlar.

Bunu etkinleştirirseniz, MFC araç çubuklarının kullanıcıları bunları bir pencerenin kenarına sabitleyebilir veya uygulama penceresi içinde herhangi bir yere "yüzdürebilir". MFC, geliştirme ortamındaki gibi özelleştirilebilir araç çubuklarını desteklemez.

MFC ayrıca araç ipuçlarını da destekler: fareyi düğmenin üzerine konumlandırdığınızda araç çubuğu düğmesinin amacını açıklayan küçük açılır pencereler. Varsayılan olarak, kullanıcı bir araç çubuğu düğmesine bastığında durum çubuğunda bir durum dizesi görüntülenir (varsa). Fare düğmeye basmadan konumlandığında durum dizesini görüntülemek için "fly by" durum çubuğunu etkinleştirebilirsiniz.

> [!NOTE]
> MFC sürüm 4.0 itibariyle, araç çubukları ve araç ipuçları, MFC'ye özgü önceki uygulama yerine Windows 95 ve daha sonraki işlevler kullanılarak uygulanır.

Geriye dönük uyumluluk için, MFC sınıftaki `COldToolBar`eski araç çubuğu uygulamasını korur. MFC'nin önceki sürümleri `COldToolBar` için `CToolBar`belgeler altında açıklanır.

Uygulama Sihirbazı'ndaki Araç Çubuğu seçeneğini seçerek programınızdaki ilk araç çubuğunu oluşturun. Ek araç çubukları da oluşturabilirsiniz.

Bu makalede aşağıdakiler belirtilmiştir:

- [Araç çubuğu düğmeleri](#_core_toolbar_buttons)

- [Yerleşen ve kayan araç çubukları](#_core_docking_and_floating_toolbars)

- [Araç çubukları ve araç ipuçları](#_core_toolbars_and_tool_tips)

- [CToolBar ve CToolBarCtrl sınıfları](#_core_the_ctoolbar_and_ctoolbarctrl_classes)

- [Araç Çubuğu bit eşlemi](#_core_the_toolbar_bitmap)

## <a name="toolbar-buttons"></a><a name="_core_toolbar_buttons"></a>Araç Çubuğu Düğmeleri

Araç çubuğundaki düğmeler menüdeki öğelere benzer. Her iki kullanıcı arabirimi nesnesi türü de, programınızın işleyici işlevleri sağlayarak işlediği komutları oluşturur. Genellikle araç çubuğu düğmeleri menü komutlarının işlevselliğini çoğaltarak aynı işlevsellik için alternatif bir kullanıcı arabirimi sağlar. Bu tür yineleme sadece düğme ve menü öğesi aynı kimlik vererek düzenlenir.

Araç çubuğundaki düğmelerin düğmelerin görünmesini ve düğme, onay kutusu veya radyo düğmesi gibi görünmesini sağlayabilirsiniz. Daha fazla bilgi için [cToolBar](../mfc/reference/ctoolbar-class.md)sınıfına bakın.

## <a name="docking-and-floating-toolbars"></a><a name="_core_docking_and_floating_toolbars"></a>Yerleştirme ve Kayan Araç Çubukları

Bir MFC araç çubuğu şunları yapabilir:

- Ana penceresinin bir tarafı boyunca sabit kalır.

- Kullanıcı tarafından belirttiğiniz ana pencerenin herhangi bir tarafına veya tarafına sürüklenip "kenetlenmiş" veya iliştirilsin.

- Kullanıcının uygun herhangi bir konuma taşıyabilmesi için kendi mini çerçeve penceresinde "yüzdürülebilir" veya çerçeve penceresinden ayrılsın.

- Yüzerken yeniden boyutlandırılın.

Daha fazla bilgi için, [docking ve Kayan Araç Çubukları](../mfc/docking-and-floating-toolbars.md)makalesine bakın.

## <a name="toolbars-and-tool-tips"></a><a name="_core_toolbars_and_tool_tips"></a>Araç Çubukları ve Araç İpuçları

MFC araç çubukları da "araç ipuçları" görüntülemek için yapılabilir - küçük pop-up pencereler bir araç çubuğu düğmesinin amacı kısa bir metin açıklaması içeren. Kullanıcı fareyi bir araç çubuğu düğmesi üzerinde hareket ettirirken, araç ipucu penceresi bir ipucu sunmak için açılır. Daha fazla bilgi için Araç [Çubuğu Araç İpuçları](../mfc/toolbar-tool-tips.md)makalesine bakın.

## <a name="the-ctoolbar-and-ctoolbarctrl-classes"></a><a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a>CToolBar ve CToolBarCtrl Sınıfları

Uygulamanızın araç çubuklarını [CToolBar](../mfc/reference/ctoolbar-class.md)sınıfı üzerinden yönetirsiniz. MFC sürüm 4.0 `CToolBar` itibariyle, Windows 95 veya daha sonra ve Windows NT sürüm 3.51 veya daha sonra altında kullanılabilir araç çubuğu ortak denetimi kullanmak için yeniden uygulanmıştır.

Bu yeniden uygulama araç çubukları için daha az MFC koduyla sonuçlanır, çünkü MFC işletim sistemi desteğinden kullanır. Yeniden uygulama da yeteneğini artırır. Araç çubuklarını işlemek için üye işlevleri kullanabilir `CToolBar` veya alttaki [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesine bir başvuru alabilir ve araç çubuğu özelleştirmesi ve ek işlevsellik için üye işlevlerini arayabilirsiniz.

> [!TIP]
> Eski MFC uygulamasına büyük yatırımlar yaptıksa, `CToolBar`bu destek hala kullanılabilir. [Eski Araç Çubuklarınızı Kullanarak](../mfc/using-your-old-toolbars.md)makaleye bakın.

Ayrıca MFC Genel örnek [DOCKTOOL](../overview/visual-cpp-samples.md)bakın.

## <a name="the-toolbar-bitmap"></a><a name="_core_the_toolbar_bitmap"></a>Araç Çubuğu Bit Haritası

Bir kez `CToolBar` oluşturulduktan sonra, bir nesne her düğme için bir görüntü içeren tek bir bit eşlemi yükleyerek araç çubuğu görüntüsünü oluşturur. Uygulama Sihirbazı, Visual C++ [araç çubuğu düzenleyicisi](../windows/toolbar-editor.md)ile özelleştirebileceğiniz standart bir araç çubuğu bit eşlemesi oluşturur.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Araç çubuğu temelleri](../mfc/toolbar-fundamentals.md)

- [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)

- [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)

- [Araç Çubuğu Denetimi ile çalışma](../mfc/working-with-the-toolbar-control.md)

- [Eski Araç Çubuklarınızı Kullanma](../mfc/using-your-old-toolbars.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları

## <a name="see-also"></a>Ayrıca bkz.

[Araç Çubukları](../mfc/toolbars.md)<br/>
[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)
