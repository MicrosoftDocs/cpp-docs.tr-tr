---
description: 'Hakkında daha fazla bilgi edinin: başlık denetimleriyle birlikte görüntü listeleri kullanma'
title: Üstbilgi Denetimleriyle Birlikte Görüntü Listeleri Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
ms.openlocfilehash: 549f54c9fae7e0e0a63c726f4b75d2adeb38eef8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322737"
---
# <a name="using-image-lists-with-header-controls"></a>Üstbilgi Denetimleriyle Birlikte Görüntü Listeleri Kullanma

Üst bilgi öğelerinin bir başlık öğesi içinde görüntü görüntülemesine olanak tanır. İlişkili bir görüntü listesinde depolanan bu görüntü 16 x 16 pikseldir ve liste görünümü denetiminde kullanılan simge görüntüleriyle aynı özelliklere sahiptir. Bu davranışı başarıyla uygulamak için, önce görüntü listesini oluşturmalı ve başlatmalısınız, listeyi üst bilgi denetimiyle ilişkilendirmeli ve sonra görüntüyü görüntüleyen üst bilgi öğesinin özniteliklerini değiştirmelisiniz.

Aşağıdaki yordamda, üst bilgi denetimine () yönelik bir işaretçi `m_pHdrCtrl` ve bir resim listesi () işaretçisi kullanılarak Ayrıntılar gösterilmektedir `m_pHdrImages` .

### <a name="to-display-an-image-in-a-header-item"></a>Bir üst bilgi öğesinde görüntü görüntüleme

1. Yeni bir görüntü listesi oluşturun (veya var olan bir görüntü listesi nesnesini kullanın) ve sonuç işaretçisini depolayarak [CImageList](../mfc/reference/cimagelist-class.md) oluşturucusunu kullanarak.

1. Yeni görüntü listesi nesnesini, [CImageList:: Create](../mfc/reference/cimagelist-class.md#create)öğesini çağırarak başlatın. Aşağıdaki kod bu çağrının bir örneğidir.

   [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]

1. Her üstbilgi öğesi için görüntüleri ekleyin. Aşağıdaki kod önceden tanımlanmış iki görüntü ekler.

   [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]

1. Resim listesini bir [CHeaderCtrl:: SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist)çağrısıyla birlikte üstbilgi denetimiyle ilişkilendirin.

1. Başlık öğesini, ilişkili görüntü listesinden bir resim görüntüleyecek şekilde değiştirin. Aşağıdaki örnek ilk görüntüsünü, öğesinden `m_phdrImages` ilk üstbilgi öğesine atar `m_pHdrCtrl` .

   [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]

Kullanılan parametre değerleriyle ilgili ayrıntılı bilgi için, ilgili [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)' i inceleyin.

> [!NOTE]
> Aynı görüntü listesini kullanan birden çok denetim olması mümkündür. Örneğin, standart liste görünümü denetiminde, bir liste görünümü denetiminin küçük simge görünümü ve liste görünümü denetiminin üst bilgi öğeleri tarafından kullanılan bir görüntü listesi (16 x 16 piksellik görüntü) olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)
