---
title: CToolBarCtrl Nesnesi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
ms.openlocfilehash: cf1d2eeb9efd2f8a1e7b433c0e18dd868a8b9aca
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445885"
---
# <a name="creating-a-ctoolbarctrl-object"></a>CToolBarCtrl Nesnesi Oluşturma

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesneleri çeşitli iç veri yapıları, düğme resmi bit eşlemlerinin listesi, düğme etiketi dizelerinin listesi ve bir görüntüyü ve/veya dizeyi, düğmenin konumu, stili, durumu ve komut kimliğiyle ilişkilendiren `TBBUTTON` yapılarının bir listesini içerir. Bu veri yapılarının her bir öğesi sıfır tabanlı bir dizin tarafından adlandırılır. `CToolBarCtrl` nesnesini kullanabilmeniz için, bu veri yapılarını ayarlamanız gerekir. Veri yapılarının bir listesi için, Windows SDK [araç çubuğu denetimleri](controls-mfc.md) bölümüne bakın. Dizeler listesi yalnızca düğme etiketleri için kullanılabilir; araç çubuğundan dizeleri alamazsınız.

`CToolBarCtrl` nesnesini kullanmak için, genellikle bu adımları takip edersiniz:

### <a name="to-use-a-ctoolbarctrl-object"></a>CToolBarCtrl nesnesi kullanmak için

1. [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesini oluşturun.

1. Windows araç çubuğu ortak denetimini oluşturmak ve `CToolBarCtrl` nesnesine eklemek için [Oluştur](../mfc/reference/ctoolbarctrl-class.md#create) ' a çağrı yapın. Düğmeler için bit eşlem görüntüleri istiyorsanız, [AddBitmap](../mfc/reference/ctoolbarctrl-class.md#addbitmap)'i çağırarak düğme bit eşlemlerini araç çubuğuna ekleyin. Düğmeler için dize etiketleri istiyorsanız, [AddString](../mfc/reference/ctoolbarctrl-class.md#addstring) ve/veya [AddStrings](../mfc/reference/ctoolbarctrl-class.md#addstrings)çağırarak dizeleri araç çubuğuna ekleyin. `AddString` ve/veya `AddStrings`çağrıldıktan sonra, görüntülenecek dize veya dizeleri almak için [AutoSize](../mfc/reference/ctoolbarctrl-class.md#autosize) 'i çağırmanız gerekir.

1. [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)'ı çağırarak araç çubuğuna düğme yapıları ekleyin.

1. Araç ipuçları istiyorsanız araç [Ipucu bildirimlerini işleme](../mfc/handling-tool-tip-notifications.md)bölümünde açıklandığı gibi araç çubuğunun sahip penceresinde **TTN_NEEDTEXT** iletileri işleyin.

1. Kullanıcılarınızın araç çubuğunu özelleştirebilmesini istiyorsanız, özelleştirme [bildirimlerini işleme](../mfc/handling-customization-notifications.md)bölümünde açıklandığı gibi, sahip penceresinde özelleştirme bildirim iletilerini işleyin.

## <a name="see-also"></a>Ayrıca bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
