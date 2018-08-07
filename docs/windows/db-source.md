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
ms.openlocfilehash: f7c1f02c3791e75d3f42db6a942f5b2055234517
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570616"
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
  
### <a name="parameters"></a>Parametreler  
 *db_source*  
 Veri kaynağına bağlanmak için kullanılan bağlantı dizesi. Bağlantı dizesinin biçimi için bkz: [bağlantı dizelerini ve veri bağlantıları](https://msdn.microsoft.com/library/ms718376.aspx) içinde SDK Microsoft Data Access Components (MDAC).  
  
 *Ad* (isteğe bağlı)  
 Kullanırken **db_source** bir sınıfta *adı* sahip bir veri kaynağı nesnesinin bir örneğini **db_source** (bkz. örnek 1) uygulanan bir öznitelik. Kullanırken **db_source** satır bir yöntem uygulaması içinde *adı* verilere erişmek için kullanılan bir değişken (yöntemi yerel) (2 örneğe bakın) kaynak. Bu geçirdiğiniz *adı* için *source_name* parametresinin `db_command` veri kaynağı bir komut ile ilişkilendirilecek.  
  
 *HRESULT* (isteğe bağlı)  
 Alacak değişkeni tanımlar `HRESULT` bu veritabanı komutunun. Değişkeni mevcut değilse özniteliği tarafından otomatik olarak eklenecek.  
  
## <a name="remarks"></a>Açıklamalar  
 **db_source** oluşturur bir [CDataSource](../data/oledb/cdatasource-class.md) ve [CSession](../data/oledb/csession-class.md) birlikte bir OLE DB Tüketici veri kaynağı ile bağlantı temsil eden nesne.  
  
 Kullanırken **db_source** bir sınıfta `CSession` nesne sınıfının bir üyesi haline gelir.  
  
 Kullanırken **db_source** bir yöntemde, yöntemi kapsam içinde eklenen kodu yürütülür ve `CSession` nesnesi, yerel bir değişken olarak oluşturulur.  
  
 **db_source** bir sınıfa ya da bir yöntem içinde veri kaynağı özellikleri ekler. İle birlikte kullanılan `db_command` (hangi alır *db_source* *adı* parametre olarak kendi *source_name* parametresi).  
  
 Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uygulandığında, derleyici sınıf için yeniden adlandıracağını \_ *YourClassName*erişimci burada *YourClassName* verdiğiniz addır sınıf ve derleyici adlı bir sınıf oluşturur ayrıca *YourClassName*, öğesinden türetildiğini \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, hem sınıflarını görürsünüz.  
  
 Bu öznitelik, bir uygulamada kullanılan bir örnek için örneklere bakın [AtlAgent](http://msdn.microsoft.com/52bef5da-c1a0-4223-b4e6-9e464b6db409) ve [MultiRead](http://msdn.microsoft.com/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## <a name="example"></a>Örnek  
 Bu örneği çağırır **db_source** veri kaynağı ile bağlantı oluşturmak için bir sınıf `ds` kullanarak Northwind veritabanı. `ds` dahili olarak kullanılan veri kaynağı için bir tanıtıcı `CMyCommand` sınıfı.  
  
```cpp  
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
|**İçin geçerlidir**|**sınıf**, **yapı**, üye, yöntem, yerel|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Öznitelikleri](../windows/ole-db-consumer-attributes.md)   