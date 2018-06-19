---
title: db_source | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b826e5d630b52062892001c26efda01b5c7293f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873725"
---
# <a name="dbsource"></a>db_source
Bir veri kaynağı için bir bağlantı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ db_source(   
   db_source,   
   name,   
   hresult   
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *db_source*  
 Veri kaynağına bağlanmak için kullanılan bağlantı dizesi. Bağlantı dizesi biçimi için bkz: [bağlantı dizeleri ve veri bağlantıları](https://msdn.microsoft.com/en-us/library/ms718376.aspx) içinde SDK Microsoft Veri Access Components (MDAC).  
  
 *ad* (isteğe bağlı)  
 Kullandığınızda `db_source` bir sınıfını *adı* sahip bir veri kaynağı nesnesi örneği `db_source` (örnek 1 bakın) özniteliğinin. Kullandığınızda `db_source` satır bir yöntem uygulaması içinde *adı* verilere erişmek için kullanılan bir değişken (yerel yöntemi) (örnek 2 bakın) kaynak. Bu geçirdiğiniz *adı* için `source_name` parametresinin **db_command** veri kaynağı bir komutu ile ilişkilendirilecek.  
  
 `hresult` (isteğe bağlı)  
 Alacak değişkeni tanımlayan `HRESULT` bu veritabanı komutu. Değişkeni yoksa özniteliği tarafından otomatik olarak eklenecek.  
  
## <a name="remarks"></a>Açıklamalar  
 `db_source` oluşturur bir [CDataSource](../data/oledb/cdatasource-class.md) ve [CSession](../data/oledb/csession-class.md) birlikte bir OLE DB Tüketici veri kaynağı ile bağlantı temsil eden nesne.  
  
 Kullandığınızda `db_source` bir sınıfını `CSession` nesne sınıfının bir üyesi haline gelir.  
  
 Kullandığınızda `db_source` yöntemi kapsamında bir yöntemde, eklenen kodu yürütülür ve `CSession` nesnesi, yerel bir değişken olarak oluşturulur.  
  
 `db_source` veri kaynağı özellikleri için bir sınıf ya da bir yöntem içinde ekler. İle birlikte kullanılan **db_command** (hangi alır `db_source` *adı* parametre olarak kendi `source_name` parametresi).  
  
 Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uyguladığında derleyici sınıfa adlandıracak \_ *YourClassName*erişimci nerede *YourClassName* verdiğiniz adı sınıf ve derleyici adlı bir sınıf oluşturur de *YourClassName*, den türetilen \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, her iki sınıfları görürsünüz.  
  
 Örnekler bir uygulamada kullanılan bu öznitelik bir örnek için bkz [AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409) ve [MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## <a name="example"></a>Örnek  
 Bu örnek çağırır `db_source` veri kaynağı için bir bağlantı oluşturmak için bir sınıf `ds` Northwind veritabanı kullanıyor. `ds` dahili olarak kullanılan veri kaynağı için tanıtıcı `CMyCommand` sınıfı.  
  
```  
// db_source_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[  
  db_source(L"my_connection_string", name="ds"),  
  db_command(L"select * from Products")  
]  
class CMyCommand {};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**, `struct`, üye, yöntem, yerel|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Öznitelikleri](../windows/ole-db-consumer-attributes.md)   
