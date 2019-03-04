---
title: Genişletilmiş Birleşik Giriş Kutusu Denetiminde Görüntü Listeleri Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], combo boxes
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
ms.openlocfilehash: 6e4d983d53e49fc8d9c80c206f1a23078eb82f61
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57266997"
---
# <a name="using-image-lists-in-an-extended-combo-box-control"></a>Genişletilmiş Birleşik Giriş Kutusu Denetiminde Görüntü Listeleri Kullanma

Genişletilmiş Birleşik giriş kutusu denetimleri'nin ana özelliği bir birleşik giriş kutusu denetimi öğeleri ayrı ayrı bir görüntü listesinden görüntü ilişkilendirmek yeteneğidir. Üç farklı resimleri görüntülemek her bir öğe bulabildiği: Seçili durumuna, nonselected durumu ve bir üçüncü katman görüntü için bir tane.

Aşağıdaki yordam bir görüntü listesi bir Genişletilmiş Birleşik giriş kutusu denetimi ile ilişkilendirir:

### <a name="to-associate-an-image-list-with-an-extended-combo-box-control"></a>Görüntü listesi bir Genişletilmiş Birleşik giriş kutusu denetimi ile ilişkilendirmek için

1. Yeni bir görüntü listesi oluşturun (veya varolan bir görüntü listesi nesnesi kullanma) kullanarak [Cımagelist](../mfc/reference/cimagelist-class.md) oluşturucusu ve sonuçta elde edilen işaretçi depolama.

1. Yeni görüntü listesi nesnesi çağırarak başlatılmaya [CImageList::Create](../mfc/reference/cimagelist-class.md#create). Aşağıdaki kod, bu çağrının bir örnektir.

   [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_1.cpp)]

1. Olası her durum için isteğe bağlı görüntü ekleme: seçilen veya nonselected ve bir katmana. Aşağıdaki kod üç önceden tanımlanmış görüntüler ekler.

   [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_2.cpp)]

1. Görüntü listesi denetimi için bir çağrı ile ilişkilendirmek [CComboBoxEx::SetImageList](../mfc/reference/ccomboboxex-class.md#setimagelist).

Görüntü listesi denetimi ile ilişkilendirildikten sonra tek tek her öğe için üç olası durum kullanacağı görüntüleri belirtebilirsiniz. Daha fazla bilgi için [ayrı bir öğe için görüntüleri ayarlama](../mfc/setting-the-images-for-an-individual-item.md).

## <a name="see-also"></a>Ayrıca bkz.

[CComboBoxEx Kullanma](../mfc/using-ccomboboxex.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
