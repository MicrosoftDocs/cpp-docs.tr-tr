---
title: Animasyon denetimi kullanma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d06770c13a3150bc291baa296aec225b9ab28e5a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-an-animation-control"></a>Animasyon Denetimi Kullanma
Animasyon denetimi tipik kullanımını deseni izler:  
  
-   Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilirse, iletişim kutusu oluşturulurken oluşturma otomatik olarak yapılır. (Olması bir [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) üye iletişim sınıfınızda animasyon denetimi karşılık gelir.) Alternatif olarak, kullanabileceğiniz [oluşturma](../mfc/reference/canimatectrl-class.md#create) denetimi penceresi alt pencere olarak oluşturmak için üye işlevi.  
  
-   Çağırarak animasyon denetime AVI küçük yük [açık](../mfc/reference/canimatectrl-class.md#open) üye işlevi. Animasyon denetimi iletişim kutusunda, bunu yapmak için uygun bir yerdir iletişim sınıfının ise [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlevi.  
  
-   Küçük çağırarak yürütmek [Yürüt](../mfc/reference/canimatectrl-class.md#play) üye işlevi. Animasyon denetimi iletişim kutusunda, bunu yapmak için uygun bir yerdir iletişim sınıfının ise **OnInitDialog** işlevi. Çağırma **Yürüt** animasyon denetimi varsa gerekli değil `ACS_AUTOPLAY` stil kümesi.  
  
-   Küçük bölümlerini görüntülemek veya kare kare kullanım oynatmak istiyorsanız `Seek` üye işlevi. Yürütülen bir küçük durdurmak için kullanma `Stop` üye işlevi.  
  
-   Denetim hemen yok etmek için yapmayacağınız, küçük bellekten çağırarak kaldırmak **Kapat** üye işlevi.  
  
-   Animasyon denetimi iletişim kutusunda, varsa onu ve `CAnimateCtrl` nesne yok otomatik olarak. Her iki denetimi emin olmak ihtiyacınız olmayan, varsa ve `CAnimateCtrl` nesne düzgün yok. Otomatik olarak denetimini yok etme AVI küçük kapatır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAnimateCtrl kullanma](../mfc/using-canimatectrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

