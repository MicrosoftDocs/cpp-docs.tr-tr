---
title: OLE DB Kayıt Görünümlerini Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB record views
- COleDBRecordView class, overview
- rowsets, record views
- record views, record view objects
- OLE DB, record views
- MFC, record views
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
ms.openlocfilehash: 631e78e1a397ec360b1f3b2d94d7340e96925e23
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582727"
---
# <a name="using-ole-db-record-views"></a>OLE DB Kayıt Görünümlerini Kullanma

OLE DB satır kümesi veri bir MFC uygulamasında görüntülemek istiyorsanız, MFC sınıfı kullanın [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md). Kayıt görünümü nesne oluşturulduğu `COleDBRecordView` MFC denetimlerde veritabanı kayıtlarını görüntülemenizi sağlar. Kayıt görünümü oluşturulan bir OLE DB satır kümesi nesnesi doğrudan bağlı bir iletişim formu görünümüdür `CRowset` Şablon sınıfı. Satır kümesi nesnesi için bir tanıtıcı almak basittir:

```cpp
COleDBRecordView myRecordView;
...
// CProductAccessor is a user record class
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();
```

Görünüm alanlarını görüntüler `CRowset` iletişim kutusunun denetimleri nesnesi. `COleDBRecordView` Nesne iletişim kutusu veri değişimi (DDX) kullanır ve gezinti işlevselliğini yerleşik `CRowset` (`MoveFirst`, `MoveNext`, `MovePrev`, ve `MoveLast`) form üzerinde denetimleri arasında veri taşıma işlemlerini otomatik hale getirmek için ve alanları kümesi. `COleDBRecordView` kullanıcının konumunu satır kümesindeki kayıt görünümü kullanıcı arabirimi ve kaynakları güncelleştirebilmeniz adına izler bir [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove) diğerine geçmeden önce geçerli kaydı güncelleştirmek için yöntemi.

DDX işlevleri ile kullanabileceğiniz `COleDbRecordView` doğrudan veritabanı kayıt kümesinden veri almak ve bir iletişim kutusu denetiminde görüntüleme. Kullanım **DDX_** <strong>\*</strong> yöntemleri (gibi `DDX_Text`) değil **DDX_Field** <strong>\*</strong> işlevleri () gibi `DDX_FieldText`) ile `COleDbRecordView`.

## <a name="see-also"></a>Ayrıca Bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)<br/>
[COleDBRecordView Sınıfı](../../mfc/reference/coledbrecordview-class.md)<br/>
