---
description: 'Hakkında daha fazla bilgi edinin: kayıt görünümleri için User-Interface güncelleştirme (MFC veri erişimi)'
title: Kayıt görünümleri için User-Interface Güncelleştirmesi (MFC veri erişimi)
ms.date: 11/04/2016
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
ms.openlocfilehash: 3a199faa3e606260257ece0fff9a7d1de3095d18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116450"
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>Kayıt görünümleri için User-Interface Güncelleştirmesi (MFC veri erişimi)

`CRecordView` , Gezinti komutları için varsayılan kullanıcı arabirimi güncelleştirme işleyicileri sağlar. Bu işleyiciler Kullanıcı arabirimi nesnelerinin (menü öğeleri ve araç çubuğu düğmeleri) etkinleştirilmesini ve devre dışı bırakılmasını otomatik hale getirir. Uygulama Sihirbazı Standart menüler sağlar ve komutlar için bir araç çubuğu düğmesi olan **dockable araç çubuğu** seçeneğini belirlerseniz. Kullanarak bir kayıt görünümü sınıfı oluşturursanız `CRecordView` , uygulamanıza benzer kullanıcı arabirimi nesneleri eklemek isteyebilirsiniz.

### <a name="to-create-menu-resources-with-the-menu-editor"></a>Menü Düzenleyicisi ile menü kaynakları oluşturmak için

1. [Menü düzenleyicisini](../windows/menu-editor.md)kullanma hakkındaki bilgilere başvurarak, aynı dört komuta sahip kendi menüsünü oluşturun.

#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>Grafik Düzenleyicisi ile araç çubuğu düğmeleri oluşturmak için

1. [Araç çubuğu düzenleyicisini](../windows/toolbar-editor.md)kullanma hakkındaki bilgilere başvurarak, kayıt gezinti komutlarınız için araç çubuğu düğmelerini eklemek üzere araç çubuğu kaynağını düzenleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Bir kayıt görünümünde Gezintiyi Destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)<br/>
[Kayıt görünümü kullanma](../data/using-a-record-view-mfc-data-access.md)
