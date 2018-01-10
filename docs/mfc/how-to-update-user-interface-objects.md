---
title: "Nasıl yapılır: kullanıcı arabirimi nesnelerini güncelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- user interface objects [MFC]
- update handlers [MFC]
- enabling UI elements [MFC]
- disabling menus [MFC]
- updating user-interface objects [MFC]
- disabling UI elements [MFC]
- commands [MFC], updating UI
- enabling menus [MFC]
ms.assetid: 82f09773-c978-427b-b321-05a6143b7369
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 91e6d13e840c29d3ea9600183fafd9260966a2f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-update-user-interface-objects"></a>Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme
Genellikle, menü öğeleri ve araç çubuğu düğmeleri birden fazla durum vardır. Örneğin, mevcut bağlamda kullanılamaz durumdaysa menü öğesi (soluk) renkte görüntülenir. Menü öğeleri de işaretli veya işaretsiz olabilir. Araç çubuğu düğmesi de mümkün değilse devre dışı bırakılabilir ya da kontrol.  
  
 Kimin menü öğesi tarafından işlenen komut oluşturursa koşullar değişiklik mantıksal olarak, program yazarken bu öğeler, say, bir belgenin durumunu güncelleştirir, belgenin menü öğesi güncelleştirme için mantıklıdır. Belge büyük olasılıkla güncelleştirme temel bilgileri içerir.  
  
 Bir komut birden çok kullanıcı arabirimi nesnelerini (belki de menü öğesi ve bir araç çubuğu düğmesi) varsa, her ikisi de aynı işleyici işlevi yönlendirilir. Tüm tek bir yerde eşdeğer kullanıcı arabirimi nesneleri için kullanıcı arabirimi güncelleştirme kodunuzu yalıtır.  
  
 Çerçeve, otomatik olarak kullanıcı arabirimi nesnelerini güncelleştirme için kullanışlı bir arabirim sağlar. Diğer herhangi bir yolla güncelleştirme yapmak seçebilirsiniz, ancak sağlanan verimli ve kullanımı kolay arabirimidir.  
  
 Aşağıdaki konularda, güncelleştirme işleyicileri kullanımını açıklanır:  
  
-   [Güncelleştirme işleyicilerini çağırma zamanı](../mfc/when-update-handlers-are-called.md)  
  
-   [On_update_command_uı makrosu](../mfc/on-update-command-ui-macro.md)  
  
-   [Ccmduı sınıfı](../mfc/the-ccmdui-class.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menüleri](../mfc/menus-mfc.md)

