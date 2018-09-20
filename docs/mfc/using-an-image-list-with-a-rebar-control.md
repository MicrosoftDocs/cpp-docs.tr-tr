---
title: Rebar denetimiyle birlikte bir görüntü listesi kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- image lists [MFC], rebar controls
- rebar controls [MFC], image lists
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ff524f1f29e4db2ac5bb4628064583f0fe7583e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372372"
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

## <a name="see-also"></a>Ayrıca Bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

