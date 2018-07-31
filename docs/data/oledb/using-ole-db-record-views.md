---
title: OLE DB kayıt görünümlerini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB record views
- COleDBRecordView class, overview
- rowsets, record views
- record views, record view objects
- OLE DB, record views
- MFC, record views
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d98b2f95c9b06d748b7486955b03f34f41e9ab57
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339519"
---
# <a name="using-ole-db-record-views"></a>OLE DB Kayıt Görünümlerini Kullanma
OLE DB satır kümesi veri bir MFC uygulamasında görüntülemek istiyorsanız, MFC sınıfı kullanmalısınız [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md). Kayıt görünümü nesne oluşturulduğu `COleDBRecordView` MFC denetimlerde veritabanı kayıtlarını görüntülemenizi sağlar. Kayıt görünümü oluşturulan bir OLE DB satır kümesi nesnesi doğrudan bağlı bir iletişim formu görünümüdür `CRowset` Şablon sınıfı. Satır kümesi nesnesi için bir tanıtıcı elde basittir:  
  
```cpp  
COleDBRecordView myRecordView;  
...  
// CProductAccessor is a user record class  
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();  
```  
  
 Görünüm alanlarını görüntüler `CRowset` iletişim kutusunun denetimleri nesnesi. `COleDBRecordView` Nesne iletişim kutusu veri değişimi (DDX) kullanır ve gezinti işlevselliğini yerleşik `CRowset` (`MoveFirst`, `MoveNext`, `MovePrev`, ve `MoveLast`) form üzerinde denetimleri arasında veri taşıma işlemlerini otomatik hale getirmek için ve alanları kümesi. `COleDBRecordView` kullanıcının konumunu satır kümesindeki kayıt görünümü kullanıcı arabirimi ve kaynakları güncelleştirebilmeniz adına izler bir [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove) diğerine geçmeden önce geçerli kaydı güncelleştirmek için yöntemi.  
  
 DDX işlevleri ile kullanabileceğiniz `COleDbRecordView` doğrudan veritabanı kayıt kümesinden veri almak ve bir iletişim kutusu denetiminde görüntüleme. Kullanmanız gereken **DDX_\***  yöntemleri (gibi `DDX_Text`) değil **DDX_Field\***  işlevleri (gibi `DDX_FieldText`) ile `COleDbRecordView`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri kullanma](../../data/oledb/using-accessors.md)   
 [COleDBRecordView Sınıfı](../../mfc/reference/coledbrecordview-class.md)