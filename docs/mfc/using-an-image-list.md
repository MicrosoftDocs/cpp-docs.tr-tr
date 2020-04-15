---
title: Resim Listesi Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
ms.openlocfilehash: 0d9566739a15e5d216eb052a7265313850515648
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366567"
---
# <a name="using-an-image-list"></a>Resim Listesi Kullanma

Bir resim listesinin tipik kullanımı aşağıdaki deseni izler:

- Bir [CImageList](../mfc/reference/cimagelist-class.md) nesnesi oluşturun ve görüntü [Create](../mfc/reference/cimagelist-class.md#create) listesi oluşturmak ve `CImageList` nesneye eklemek için Create işlevinin aşırı yüklerinden birini çağırın.

- Resim listesini oluştururken resim eklemediyseniz, [Üye Ekle](../mfc/reference/cimagelist-class.md#add) veya [Oku](../mfc/reference/cimagelist-class.md#read) işlevini arayarak resim listesini resim listesine ekleyin.

- Bu denetimin uygun üye işlevini çağırarak görüntü listesini bir denetimle ilişkilendirin veya resim listesinin [Draw](../mfc/reference/cimagelist-class.md#draw) üye işlevini kullanarak resim listesinden görüntüler kendiniz çizin.

- Belki de kullanıcının, sürükleme için görüntü listesinin yerleşik desteğini kullanarak görüntüyü sürüklemesine izin verin.

> [!NOTE]
> Görüntü listesi **yeni** işleçle oluşturulduysa, onunla `CImageList` yaptığınız da nesneyi yok etmelisiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CImageList Kullanma](../mfc/using-cimagelist.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
