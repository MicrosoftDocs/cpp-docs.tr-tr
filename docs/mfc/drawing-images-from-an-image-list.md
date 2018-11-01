---
title: Görüntü Listesinden Görüntü Çizme
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], drawing images from
- drawing [MFC], images from image lists
- image lists [MFC], drawing images from
- images [MFC], drawing
ms.assetid: 2f6063fb-1c28-45f8-a333-008c064db11c
ms.openlocfilehash: 2ed309ec4a6e58fbc4a900bc541a80004d6be3d0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490564"
---
# <a name="drawing-images-from-an-image-list"></a>Görüntü Listesinden Görüntü Çizme

Görüntü çizmek için [CImageList::Draw](../mfc/reference/cimagelist-class.md#draw) üye işlevi. Bir cihaz bağlamı nesnesi, çizmek için cihaz bağlamı veren görüntü çizme konumda görüntünün dizinini ve çizim stilini belirtmek için bayrakları bir dizi işaretçi belirteceksiniz.

Belirttiğinizde **ILD_TRANSPARENT** stili `Draw` maskelenmiş bir görüntü çizin için iki adımlı bir işlem kullanır. İlk olarak, bir mantıksal gerçekleştirir- ve işlem bit görüntünün ve bit maskesi. Ardından bir mantıksal XOR işlemi ilk işlemin sonuçları ve arka plan BITS hedef cihaz bağlamının gerçekleştirir. Bu işlem, saydam alanlara içinde elde edilen görüntü oluşturur; diğer bir deyişle, her beyaz bir bit maskesi içinde saydam olarak elde edilen görüntü içinde karşılık gelen bit neden olur.

Düz renk arka plan üzerinde maskelenmiş bir görüntü çizmeden önce kullanmanız gereken [SetBkColor](../mfc/reference/cimagelist-class.md#setbkcolor) hedef aynı renge görüntü listesi arka plan rengini ayarlamak için üye işlevi. Rengi ayarlama saydam alanlara görüntüyü oluşturma ihtiyacını ortadan kaldırır ve sağlar `Draw` yalnızca performansın önemli bir artış výsledek hedef cihaz bağlamının görüntüyü kopyalamak için. Resim çizmek için belirtin **ILD_NORMAL** stil çağırdığınızda `Draw`.

Maskeli görüntü listesi arka plan rengini ayarlayabilirsiniz ([Cımagelist](../mfc/reference/cimagelist-class.md)) olan herhangi bir düz arka plan üzerinde doğru şekilde çizer. Bu nedenle, istediğiniz zaman. Arka plan rengini ayarlamak **CLR_NONE** şeffaf bir şekilde varsayılan olarak çizilecek görüntüleri neden olur. Görüntü listesi arka plan rengini almak için kullanın [GetBkColor](../mfc/reference/cimagelist-class.md#getbkcolor) üye işlevi.

**ILD_BLEND25** ve **ILD_BLEND50** stilleri titreme sistem vurgulama rengiyle görüntü. Kullanıcının seçebileceği bir nesneyi göstermek için maskelenmiş bir görüntü kullanırsanız, bu stilleri yararlıdır. Örneğin, kullanabileceğiniz **ILD_BLEND50** stilini kullanıcı seçtiğinde bir görüntü çizin.

Hedef cihaz kullanarak bağlamı nonmasked görüntü kopyalanır `SRCCOPY` ızgara işlemi. Görüntü renkleri arka plan rengi cihaz bağlamının bağımsız olarak aynı görünür. Belirtilen çizim stili `Draw` ayrıca nonmasked görüntünün görünümünü üzerinde hiçbir etkisi yoktur.

Çizme üye işlevi, başka bir işlev yanı sıra [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect), görüntü işleme olanağına genişletir. `DrawIndirect` gerçekleştirilen işlemlerin, parametre olarak bir [IMAGELISTDRAWPARAMS](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams) yapısı. Bu yapı, işleme ızgara işlemi (KIRPMA) kodları kullanımı dahil olmak üzere geçerli görüntünün özelleştirmek için kullanılabilir. KIRPMA kodları hakkında daha fazla bilgi için bkz. [ızgara işlemi kodları](/windows/desktop/gdi/raster-operation-codes) ve [Fırçalar bit eşlemleri](/windows/desktop/gdi/bitmaps-as-brushes) Windows SDK.

## <a name="see-also"></a>Ayrıca Bkz.

[CImageList Kullanma](../mfc/using-cimagelist.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

