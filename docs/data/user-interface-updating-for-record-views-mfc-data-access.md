---
title: Kayıt görünümleri için Kullanıcı arabirimi Güncelleştirmesi (MFC veri erişimi)
ms.date: 11/04/2016
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
ms.openlocfilehash: 9bfb907d21c928c605b304c595acb834d0046e35
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209059"
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>Kayıt görünümleri için Kullanıcı arabirimi Güncelleştirmesi (MFC veri erişimi)

`CRecordView`, Gezinti komutları için varsayılan kullanıcı arabirimi güncelleştirme işleyicileri sağlar. Bu işleyiciler Kullanıcı arabirimi nesnelerinin (menü öğeleri ve araç çubuğu düğmeleri) etkinleştirilmesini ve devre dışı bırakılmasını otomatik hale getirir. Uygulama Sihirbazı Standart menüler sağlar ve komutlar için bir araç çubuğu düğmesi olan **dockable araç çubuğu** seçeneğini belirlerseniz. `CRecordView`kullanarak bir kayıt görünümü sınıfı oluşturursanız, uygulamanıza benzer kullanıcı arabirimi nesneleri eklemek isteyebilirsiniz.

### <a name="to-create-menu-resources-with-the-menu-editor"></a>Menü Düzenleyicisi ile menü kaynakları oluşturmak için

1. [Menü düzenleyicisini](../windows/menu-editor.md)kullanma hakkındaki bilgilere başvurarak, aynı dört komuta sahip kendi menüsünü oluşturun.

#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>Grafik Düzenleyicisi ile araç çubuğu düğmeleri oluşturmak için

1. [Araç çubuğu düzenleyicisini](../windows/toolbar-editor.md)kullanma hakkındaki bilgilere başvurarak, kayıt gezinti komutlarınız için araç çubuğu düğmelerini eklemek üzere araç çubuğu kaynağını düzenleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Bir kayıt görünümünde Gezintiyi Destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)<br/>
[Kayıt görünümü kullanma](../data/using-a-record-view-mfc-data-access.md)
