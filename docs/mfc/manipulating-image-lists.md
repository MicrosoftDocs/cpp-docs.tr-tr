---
title: Görüntü Listelerini Düzenleme
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], manipulating
- lists [MFC], image
- CImageList class [MFC], manipulating
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
ms.openlocfilehash: 7ec641f1e7090e27edd367203b430b932ede52a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643774"
---
# <a name="manipulating-image-lists"></a>Görüntü Listelerini Düzenleme

[Değiştirin](../mfc/reference/cimagelist-class.md#replace) üye işlevi bir görüntü listesi görüntüde değiştirir ([Cımagelist](../mfc/reference/cimagelist-class.md)) ile yeni bir görüntüsü. Bu işlev, ayrıca dinamik olarak bir görüntü listesi nesne görüntülerdeki sayısını artırmanız gerekiyorsa yararlıdır. [SetImageCount](../mfc/reference/cimagelist-class.md#setimagecount) işlevi, depolanan görüntü listesinden görüntü sayısını dinamik olarak değişir. Görüntü listesi boyutunu artırmak için çağrı `Replace` görüntüleri için yeni görüntü yuva eklemek için. Görüntü listesi boyutu azaltırsanız, yeni boyut ötesinde görüntüleri kurtulurlar.

[Kaldır](../mfc/reference/cimagelist-class.md#remove) üye işlevi, görüntü listesinden görüntü kaldırır. [Kopyalama](../mfc/reference/cimagelist-class.md#copy) üye işlevi kopyalayabilir veya takas görüntü listesi içinde görüntüler. Bu işlev, kaynak görüntüyü hedef dizine kopyalanmalıdır ya da kaynak ve hedef görüntüleri takas belirtmenize olanak sağlar.

İki görüntü listeleri birleştirerek yeni bir görüntü listesi oluşturmak için uygun aşırı yüklemesini kullanın. [Oluştur](../mfc/reference/cimagelist-class.md#create) üye işlevi. Bu aşırı yüklemesini `Create` birleştirmeleri mevcut görüntü ilk görüntüsü listeler, sonuçta elde edilen görüntü yeni bir görüntü listesi nesnesi içinde depolamak. Yeni görüntü, ikinci görüntü şeffaf bir şekilde ilk çizim tarafından oluşturulur. Yeni görüntü için bit maskeleri mantıksal OR işleminde için iki var olan görüntülerden gerçekleştirmenin sonucunun maskesidir.

Tüm görüntüleri birleştirilir ve yeni görüntüyü Liste nesnesine eklenen kadar yinelenir.

Çağırarak arşive görüntü bilgileri yazabilirsiniz [yazma](../mfc/reference/cimagelist-class.md#write) üye işlevine ve geri çağrı yaparak okuma [okuma](../mfc/reference/cimagelist-class.md#read) üye işlevi.

[GetSafeHandle](../mfc/reference/cimagelist-class.md#getsafehandle), [iliştirme](../mfc/reference/cimagelist-class.md#attach), ve [ayırma](../mfc/reference/cimagelist-class.md#detach) üye işlevleri bağlı görüntü listesinin tanıtıcı değiştirmenize izin `CImageList` nesnesi sırada [DeleteImageList](../mfc/reference/cimagelist-class.md#deleteimagelist) üye işlevini, yok etme olmadan görüntü listesi siler `CImageList` nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[CImageList Kullanma](../mfc/using-cimagelist.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

