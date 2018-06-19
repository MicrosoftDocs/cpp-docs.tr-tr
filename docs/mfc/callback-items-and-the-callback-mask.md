---
title: Geri çağrı öğeleri ve geri çağrı maskesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95c896308970ffc6a2040657927dc127eee278ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342780"
---
# <a name="callback-items-and-the-callback-mask"></a>Geri Çağrı Öğeleri ve Geri Çağrı Maskesi
Her öğelerinden biri için bir liste görünümü denetimi genellikle etiket metnini, öğenin simgelerin görüntü listesi dizini depolar ve bit kümesi için öğesi'nin durumu bayrakları. Uygulama zaten bir öğe için bilgilerin bazıları depoluyorsa yararlı geri çağrı öğeleri olarak ayrı öğeleri tanımlayabilirsiniz.  
  
 Bir öğe için uygun değerleri belirterek bir geri çağırma öğesi olarak tanımlamak `pszText` ve `iImage` üyeleri **LV_ITEM** yapısı (bkz [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem)). Uygulama öğenin veya alt'ın metin koruyorsa, belirtin **LPSTR_TEXTCALLBACK** değerini `pszText` üyesi. Uygulama öğenin simgesini izler belirtebilmeniz **I_IMAGECALLBACK** değerini `iImage` üyesi.  
  
 Geri çağrı öğeleri tanımlamanın yanı sıra, denetimin geri çağrı maskesi de değiştirebilirsiniz. Bir dizi denetim yerine uygulama geçerli verileri depoladığı öğesi durumları belirtin bit bayrakları maskesidir. Geri çağrı maskesi, belirli bir öğeye uygular geri çağırma öğesi ataması aksine denetimin öğelerin tümünü uygular. Geri çağrı maskesi denetimi tüm öğesi durumları izler anlamı varsayılan sıfırdır. Bu varsayılan davranışı değiştirmek için aşağıdaki değerlerden herhangi bir bileşimini maskeye başlatın:  
  
-   `LVIS_CUT` Öğe kesme ve yapıştırma işlemi için işaretlenir.  
  
-   `LVIS_DROPHILITED` Öğe bir Sürükle ve bırak hedefi olarak vurgulanır.  
  
-   `LVIS_FOCUSED` Öğenin odağa sahip.  
  
-   `LVIS_SELECTED` Öğe seçilir.  
  
-   **LVIS_OVERLAYMASK** geçerli katmana görüntünün her öğe için resim listesi dizinini uygulamayı depolar.  
  
-   **LVIS_STATEIMAGEMASK** uygulamayı şu anki durumu görüntü her öğe için resim listesi dizinini depolar.  
  
 Bu maskesi ayarlama ve alma hakkında daha fazla bilgi için bkz: [CListCtrl::GetCallbackMask](../mfc/reference/clistctrl-class.md#getcallbackmask) ve [CListCtrl::SetCallbackMask](../mfc/reference/clistctrl-class.md#setcallbackmask).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

