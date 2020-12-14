---
description: 'Daha fazla bilgi edinin: CToolBarCtrl nesnesi oluşturma'
title: CToolBarCtrl Nesnesi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
ms.openlocfilehash: 2ea6f1c170fd82a18d4ceb9d5ca9e7fbadfcdbc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310115"
---
# <a name="creating-a-ctoolbarctrl-object"></a>CToolBarCtrl Nesnesi Oluşturma

[CToolBarCtrl](reference/ctoolbarctrl-class.md) nesneleri çeşitli iç veri yapıları, düğme resmi bit eşlemlerinin listesi, düğme etiketi dizelerinin listesi ve `TBBUTTON` bir görüntüyü ve/veya dizeyi düğmenin konumu, stili, durumu ve komut kimliğiyle ilişkilendiren bir yapı listesi içerir. Bu veri yapılarının her bir öğesi sıfır tabanlı bir dizin tarafından adlandırılır. Bir nesneyi kullanabilmeniz için önce `CToolBarCtrl` Bu veri yapılarını ayarlamanız gerekir. Veri yapılarının bir listesi için, Windows SDK [araç çubuğu denetimleri](controls-mfc.md) bölümüne bakın. Dizeler listesi yalnızca düğme etiketleri için kullanılabilir; araç çubuğundan dizeleri alamazsınız.

Bir nesnesi kullanmak için `CToolBarCtrl` genellikle aşağıdaki adımları takip edersiniz:

### <a name="to-use-a-ctoolbarctrl-object"></a>CToolBarCtrl nesnesi kullanmak için

1. [CToolBarCtrl](reference/ctoolbarctrl-class.md) nesnesini oluşturun.

1. Windows araç çubuğu ortak denetimini oluşturmak ve nesnesine eklemek için [Oluştur](reference/ctoolbarctrl-class.md#create) ' a çağrı yapın `CToolBarCtrl` . Düğmeler için bit eşlem görüntüleri istiyorsanız, [AddBitmap](reference/ctoolbarctrl-class.md#addbitmap)'i çağırarak düğme bit eşlemlerini araç çubuğuna ekleyin. Düğmeler için dize etiketleri istiyorsanız, [AddString](reference/ctoolbarctrl-class.md#addstring) ve/veya [AddStrings](reference/ctoolbarctrl-class.md#addstrings)çağırarak dizeleri araç çubuğuna ekleyin. `AddString`Ve/veya çağırdıktan sonra `AddStrings` , görüntülenecek dize veya dizeleri almak için [AutoSize](reference/ctoolbarctrl-class.md#autosize) 'i çağırmanız gerekir.

1. [AddButtons](reference/ctoolbarctrl-class.md#addbuttons)'ı çağırarak araç çubuğuna düğme yapıları ekleyin.

1. Araç ipuçları istiyorsanız araç [Ipucu bildirimlerini işleme](handling-tool-tip-notifications.md)bölümünde açıklandığı gibi araç çubuğunun sahip penceresinde **TTN_NEEDTEXT** iletileri işleyin.

1. Kullanıcılarınızın araç çubuğunu özelleştirebilmesini istiyorsanız, özelleştirme [bildirimlerini işleme](handling-customization-notifications.md)bölümünde açıklandığı gibi, sahip penceresinde özelleştirme bildirim iletilerini işleyin.

## <a name="see-also"></a>Ayrıca bkz.

[CToolBarCtrl Kullanma](using-ctoolbarctrl.md)<br/>
[Denetimler](controls-mfc.md)
