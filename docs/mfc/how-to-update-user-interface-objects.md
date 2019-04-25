---
title: 'Nasıl yapılır: Kullanıcı arabirimi nesnelerini güncelleştirme'
ms.date: 11/04/2016
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
ms.openlocfilehash: 0dee9bb48c11cf061af60ebaf9a80c0123d339be
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160282"
---
# <a name="how-to-update-user-interface-objects"></a>Nasıl yapılır: Kullanıcı arabirimi nesnelerini güncelleştirme

Genellikle, menü öğeleri ve araç çubuğu düğmeleri birden fazla durum sahiptir. Örneğin, mevcut bağlamda kullanılamaz durumdaysa bir menü öğesi (gri) renkte gösterilir. Menü öğeleri de işaretli veya işaretsiz olabilir. Araç çubuğu düğmesi de mümkün değilse devre dışı bırakılabilir veya iade.

Kimin bir menü öğesi tarafından işlenen komut oluşturursa koşullar oluşursa mantıksal olarak, programı bu öğeler, say, bir belge durumunu güncelleştirir, menü öğesi güncelleştirme belgeniz mantıklıdır. Belge, büyük olasılıkla, güncelleştirme temel bilgileri içerir.

Bir komutu birden çok kullanıcı arabirimi nesneleri (belki de bir menü öğesi ve araç çubuğu düğmesi) varsa, her ikisi de aynı işleyici işlevine yönlendirilir. Bu, tüm tek bir yerde eşdeğer kullanıcı arabirimi nesneleri için kullanıcı arabirimi güncelleştirme kodunuzu kapsüller.

Framework, otomatik olarak kullanıcı arabirimi nesnelerini güncelleştirme için kullanışlı bir arabirim sağlar. Başka bir şekilde güncelleştirme yapmak seçebilirsiniz, ancak sağlanan arabirim verimli ve kullanımı kolay.

Aşağıdaki konular, güncelleştirme işleyicileri kullanımını açıklar:

- [Güncelleştirme işleyicilerini çağırma](../mfc/when-update-handlers-are-called.md)

- [On_update_command_uı makrosu](../mfc/on-update-command-ui-macro.md)

- [Ccmduı sınıfı](../mfc/the-ccmdui-class.md)

## <a name="see-also"></a>Ayrıca bkz.

[Menüler](../mfc/menus-mfc.md)
