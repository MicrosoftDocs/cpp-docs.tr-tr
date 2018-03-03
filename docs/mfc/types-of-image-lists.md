---
title: "Görüntü listesi türleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84a2118978d5ebd722d4fe56cdeec2aa0f74a94e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="types-of-image-lists"></a>Görüntü Listesi Türleri
Görüntü listeleri iki tür vardır ([Cımagelist](../mfc/reference/cimagelist-class.md)): nonmasked ve maskelenmiş. "Nonmasked resim listesi" bir veya daha fazla görüntü içeren bir renk bit eşlem oluşur. "Maskelenmiş resim listesi" eşit boyutu iki bit eşlemler oluşur. Görüntüleri içeren bir renk bit eşlem ilk ve ikinci bir dizi maskelerini içeren tek renkli bir bit eşlem ise — her görüntüde ilk bit eşlem için bir tane.  
  
 Aşırı birini **oluşturma** üye işlevi resim listesi maskelenir olup olmadığını belirten bir bayrak alır. (Diğer aşırı yüklemeler maskelenmiş görüntü listeleri oluşturma.)  
  
 Nonmasked görüntü çizildiğinde, yalnızca hedef cihaz bağlamına kopyalanır; diğer bir deyişle, cihaz bağlamı varolan arka plan rengi çizilir. Maskelenmiş bir görüntü çizildiğinde BITS görüntünün hedef cihaz bağlamı arka plan rengini burada görünür bit eşlem saydam alanları genellikle oluşturan maske, BITS ile birleştirilir. Çeşitli çizim stilleri maskelenmiş bir resim çizerken belirtebilirsiniz. Örneğin, görüntünün seçili nesnenin belirtmek için Titrek belirtebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cımagelist kullanma](../mfc/using-cimagelist.md)   
 [Denetimler](../mfc/controls-mfc.md)

