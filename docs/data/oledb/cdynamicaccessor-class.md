---
title: "CDynamicAccessor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDynamicAccessor
- ATL::CDynamicAccessor
- CDynamicAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicAccessor class
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1f07ceae02c9c243f59f37ea49e77ef3113b5a54
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessor-class"></a>CDynamicAccessor Sınıfı
Veritabanı şeması (veritabanının temel yapısı) olanağıyla varsa, bir veri kaynağına erişim sağlar.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CDynamicAccessor : public CAccessorBase  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cdynamicaccessor-addbindentry.md)|Bir BIND girişi varsayılan erişimciyi geçersiz kılma için çıktı sütunları ekler.|  
|[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)|Oluşturur ve başlatır `CDynamicAccessor` nesnesi.|  
|[Kapat](../../data/oledb/cdynamicaccessor-close.md)|Tüm sütunları bağlantısını keser, ayrılan belleği serbest bırakır ve serbest [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) sınıfında arabirim işaretçisi.|  
|[GetBookmark](../../data/oledb/cdynamicaccessor-getbookmark.md)|Geçerli satır için yer alır.|  
|[GetBlobHandling](../../data/oledb/cdynamicaccessor-getblobhandling.md)|Geçerli satır değeri işleme BLOB alır.|  
|[GetBlobSizeLimit](../../data/oledb/cdynamicaccessor-getblobsizelimit.md)|Bayt cinsinden en büyük BLOB boyutu alır.|  
|[GetColumnCount](../../data/oledb/cdynamicaccessor-getcolumncount.md)|Satır kümesindeki sütunların sayısını alır.|  
|[GetColumnFlags](../../data/oledb/cdynamicaccessor-getcolumnflags.md)|Sütun özelliklerini alır.|  
|[GetColumnInfo](../../data/oledb/cdynamicaccessor-getcolumninfo.md)|Sütun meta verileri alır.|  
|[GetColumnName](../../data/oledb/cdynamicaccessor-getcolumnname.md)|Belirtilen sütunun adını alır.|  
|[GetColumnType](../../data/oledb/cdynamicaccessor-getcolumntype.md)|Belirtilen sütunun veri türünü alır.|  
|[GetLength](../../data/oledb/cdynamicaccessor-getlength.md)|Olası bir sütun bayt cinsinden uzunluğu en fazla alır.|  
|[GetOrdinal](../../data/oledb/cdynamicaccessor-getordinal.md)|Bir sütun adı verilen sütun dizini alır.|  
|[GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)|Belirtilen sütun durumunu alır.|  
|[GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)|Verileri arabelleğinden alır.|  
|[SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)|Geçerli satır değeri işleme BLOB ayarlar.|  
|[SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)|KABARCIK boyutunu bayt cinsinden ayarlar.|  
|[SetLength](../../data/oledb/cdynamicaccessor-setlength.md)|Sütun uzunluğu bayt cinsinden ayarlar.|  
|[SetStatus](../../data/oledb/cdynamicaccessor-setstatus.md)|Belirtilen sütun durumunu ayarlar.|  
|[SetValue](../../data/oledb/cdynamicaccessor-setvalue.md)|Arabellek verileri depolar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `CDynamicAccessor` sütun adlarının, sütun sayısı, veri türü vb. gibi sütun bilgileri almak için yöntemleri. Erişimci çalışma zamanında dinamik olarak oluşturmak için bu sütun bilgileri kullanın.  
  
 Sütun bilgileri oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Arabellek kullanımından verileri elde [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md).  
  
 Bir tartışma ve dinamik erişimciyi sınıfları kullanma örnekleri için bkz: [Dinamik Erişimcileri Kullanma](../../data/oledb/using-dynamic-accessors.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor sınıfı](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor Sınıfı](../../data/oledb/cmanualaccessor-class.md)