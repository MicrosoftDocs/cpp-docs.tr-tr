---
title: "Liste Denetim stillerini değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6758cce9ab42c0dea490dd8ac9803588edceac5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="changing-list-control-styles"></a>Liste Denetim Stillerini Değiştirme
Liste denetimi penceresi stilini değiştirebilirsiniz ([CListCtrl](../mfc/reference/clistctrl-class.md)) oluşturduktan sonra dilediğiniz zaman. Pencere stili değiştirerek ekleyeceğini görünüm türünü değiştirin. Örneğin, Explorer benzetmek için menü öğeleri veya denetimleri farklı görünümleri arasında geçiş için araç çubuğu düğmeleri sağlayabilir: simge görünümü, liste görünümü ve benzeri.  
  
 Örneğin, bir çağrı yapmak kullanıcı menü öğesine seçtiğinde [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) denetimi geçerli stilini alır ve ardından çağırmak için [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) stili sıfırlanır. Daha fazla bilgi için bkz: [liste görünümü denetimleri kullanarak](http://msdn.microsoft.com/library/windows/desktop/bb774736) Windows SDK.  
  
 Kullanılabilir stiller içinde listelenen [oluşturma](../mfc/reference/clistctrl-class.md#create). Stilleri `LVS_ICON`, `LVS_SMALLICON`, `LVS_LIST`, ve `LVS_REPORT` dört liste denetim görünümleri belirleyin.  
  
## <a name="extended-styles"></a>Genişletilmiş stilleri  
 Liste denetimi için standart stiller yanı sıra Genişletilmiş Stil olarak başvurulan başka bir grubu yok. İçinde açıklanan bu stiller [Genişletilmiş liste görünümü stilleri](http://msdn.microsoft.com/library/windows/desktop/bb774732) Windows SDK'ın çeşitli liste denetiminiz davranışını özelleştiren kullanışlı özellikler sağlar. Belirli bir stil (örneğin, vurgulu seçimi) davranışını uygulamak için çağırmaya [CListCtrl::SetExtendedStyle](../mfc/reference/clistctrl-class.md#setextendedstyle), gerekli stili geçirme. Aşağıdaki örnek, işlev çağrısı gösterir:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]  
  
> [!NOTE]
>  Vurgulu seçimi çalışmak de ya da olmalıdır **LVS_EX_ONECLICKACTIVATE** veya **LVS_EX_TWOCLICKACTIVATE** açık.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

