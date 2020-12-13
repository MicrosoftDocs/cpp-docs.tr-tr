---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: User-Interface nesneleri güncelleştirme'
title: 'Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme'
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
ms.openlocfilehash: 32d7c033d03ba679fa295237c1c49c5060c731ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330173"
---
# <a name="how-to-update-user-interface-objects"></a>Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme

Genellikle, menü öğeleri ve araç çubuğu düğmelerinin birden fazla durumu vardır. Örneğin, bir menü öğesi, var olan bağlamda kullanılamaz durumdaysa gri (soluk) olur. Menü öğeleri de denetlenebilir veya işaretlenmemiş olabilir. Bir araç çubuğu düğmesi kullanılamaz durumdaysa da devre dışı bırakılabilir veya denetlenebilirler.

Bu öğelerin durumunu program koşulları olarak değiştiren bir menü öğesi, bir belge tarafından işlenen bir komut oluşturursa, belgenin menü öğesini güncelleştirmesini sağlamak mantıklı olur. Belge muhtemelen güncelleştirmenin temel aldığı bilgileri içerir.

Bir komutta birden çok kullanıcı arabirimi nesnesi varsa (Belki de bir menü öğesi ve bir araç çubuğu düğmesi), her ikisi de aynı işleyici işlevine yönlendirilir. Bu, tüm eşdeğer kullanıcı arabirimi nesneleri için Kullanıcı arabirimi güncelleştirme kodunuzu tek bir yerde kapsüller.

Framework, Kullanıcı arabirimi nesnelerini otomatik olarak güncelleştirmek için uygun bir arabirim sağlar. Güncelleştirmeyi başka bir şekilde yapabilirsiniz, ancak sunulan arabirim verimli ve kullanımı kolay bir işlemdir.

Aşağıdaki konularda güncelleştirme işleyicilerinin kullanımı açıklanmaktadır:

- [Güncelleştirme işleyicilerini çağırma zamanı](when-update-handlers-are-called.md)

- [ON_UPDATE_COMMAND_UI makrosu](on-update-command-ui-macro.md)

- [CCmdUI sınıfı](the-ccmdui-class.md)

## <a name="see-also"></a>Ayrıca bkz.

[Menüler](menus-mfc.md)
