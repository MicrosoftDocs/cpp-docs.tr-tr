---
title: Ağaç denetim öğesi seçimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fb08fcbb1bd77cc80fdbe014d8c9e8a0851254d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-item-selection"></a>Ağaç Denetim Öğesi Seçimi
Seçim değiştiğinde bir öğeden diğerine ağaç denetimi ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) gönderir [TVN_SELCHANGING](http://msdn.microsoft.com/library/windows/desktop/bb773547) ve [TVN_SELCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb773544) bildirim iletileri. Her iki bildirim değişikliği fare tıklatma veya bir tuş vuruşu sonucu olup olmadığını belirten bir değer içerir. Bildirimler ayrıca seçimi sağlamasını öğe ve seçim kaybetme öğe hakkındaki bilgileri içerir. Öğe seçimi durumunu bağımlı öğesi özniteliklerini ayarlamak için bu bilgileri kullanın. Döndürme **TRUE** yanıt olarak **TVN_SELCHANGING** döndürme değiştirme; seçimden engeller **FALSE** değişiklik sağlar.  
  
 Bir uygulama çağırarak seçimi değiştirebilirsiniz [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

