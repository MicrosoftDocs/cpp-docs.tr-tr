---
title: Üstbilgi Denetimleriyle Birlikte Görüntü Listeleri Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
ms.openlocfilehash: 8002c16d1cdf5e0683b642001409b6da9c260660
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366465"
---
# <a name="using-image-lists-with-header-controls"></a>Üstbilgi Denetimleriyle Birlikte Görüntü Listeleri Kullanma

Üstbilgi öğeleri, üstbilgi öğesi içinde bir görüntü görüntüleme yeteneğine sahiptir. İlişkili bir görüntü listesinde depolanan bu resim 16 x 16 pikseldir ve liste görünümü denetiminde kullanılan simge görüntüleriyle aynı özelliklere sahiptir. Bu davranışı başarılı bir şekilde uygulamak için, önce resim listesini oluşturmanız ve başlatmanız, listeyi üstbilgi denetimiyle ilişkilendirmeniz ve ardından görüntüyü görüntüleyecek üstbilgi öğesinin özniteliklerini değiştirmeniz gerekir.

Aşağıdaki yordam, bir üstbilgi denetimi (`m_pHdrCtrl`) ve bir görüntü listesi (`m_pHdrImages`için bir işaretçi kullanarak ayrıntıları gösterir.

### <a name="to-display-an-image-in-a-header-item"></a>Üstbilgi öğesinde görüntü görüntülemek için

1. [CImageList](../mfc/reference/cimagelist-class.md) oluşturucuyu kullanarak yeni bir görüntü listesi (veya varolan bir görüntü listesi nesnesi kullanın) oluşturarak ortaya çıkan işaretçiyi depola.

1. CImageList'i arayarak yeni resim listesi nesnesini [başlatma::Oluştur](../mfc/reference/cimagelist-class.md#create). Aşağıdaki kod bu çağrının bir örneğidir.

   [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]

1. Her üstbilgi öğesi için görüntüleri ekleyin. Aşağıdaki kod iki önceden tanımlanmış görüntü ekler.

   [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]

1. Resim listesini üstbilgi denetimiyle [CHeaderCtrl::SetImageList'e](../mfc/reference/cheaderctrl-class.md#setimagelist)yapılan bir çağrıyla ilişkilendirin.

1. İlişkili resim listesinden bir resim görüntülemek için üstbilgi öğesini değiştirin. Aşağıdaki örnek, ilk `m_phdrImages`görüntüyü, ilk üstbilgi öğesine `m_pHdrCtrl`atar.

   [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]

Kullanılan parametre değerleri hakkında ayrıntılı bilgi için ilgili [CHeaderCtrl'ye](../mfc/reference/cheaderctrl-class.md)başvurun.

> [!NOTE]
> Aynı resim listesini kullanarak birden çok denetime sahip olmak mümkündür. Örneğin, standart bir liste görünümü denetiminde, hem liste görünümü denetiminin küçük simge görünümü hem de liste görünümü denetiminin üstbilgi öğeleri tarafından kullanılan bir görüntü listesi (16 x 16 piksel görüntüler) olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)
