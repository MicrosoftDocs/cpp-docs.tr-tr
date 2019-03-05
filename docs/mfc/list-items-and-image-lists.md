---
title: Liste Öğeleri ve Görüntü Listeleri
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
ms.openlocfilehash: 1679b5c59c6dd55ca47c70ea7c880493304ebf4e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304320"
---
# <a name="list-items-and-image-lists"></a>Liste Öğeleri ve Görüntü Listeleri

Bir "öğesinde" liste denetimi ([CListCtrl](../mfc/reference/clistctrl-class.md)) bir simge bir etiket ve büyük olasılıkla diğer bilgiler ("alt öğesi") oluşur.

Liste denetim öğeleri için simgeler, görüntü listeleri yer alır. Bir görüntü listesi simge görünümünde kullanılan tam boyutlu simgeler içerir. İkinci, isteğe bağlı, görüntü listesi denetimi diğer görünümleri kullanmak için aynı simgeleri daha küçük sürümlerini içerir. İsteğe bağlı üçüncü bir liste gibi belirli görünümlerinde küçük simgeleri önünde görüntülemek için onay kutularını "state" görüntüleri içerir. Dördüncü isteğe bağlı bir liste içinde tek tek üstbilgi öğeleri listesi denetiminin görüntülenen görüntüleri içerir.

> [!NOTE]
>  Bir liste görünümü denetimi LVS_SHAREIMAGELISTS stiliyle oluşturduysanız, artık kullanımda olduğunda görüntü listeleri yok etmek sorumludur. Birden fazla liste görünümü denetimi aynı görüntü atamanız durumunda bu stil listeleri belirtin. Aksi takdirde, birden fazla denetim aynı görüntü listesi yok edilemiyor deneyebilir.

Liste öğeleri hakkında daha fazla bilgi için bkz. [liste görünümü görüntü listeler](/windows/desktop/Controls/using-list-view-controls) ve [öğeler ve alt öğeleri](/windows/desktop/Controls/using-list-view-controls) Windows SDK. Ayrıca bkz [Cımagelist](../mfc/reference/cimagelist-class.md) içinde *MFC başvurusu* ve [Cımagelist kullanma](../mfc/using-cimagelist.md) makaleler bu ailesi.

Liste denetimi oluşturmak için görüntü listeleri listeye yeni öğeler eklediğinizde, kullanılacak sağlamanız gerekir. Aşağıdaki örnek, bu yordamı gösterir. burada *m_pImagelist* bir işaretçi türü `CImageList` ve *m_listctrl* olduğu bir `CListCtrl` veri üyesi.

[!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]

Ancak, liste görünümü veya liste denetimi simgeleri göstermek planlamıyorsanız, görüntü listeleri gerekmez.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
