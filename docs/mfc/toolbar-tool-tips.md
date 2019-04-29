---
title: Araç Çubuğu Araç İpuçları
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], activating
- CBRS_TOOLTIPS constant [MFC]
- tool tips [MFC], adding text
- updates [MFC]
- CBRS_FLYBY constant [MFC]
- tool tips [MFC]
- updating status bar messages
- updates, status bar messages
- status bars [MFC], tool tips
- flyby status bar updates
ms.assetid: d1696305-b604-4fad-9f09-638878371412
ms.openlocfilehash: 4582b03844e1be3d4cf70bcc3fff1c3b66119ae3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351780"
---
# <a name="toolbar-tool-tips"></a>Araç Çubuğu Araç İpuçları

Araç ipuçları, fare bir süre için bir düğmenin üzerine getirdiğinizde, bir araç çubuğu düğmesinin amaçlı kısa açıklamaları sunan küçük bir açılır pencereleri ' dir. Uygulama Sihirbazı ile bir araç olan bir uygulama oluşturduğunuzda, sizin için araç ipucu desteği sağlanır. Bu makalede, Uygulama Sihirbazı'nı ve uygulamanıza nasıl araç ipucu desteği ekleme tarafından oluşturulan her iki araç ipucu desteği açıklanmaktadır.

Bu makalede ele alınmıştır:

- [Araç ipuçlarını etkinleştirme](#_core_activating_tool_tips)

- [Flyby durum çubuğu güncelleştirmeleri](#_core_fly_by_status_bar_updates)

##  <a name="_core_activating_tool_tips"></a> Araç ipuçlarını etkinleştirme

Araç ipuçları, uygulamanızda etkinleştirmek için iki işlem yapmanız gerekir:

- Diğer stil cbrs_tooltıps stili eklemek (WS_CHILD ws_vısıble ve diğer gibi **CBRS_** stilleri) olarak geçirilen *dwStyle* parametresi [CToolBar::Create](../mfc/reference/ctoolbar-class.md#create) işlev veya [SetBarStyle](../mfc/reference/ccontrolbar-class.md#setbarstyle).

- Aşağıdaki yordamda açıklandığı gibi bir yeni satır karakteri ('\n'), araç komutu için komut satırı istemi içeren dize kaynağına ayrılmış araç ipucu metni ekleyin. Araç çubuğu düğmesini kimliği dize kaynağını paylaşır.

#### <a name="to-add-the-tool-tip-text"></a>Araç İpucu metni eklemek için

1. Araç çubuğu Düzenleyicisi araç düzenlerken açın **araç çubuğu düğmesi özellikleri** penceresi için belirli bir düğme.

1. İçinde **istemi** kutusunda, düğmenin araç ipucu olarak görünmesini istediğiniz metni belirtin.

> [!NOTE]
>  Metin bir düğme özelliği araç çubuğu düzenleyicisinde zorunda kalınan önceki yordamı değiştirir gibi ayarlar açın ve dize kaynağı düzenleyemez.

Araç ipuçları etkin bir denetim çubuğu üzerinde alt denetimlerin varsa, aşağıdaki ölçütleri karşıladığı sürece denetim çubuğu denetim çubuğundaki her alt denetim için araç ipucu görüntülenir:

- 1. değil - denetiminin kimliği.

- Dize tablosu girişi alt denetimin kaynak dosyasında aynı Kimliğe sahip bir araç ipucu dize var.

##  <a name="_core_fly_by_status_bar_updates"></a> Flyby durum çubuğu güncelleştirmeleri

Araç ipuçları için ilgili bir güncelleştirme çubuğu "flyby" durumu özelliğidir. Düğme etkin olduğunda varsayılan olarak, yalnızca belirli bir araç çubuğu düğmesi durum çubuğundaki ileti açıklar. CBRS_FLYBY geçirilen stilleri listesine ekleyerek `CToolBar::Create`, bu iletileri fare imleci düğmenin etkinleştirmeden araç geçerken güncelleştirilmiş olabilir.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [MFC araç çubuğu uygulaması (araç çubuklarında genel bakış bilgileri)](../mfc/mfc-toolbar-implementation.md)

- [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları

- [Araç çubuğu denetimiyle çalışma](../mfc/working-with-the-toolbar-control.md)

- [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Araç Çubuğu Uygulaması](../mfc/mfc-toolbar-implementation.md)
