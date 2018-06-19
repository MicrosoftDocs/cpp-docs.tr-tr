---
title: Ccmduı sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CCmdUI
dev_langs:
- C++
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dde8c31620f64e6201c59b7031c789caa16c4902
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379814"
---
# <a name="the-ccmdui-class"></a>CCmdUI Sınıfı
Kendi işleyicisi için bir güncelleştirme komutu yönlendirirken framework işleyici için bir işaretçi geçirir. bir `CCmdUI` nesne (veya bir nesne için bir `CCmdUI`-türetilmiş sınıf). Bu nesne menü öğesi veya araç çubuğu düğmesini veya komutu oluşturulan başka bir kullanıcı arabirimi nesneyi temsil eder. Güncelleştirme işleyici üye işlevlerini çağırır `CCmdUI` kullanıcı arabirimi nesneyi güncelleştirmek için işaretçiyi aracılığıyla yapısı. Örneğin, bir güncelleştirme işleyici Tümünü Temizle menü öğesi için şöyledir:  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]  
  
 Bu işleyici çağırması **etkinleştirmek** üye işlevini menü öğesine erişimi olan bir nesne. **Etkinleştirme** öğesi kullanılabilir hale getirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme](../mfc/how-to-update-user-interface-objects.md)

