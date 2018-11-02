---
title: Üstbilgi Denetimleriyle Birlikte Görüntü Listeleri Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
ms.openlocfilehash: 5c623024ef64f49e3379ef02154cda72d445a197
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545255"
---
# <a name="using-image-lists-with-header-controls"></a>Üstbilgi Denetimleriyle Birlikte Görüntü Listeleri Kullanma

Üstbilgi öğeleri bir görüntüyü bir üst öğesi içinde seçeneğine sahipsiniz. Bir ilişkili görüntü listesinde depolanan bu görüntü, 16 x 16 pikseldir ve liste görünümü denetimi içinde kullanılan simge görüntüleri olarak aynı özelliklere sahiptir. Bu davranış başarıyla uygulamak için önce oluşturun ve görüntü listesini listenin üst denetimle ilişkilendirme ve ardından görüntüyü görüntüler üstbilgi öğesi özniteliklerini değiştirin gerekir.

Üstbilgi denetimi için bir işaretçi kullanarak ayrıntıları, aşağıdaki yordamı gösterir (`m_pHdrCtrl`) ve bir görüntü listesi için bir işaretçi (`m_pHdrImages`).

### <a name="to-display-an-image-in-a-header-item"></a>Bir üst öğesi içinde bir resim görüntülemek için

1. Yeni bir görüntü listesi oluşturun (veya varolan bir görüntü listesi nesnesi kullanma) kullanarak [Cımagelist](../mfc/reference/cimagelist-class.md) oluşturucusu, sonuç işaretçi depolama.

1. Yeni görüntü listesi nesnesi çağırarak başlatılmaya [CImageList::Create](../mfc/reference/cimagelist-class.md#create). Aşağıdaki kod, bu çağrının bir örnektir.

   [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]

1. Her bir üst öğe için görüntüleri ekleyin. Aşağıdaki kod, iki önceden tanımlanmış görüntüler ekler.

   [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]

1. Üstbilgi denetimi çağrısı ile görüntü listesi ilişkilendirmek [CHeaderCtrl::SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist).

1. Üstbilgi öğesi bir görüntüden ilişkili görüntü listesini görüntülemek için değiştirin. Aşağıdaki örnek, gelen ilk görüntü atar `m_phdrImages`, ilk üst öğe `m_pHdrCtrl`.

   [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]

Kullanılan parametre değerlerini hakkında ayrıntılı bilgi için ilgili başvurun [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md).

> [!NOTE]
>  Birden çok denetim aynı görüntü listesi kullanma olması mümkündür. Örneğin, standart liste görünümü denetimi olabilir hem küçük simge görünümünde bir liste görünümü denetimi ve liste görünümü denetimi üstbilgi öğeleri tarafından kullanılan bir görüntü listesi (16 x 16 piksel görüntülerin).

## <a name="see-also"></a>Ayrıca Bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)

