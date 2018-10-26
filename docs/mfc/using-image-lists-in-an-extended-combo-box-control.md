---
title: Bir Genişletilmiş Birleşik giriş kutusu denetiminde görüntü listeleri kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- image lists [MFC], combo boxes
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 15b069c1075a1b2b7db484da588684fca280ef29
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083405"
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

## <a name="see-also"></a>Ayrıca Bkz.

[CComboBoxEx Kullanma](../mfc/using-ccomboboxex.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

