---
title: Resim Listesi Türleri
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
ms.openlocfilehash: 939aad78b7cf8cca9c940bae11892d23dbb659cb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304762"
---
# <a name="types-of-image-lists"></a>Resim Listesi Türleri

Görüntü listeleri iki tür vardır ([Cımagelist](../mfc/reference/cimagelist-class.md)): nonmasked ve maskelenmiş. Bir veya daha fazla görüntü içeren bir renk bit eşlem "Nonmasked görüntü listesi" oluşur. "Maskelenmiş görüntü listesi" eşit boyutta iki bit eşlemler oluşur. Görüntüleri içeren renkli bir bit eşlem ilk ve ikinci bir dizi maskelerini içeren tek renkli bir bit eşlem ise — bir ilk bit eşlem resmi.

Bir aşırı yüklemelerinden birini `Create` üye işlev görüntü listesi maskelenir olup olmadığını belirten bir bayrak alır. (Diğer aşırı yüklemeler maskelenmiş görüntü listeleri oluşturun.)

Nonmasked görüntü çizildiğinde, yalnızca hedef cihaz bağlamına kopyalanır; diğer bir deyişle, bu cihaz bağlamı mevcut arka plan rengi çizilir. Maskelenmiş bir görüntü çizildiğinde, görüntünün BITS arka plan rengi hedef cihaz bağlamının burada görünür bit eşlem saydam alanlar genellikle üretme maskesi, BITS ile birleştirilir. Çeşitli çizim stilleri, maskelenmiş bir resim çizerken belirtebilirsiniz. Örneğin, görüntüyü seçili nesneyi göstermek için Titrek belirtebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CImageList Kullanma](../mfc/using-cimagelist.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
