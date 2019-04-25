---
title: Resim Listesi Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
ms.openlocfilehash: cb95de134939e1b06e2a8b827424c986f8c48ef3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180472"
---
# <a name="using-an-image-list"></a>Resim Listesi Kullanma

Görüntü listesi tipik kullanımını aşağıdaki deseni izler:

- Oluşturmak bir [Cımagelist](../mfc/reference/cimagelist-class.md) nesnesi ve bir aşırı yüklemelerinden birini çağırın, [Oluştur](../mfc/reference/cimagelist-class.md#create) bir görüntü listesi oluşturma ve buna eklemek için işlevi `CImageList` nesne.

- Görüntü listesi oluşturduğunuzda görüntüleri eklemezseniz, görüntüleri görüntü listeye çağırarak eklemek [Ekle](../mfc/reference/cimagelist-class.md#add) veya [okuma](../mfc/reference/cimagelist-class.md#read) üye işlevi.

- Görüntü listesi denetimin uygun üye işlevini çağırarak bir denetimle ilişkilendirme veya görüntü listesinden görüntü listenin kullanarak kendiniz görüntüler çizme [çizmek](../mfc/reference/cimagelist-class.md#draw) üye işlevi.

- Belki de sürüklemek için görüntü listesinin yerleşik desteği kullanarak görüntü, sürükleyin izin verin.

> [!NOTE]
>  Görüntü listesi oluşturulurken **yeni** işleci gerekir yok `CImageList` ile işiniz bittiğinde nesne.

## <a name="see-also"></a>Ayrıca bkz.

[CImageList Kullanma](../mfc/using-cimagelist.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
