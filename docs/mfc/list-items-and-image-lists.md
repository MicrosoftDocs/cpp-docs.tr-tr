---
title: Liste Öğeleri ve Görüntü Listeleri
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
ms.openlocfilehash: d378c6e07280349f9995981ad794039ebc015b25
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353060"
---
# <a name="list-items-and-image-lists"></a>Liste Öğeleri ve Görüntü Listeleri

Liste denetimindeki[(CListCtrl)](../mfc/reference/clistctrl-class.md)bir "öğe" bir simge, etiket ve muhtemelen diğer bilgilerden ("alt öğeler") oluşur.

Liste denetim öğeleri için simgeler resim listelerinde bulunur. Bir resim listesi simge görünümünde kullanılan tam boyutlu simgeler içerir. İkinci, isteğe bağlı, görüntü listesi denetimin diğer görünümlerinde kullanılmak üzere aynı simgelerin daha küçük sürümlerini içerir. Üçüncü isteğe bağlı liste, belirli görünümlerde küçük simgelerin önünde görüntülenmek üzere onay kutuları gibi "durum" görüntüleri içerir. Dördüncü isteğe bağlı liste, liste denetiminin tek tek üstbilgi öğelerinde görüntülenen görüntüler içerir.

> [!NOTE]
> LVS_SHAREIMAGELISTS stiliyle bir liste görünümü denetimi oluşturulursa, artık kullanılmadıklarında görüntü listelerini yok etmek sizin sorumluluğunuzdadır. Aynı resim listelerini birden çok liste görünümü denetimine atarsanız bu stili belirtin; aksi takdirde, birden fazla denetim aynı görüntü listesini yok etmeye çalışabilir.

Liste öğeleri hakkında daha fazla bilgi için Windows SDK'daki [Liste Görünümü Resim Listeleri](/windows/win32/Controls/using-list-view-controls) ve Öğeleri ve Alt [Öğeleri'ne](/windows/win32/Controls/using-list-view-controls) bakın. Ayrıca, bu makale ailesinde *MFC Başvurusu* ve [CImageList'i kullanma](../mfc/using-cimagelist.md) sınıfındaki [CImageList](../mfc/reference/cimagelist-class.md) sınıfına bakın.

Liste denetimi oluşturmak için, listeye yeni öğeler eklediğinizde kullanılacak resim listeleri sağlamanız gerekir. Aşağıdaki örnek, *m_pImagelist* bir tür `CImageList` işaretçisi ve *m_listctrl* bir `CListCtrl` veri üyesi olduğu bu yordamı gösterir.

[!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]

Ancak, liste görünümünde veya liste denetiminizde simgeleri görüntülemeyi planlamıyorsanız, resim listelerine ihtiyacınız yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
