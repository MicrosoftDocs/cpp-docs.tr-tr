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
ms.openlocfilehash: 8afe8f6f7594c2dff75125aa56a210505bf5301d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410596"
---
# <a name="how-to-update-user-interface-objects"></a>Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme

Genellikle, menü öğeleri ve araç çubuğu düğmeleri birden fazla durum sahiptir. Örneğin, mevcut bağlamda kullanılamaz durumdaysa bir menü öğesi (gri) renkte gösterilir. Menü öğeleri de işaretli veya işaretsiz olabilir. Araç çubuğu düğmesi de mümkün değilse devre dışı bırakılabilir veya iade.

Kimin bir menü öğesi tarafından işlenen komut oluşturursa koşullar oluşursa mantıksal olarak, programı bu öğeler, say, bir belge durumunu güncelleştirir, menü öğesi güncelleştirme belgeniz mantıklıdır. Belge, büyük olasılıkla, güncelleştirme temel bilgileri içerir.

Bir komutu birden çok kullanıcı arabirimi nesneleri (belki de bir menü öğesi ve araç çubuğu düğmesi) varsa, her ikisi de aynı işleyici işlevine yönlendirilir. Bu, tüm tek bir yerde eşdeğer kullanıcı arabirimi nesneleri için kullanıcı arabirimi güncelleştirme kodunuzu kapsüller.

Framework, otomatik olarak kullanıcı arabirimi nesnelerini güncelleştirme için kullanışlı bir arabirim sağlar. Başka bir şekilde güncelleştirme yapmak seçebilirsiniz, ancak sağlanan arabirim verimli ve kullanımı kolay.

Aşağıdaki konular, güncelleştirme işleyicileri kullanımını açıklar:

- [Güncelleştirme işleyicilerini çağırma](../mfc/when-update-handlers-are-called.md)

- [On_update_command_uı makrosu](../mfc/on-update-command-ui-macro.md)

- [Ccmduı sınıfı](../mfc/the-ccmdui-class.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Menüler](../mfc/menus-mfc.md)

