---
title: Resim Listesinden Resim Çizme
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], drawing images from
- drawing [MFC], images from image lists
- image lists [MFC], drawing images from
- images [MFC], drawing
ms.assetid: 2f6063fb-1c28-45f8-a333-008c064db11c
ms.openlocfilehash: e4e60f0e6e4ee22712e4bbce344fd6437cf3db7e
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916418"
---
# <a name="drawing-images-from-an-image-list"></a>Resim Listesinden Resim Çizme

Bir görüntü çizmek için, [CImageList::D RAW](../mfc/reference/cimagelist-class.md#draw) üye işlevini kullanın. Bir cihaz bağlam nesnesi, çizilecek görüntünün dizini, görüntünün çizildiği cihaz bağlamındaki konum ve çizim stilini göstermek için bir bayraklar kümesi belirteceksiniz.

**ILD_TRANSPARENT** stilini belirttiğinizde, `Draw` maskelenmiş bir görüntü çizmek için iki adımlı bir işlem kullanır. İlk olarak, görüntünün bitleri ve maskenin bitleri üzerinde bir mantıksal ve işlem gerçekleştirir. Ardından, ilk işlemin sonuçlarında ve hedef cihaz bağlamının arka plan bitlerinin bir mantıksal-XOR işlemi gerçekleştirir. Bu işlem, sonuçta elde edilen görüntüde saydam alanlar oluşturur; diğer bir deyişle, maskede her bir beyaz bit, sonuçta elde edilen görüntüde karşılık gelen bitin saydam olmasına neden olur.

Maskelenmiş bir görüntüyü düz bir arka planda çizmadan önce, görüntü listesinin arka plan rengini hedefle aynı renge ayarlamak için [SetBkColor](../mfc/reference/cimagelist-class.md#setbkcolor) üye işlevini kullanmanız gerekir. Rengin ayarlanması görüntüde saydam alanlar oluşturma gereksinimini ortadan kaldırır ve `Draw` görüntüyü hedef cihaz bağlamına kopyalamanız sayesinde performansı önemli ölçüde artırır. Görüntüyü çizmek için, çağırdığınızda `Draw` **ILD_NORMAL** stilini belirtin.

Bir maskelenmiş görüntü listesi ([CImageList](../mfc/reference/cimagelist-class.md)) için arka plan rengini dilediğiniz zaman, herhangi bir katı arka plana doğru bir şekilde çizmiş olacak şekilde ayarlayabilirsiniz. Arka plan renginin **CLR_NONE** olarak ayarlanması görüntülerin varsayılan olarak saydam olarak çizilmesini sağlar. Bir görüntü listesinin arka plan rengini almak için [GetBkColor](../mfc/reference/cimagelist-class.md#getbkcolor) üye işlevini kullanın.

**ILD_BLEND25** ve **ILD_BLEND50** stilleri, görüntüyü sistem vurgu rengi ile renk taklidi. Bu stiller, kullanıcının seçim kullanabileceği bir nesneyi temsil etmek için maskelenmiş bir görüntü kullanırsanız faydalıdır. Örneğin, **ILD_BLEND50** stilini kullanıcının seçtiği zaman görüntüyü çizmek için kullanabilirsiniz.

Maskelenmiş olmayan bir görüntü, `SRCCOPY` tarama işlemi kullanılarak hedef cihaz bağlamına kopyalanır. Görüntüdeki renkler, cihaz bağlamının arka plan rengine bakılmaksızın aynı görüntülenir. ' De `Draw` belirtilen çizim stillerinin, maskeli olmayan bir görüntünün görünümü üzerinde hiçbir etkisi yoktur.

Çiz üye işlevine ek olarak, başka bir işlev olan [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect), bir görüntüyü işleme yeteneğini genişletir. `DrawIndirect`, bir [IMAGELISTDRAWPARAMS](/windows/desktop/api/commctrl/ns-commctrl-imagelistdrawparams) yapısı olan bir parametre olarak alır. Bu yapı, raster işlem (ROP) kodlarının kullanımı da dahil olmak üzere geçerli görüntünün işlenmesini özelleştirmek için kullanılabilir. ROP kodları hakkında daha fazla bilgi için, Windows SDK fırçalar olarak [raster Işlem kodları](/windows/desktop/gdi/raster-operation-codes) ve [bit eşlemler](/windows/desktop/gdi/bitmaps-as-brushes) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CImageList Kullanma](../mfc/using-cimagelist.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
