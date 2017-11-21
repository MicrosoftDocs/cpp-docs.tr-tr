---
title: "Ağaç denetim öğesi seçimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fac551ed757cf0510f0a8b61522bc969c6b6be6d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="tree-control-item-selection"></a>Ağaç Denetim Öğesi Seçimi
Seçim değiştiğinde bir öğeden diğerine ağaç denetimi ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) gönderir [TVN_SELCHANGING](http://msdn.microsoft.com/library/windows/desktop/bb773547) ve [TVN_SELCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb773544) bildirim iletileri. Her iki bildirim değişikliği fare tıklatma veya bir tuş vuruşu sonucu olup olmadığını belirten bir değer içerir. Bildirimler ayrıca seçimi sağlamasını öğe ve seçim kaybetme öğe hakkındaki bilgileri içerir. Öğe seçimi durumunu bağımlı öğesi özniteliklerini ayarlamak için bu bilgileri kullanın. Döndürme **TRUE** yanıt olarak **TVN_SELCHANGING** döndürme değiştirme; seçimden engeller **FALSE** değişiklik sağlar.  
  
 Bir uygulama çağırarak seçimi değiştirebilirsiniz [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

