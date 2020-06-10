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
ms.openlocfilehash: 7876e9403389c19a24e5a482534d0f223eaa4bf5
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626124"
---
# <a name="mfc-toolbar-implementation"></a>MFC Araç Çubuğu Uygulaması

Araç çubuğu, denetimlerin bit eşlem görüntülerini içeren bir [denetim çubuğudur](control-bars.md) . Bu görüntüler, itme düğmeleri, onay kutuları veya radyo düğmeleri gibi davranabilir. MFC araç çubuklarını yönetmek için sınıf [CToolBar](reference/ctoolbar-class.md) sağlar.

Bu ayarı etkinleştirirseniz, MFC araç çubuklarının kullanıcıları bunları bir pencerenin kenarına veya "float" uygulamasını uygulama penceresi içinde herhangi bir yere sabitleyebilir. MFC, geliştirme ortamdakiler gibi Özelleştirilebilir araç çubuklarını desteklemez.

MFC ayrıca araç ipuçlarını destekler: fare düğmesini düğmenin üzerine konumlandırdığınızda bir araç çubuğu düğmesinin amacını tanımlayan küçük açılır pencereler. Varsayılan olarak, Kullanıcı bir araç çubuğu düğmesine bastığında durum çubuğunda (varsa) bir durum dizesi görüntülenir. Fare düğmenin üzerine basıldığında durum dizesini göstermek için "durum çubuğu güncelleştirme" i etkinleştirebilirsiniz.

> [!NOTE]
> MFC sürüm 4,0 itibariyle, araç çubukları ve araç ipuçları, MFC 'ye özgü önceki uygulama yerine Windows 95 ve sonraki işlevleri kullanılarak uygulanır.

Ters uyumluluk için MFC, sınıfında eski araç çubuğu uygulamasını korur `COldToolBar` . MFC 'nin önceki sürümlerine yönelik belgeler altında açıklanır `COldToolBar` `CToolBar` .

Uygulama sihirbazındaki araç çubuğu seçeneğini belirleyerek programınızdaki ilk araç çubuğunu oluşturun. Ayrıca, ek araç çubukları da oluşturabilirsiniz.

Aşağıdakiler bu makalede sunulmuştur:

- [Araç çubuğu düğmeleri](#_core_toolbar_buttons)

- [Yerleşen ve kayan araç çubukları](#_core_docking_and_floating_toolbars)

- [Araç çubukları ve araç ipuçları](#_core_toolbars_and_tool_tips)

- [CToolBar ve CToolBarCtrl sınıfları](#_core_the_ctoolbar_and_ctoolbarctrl_classes)

- [Toolbar bit eşlemi](#_core_the_toolbar_bitmap)

## <a name="toolbar-buttons"></a><a name="_core_toolbar_buttons"></a>Araç çubuğu düğmeleri

Bir araç çubuğundaki düğmeler, bir menüdeki öğelerle benzerdir. Her iki tür Kullanıcı arabirimi nesnesi, programınızın işleyici işlevleri sunarak işlediği komutlar oluşturur. Çoğu zaman araç çubuğu düğmeleri menü komutlarının işlevselliğini yineleyen aynı işlevselliğe alternatif bir kullanıcı arabirimi sağlar. Bu tür yineleme yalnızca düğme ve menü öğesi aynı KIMLIĞE vererek düzenlenir.

Bir araç çubuğundaki düğmelerin görünmesini ve bir düğme, onay kutusu ya da radyo düğmesi olarak davranmasını sağlayabilirsiniz. Daha fazla bilgi için bkz. sınıf [CToolBar](reference/ctoolbar-class.md).

## <a name="docking-and-floating-toolbars"></a><a name="_core_docking_and_floating_toolbars"></a>Yerleştirme ve kayan araç çubukları

MFC araç çubuğu şunları yapabilir:

- Ana penceresinin bir tarafında sabit kalır.

- Kullanıcı tarafından belirttiğiniz ana pencerenin herhangi bir tarafına veya tarafına sürüklenebilir ve "sabitlenmiş" ya da iliştirilir.

- Kullanıcının onu uygun bir konuma taşıyabilmesi için, kendi mini kare penceresinde "kaydırılmış" veya ayrılmış olmalıdır.

- Kayan sırada yeniden boyutlandırılıyor.

Daha fazla bilgi için bkz. [yerleştirme ve kayan araç çubukları](docking-and-floating-toolbars.md).

## <a name="toolbars-and-tool-tips"></a><a name="_core_toolbars_and_tool_tips"></a>Araç çubukları ve araç Ipuçları

MFC araç çubukları, bir araç çubuğu düğmesinin amacını kısa bir metin açıklaması içeren küçük bir açılan pencere olan "araç ipuçlarını" göstermek için de yapılabilir. Kullanıcı fareyi bir araç çubuğu düğmesinin üzerine taşırken, araç ipucu penceresi bir ipucu sunmak için açılır. Daha fazla bilgi için [araç çubuğu araç ipuçları](toolbar-tool-tips.md)makalesine bakın.

## <a name="the-ctoolbar-and-ctoolbarctrl-classes"></a><a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a>CToolBar ve CToolBarCtrl sınıfları

[CToolBar](reference/ctoolbar-class.md)sınıfı aracılığıyla uygulamanızın araç çubuklarını yönetirsiniz. MFC sürüm 4,0 itibariyle, `CToolBar` windows 95 veya üzeri ve WINDOWS NT sürüm 3,51 veya sonraki sürümlerinde bulunan araç çubuğu ortak denetimini kullanmak için yeniden uygulanmıştır.

MFC işletim sistemi desteğini kullandığından, bu yeniden uygulama, araç çubuklarının daha az MFC koduna neden olur. Yeniden uygulama özelliği de geliştirir. `CToolBar`Araç çubuklarını değiştirmek için üye işlevlerini kullanabilir veya temel alınan [CToolBarCtrl](reference/ctoolbarctrl-class.md) nesnesine bir başvuru elde edebilir ve araç çubuğu özelleştirmesi ve ek işlevler için üye işlevlerini çağırabilirsiniz.

> [!TIP]
> Daha eski MFC uygulamasında çok fazla yatırım yaptıysanız `CToolBar` , bu destek yine de kullanılabilir. [Eski araç çubuklarınızı kullanarak](using-your-old-toolbars.md)makaleye bakın.

Ayrıca bkz. MFC genel örnek [Dockaracı](../overview/visual-cpp-samples.md).

## <a name="the-toolbar-bitmap"></a><a name="_core_the_toolbar_bitmap"></a>Toolbar bit eşlemi

Bir nesne oluşturulduktan sonra, `CToolBar` her düğme için bir görüntü içeren tek bir bit eşlem yükleyerek araç çubuğu görüntüsünü oluşturur. Uygulama Sihirbazı Visual C++ [Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)ile özelleştirebileceğiniz standart bir araç çubuğu bit eşlemi oluşturur.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Araç çubuğu temelleri](toolbar-fundamentals.md)

- [Yerleşen ve kayan araç çubukları](docking-and-floating-toolbars.md)

- [Araç çubuğu araç ipuçları](toolbar-tool-tips.md)

- [Araç çubuğu denetimiyle çalışma](working-with-the-toolbar-control.md)

- [Eski araç çubuklarınızı kullanma](using-your-old-toolbars.md)

- [CToolBar](reference/ctoolbar-class.md) ve [CToolBarCtrl](reference/ctoolbarctrl-class.md) sınıfları

## <a name="see-also"></a>Ayrıca bkz.

[Araç Çubukları](toolbars.md)<br/>
[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)
