---
title: Rebar Denetimiyle Birlikte Bir Görüntü Listesi Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], rebar controls
- rebar controls [MFC], image lists
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
ms.openlocfilehash: fa5307c201850fc42439c79a1c638a0707379913
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285405"
---
# <a name="using-an-image-list-with-a-rebar-control"></a>Rebar Denetimiyle Birlikte Bir Görüntü Listesi Kullanma

Her çubuk barınağı bant, diğerlerinin yanı sıra bir görüntüden bir ilişkili görüntü listesini içerebilir. Aşağıdaki yordam bir görüntü bir çubuk barınağı bandı görüntülemek için gerekli adımları ayrıntılı olarak açıklanmaktadır.

### <a name="to-display-images-in-a-rebar-band"></a>Bir rebar bant resimleri görüntülemek için

1. Görüntü listesi, çubuk barınağı denetimi nesneye bir çağrı yaparak ekleme [SetImageList](../mfc/reference/crebarctrl-class.md#setimagelist), varolan bir görüntü listesinin bir işaretçi geçirme.

1. Değiştirme **REBARBANDINFO** yapısı bir çubuk barınağı bant için bir görüntü atamak için:

   - Ayarlama *fMask* üyesine `RBBIM_IMAGE`, gerektiği gibi ek bayrakları dahil etmek için bit düzeyinde OR işleci kullanarak.

   - Ayarlama *iImage* görüntülenecek üye görüntünün görüntü listesi dizin.

1. Boyut, metin ve gerekli bilgileri içerdiği alt pencere tanıtıcısı gibi kalan tüm veri üyeleri başlatın.

1. Çağrısıyla (Resimli) yeni bant ekleme [CReBarCtrl::InsertBand](../mfc/reference/crebarctrl-class.md#insertband), geçen **REBARBANDINFO** yapısı.

Aşağıdaki örnek iki görüntü sahip mevcut bir görüntü listesi nesnesi çubuk barınağı denetimi nesneye iliştirilmiş olduğu varsayılır (`m_wndReBar`). Yeni bir çubuk barınağı bant (tarafından tanımlanan `rbi`), ilk görüntü içeren, bir çağrı ile eklenen `InsertBand`:

[!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/cpp/using-an-image-list-with-a-rebar-control_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
