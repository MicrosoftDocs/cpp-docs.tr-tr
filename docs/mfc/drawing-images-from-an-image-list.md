---
description: 'Hakkında daha fazla bilgi edinin: görüntü listesinden resim çizme'
title: Resim Listesinden Resim Çizme
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], drawing images from
- drawing [MFC], images from image lists
- image lists [MFC], drawing images from
- images [MFC], drawing
ms.assetid: 2f6063fb-1c28-45f8-a333-008c064db11c
ms.openlocfilehash: 2c413092e1e7568488a091acd2b0db175d03dab9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283465"
---
# <a name="drawing-images-from-an-image-list"></a>Resim Listesinden Resim Çizme

Bir görüntü çizmek için, [CImageList::D RAW](reference/cimagelist-class.md#draw) üye işlevini kullanın. Bir cihaz bağlam nesnesi, çizilecek görüntünün dizini, görüntünün çizildiği cihaz bağlamındaki konum ve çizim stilini göstermek için bir bayraklar kümesi belirteceksiniz.

**ILD_TRANSPARENT** stilini belirttiğinizde, `Draw` maskelenmiş bir görüntü çizmek için iki adımlı bir işlem kullanır. İlk olarak, görüntünün bitleri ve maskenin bitleri üzerinde bir mantıksal ve işlem gerçekleştirir. Ardından, ilk işlemin sonuçlarında ve hedef cihaz bağlamının arka plan bitlerinin bir mantıksal-XOR işlemi gerçekleştirir. Bu işlem, sonuçta elde edilen görüntüde saydam alanlar oluşturur; diğer bir deyişle, maskede her bir beyaz bit, sonuçta elde edilen görüntüde karşılık gelen bitin saydam olmasına neden olur.

Maskelenmiş bir görüntüyü düz bir arka planda çizmadan önce, görüntü listesinin arka plan rengini hedefle aynı renge ayarlamak için [SetBkColor](reference/cimagelist-class.md#setbkcolor) üye işlevini kullanmanız gerekir. Rengin ayarlanması görüntüde saydam alanlar oluşturma gereksinimini ortadan kaldırır ve `Draw` görüntüyü hedef cihaz bağlamına kopyalamanız sayesinde performansı önemli ölçüde artırır. Görüntüyü çizmek için, ' i çağırdığınızda **ILD_NORMAL** stilini belirtin `Draw` .

Bir maskelenmiş görüntü listesi ([CImageList](reference/cimagelist-class.md)) için arka plan rengini dilediğiniz zaman, herhangi bir katı arka plana doğru bir şekilde çizmiş olacak şekilde ayarlayabilirsiniz. Arka plan renginin **CLR_NONE** olarak ayarlanması görüntülerin varsayılan olarak saydam olarak çizilmesini sağlar. Bir görüntü listesinin arka plan rengini almak için [GetBkColor](reference/cimagelist-class.md#getbkcolor) üye işlevini kullanın.

**ILD_BLEND25** ve **ILD_BLEND50** stilleri, görüntüyü sistem vurgu rengi ile renk taklidi. Bu stiller, kullanıcının seçim kullanabileceği bir nesneyi temsil etmek için maskelenmiş bir görüntü kullanırsanız faydalıdır. Örneğin, kullanıcının onu seçtiği zaman görüntüyü çizmek için **ILD_BLEND50** stilini kullanabilirsiniz.

Maskelenmiş olmayan bir görüntü, tarama işlemi kullanılarak hedef cihaz bağlamına kopyalanır `SRCCOPY` . Görüntüdeki renkler, cihaz bağlamının arka plan rengine bakılmaksızın aynı görüntülenir. ' De belirtilen çizim stillerinin, `Draw` maskeli olmayan bir görüntünün görünümü üzerinde hiçbir etkisi yoktur.

Çiz üye işlevine ek olarak, başka bir işlev olan [DrawIndirect](reference/cimagelist-class.md#drawindirect), bir görüntüyü işleme yeteneğini genişletir. `DrawIndirect` , bir [IMAGELISTDRAWPARAMS](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) yapısı olan bir parametre olarak alır. Bu yapı, raster işlem (ROP) kodlarının kullanımı da dahil olmak üzere geçerli görüntünün işlenmesini özelleştirmek için kullanılabilir. ROP kodları hakkında daha fazla bilgi için, Windows SDK fırçalar olarak [raster Işlem kodları](/windows/win32/gdi/raster-operation-codes) ve [bit eşlemler](/windows/win32/gdi/bitmaps-as-brushes) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CImageList Kullanma](using-cimagelist.md)<br/>
[Denetimler](controls-mfc.md)
