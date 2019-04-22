---
title: Kayıt görünümleri (MFC veri erişimi) için kullanıcı arabirimi güncelleştiriliyor
ms.date: 11/04/2016
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
ms.openlocfilehash: de94b28e713459edfd63aff832caecc7ea49ca33
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023366"
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>Kayıt görünümleri (MFC veri erişimi) için kullanıcı arabirimi güncelleştiriliyor

`CRecordView` Varsayılan kullanıcı arabirimini güncelleştirme işleyicileri için Gezinti komutlarını sağlar. Etkinleştirme ve devre dışı kullanıcı arabirimi nesneleri bu işleyicileri otomatik hale getirin; menü öğeleri ve araç çubuğu düğmeleri. Uygulama Sihirbazı'nı Standart menüler sağlar ve seçerseniz **yerleştirilebilir araç** seçeneği, bir dizi komutlar için araç çubuğu düğmesi. Kayıt görünümü sınıfını kullanarak oluşturmak istiyorsanız `CRecordView`, uygulamanıza benzer kullanıcı arabirimi nesneleri eklemek isteyebilirsiniz.

### <a name="to-create-menu-resources-with-the-menu-editor"></a>Düzenleyici menü menü kaynakları oluşturmak için

1. Kullanma hakkında bilgi için söz konusu [Menü Düzenleyici](../windows/menu-editor.md), kendi menü ile aynı dört komutlar oluşturur.

#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>Araç çubuğu düğmeleri grafik düzenleyici oluşturmak için

1. Kullanma hakkında bilgi için söz konusu [araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md), araç çubuğu düğmeleri için kayıt gezinti komutlarınızı eklemek için araç çubuğu kaynağı düzenleyemez.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Görünümünde Gezintiyi Destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)<br/>
[Kayıt görünümünü kullanma](../data/using-a-record-view-mfc-data-access.md)