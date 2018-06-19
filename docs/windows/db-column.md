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
ms.openlocfilehash: 35ab2472ac9e46b620ca735d06b23806126871e0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879639"
---
# <a name="dbcolumn"></a>db_column
Belirtilen sütun satır kümesindeki bir değişken bağlar.  
  
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
 `ordinal`  
 Sıralı sütun numarası (**DBCOLUMNINFO** sıralı) veya veri bağlanacak satır kümesindeki bir alana karşılık gelen sütun adı (ANSI veya Unicode dize). Sayı kullanırsanız, ardışık sıra numaraları atlayabilirsiniz (örneğin: 1, 2, 3, 5). Kullandığınız OLE DB sağlayıcısı destekliyorsa ad boşluk içeremez. Örneğin, aşağıdaki biçimlerden birini kullanabilirsiniz:  
  
```  
[db_column("2")] TCHAR szCity[30];  
[db_column(L"city_name")] TCHAR szCity[30];  
```  
  
 *DbType* (isteğe bağlı)  
 OLE DB [türü göstergesi](https://msdn.microsoft.com/en-us/library/ms711251.aspx) sütun girişi.  
  
 *Duyarlık* (isteğe bağlı)  
 Sütun girişini kullanılacak hassasiyet. Ayrıntılar için açıklamasını görmek `bPrecision` öğesinin [IAccessor::CreateAccessor'ı yapısı](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Ölçek* (isteğe bağlı)  
 Sütun girişini kullanılacak ölçeklendirin. Ayrıntılar için açıklamasını görmek `bScale` öğesinin [IAccessor::CreateAccessor'ı yapısı](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Durum* (isteğe bağlı)  
 Bu sütun durumunu tutmak için kullanılan bir üye değişkeni. Durum sütun değeri bir veri değeri veya başka bir değer, gibi olup olmadığını belirten **NULL**. Olası değerler için bkz: [durum](https://msdn.microsoft.com/en-us/library/ms722617.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 *Uzunluk* (isteğe bağlı)  
 Sütunun boyutunu bayt cinsinden tutmak için kullanılan bir üye değişkeni.  
  
## <a name="remarks"></a>Açıklamalar  
 **db_column** satır kümesindeki bir değişken için belirtilen tablo sütununun bağlar. OLE DB'de katılabilir üye verileri sınırlandırır `IAccessor`-bağlama dayalı. Bu öznitelik normalde OLE DB Tüketici makroları kullanılarak tanımlanan sütun eşlemesi ayarlar [BEGIN_COLUMN_MAP](../data/oledb/begin-column-map.md), [END_COLUMN_MAP](../data/oledb/end-column-map.md), ve [COLUMN_ENTRY](../data/oledb/column-entry.md). Bunlar OLE DB işlemek [IAccessor::CreateAccessor'ı yapısı](https://msdn.microsoft.com/en-us/library/ms716845.aspx) belirtilen sütun bağlamak için. İşaretleme ile her üye **db_column** özniteliği kaplar bir giriş sütun girişi biçiminde sütun eşlemesindeki. Bu nedenle, bu öznitelik Burada, sütun eşlemesi, diğer bir deyişle, komut veya tablo sınıfında koyabilirsiniz çağırın.  
  
 Kullanım **db_column** ya da birlikte [db_table](../windows/db-table.md) veya [db_command](../windows/db-command.md) öznitelikleri.  
  
 Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uyguladığında derleyici sınıfa adlandıracak \_ *YourClassName*erişimci nerede *YourClassName* verdiğiniz adı sınıf ve derleyici adlı bir sınıf oluşturur de *YourClassName*, den türetilen \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, her iki sınıfları görürsünüz.  
  
 Bu öznitelik bir uygulamada kullanılan örnekleri görmek için örnekler [AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409), ve [MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## <a name="example"></a>Örnek  
 Bu örnek, bir tablodaki bir sütun bağlar bir **uzun** veri üyesi ve durum ve uzunluk alanları belirtir.  
  
```  
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
 Bu örnek için dört sütun bağlar bir **uzun**, bir karakter dizesi, bir zaman damgası ve **DB_NUMERIC** bu sırayla tamsayı.  
  
```  
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
|**Uygulandığı öğe:**|**sınıf**, `struct`, üye, yöntemi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB tüketici öznitelikleri](../windows/ole-db-consumer-attributes.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   
