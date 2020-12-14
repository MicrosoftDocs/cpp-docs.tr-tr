---
description: 'Daha fazla bilgi edinin: araç çubuğu araç Ipuçları'
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
ms.openlocfilehash: bbf60246e778b60c2a6eacbcb55441806c00fad2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264290"
---
# <a name="toolbar-tool-tips"></a>Araç Çubuğu Araç İpuçları

Araç ipuçları, fare işaretçisini bir süre için bir düğmenin üzerine konumlandırdığınızda bir araç çubuğu düğmesinin amacının kısa açıklamalarını sunan küçük bir açılan pencere. Bir araç çubuğu olan uygulama sihirbazıyla bir uygulama oluşturduğunuzda sizin için araç ipucu desteği sağlanır. Bu makalede, uygulama Sihirbazı tarafından oluşturulan araç ipucu desteğinin yanı sıra uygulamanıza araç ipucu desteğinin nasıl ekleneceği açıklanmaktadır.

Bu makalede şunları ele alınmaktadır:

- [Araç ipuçlarını etkinleştirme](#_core_activating_tool_tips)

- [Durum çubuğu güncelleştirmelerine göre daha fazla](#_core_fly_by_status_bar_updates)

## <a name="activating-tool-tips"></a><a name="_core_activating_tool_tips"></a> Araç Ipuçlarını etkinleştirme

Uygulamanızdaki araç ipuçlarını etkinleştirmek için iki şey yapmanız gerekir:

- CBRS_TOOLTIPS stilini, [CToolBar:: Create](../mfc/reference/ctoolbar-class.md#create) Işlevine veya [SetBarStyle](../mfc/reference/ccontrolbar-class.md#setbarstyle)öğesine *dwStyle* parametresi olarak geçirilen diğer stillere (WS_CHILD, WS_VISIBLE ve diğer **cbrs_** stilleri gibi) ekleyin.

- Aşağıdaki yordamda açıklandığı gibi, bir yeni satır karakteri (' \n ') ile ayrılmış araç çubuğu ipucu metnini, Toolbar komutu için komut satırı istemi içeren dize kaynağına ekleyin. Dize kaynağı araç çubuğu düğmesinin KIMLIĞINI paylaşır.

#### <a name="to-add-the-tool-tip-text"></a>Araç ipucu metnini eklemek için

1. Araç çubuğu düzenleyicisinde araç çubuğunu düzenleirken, belirli bir düğme için **araç çubuğu düğmesi özellikleri** penceresini açın.

1. **İstem** kutusunda, söz konusu düğmenin araç ipucunda görünmesini istediğiniz metni belirtin.

> [!NOTE]
> Metni araç çubuğu düzenleyicisinde düğme özelliği olarak ayarlamak, içinde dize kaynağını açıp düzenlemeniz gereken önceki yordamı değiştirir.

Araç ipuçlarına sahip bir denetim çubuğunda alt denetimler varsa, denetim çubuğu aşağıdaki ölçütlere uyan denetim çubuğundaki her alt denetim için bir araç ipucu görüntüler:

- Denetimin KIMLIĞI-1 değil.

- Kaynak dosyasındaki alt denetimle aynı KIMLIĞE sahip dize tablosu girişinin bir araç ipucu dizesi vardır.

## <a name="flyby-status-bar-updates"></a><a name="_core_fly_by_status_bar_updates"></a> Durum çubuğu güncelleştirmelerine göre daha fazla

Araç ipuçlarıyla ilgili bir özellik, "daha fazla" durum çubuğu güncelleştirmesine sahiptir. Varsayılan olarak, durum çubuğundaki ileti, düğme etkinleştirildiğinde yalnızca belirli bir araç çubuğu düğmesini tanımlar. Geçirilen stil listenize CBRS_FLYBY dahil ederek `CToolBar::Create` , fare imleci düğmeyi etkinleştirmeden araç çubuğunun üzerinden geçtiğinde, bu iletilerin güncelleştirilmesini sağlayabilirsiniz.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [MFC araç çubuğu uygulama (araç çubuklarında genel bakış bilgileri)](../mfc/mfc-toolbar-implementation.md)

- [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları

- [Araç çubuğu denetimiyle çalışma](../mfc/working-with-the-toolbar-control.md)

- [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC araç çubuğu uygulama](../mfc/mfc-toolbar-implementation.md)
