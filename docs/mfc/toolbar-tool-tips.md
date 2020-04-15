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
ms.openlocfilehash: 1762931b75734801659fd6271377260bd0473614
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373451"
---
# <a name="toolbar-tool-tips"></a>Araç Çubuğu Araç İpuçları

Araç ipuçları, fareyi bir süre boyunca bir düğmeüzerinde konumlandırdığınızda araç çubuğu düğmesinin amacının kısa açıklamalarını sunan küçük açılır pencerelerdir. Uygulama Sihirbazı'nda araç çubuğu olan bir uygulama oluşturduğunuzda, sizin için araç ipucu desteği sağlanır. Bu makalede, hem Uygulama Sihirbazı tarafından oluşturulan araç ipucu desteği hem de uygulamanıza araç ipucu desteği nin nasıl ekleyeceğiniaçık.

Bu makale şunları kapsamaktadır:

- [Araç ipuçlarını etkinleştirme](#_core_activating_tool_tips)

- [Flyby durum çubuğu güncellemeleri](#_core_fly_by_status_bar_updates)

## <a name="activating-tool-tips"></a><a name="_core_activating_tool_tips"></a>Etkinleştirme Aracı İpuçları

Uygulamanızdaki araç ipuçlarını etkinleştirmek için iki şey yapmanız gerekir:

- CToolBar için *dwStyle* parametresi olarak geçirilen diğer stiller (WS_CHILD, WS_VISIBLE ve diğer **CBRS_** stilleri gibi) CBRS_TOOLTIPS stili [ekleyin::İşlev oluştur](../mfc/reference/ctoolbar-class.md#create) veya [SetBarStyle'da.](../mfc/reference/ccontrolbar-class.md#setbarstyle)

- Aşağıdaki yordamda açıklandığı gibi, araç çubuğu komutu komut satırı istemini içeren dize kaynağına yeni bir satır karakteri ('\n') ile ayrılan araç çubuğu ipucu metnini ekleyin. Dize kaynağı araç çubuğu düğmesinin kimliğini paylaşır.

#### <a name="to-add-the-tool-tip-text"></a>Araç ipucu metnini eklemek için

1. Araç çubuğu düzenleyicisinde araç çubuğunu düzenlerken, belirli bir düğme için **Araç Çubuğu Düğme Özellikleri** penceresini açın.

1. **İstem** kutusunda, bu düğmenin araç ucunda görünmesini istediğiniz metni belirtin.

> [!NOTE]
> Metni araç çubuğu düzenleyicisinde bir düğme özelliği olarak ayarlamak, dize kaynağını açmanız ve düzenlemeniz gereken eski yordamın yerini alır.

Araç uçları etkinleştirilmiş bir denetim çubuğunda alt denetimler varsa, denetim çubuğu aşağıdaki ölçütleri karşıladığı sürece denetim çubuğundaki her alt denetim için bir araç ipucu görüntüler:

- Denetimin kimliği - 1 değildir.

- Kaynak dosyasındaki alt denetimle aynı kimliği içeren dize tablosu girişinin bir araç ipucu dizesi vardır.

## <a name="flyby-status-bar-updates"></a><a name="_core_fly_by_status_bar_updates"></a>Flyby Durum Çubuğu Güncellemeleri

Araç ipuçlarıyla ilgili bir özellik "flyby" durum çubuğu güncelleştirmedir. Varsayılan olarak, durum çubuğundaki ileti, düğme etkinleştirildiğinde yalnızca belirli bir araç çubuğu düğmesini açıklar. Geçirilen stiller listenize CBRS_FLYBY `CToolBar::Create`ekleyerek, fare imleci düğmeyi etkinleştirmeden araç çubuğunun üzerinden geçtiğinde bu iletileri güncelleştirebilirsiniz.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [MFC Araç Çubuğu Uygulaması (araç çubuklarına genel bakış bilgileri)](../mfc/mfc-toolbar-implementation.md)

- [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları

- [Araç çubuğu denetimiyle çalışma](../mfc/working-with-the-toolbar-control.md)

- [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Araç Çubuğu Uygulaması](../mfc/mfc-toolbar-implementation.md)
