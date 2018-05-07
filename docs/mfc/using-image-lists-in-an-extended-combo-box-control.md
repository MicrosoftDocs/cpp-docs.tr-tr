---
title: Genişletilmiş Birleşik giriş kutusu denetiminde görüntü listeleri kullanma | Microsoft Docs
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
ms.openlocfilehash: 7c9a701871631fead48c22b1ffb2cbc3c386b960
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="using-image-lists-in-an-extended-combo-box-control"></a>Genişletilmiş Birleşik Giriş Kutusu Denetiminde Görüntü Listeleri Kullanma
Ana Genişletilmiş Birleşik giriş kutusu denetimleri birleşik giriş kutusu denetimi öğeleri ayrı ayrı bir görüntü listesi görüntülerden ilişkilendirmek olanağı özelliğidir. Her üç farklı görüntüleri görüntüleyemeyecek öğesidir: Seçili durumunda, biri kendi nonselected durumu ve üçüncü bir katmana görüntüsü için için bir tane.  
  
 Aşağıdaki yordam bir resim listesi Genişletilmiş Birleşik giriş kutusu denetimi ile ilişkilendirir:  
  
### <a name="to-associate-an-image-list-with-an-extended-combo-box-control"></a>Genişletilmiş Birleşik giriş kutusu denetimi ile resim listesi ilişkilendirmek için  
  
1.  Yeni bir görüntü listesi oluşturun (veya varolan bir görüntü listesi nesnesini kullanın) kullanarak [Cımagelist](../mfc/reference/cimagelist-class.md) oluşturucusu ve sonuç işaretçi depolama.  
  
2.  Çağırarak yeni görüntü listesi nesnesi başlatılmaya [CImageList::Create](../mfc/reference/cimagelist-class.md#create). Aşağıdaki kod, bu çağrının bir örnektir.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_1.cpp)]  
  
3.  Olası her durum için isteğe bağlı görüntüleri ekleme: Seçili veya nonselected ve bir katmana. Aşağıdaki kod, üç önceden tanımlanmış görüntüler ekler.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_2.cpp)]  
  
4.  Görüntü listesi denetimi çağrısı ile ilişkilendirmek [CComboBoxEx::SetImageList](../mfc/reference/ccomboboxex-class.md#setimagelist).  
  
 Görüntü listesi denetimi ile ilişkilendirildikten sonra ayrı ayrı her öğe için üç olası durumlar kullanacağı görüntüleri belirtebilirsiniz. Daha fazla bilgi için bkz: [ayrı bir öğe için resimleri ayarlama](../mfc/setting-the-images-for-an-individual-item.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComboBoxEx kullanma](../mfc/using-ccomboboxex.md)   
 [Denetimler](../mfc/controls-mfc.md)

