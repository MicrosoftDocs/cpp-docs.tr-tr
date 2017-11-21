---
title: "Geri çağrı öğeleri ve geri çağrı maskesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f2d286bcc9e5119e373af6ae2e02d7e39190dc3a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="callback-items-and-the-callback-mask"></a>Geri Çağrı Öğeleri ve Geri Çağrı Maskesi
Her öğelerinden biri için bir liste görünümü denetimi genellikle etiket metnini, öğenin simgelerin görüntü listesi dizini depolar ve bit kümesi için öğesi'nin durumu bayrakları. Uygulama zaten bir öğe için bilgilerin bazıları depoluyorsa yararlı geri çağrı öğeleri olarak ayrı öğeleri tanımlayabilirsiniz.  
  
 Bir öğe için uygun değerleri belirterek bir geri çağırma öğesi olarak tanımlamak `pszText` ve `iImage` üyeleri **LV_ITEM** yapısı (bkz [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem)). Uygulama öğenin veya alt'ın metin koruyorsa, belirtin **LPSTR_TEXTCALLBACK** değerini `pszText` üyesi. Uygulama öğenin simgesini izler belirtebilmeniz **I_IMAGECALLBACK** değerini `iImage` üyesi.  
  
 Geri çağrı öğeleri tanımlamanın yanı sıra, denetimin geri çağrı maskesi de değiştirebilirsiniz. Bir dizi denetim yerine uygulama geçerli verileri depoladığı öğesi durumları belirtin bit bayrakları maskesidir. Geri çağrı maskesi, belirli bir öğeye uygular geri çağırma öğesi ataması aksine denetimin öğelerin tümünü uygular. Geri çağrı maskesi denetimi tüm öğesi durumları izler anlamı varsayılan sıfırdır. Bu varsayılan davranışı değiştirmek için aşağıdaki değerlerden herhangi bir bileşimini maskeye başlatın:  
  
-   `LVIS_CUT`Öğe kesme ve yapıştırma işlemi için işaretlenir.  
  
-   `LVIS_DROPHILITED`Öğe bir Sürükle ve bırak hedefi olarak vurgulanır.  
  
-   `LVIS_FOCUSED`Öğenin odağa sahip.  
  
-   `LVIS_SELECTED`Öğe seçilir.  
  
-   **LVIS_OVERLAYMASK** geçerli katmana görüntünün her öğe için resim listesi dizinini uygulamayı depolar.  
  
-   **LVIS_STATEIMAGEMASK** uygulamayı şu anki durumu görüntü her öğe için resim listesi dizinini depolar.  
  
 Bu maskesi ayarlama ve alma hakkında daha fazla bilgi için bkz: [CListCtrl::GetCallbackMask](../mfc/reference/clistctrl-class.md#getcallbackmask) ve [CListCtrl::SetCallbackMask](../mfc/reference/clistctrl-class.md#setcallbackmask).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

