---
title: Resim Listesi Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
ms.openlocfilehash: 710831ea8ef6b52292ba3e8eb84a69575c6c7508
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226834"
---
# <a name="using-an-image-list"></a>Resim Listesi Kullanma

Bir görüntü listesinin tipik kullanımı aşağıdaki kalıbı izler:

- Bir [CImageList](../mfc/reference/cimagelist-class.md) nesnesi oluşturun ve bir görüntü listesi oluşturup nesneye Iliştirmek için [Create](../mfc/reference/cimagelist-class.md#create) işlevinin aşırı yüklemelerinden birini çağırın `CImageList` .

- Görüntü listesini oluştururken resim eklemediğiniz takdirde, [Add](../mfc/reference/cimagelist-class.md#add) veya [Read](../mfc/reference/cimagelist-class.md#read) member işlevini çağırarak görüntü listesine resim ekleyin.

- Görüntü listesini, bu denetimin uygun üye işlevini çağırarak bir denetimle ilişkilendirin ya da görüntü listesinin [Çizim](../mfc/reference/cimagelist-class.md#draw) üye işlevini kullanarak görüntü listesinden kendi görüntülerini çizin.

- Büyük olasılıkla kullanıcının resim listesinin yerleşik desteğini sürükleyerek bir görüntüyü sürüklemeye izin verebilir.

> [!NOTE]
> Görüntü listesi **`new`** işleçle oluşturulduysa, bununla `CImageList` işiniz bittiğinde nesneyi yok etmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[CImageList Kullanma](../mfc/using-cimagelist.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
