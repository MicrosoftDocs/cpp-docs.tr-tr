---
title: "Ccmduı sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CCmdUI
dev_langs: C++
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 76f5dd1fa4ebaaa3a8c53f9eb27d6c83efd81bfd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="the-ccmdui-class"></a>CCmdUI Sınıfı
Kendi işleyicisi için bir güncelleştirme komutu yönlendirirken framework işleyici için bir işaretçi geçirir. bir `CCmdUI` nesne (veya bir nesne için bir `CCmdUI`-türetilmiş sınıf). Bu nesne menü öğesi veya araç çubuğu düğmesini veya komutu oluşturulan başka bir kullanıcı arabirimi nesneyi temsil eder. Güncelleştirme işleyici üye işlevlerini çağırır `CCmdUI` kullanıcı arabirimi nesneyi güncelleştirmek için işaretçiyi aracılığıyla yapısı. Örneğin, bir güncelleştirme işleyici Tümünü Temizle menü öğesi için şöyledir:  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]  
  
 Bu işleyici çağırması **etkinleştirmek** üye işlevini menü öğesine erişimi olan bir nesne. **Etkinleştirme** öğesi kullanılabilir hale getirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: kullanıcı arabirimi nesnelerini güncelleştirme](../mfc/how-to-update-user-interface-objects.md)

