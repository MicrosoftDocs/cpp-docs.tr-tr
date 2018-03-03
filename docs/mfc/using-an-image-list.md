---
title: "Görüntü listesi kullanma | Microsoft Docs"
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
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4321649bf4e8fe0e34fef8fe37b8c96598bef2c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-image-list"></a>Görüntü Listesi Kullanma
Görüntü listesi tipik kullanımını deseni izler:  
  
-   Oluşturmak bir [Cımagelist](../mfc/reference/cimagelist-class.md) nesne ve aşırı birini çağırın kendi [oluşturma](../mfc/reference/cimagelist-class.md#create) resim listesi oluşturmak ve ona eklemek için işlevi `CImageList` nesnesi.  
  
-   Resim listesi oluşturduğunuzda görüntüleri eklemezseniz, görüntüleri için resim listesi çağırarak ekleme [Ekle](../mfc/reference/cimagelist-class.md#add) veya [okuma](../mfc/reference/cimagelist-class.md#read) üye işlevi.  
  
-   Görüntü listesi denetimi uygun üye işlevini çağırarak bir denetimle ilişkilendirme veya görüntüleri görüntü listesinden görüntü listenin kullanarak kendiniz çizmek [çizin](../mfc/reference/cimagelist-class.md#draw) üye işlevi.  
  
-   Belki de sürükleme için görüntü listenin yerleşik destek kullanarak bir görüntü sürükleme izin verin.  
  
> [!NOTE]
>  Resim listesi ile oluşturulmuşsa, **yeni** işleci gerekir destroy `CImageList` nesnesi ile bittiğinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cımagelist kullanma](../mfc/using-cimagelist.md)   
 [Denetimler](../mfc/controls-mfc.md)

