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
ms.openlocfilehash: 5722a2ef8c4e93e4996ee243b3c01b6dd6aeca78
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381611"
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

