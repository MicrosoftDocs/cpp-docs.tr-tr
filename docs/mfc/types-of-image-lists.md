---
description: 'Daha fazla bilgi edinin: görüntü listesi türleri'
title: Resim Listesi Türleri
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
ms.openlocfilehash: be18a523db366813a236fd4fd94bbb001345f0d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263744"
---
# <a name="types-of-image-lists"></a>Resim Listesi Türleri

İki tür görüntü listesi vardır ([CImageList](../mfc/reference/cimagelist-class.md)): maskelenmez ve maskelenir. "Maskeli olmayan görüntü listesi" bir veya daha fazla görüntü içeren bir renk bit eşleminden oluşur. "Maskelenmiş görüntü listesi", eşit boyuttaki iki bit eşlemden oluşur. Birincisi görüntüleri içeren bir renk bit eşlemdir ve ikincisi, ilk bit eşlemdeki her görüntü için bir maske serisi içeren tek renkli bir bit eşlemdir.

Üye işlevinin aşırı yüklerinden biri, `Create` görüntü listesinin maskelenmiş olup olmadığını belirten bir bayrak alır. (Diğer aşırı yüklemeler maskelenmiş görüntü listeleri oluşturur.)

Maskeli olmayan bir görüntü çizildiğinde, hedef cihaz bağlamına yalnızca kopyalanır; diğer bir deyişle, cihaz bağlamının var olan arka plan rengine çizilir. Maskelenmiş bir görüntü çizildiğinde, görüntü bitleri maskenin bitleri ile birleştirilir ve genellikle, hedef cihaz bağlamının arka plan renginin gösterdiği bit eşlemde saydam alanlar üretir. Maskelenmiş bir görüntü çizerken birçok çizim stili belirtebilirsiniz. Örneğin, seçilen bir nesneyi göstermek için görüntünün titremeli olduğunu belirtebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CImageList Kullanma](../mfc/using-cimagelist.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
