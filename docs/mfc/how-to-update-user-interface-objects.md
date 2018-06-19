---
title: 'Nasıl yapılır: kullanıcı arabirimi nesnelerini güncelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 422be3d80614c526c7e634d22a0930458e4b4e26
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346213"
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
 [Menüler](../mfc/menus-mfc.md)

