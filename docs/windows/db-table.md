---
title: db_table | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.db_table
dev_langs:
- C++
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37dd6fd80a0d18f1b9d93f5299fca797238a509f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dbtable"></a>db_table
OLE DB tablo açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ db_table(   
   db_table,   
   name,   
   source_name,   
   hresult   
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *db_table*  
 (Örneğin, "Ürünler") veritabanı tablosunun adını belirten dize.  
  
 *ad* (isteğe bağlı)  
 Tanıtıcı adını tablo ile birlikte çalışmak için kullanın. Birden fazla satır sonuçları döndürmek istiyorsanız bu parametreyi belirtmeniz gerekir. **db_table** belirtilen sahip bir değişken oluşturur *adı* satır çapraz geçiş yapamaz veya birden çok eylem sorguları yürütmek için kullanılabilir.  
  
 *source_name* (isteğe bağlı)  
 `CSession` Değişkeni veya olan bir sınıfı örneği `db_source` özniteliği uygulanmış üzerinde komutu yürütür. Bkz: [db_source](../windows/db-source.md).  
  
 `hresult`(isteğe bağlı)  
 Alacak değişkeni tanımlayan `HRESULT` bu veritabanı komutu. Değişkeni yoksa özniteliği tarafından otomatik olarak eklenecek.  
  
## <a name="remarks"></a>Açıklamalar  
 **db_table** oluşturur bir [CTable](../data/oledb/ctable-class.md) bir tabloyu açmak için bir OLE DB tüketici tarafından kullanılan nesne. Bu öznitelik yalnızca sınıf düzeyinde kullanabilirsiniz; Satır içi kullanamazsınız. Kullanmak **db_column** değişkenlere; tablo sütunları bağlamak için kullanmak **db_param** sınırlandırmak için (parametre türü ve bunu parametrelerinin ayarlayın).  
  
 Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uyguladığında derleyici sınıfa adlandıracak \_ *YourClassName*erişimci nerede *YourClassName* verdiğiniz adı sınıf ve derleyici adlı bir sınıf oluşturur de *YourClassName*, den türetilen \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, her iki sınıfları görürsünüz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek tarafından kullanılmak üzere Ürünler tablosuna açılır `CProducts`.  
  
```  
// db_table.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_table(L"dbo.Products") ]  
class CProducts {  
   [ db_column("1") ] LONG m_ProductID;  
};  
```  
  
 Örnekler bir uygulamada kullanılan bu öznitelik bir örnek için bkz [AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409) ve [MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**,`struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Öznitelikleri](../windows/ole-db-consumer-attributes.md)   
