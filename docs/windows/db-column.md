---
title: db_column | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_column
dev_langs:
- C++
helpviewer_keywords:
- db_column attribute
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 20c651c6e671c7c4895fc7dba85d16fdeb998ad5
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570707"
---
# <a name="dbcolumn"></a>db_column
Belirtilen sütun, satır kümesindeki bir değişkene bağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ db_column(   
   ordinal,   
   dbtype,   
   precision,   
   scale,   
   status,   
   length   
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Sıra*  
 Sıralı sütun sayısı (`DBCOLUMNINFO` sıralı) veya satır kümesi veri bağlanacak bir alana karşılık gelen sütun adı (ANSI veya Unicode dize). Sayı kullanıyorsanız, ardışık sıra sayıları atlayabilirsiniz (örneğin: 1, 2, 3, 5). OLE DB sağlayıcı destekliyorsa ad boşluk içeremez. Örneğin, aşağıdaki biçimlerden birini kullanabilirsiniz:  
  
```  
[db_column("2")] TCHAR szCity[30];  
[db_column(L"city_name")] TCHAR szCity[30];  
```  
  
 *DbType* (isteğe bağlı)  
 Bir OLE DB [türü göstergesi](https://msdn.microsoft.com/library/ms711251.aspx) sütun girişi.  
  
 *Duyarlık* (isteğe bağlı)  
 Sütun girişini kullanılacak hassasiyet. Ayrıntılar için açıklamasını görmek `bPrecision` öğesinin [IAccessor::CreateAccessor'ı yapısı](https://msdn.microsoft.com/library/ms716845.aspx)  
  
 *Ölçek* (isteğe bağlı)  
 Sütun girişi için kullanılacak ölçek. Ayrıntılar için açıklamasını görmek `bScale` öğesinin [IAccessor::CreateAccessor'ı yapısı](https://msdn.microsoft.com/library/ms716845.aspx)  
  
 *Durum* (isteğe bağlı)  
 Bu sütun durumunu tutmak için kullanılan bir üye değişkeni. Durum sütun değeri veri değeri NULL gibi diğer bazı değeri olup olmadığını gösterir. Olası değerler için bkz. [durumu](https://msdn.microsoft.com/library/ms722617.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 *uzunluğu* (isteğe bağlı)  
 Sütun boyutunu bayt cinsinden tutmak için kullanılan bir üye değişkeni.  
  
## <a name="remarks"></a>Açıklamalar  
 **db_column** satır kümesindeki bir değişken için belirtilen tablo sütunu bağlar. OLE DB içinde yer alabilirler üye verileri sınırlandırır `IAccessor`-bağlama dayalı. Bu öznitelik normalde OLE DB Tüketici makroları kullanarak tanımlanan sütun eşlemesi ayarlar [BEGIN_COLUMN_MAP](../data/oledb/begin-column-map.md), [END_COLUMN_MAP](../data/oledb/end-column-map.md), ve [COLUMN_ENTRY](../data/oledb/column-entry.md). Bunlar OLE DB işlemek [IAccessor::CreateAccessor'ı yapısı](https://msdn.microsoft.com/library/ms716845.aspx) belirtilen sütun bağlamak için. Her üye ile işaretle **db_column** biçiminde bir sütunu giriş sütun eşlemesi içinde bir giriş özniteliği dolduracaktır. Bu nedenle, bu öznitelik Burada, sütun eşleme, diğer bir deyişle, komut veya tablo sınıfında koyabilirsiniz çağırın.  
  
 Kullanım **db_column** ya da birlikte [db_table](../windows/db-table.md) veya [db_command](../windows/db-command.md) öznitelikleri.  
  
 Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uygulandığında, derleyici sınıf için yeniden adlandıracağını \_ *YourClassName*erişimci burada *YourClassName* verdiğiniz addır sınıf ve derleyici adlı bir sınıf oluşturur ayrıca *YourClassName*, öğesinden türetildiğini \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, hem sınıflarını görürsünüz.  
  
 Bu öznitelik, bir uygulamada kullanılan örneklerini görmek için örnekleri [AtlAgent](http://msdn.microsoft.com/52bef5da-c1a0-4223-b4e6-9e464b6db409), ve [MultiRead](http://msdn.microsoft.com/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## <a name="example"></a>Örnek  
 Bu örnek, bir tablodaki bir sütun bağlar. bir **uzun** veri üyesi ve durum ve uzunluğu alanlarını belirtir.  
  
```cpp  
// db_column_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   DBSTATUS m_dwProductIDStatus;  
   DBLENGTH m_dwProductIDLength;  
  
   [ db_column("1", status="m_dwProductIDStatus", length="m_dwProductIDLength") ] LONG m_ProductID;  
};  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek için dört sütun bağlayan bir **uzun**, bir karakter dizesi, bir zaman damgası ve `DB_NUMERIC` o sırada bir tamsayı.  
  
```cpp  
// db_column_2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   [db_column("1")] LONG m_OrderID;  
   [db_column("2")] TCHAR m_CustomerID[6];  
   [db_column("4")] DB_NUMERIC m_OrderDate;     
   [db_column("7", dbtype="DBTYPE_NUMERIC")] DB_NUMERIC m_ShipVia;  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|**sınıf**, **yapı**, üye, yöntemi|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB tüketici öznitelikleri](../windows/ole-db-consumer-attributes.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   