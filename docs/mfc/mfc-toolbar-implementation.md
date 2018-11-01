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
ms.openlocfilehash: 93cf2f2a11c34b1bbe2d62e4e4cc6afab16e2fd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666797"
---
# <a name="mfc-toolbar-implementation"></a>MFC Araç Çubuğu Uygulaması

Bir araç çubuğu bir [denetim çubuğu](../mfc/control-bars.md) denetimlerin bit eşlem resimleri içeren. Bu görüntüler, pushbuttons, onay kutusu veya radyo düğmeleri gibi davranabilir. MFC sağlar sınıfını [CToolbar](../mfc/reference/ctoolbar-class.md) araç çubukları yönetmek için.

Etkinleştirirseniz, MFC araç çubukları, kullanıcılar bunları bir pencere kenarına sabitlemek veya "herhangi bir uygulama penceresinin içinde kaydırmak". MFC geliştirme ortamındaki benzer özelleştirilebilir araç çubukları desteklemiyor.

MFC araç ipuçları da destekler: düğmenin üzerine fare getirdiğinizde araç çubuğu düğmesinin amacını açıklayan küçük açılır pencereleri. Kullanıcı bir araç çubuğu düğmesine bastığında varsayılan olarak, bir durum dizesi (varsa) durum çubuğunda görünür. Durum dizesi fare tuşuna basmadan düğmenin üzerine getirildiğinde gösterilecek güncelleştirme çubuğu "tarafından yaklaştığında" durumu etkinleştirebilirsiniz.

> [!NOTE]
>  MFC sürüm 4.0 itibariyle araç çubukları ve araç ipuçları için MFC belirli önceki uygulaması yerine Windows 95 ve daha sonra İşlevler kullanılarak uygulanır.

Geriye dönük uyumluluk için eski araç çubuğu uygulaması sınıfında MFC korur `COldToolBar`. Önceki sürümlerdeki MFC belgelerini açıklamak `COldToolBar` altında `CToolBar`.

İlk araç, Uygulama Sihirbazı'nda araç seçeneği seçerek programınıza oluşturun. Ek araç çubuklarını da oluşturabilirsiniz.

Bu makalede aşağıdaki yapılmıştır:

- [Araç çubuğu düğmeleri](#_core_toolbar_buttons)

- [Yerleşen ve kayan araç çubukları](#_core_docking_and_floating_toolbars)

- [Araç çubukları ve araç ipuçları](#_core_toolbars_and_tool_tips)

- [CToolBar ve CToolBarCtrl sınıfları](#_core_the_ctoolbar_and_ctoolbarctrl_classes)

- [Araç çubuğu bit eşlemi](#_core_the_toolbar_bitmap)

##  <a name="_core_toolbar_buttons"></a> Araç çubuğu düğmeleri

Araç çubuğu düğmeleri için menü öğeleri benzer. İşleyici işlevleri sağlayarak programınızı işleme komutları, her iki tür kullanıcı arabirimi nesneleri oluşturur. Araç çubuğu düğmeleri genellikle aynı işlevselliği için bir alternatif kullanıcı arayüzü sağlama, menü komutlarının işlevlerin birer yinelemesidir. Bu çoğaltma yalnızca düğme ve menü öğesi aynı kimliğe vererek düzenlenmiş

Görünür ve pushbuttons, onay kutusu veya radyo düğmeleri davranır düğmeleri bir araç hale getirebilirsiniz. Daha fazla bilgi için bkz. [CToolBar](../mfc/reference/ctoolbar-class.md).

##  <a name="_core_docking_and_floating_toolbars"></a> Yerleşen ve kayan araç çubukları

MFC araç yapabilirsiniz:

- Bir üst pencereye tarafında sabit kalır.

- Sürüklenen ve "yerleşik" veya herhangi bir yan veya belirttiğiniz ana penceresinin kullanıcı tarafından eklenmiş.

- "Kaydırıldı" veya çerçeve penceresinde kullanıcı, uygun bir konuma taşıyabilirsiniz şekilde kendi Mini çerçeve penceresindeki ayrılır.

- Kayan çalışırken yeniden boyutlandırılabilir.

Daha fazla bilgi için bkz [Docking ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md).

##  <a name="_core_toolbars_and_tool_tips"></a> Araç çubukları ve araç ipuçları

MFC araç çubukları de yapılabilir "araç ipucu" görüntülenecek — küçük açılır pencereleri içeren bir araç çubuğu düğmesinin amaçlı kısa metin açıklaması. Kullanıcı araç çubuğu düğmesi üzerinde fareyi hareket gibi araç ipucu penceresi bir ipucu sunmak için açılır. Daha fazla bilgi için bkz [araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md).

##  <a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a> CToolBarCtrl sınıfları ve CToolBar

Uygulama araç çubukları sınıfı aracılığıyla yönettiğiniz [CToolBar](../mfc/reference/ctoolbar-class.md). MFC sürüm 4.0 itibariyle `CToolBar` araç çubuğu ortak denetim altında Windows 95 ya da üzeri ve Windows NT 3.51 sürümü veya sonraki bir sürümü kullanmayı reimplemented.

MFC yaptığından bu reimplementation daha az araç çubukları için MFC kodu sonuçlanır. işletim sistemi desteğini kullanın. Reimplementation özelliği da artırır. Kullanabileceğiniz `CToolBar` araç çubukları veya yönlendirmek üzere öğe işlevleri temel alınan bir başvuru elde edebilirsiniz [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesne ve araç çubuğu özelleştirme ve ek işlevler için kendi üye işlevlerini çağırın.

> [!TIP]
>  Yoğun eski öğesinin MFC uygulamasında yatırım yapmış, `CToolBar`, destek hala kullanılabilir. Makaleye göz atın [kullanarak bilgisayarınızı eski araç çubukları](../mfc/using-your-old-toolbars.md).

Ayrıca bkz. MFC genel örnek [DOCKTOOL](../visual-cpp-samples.md).

##  <a name="_core_the_toolbar_bitmap"></a> Araç çubuğu bit eşlemi

Bir kez çağrılamadığından bir `CToolBar` nesnesi, her düğme için bir görüntü içeren tek bir bit eşlem yükleyerek araç çubuğu görüntüsü oluşturur. Uygulama Sihirbazı'nı Visual C++ ile özelleştirebileceğiniz bir standart araç çubuğu bit eşlem oluşturur [araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md).

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Araç çubuğu temelleri](../mfc/toolbar-fundamentals.md)

- [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)

- [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)

- [Araç Çubuğu Denetimiyle Çalışma](../mfc/working-with-the-toolbar-control.md)

- [Eski Araç Çubuklarınızı Kullanma](../mfc/using-your-old-toolbars.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları

## <a name="see-also"></a>Ayrıca Bkz.

[Araç Çubukları](../mfc/toolbars.md)<br/>
[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)

