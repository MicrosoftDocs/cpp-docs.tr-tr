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
ms.openlocfilehash: fd6632a44dd4806b8f13683b50cad76b5eebe27a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212587"
---
# <a name="tree-control-item-selection"></a>Ağaç Denetim Öğesi Seçimi
Seçimi değiştiğinde bir öğeden diğerine, bir ağaç denetimi ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) gönderir [TVN_SELCHANGING](/windows/desktop/Controls/tvn-selchanging) ve [TVN_SELCHANGED](/windows/desktop/Controls/tvn-selchanged) bildirim iletileri. Her iki bildirim değişiklik fare tıklatın veya tuş vuruşu sonucu olup olmadığını belirten bir değer içerir. Bildirimler, ayrıca seçimi sağlamasını öğesi ve seçim kaybetme öğesi hakkında bilgiler içerir. Öğe seçimi durumuna bağımlı öğesi öznitelikleri ayarlamak için bu bilgileri kullanabilirsiniz. Döndüren **TRUE** yanıt olarak `TVN_SELCHANGING` döndüren değiştirmesini; seçimi engeller **FALSE** değişiklik sağlar.  
  
 Uygulama seçimi çağırarak değiştirebilirsiniz [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

