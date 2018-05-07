---
title: İlerleme denetimi ayarları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26afdcb58a64f2d2042596349acc4496aa530468
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="settings-for-the-progress-control"></a>İlerleme Denetimi Ayarları
İlerleme denetimi için temel ayarları ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) aralık ve geçerli konumu. Aralığın işlem süresini temsil eder. Geçerli konumu, uygulamanızın işleminin tamamlanmasına yönelik yaptı ilerlemesini gösterir. Aralık veya konumu değişiklikleri kendisini yeniden çizmek ilerleme durumu denetimini neden.  
  
 Varsayılan olarak, aralığı ayarlamak için 0 - 100 ve ilk konum 0 olarak ayarlanmış. İlerleme denetimi için geçerli aralık ayarlarını almak için kullanmak [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) üye işlevi. Aralığını değiştirmek için kullanmak [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) üye işlevi.  
  
 Konumu ayarlamak için kullanın [SetPos](../mfc/reference/cprogressctrl-class.md#setpos). Yeni bir değer belirtmeden geçerli konumunu almak için kullanın [GetPos](../mfc/reference/cprogressctrl-class.md#getpos). Örneğin, yalnızca üzerinde geçerli işlem durumunu sorgulamak isteyebilirsiniz.  
  
 İlerleme denetimi geçerli konumunu adım için kullanmak [StepIt](../mfc/reference/cprogressctrl-class.md#stepit). Her adım miktarını ayarlamak için kullanın [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CProgressCtrl kullanma](../mfc/using-cprogressctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

