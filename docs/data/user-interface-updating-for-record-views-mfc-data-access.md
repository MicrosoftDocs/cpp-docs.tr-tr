---
title: Kayıt görünümleri (MFC veri erişimi) için kullanıcı arabirimi güncelleştiriliyor
ms.date: 11/04/2016
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
ms.openlocfilehash: 914a262560a10ba4085e0605a0c9f677d7a447fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630405"
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>Kayıt görünümleri (MFC veri erişimi) için kullanıcı arabirimi güncelleştiriliyor

`CRecordView` Varsayılan kullanıcı arabirimini güncelleştirme işleyicileri için Gezinti komutlarını sağlar. Etkinleştirme ve devre dışı kullanıcı arabirimi nesneleri bu işleyicileri otomatik hale getirin; menü öğeleri ve araç çubuğu düğmeleri. Uygulama Sihirbazı'nı Standart menüler sağlar ve seçerseniz **yerleştirilebilir araç** seçeneği, bir dizi komutlar için araç çubuğu düğmesi. Kayıt görünümü sınıfını kullanarak oluşturmak istiyorsanız `CRecordView`, uygulamanıza benzer kullanıcı arabirimi nesneleri eklemek isteyebilirsiniz.

### <a name="to-create-menu-resources-with-the-menu-editor"></a>Düzenleyici menü menü kaynakları oluşturmak için

1. Kullanma hakkında bilgi için söz konusu [Menü Düzenleyici](../windows/menu-editor.md), kendi menü ile aynı dört komutlar oluşturur.

#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>Araç çubuğu düğmeleri grafik düzenleyici oluşturmak için

1. Kullanma hakkında bilgi için söz konusu [araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md), araç çubuğu düğmeleri için kayıt gezinti komutlarınızı eklemek için araç çubuğu kaynağı düzenleyemez.

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt Görünümünde Gezintiyi Destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)<br/>
[Kayıt görünümünü kullanma](../data/using-a-record-view-mfc-data-access.md)