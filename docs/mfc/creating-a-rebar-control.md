---
title: Rebar Denetimi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- rebar controls [MFC], creating
- CReBarCtrl class [MFC], creating
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
ms.openlocfilehash: 0fb651aef599b64b787d96a668e2e1496c1dff8e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274469"
---
# <a name="creating-a-rebar-control"></a>Rebar Denetimi Oluşturma

[CReBarCtrl](../mfc/reference/crebarctrl-class.md) nesneler üst nesneden görünür önce oluşturulmalıdır. Bu olasılıklar boyama sorunları en aza indirir.

Örneği için çubuk barınağı denetimleri (kullanılan çerçeve pencere nesneleri) için araç çubuğu denetimleri genellikle üst windows kullanılır. Bu nedenle, çubuk barınağı denetiminin üst çerçeve penceresi nesnedir. Ana çerçeve penceresi nesnesi olduğu için `OnCreate` (üst), üye işlev, çubuk barınağı denetimi oluşturmak için mükemmel bir yerde.

Kullanılacak bir `CReBarCtrl` nesnesi, genellikle şu adımları izleyin:

### <a name="to-use-a-crebarctrl-object"></a>CReBarCtrl nesnesini kullanmak için

1. Oluşturmak [CReBarCtrl](../mfc/reference/crebarctrl-class.md) nesne.

1. Çağrı [Oluştur](../mfc/reference/crebarctrl-class.md#create) Windows ortak çubuk barınağı denetimi oluşturun ve buna eklemek için `CReBarCtrl` nesne, istenen tüm stilleri belirtme.

1. Bir çağrı ile bir bit eşlem yük [CBitmap::LoadBitmap](../mfc/reference/cbitmap-class.md#loadbitmap), çubuk barınağı denetim nesnesi arka planı olarak kullanılacak.

1. Oluşturun ve çubuk barınağı denetimi nesnenin içerdiği tüm alt pencere nesneleri (araç çubukları, iletişim kutusu denetimleri ve benzeri) başlatın.

1. Başlatma bir **REBARBANDINFO** yapısı hakkında eklenecek bant için gerekli bilgileri.

1. Çağrı [InsertBand](../mfc/reference/crebarctrl-class.md#insertband) varolan alt öğe pencerelerini eklemek için (gibi `m_wndReToolBar`) içine yeni bir çubuk barınağı denetimi. Varolan bir çubuk barınağı denetimi bant ekleme konusunda daha fazla bilgi için bkz. [Rebar denetimleri ve bantları](../mfc/rebar-controls-and-bands.md).

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
