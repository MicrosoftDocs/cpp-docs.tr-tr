---
description: 'Hakkında daha fazla bilgi için: liste öğeleri ve görüntü listeleri'
title: Liste Öğeleri ve Görüntü Listeleri
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
ms.openlocfilehash: 674c67c2eb104d86f0bd80732469129b6c70e0f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283374"
---
# <a name="list-items-and-image-lists"></a>Liste Öğeleri ve Görüntü Listeleri

Liste denetimindeki bir "öğe" ([CListCtrl](reference/clistctrl-class.md)) bir simge, etiket ve muhtemelen diğer bilgilerden oluşur ("alt öğeler" içinde).

Liste denetim öğelerinin simgeleri resim listelerinde bulunur. Bir görüntü listesi, simge görünümünde kullanılan tam boyutlu simgeleri içerir. İkinci bir isteğe bağlı görüntü listesi, denetimin diğer görünümlerinde kullanmak için aynı simgelerin daha küçük sürümlerini içerir. Üçüncü bir isteğe bağlı liste, belirli görünümlerde küçük simgelerin önünde görüntülenmek üzere, onay kutuları gibi "durum" görüntülerini içerir. Dördüncü bir isteğe bağlı liste, liste denetiminin tek başlık öğelerinde görüntülenen görüntüleri içerir.

> [!NOTE]
> LVS_SHAREIMAGELISTS stiliyle bir liste görünümü denetimi oluşturulduysa, artık kullanımda olmadığında görüntü listelerinin yok edilmesi sizin sorumluluğunuzdadır. Aynı görüntü listelerini birden çok liste görünümü denetimine atarsanız, bu stili belirtin; Aksi halde, birden fazla denetim aynı görüntü listesini yok etme deneyebilir.

Liste öğeleri hakkında daha fazla bilgi için bkz. [liste görünümü görüntü listeleri](/windows/win32/Controls/using-list-view-controls) ve [öğe ve](/windows/win32/Controls/using-list-view-controls) alt öğeleri Windows SDK. Ayrıca, *MFC başvurusu* ' nda sınıf [CImageList](reference/cimagelist-class.md) ' i ve bu makale ailesinde [CImageList](using-cimagelist.md) ' i kullanma bölümüne bakın.

Liste denetimi oluşturmak için, listeye yeni öğeler eklediğinizde kullanılacak görüntü listeleri sağlamanız gerekir. Aşağıdaki örnek, *m_pImagelist* türünün bir işaretçisi olduğu `CImageList` ve *m_listCtrl* bir veri üyesi olduğu bu yordamı göstermektedir `CListCtrl` .

[!code-cpp[NVC_MFCControlLadenDialog#19](codesnippet/cpp/list-items-and-image-lists_1.cpp)]

Ancak, liste görünümünüzde veya liste denetiminizdeki simgeleri görüntülemeyi düşünmüyorsanız, görüntü listelerine ihtiyacınız yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](using-clistctrl.md)<br/>
[Denetimler](controls-mfc.md)
