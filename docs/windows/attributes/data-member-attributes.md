---
title: Veri üyesi öznitelikleri (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- data members [C++], attributes
- data members [C++]
ms.assetid: 95b2397d-1daf-4ae4-8cd0-06956d005b13
ms.openlocfilehash: ad21ed16eee8cd14e8f798450ff385d5f429a280
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041156"
---
# <a name="data-member-attributes"></a>Veri Üyesi Öznitelikleri

Veri üyeleri sınıf, coclass'ı veya arabirimi aşağıdaki özniteliklere uygulanır.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[db_accessor](db-accessor.md)|Grupları `db_column` katılmak öznitelikleri `IAccessor`-bağlama dayalı.|
|[db_column](db-column.md)|Belirtilen sütun, satır kümesine bağlar.|
|[db_command](db-command.md)|OLE DB komut oluşturur.|
|[db_param](db-param.md)|Belirtilen üye bağımsız değişkenine bir giriş veya çıkış parametresi ile ilişkilendirir ve değişken sınırlandırır.|
|[db_source](db-source.md)|Bir veri kaynağı için bir bağlantı oluşturur.|
|[db_table](db-table.md)|Bir OLE DB tablosu açılır.|
|[defaultbind](defaultbind.md)|En iyi nesneyi temsil eden tek ve bağlanabilir özelliği belirtir.|
|[displaybind](displaybind.md)|Kullanıcıya bağlanabilir olarak görüntülenmesi gereken özelliği belirtir.|
|[id](id.md)|DISPID bir üye işlevinin (bir özelliği ya da bir yöntemde, arabirim veya dispinterface) belirtir.|
|[range](range-cpp.md)|Bağımsız değişkenler veya değerleri çalışma zamanında ayarlanır alanlar için izin verilen değer aralığı belirtir.|
|[rdx](rdx.md)|Bir kayıt defteri anahtarı oluşturur veya mevcut bir kayıt defteri anahtarı değiştirir.|
|[readonly](readonly-cpp.md)|Bir veri üyesine atama yasaklar.|
|[requestedit](requestedit.md)|Özelliğin desteklediğini belirtir `OnRequestEdit` bildirim.|

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıma Göre Öznitelikler](attributes-by-usage.md)