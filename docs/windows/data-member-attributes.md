---
title: Veri üyesi öznitelikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- data members [C++], attributes
- data members [C++]
ms.assetid: 95b2397d-1daf-4ae4-8cd0-06956d005b13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9fc5bfb34e2df0fad363e499cc5a7277d15d14d1
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318856"
---
# <a name="data-member-attributes"></a>Veri Üyesi Öznitelikleri

Veri üyeleri sınıf, coclass'ı veya arabirimi aşağıdaki özniteliklere uygulanır.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[db_accessor](../windows/db-accessor.md)|Grupları `db_column` katılmak öznitelikleri `IAccessor`-bağlama dayalı.|
|[db_column](../windows/db-column.md)|Belirtilen sütun, satır kümesine bağlar.|
|[db_command](../windows/db-command.md)|OLE DB komut oluşturur.|
|[db_param](../windows/db-param.md)|Belirtilen üye bağımsız değişkenine bir giriş veya çıkış parametresi ile ilişkilendirir ve değişken sınırlandırır.|
|[db_source](../windows/db-source.md)|Bir veri kaynağı için bir bağlantı oluşturur.|
|[db_table](../windows/db-table.md)|Bir OLE DB tablosu açılır.|
|[defaultbind](../windows/defaultbind.md)|En iyi nesneyi temsil eden tek ve bağlanabilir özelliği belirtir.|
|[displaybind](../windows/displaybind.md)|Kullanıcıya bağlanabilir olarak görüntülenmesi gereken özelliği belirtir.|
|[id](../windows/id.md)|DISPID bir üye işlevinin (bir özelliği ya da bir yöntemde, arabirim veya dispinterface) belirtir.|
|[Aralığı](../windows/range-cpp.md)|Bağımsız değişkenler veya değerleri çalışma zamanında ayarlanır alanlar için izin verilen değer aralığı belirtir.|
|[rdx](../windows/rdx.md)|Bir kayıt defteri anahtarı oluşturur veya mevcut bir kayıt defteri anahtarı değiştirir.|
|[readonly](../windows/readonly-cpp.md)|Bir veri üyesine atama yasaklar.|
|[requestedit](../windows/requestedit.md)|Özelliğin desteklediğini belirtir `OnRequestEdit` bildirim.|

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıma Göre Öznitelikler](../windows/attributes-by-usage.md)