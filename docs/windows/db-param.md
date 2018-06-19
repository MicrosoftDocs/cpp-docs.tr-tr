---
title: db_param | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_param
dev_langs:
- C++
helpviewer_keywords:
- db_param attribute
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce7cf5c8e92e7fd6e6e10d7bef0519b1ced4cf62
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880728"
---
# <a name="dbparam"></a>db_param
Belirtilen üye değişkeni bir giriş veya çıkış parametresi ile ilişkilendirir ve değişken sınırlandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ db_param(   
   ordinal,   
   paramtype="DBPARAMIO_INPUT",   
   dbtype,   
   precision,   
   scale,   
   status,   
   length  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ordinal`  
 Sütun numarası (**DBCOLUMNINFO** sıralı) veri bağlanacak satır kümesindeki bir alana karşılık gelen.  
  
 *paramtype* (isteğe bağlı)  
 İçin parametre türü. Sağlayıcılar, temel alınan veri kaynağı tarafından desteklenen parametre g/ç türlerini destekler. Bir veya daha fazla bileşimini türüdür **DBPARAMIOENUM** değerler:  
  
-   **DBPARAMIO_INPUT** giriş parametresi.  
  
-   **DBPARAMIO_OUTPUT** çıktı parametresi.  
  
-   **DBPARAMIO_NOTPARAM** erişimci hiç parametre yok. Ayarı **eParamIO** bu değere satırda erişimciler anımsatır kullanıcı parametreleri göz ardı edilir.  
  
 *DbType* (isteğe bağlı)  
 OLE DB [türü göstergesi](https://msdn.microsoft.com/en-us/library/ms711251.aspx) sütun girişi.  
  
 *Duyarlık* (isteğe bağlı)  
 Sütun girişini kullanılacak hassasiyet. Ayrıntılar için açıklamasını görmek **bPrecision** öğesinin [IAccessor::CreateAccessor'ı yapısı](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Ölçek* (isteğe bağlı)  
 Sütun girişini kullanılacak ölçeklendirin. Ayrıntılar için açıklamasını görmek **bScale** öğesinin [IAccessor::CreateAccessor'ı yapısı](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *Durum* (isteğe bağlı)  
 Bu sütun durumunu tutmak için kullanılan bir üye değişkeni. Durum sütun değeri bir veri değeri veya başka bir değer, gibi olup olmadığını belirten **NULL**. Olası değerler için bkz: [durum](https://msdn.microsoft.com/en-us/library/ms722617.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 *Uzunluk* (isteğe bağlı)  
 Sütunun boyutunu bayt cinsinden tutmak için kullanılan bir üye değişkeni.  
  
## <a name="remarks"></a>Açıklamalar  
 **db_param** parametrelerini tanımlar komutlarda kullanın; Bu nedenle ile kullandığınız **db_command**. Örneğin, kullanabileceğiniz **db_param** SQL sorguları ya da saklı yordamlar parametrelerinde bağlamak için. Saklı yordam parametreleri soru işareti (?) tarafından belirtilir ve parametreleri göründükleri sırada veri üyeleri bağlamak.  
  
 **db_param** OLE DB'de katılabilir üye verileri sınırlandırır `ICommandWithParameters`-bağlama dayalı. Parametre türü (giriş veya çıkış), OLE DB türü, duyarlık, Ölçek, durum ve belirtilen parametre uzunluğu ayarlar. Bu öznitelik, OLE DB Tüketici makroları BEGIN_PARAM_MAP ekler... END_PARAM_MAP. İşaretleme ile her üye **db_param** özniteliği kaplar bir giriş eşlemesindeki bir COLUMN_ENTRY biçiminde.  
  
 **db_param** ya da ile birlikte kullanılan [db_table](../windows/db-table.md) veya [db_command](../windows/db-command.md) öznitelikleri.  
  
 Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uyguladığında derleyici sınıfa adlandıracak \_ *YourClassName*erişimci nerede *YourClassName* verdiğiniz adı sınıf ve derleyici adlı bir sınıf oluşturur de *YourClassName*, den türetilen \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, her iki sınıfları görürsünüz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, Northwind veritabanı SalesbyYear saklı yordamda göre komut sınıfı oluşturur. Saklı yordam ile ilk parametreyi ilişkilendirir `m_RETURN_VALUE` değişkeni ve bir output parametresi olarak tanımlar. Son iki (giriş) parametreleriyle ilişkilendirir `m_Beginning_Date` ve `m_Ending_Date`.  
  
 Aşağıdaki örnek ilişkilendirir `nOutput` değişken çıkış parametreye sahip.  
  
```  
// db_param.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_source(L"my_connection_string"),   
  db_command(L"{ ? = CALL dbo.\"Sales by Year\"(?,?) }")   
]  
struct CSalesbyYear {  
   DBSTATUS m_dwShippedDateStatus;  
   DBSTATUS m_dwOrderIDStatus;  
   DBSTATUS m_dwSubtotalStatus;  
   DBSTATUS m_dwYearStatus;  
  
   DBLENGTH m_dwShippedDateLength;  
   DBLENGTH m_dwOrderIDLength;  
   DBLENGTH m_dwSubtotalLength;  
   DBLENGTH m_dwYearLength;  
  
   // Bind columns  
   [ db_column("1", status="m_dwShippedDateStatus", length="m_dwShippedDateLength") ] DBTIMESTAMP m_ShippedDate;  
   [ db_column("2", status="m_dwOrderIDStatus", length="m_dwOrderIDLength") ] LONG m_OrderID;  
   [ db_column("3", status="m_dwSubtotalStatus", length="m_dwSubtotalLength") ] CURRENCY m_Subtotal;  
   [ db_column("4", status="m_dwYearStatus", length="m_dwYearLength") ] TCHAR m_Year[31];  
  
   // Bind parameters  
   [ db_param("1", paramtype="DBPARAMIO_OUTPUT") ] LONG m_RETURN_VALUE;  
   [ db_param("2", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Beginning_Date;  
   [ db_param("3", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Ending_Date;  
};  
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
