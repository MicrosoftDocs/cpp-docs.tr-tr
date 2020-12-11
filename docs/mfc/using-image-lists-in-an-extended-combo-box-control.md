---
description: 'Hakkında daha fazla bilgi edinin: Genişletilmiş Birleşik giriş kutusu denetiminde görüntü listeleri kullanma'
title: Genişletilmiş Birleşik Giriş Kutusu Denetiminde Görüntü Listeleri Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], combo boxes
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
ms.openlocfilehash: 9fb4b70f91a8ffc3d0175ec855cd005de10da280
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154376"
---
# <a name="using-image-lists-in-an-extended-combo-box-control"></a>Genişletilmiş Birleşik Giriş Kutusu Denetiminde Görüntü Listeleri Kullanma

Genişletilmiş Birleşik giriş kutusu denetimlerinin ana özelliği, görüntüleri bir açılan kutu denetimindeki tek tek öğelerle bir görüntü listesinden ilişkilendirme olanağıdır. Her öğe üç farklı görüntüyü görüntüleyebilir: biri seçili durum için, biri seçili olmayan bir durum ve bir kaplama görüntüsü için üçüncü.

Aşağıdaki yordam bir görüntü listesini Genişletilmiş Birleşik giriş kutusu denetimiyle ilişkilendirir:

### <a name="to-associate-an-image-list-with-an-extended-combo-box-control"></a>Bir görüntü listesini Genişletilmiş Birleşik giriş kutusu denetimiyle ilişkilendirme

1. [CImageList](../mfc/reference/cimagelist-class.md) oluşturucusunu kullanarak ve sonuç işaretçisini depolayarak yeni bir görüntü listesi oluşturun (veya var olan bir görüntü listesi nesnesini kullanın).

1. Yeni görüntü listesi nesnesini, [CImageList:: Create](../mfc/reference/cimagelist-class.md#create)öğesini çağırarak başlatın. Aşağıdaki kod bu çağrının bir örneğidir.

   [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_1.cpp)]

1. Her olası durum için isteğe bağlı görüntüler ekleyin: seçili veya seçili olmayan ve bir kaplama. Aşağıdaki kod önceden tanımlanmış üç görüntü ekler.

   [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_2.cpp)]

1. Görüntü listesini bir [CComboBoxEx:: SetImageList](../mfc/reference/ccomboboxex-class.md#setimagelist)çağrısıyla birlikte denetimiyle ilişkilendirin.

Görüntü listesi denetimle ilişkilendirildiğinde, her bir öğenin her bir olası durum için kullanacağı görüntüleri tek tek belirleyebilirsiniz. Daha fazla bilgi için bkz. [tek bir öğe Için görüntüleri ayarlama](../mfc/setting-the-images-for-an-individual-item.md).

## <a name="see-also"></a>Ayrıca bkz.

[CComboBoxEx Kullanma](../mfc/using-ccomboboxex.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
