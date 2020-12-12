---
description: 'Hakkında daha fazla bilgi edinin: Rebar Denetimiyle bir görüntü listesi kullanma'
title: Rebar Denetimiyle Birlikte Bir Görüntü Listesi Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], rebar controls
- rebar controls [MFC], image lists
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
ms.openlocfilehash: ae4aa0259cbe850dbab8ef4bc04277014b39e357
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271804"
---
# <a name="using-an-image-list-with-a-rebar-control"></a>Rebar Denetimiyle Birlikte Bir Görüntü Listesi Kullanma

Her bir çubuk bandı, ilişkili bir görüntü listesinden bir resim olan diğer şeyler arasında bulunabilir. Aşağıdaki yordamda, bir yeniden çubuk bantında görüntü görüntülemek için gereken adımlar ayrıntılı olarak verilmiştir.

### <a name="to-display-images-in-a-rebar-band"></a>Resimleri bir yeniden çubuk bantta görüntüleme

1. Bir [SetImageList](../mfc/reference/crebarctrl-class.md#setimagelist)öğesine çağrı yaparak, var olan bir görüntü listesine bir işaretçi geçirerek, Rebar denetim nesneniz için bir görüntü listesi ekleyin.

1. **Rebarbanınfo** yapısını, bir yeniden çubuk bandına bir görüntü atamak için değiştirin:

   -  `RBBIM_IMAGE` Gerekli olan ek bayrakları dahil etmek için, bit düzeyinde OR Işlecini kullanarak fMask üyesini olarak ayarlayın.

   - *IImage* üyesini görüntülenecek görüntünün görüntü listesi dizinine ayarlayın.

1. Dahil edilen alt pencerenin boyut, metin ve tanıtıcısı gibi kalan tüm veri üyelerini gerekli bilgilerle başlatın.

1. Yeni bandı (görüntüyle birlikte), **Rebarbanınfo** yapısını geçirerek [CReBarCtrl:: InsertBand](../mfc/reference/crebarctrl-class.md#insertband)çağrısı ile ekleyin.

Aşağıdaki örnek, var olan bir görüntü listesi nesnesinin, Rebar denetim nesnesine () eklenmiş olduğunu varsayar `m_wndReBar` . İlk görüntüsünü içeren yeni bir çubuk bandı (tarafından tanımlanır `rbi` ), öğesine yapılan çağrısıyla eklenir `InsertBand` :

[!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/cpp/using-an-image-list-with-a-rebar-control_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
