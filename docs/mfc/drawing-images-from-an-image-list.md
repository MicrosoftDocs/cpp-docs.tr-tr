---
title: Görüntü listesinden görüntü çizme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], drawing images from
- drawing [MFC], images from image lists
- image lists [MFC], drawing images from
- images [MFC], drawing
ms.assetid: 2f6063fb-1c28-45f8-a333-008c064db11c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86983506770b9719972170dfbb70b02c8026e108
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345215"
---
# <a name="drawing-images-from-an-image-list"></a>Görüntü Listesinden Görüntü Çizme
Resim çizmek için kullanmak [CImageList::Draw](../mfc/reference/cimagelist-class.md#draw) üye işlevi. Bir cihaz bağlamı nesnesi, çizmek için resim çizmek cihaz bağlamı konumda görüntünün dizinini ve çizim stilini belirtmek için bayrakları kümesi için bir işaretçi belirtirsiniz.  
  
 Belirttiğinizde `ILD_TRANSPARENT` stili **çizin** maskelenmiş bir resim çizmek için iki adımlı bir işlem kullanır. İlk olarak, bir mantıksal gerçekleştirir- ve görüntünün bit ve bit maskesi işlemi. Ardından ilk işlemin sonuçları ve hedef cihaz bağlamı arka plan BITS XOR mantıksal işlemi gerçekleştirir. Bu işlem, elde edilen görüntü saydam alanlar oluşturur; diğer bir deyişle, her beyaz bit maskesi içinde karşılık gelen bit saydam olarak elde edilen görüntü neden olur.  
  
 Düz renk arka plan üzerinde maskelenmiş bir görüntü çizmeden önce kullanmanız gereken [SetBkColor](../mfc/reference/cimagelist-class.md#setbkcolor) hedef aynı renkte resim listesi arka plan rengini ayarlamak için üye işlevi. Rengi ayarlama görüntüde saydam alanları oluşturma ihtiyacını ortadan kaldırır ve sağlar **çizin** yalnızca performans önemli bir artışa yol hedef cihaz bağlamı için görüntüyü kopyalamak için. Resim çizmek için belirtmek `ILD_NORMAL` stil çağırdığınızda **çizin**.  
  
 Maskeli resim listesi arka plan rengini ayarlama ([Cımagelist](../mfc/reference/cimagelist-class.md)) olan tüm düz bir arka plan üzerinde doğru şekilde çizer şekilde dilediğiniz zaman. Arka plan rengini ayarlama `CLR_NONE` saydam varsayılan olarak çizilecek görüntüleri neden olur. Görüntü listesi arka plan rengini almak kullanın [GetBkColor](../mfc/reference/cimagelist-class.md#getbkcolor) üye işlevi.  
  
 `ILD_BLEND25` Ve `ILD_BLEND50` stilleri titreme sistem vurgulama renk görüntüsüyle. Bu stiller, kullanıcının seçebileceği bir nesne göstermek için bir maskelenmiş görüntüsü kullanıyorsanız yararlıdır. Örneğin, kullanabileceğiniz `ILD_BLEND50` kullanıcı seçtiğinde resim çizim stili.  
  
 Hedef aygıt kullanarak içerik nonmasked görüntü kopyalanan **SRCCOPY** tarama işlemi. Görüntü renkleri cihaz bağlamı arka plan rengini bakılmaksızın aynı görünür. Belirtilen çizim stili **çizin** de nonmasked görüntünün görünümünü üzerinde hiçbir etkisi yoktur.  
  
 Draw üye işlevi, başka bir işlev yanı sıra [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect), görüntü işleme yeteneği genişletir. `DrawIndirect` bir parametre olarak alır bir [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) yapısı. Bu yapı, tarama işlemi (KIRPMA) kodları kullanımı dahil olmak üzere geçerli görüntü işleme özelleştirmek için kullanılabilir. KIRPMA kodları hakkında daha fazla bilgi için bkz: [tarama işlemi kodları](http://msdn.microsoft.com/library/windows/desktop/dd162892) ve [Fırçalar eşlemleri](http://msdn.microsoft.com/library/windows/desktop/dd183378) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cımagelist kullanma](../mfc/using-cimagelist.md)   
 [Denetimler](../mfc/controls-mfc.md)

