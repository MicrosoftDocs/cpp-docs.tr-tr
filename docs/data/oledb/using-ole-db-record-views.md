---
description: 'Hakkında daha fazla bilgi edinin: OLE DB kaydı Görünümlerini kullanma'
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
ms.openlocfilehash: 8230ba118038852f81159d21a51165b7448a26aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332458"
---
# <a name="using-ole-db-record-views"></a>OLE DB Kayıt Görünümlerini Kullanma

Bir MFC uygulamasında OLE DB satır kümesi verilerini göstermek istiyorsanız, bir MFC sınıfının [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)öğesini kullanın. Öğesinden oluşturulan bir kayıt görünümü nesnesi `COleDBRecordView` , MFC denetimlerinde veritabanı kayıtlarını görüntülemenize izin verir. Kayıt görünümü, şablon sınıfından oluşturulan OLE DB Rowset nesnesine doğrudan bağlı bir iletişim kutusu form görünümüdür `CRowset` . Satır kümesi nesnesine bir tanıtıcı alınması basittir:

```cpp
COleDBRecordView myRecordView;
...
// CProductAccessor is a user record class
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();
```

Görünüm `CRowset` iletişim kutusu denetimlerinde nesnesinin alanlarını görüntüler. `COleDBRecordView`Nesne, `CRowset` `MoveFirst` `MoveNext` `MovePrev` `MoveLast` form üzerindeki denetimler ve satır kümesinin alanları arasında veri hareketini otomatikleştirmek için iletişim kutusu veri değişimi (DDX) ve içinde yerleşik gezinme işlevlerini (,,, ve) kullanır. `COleDBRecordView` kayıt görünümünün Kullanıcı arabirimini güncelleştirebilmesi ve başka birine geçmeden önce geçerli kaydı güncelleştirmek için bir [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove) yöntemi temin edebilmesi için kullanıcının satır kümesindeki konumunu izler.

`COleDbRecordView`Doğrudan veritabanı kayıt kümesinden veri almak ve bir iletişim kutusu denetiminde göstermek için, Ile DDX işlevlerini kullanabilirsiniz.  <strong>\*</strong> `DDX_Text` İle **DDX_Field** işlevleri değil (gibi) ddx_ Yöntemleri (gibi) kullanın <strong>\*</strong> `DDX_FieldText` `COleDbRecordView` .

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri kullanma](../../data/oledb/using-accessors.md)<br/>
[COleDBRecordView sınıfı](../../mfc/reference/coledbrecordview-class.md)<br/>
