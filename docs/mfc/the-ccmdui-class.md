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
ms.openlocfilehash: a857d1cddcc78c7cfff4243b9c99194986af3d9b
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956492"
---
# <a name="the-ccmdui-class"></a>CCmdUI Sınıfı
Kendi işleyicisi için bir güncelleştirme komutu yönlendirirken framework işleyici için bir işaretçi geçirir. bir `CCmdUI` nesne (veya bir nesne için bir `CCmdUI`-türetilmiş sınıf). Bu nesne menü öğesi veya araç çubuğu düğmesini veya komutu oluşturulan başka bir kullanıcı arabirimi nesneyi temsil eder. Güncelleştirme işleyici üye işlevlerini çağırır `CCmdUI` kullanıcı arabirimi nesneyi güncelleştirmek için işaretçiyi aracılığıyla yapısı. Örneğin, bir güncelleştirme işleyici Tümünü Temizle menü öğesi için şöyledir:  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]  
  
 Bu işleyici çağırması `Enable` üye işlevini menü öğesine erişimi olan bir nesne. `Enable` öğe kullanılabilir hale getirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme](../mfc/how-to-update-user-interface-objects.md)

