---
title: "OLE DB kayıt görünümlerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB record views
- COleDBRecordView class, overview
- rowsets, record views
- record views, record view objects
- OLE DB, record views
- MFC, record views
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 03e88eaafa82e346c720810bf567d867a9cd6096
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-ole-db-record-views"></a>OLE DB Kayıt Görünümlerini Kullanma
Bir MFC uygulamasında OLE DB satır kümesi veri görüntülemek istiyorsanız, MFC sınıfını kullanmalısınız [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md). Kayıt görünümü nesne oluşturulduğu `COleDBRecordView` MFC denetimleri veritabanı kayıtlarını görüntülemenizi sağlar. Kayıt görünümü oluşturulan bir OLE DB satır kümesi nesnesi doğrudan bağlı bir iletişim formu görünümdür `CRowset` Şablon sınıfı. Satır kümesi nesnesi için bir tanıtıcı edinmek basittir:  
  
```  
COleDBRecordView myRecordView;  
...  
// CProductAccessor is a user record class  
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();  
```  
  
 Görünüm alanlarını görüntüler `CRowset` iletişim kutusu denetimleri nesne. `COleDBRecordView` Nesne iletişim kutusu veri değişimi (DDX) kullanır ve gezinme işlevini yerleşik `CRowset` (**MoveFirst**, `MoveNext`, `MovePrev`, ve `MoveLast`) veri hareketini otomatik hale getirmek için form ve satır kümesi alanları denetimleri arasında. `COleDBRecordView`kullanıcının konumunu satır kümesindeki kayıt görünümü kullanıcı arabirimi ve kaynakları güncelleştirebilmeniz için izler bir [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove) diğerine geçmeden önce geçerli kaydı güncelleştirmek için yöntem.  
  
 DDX işlevleri ile kullanabileceğiniz **COleDbRecordView** veritabanı kayıt kümesinden doğrudan veri almak ve bir iletişim kutusu denetiminde görüntülemek için. Kullanmanız gereken **COleDBRecordView\***  yöntemleri (gibi `DDX_Text`) değil **DDX_Field\***  işlevleri (gibi `DDX_FieldText`) ile **COleDbRecordView** .  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri kullanma](../../data/oledb/using-accessors.md)   
 [COleDBRecordView Sınıfı](../../mfc/reference/coledbrecordview-class.md)