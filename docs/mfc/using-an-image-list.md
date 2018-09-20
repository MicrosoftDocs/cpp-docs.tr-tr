---
title: Görüntü listesi kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4dc30d418ae57205e4566dad7f490a773321768e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391676"
---
# <a name="using-an-image-list"></a>Görüntü Listesi Kullanma

Görüntü listesi tipik kullanımını aşağıdaki deseni izler:

- Oluşturmak bir [Cımagelist](../mfc/reference/cimagelist-class.md) nesnesi ve bir aşırı yüklemelerinden birini çağırın, [Oluştur](../mfc/reference/cimagelist-class.md#create) bir görüntü listesi oluşturma ve buna eklemek için işlevi `CImageList` nesne.

- Görüntü listesi oluşturduğunuzda görüntüleri eklemezseniz, görüntüleri görüntü listeye çağırarak eklemek [Ekle](../mfc/reference/cimagelist-class.md#add) veya [okuma](../mfc/reference/cimagelist-class.md#read) üye işlevi.

- Görüntü listesi denetimin uygun üye işlevini çağırarak bir denetimle ilişkilendirme veya görüntü listesinden görüntü listenin kullanarak kendiniz görüntüler çizme [çizmek](../mfc/reference/cimagelist-class.md#draw) üye işlevi.

- Belki de sürüklemek için görüntü listesinin yerleşik desteği kullanarak görüntü, sürükleyin izin verin.

> [!NOTE]
>  Görüntü listesi oluşturulurken **yeni** işleci gerekir yok `CImageList` ile işiniz bittiğinde nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[CImageList Kullanma](../mfc/using-cimagelist.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

