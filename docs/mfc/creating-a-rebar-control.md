---
description: 'Daha fazla bilgi edinin: Rebar denetimi oluşturma'
title: Rebar Denetimi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- rebar controls [MFC], creating
- CReBarCtrl class [MFC], creating
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
ms.openlocfilehash: 71328af9d4701c412f7876629ebd2a56fa8ffd04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310024"
---
# <a name="creating-a-rebar-control"></a>Rebar Denetimi Oluşturma

Üst nesne görünür olmadan önce [CReBarCtrl](reference/crebarctrl-class.md) nesnelerinin oluşturulması gerekir. Bu, boyama sorunlarının olasılıklarını en aza indirir.

Örneğin, Rebar denetimleri (çerçeve pencere nesnelerinde kullanılır) yaygın olarak araç çubuğu denetimleri için üst pencere olarak kullanılır. Bu nedenle, Rebar denetiminin üst öğesi çerçeve pencere nesnesidir. Çerçeve pencere nesnesi üst öğe olduğu için, `OnCreate` üye işlevi (üst öğe), Rebar denetimini oluşturmak için mükemmel bir yerdir.

Bir nesnesi kullanmak için `CReBarCtrl` genellikle aşağıdaki adımları takip edersiniz:

### <a name="to-use-a-crebarctrl-object"></a>CReBarCtrl nesnesini kullanmak için

1. [CReBarCtrl](reference/crebarctrl-class.md) nesnesini oluşturun.

1. Windows Rebar ortak denetimini oluşturmak için [Oluştur](reference/crebarctrl-class.md#create) `CReBarCtrl` ' u çağırın ve istediğiniz stilleri belirterek nesneye ekleyin.

1. Rebar Denetim nesnesinin arka planı olarak kullanılacak bir [CBitmap:: LoadBitmap](reference/cbitmap-class.md#loadbitmap)çağrısıyla bir bit eşlem yükleyin.

1. Rebar denetim nesnesi tarafından yer alacak tüm alt pencere nesnelerini (araç çubukları, iletişim kutusu denetimleri vb.) oluşturun ve başlatın.

1. Bir **Rebarbanınfo** yapısını, eklenecek bant için gerekli bilgilerle başlatın.

1. Yeni Rebar denetimine varolan alt pencereleri (gibi) eklemek için [InsertBand](reference/crebarctrl-class.md#insertband) 'i çağırın `m_wndReToolBar` . Varolan bir yeniden çubuk denetimine bant ekleme hakkında daha fazla bilgi için bkz. [Rebar denetimleri ve bantları](rebar-controls-and-bands.md).

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](using-crebarctrl.md)<br/>
[Denetimler](controls-mfc.md)
