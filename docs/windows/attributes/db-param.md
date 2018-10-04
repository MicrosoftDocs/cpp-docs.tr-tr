---
title: db_param (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: dda702a9c9df9662dc6ca3c38143853e8a407f43
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789848"
---
# <a name="dbparam"></a>db_param

Belirtilen üye bağımsız değişkenine bir giriş veya çıkış parametresi ile ilişkilendirir ve değişken sınırlandırır.

## <a name="syntax"></a>Sözdizimi

```cpp
[ db_param(ordinal, paramtype="DBPARAMIO_INPUT", dbtype, precision, scale, status, length) ]
```

### <a name="parameters"></a>Parametreler

*Sıra*<br/>
Satır kümesi veri bağlanacak bir alana karşılık gelen sütun numarası (DBCOLUMNINFO sıra).

*paramtype*<br/>
(İsteğe bağlı) İçin parametre türü. Sağlayıcılar, temel alınan veri kaynağı tarafından desteklenen parametre g/ç türlerini destekler. Bir veya daha fazla DBPARAMIOENUM değerlerinin bir birleşimini türüdür:

- DBPARAMIO_INPUT giriş parametresi.

- DBPARAMIO_OUTPUT çıkış parametresi.

- Erişimci DBPARAMIO_NOTPARAM hiç parametre yok. Ayar `eParamIO` satır içinde bu değer için erişimciler hatırlatır kullanıcı parametreleri göz ardı edilir.

*DbType*<br/>
(İsteğe bağlı) Bir OLE DB [türü göstergesi](/previous-versions/windows/desktop/ms711251\(v=vs.85\)) sütun girişi.

*Duyarlık*<br/>
(İsteğe bağlı) Sütun girişini kullanılacak hassasiyet. Ayrıntılar için açıklamasını görmek `bPrecision` öğesinin [IAccessor::CreateAccessor'ı yapısı](/previous-versions/windows/desktop/ms716845\(v=vs.85\))

*Ölçek*<br/>
(İsteğe bağlı) Sütun girişi için kullanılacak ölçek. Ayrıntılar için açıklamasını görmek `bScale` öğesinin [IAccessor::CreateAccessor'ı yapısı](/previous-versions/windows/desktop/ms716845\(v=vs.85\))

*Durumu*<br/>
(İsteğe bağlı) Bu sütun durumunu tutmak için kullanılan bir üye değişkeni. Durum sütun değeri veri değeri NULL gibi diğer bazı değeri olup olmadığını gösterir. Olası değerler için bkz. [durumu](/previous-versions/windows/desktop/ms722617\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.

*Uzunluğu*<br/>
(İsteğe bağlı) Sütun boyutunu bayt cinsinden tutmak için kullanılan bir üye değişkeni.

## <a name="remarks"></a>Açıklamalar

**db_param** parametreleri tanımlar komutları kullanın; Bu nedenle ile kullanarak `db_command`. Örneğin, kullanabileceğiniz **db_param** SQL sorguları veya saklı yordamları parametleri bağlamak için. Bir saklı yordam parametreleri soru işareti (?) belirtilir ve parametreleri göründükleri sırayla veri üyeleri bağlamanız gerekir.

**db_param** OLE DB içinde yer alabilirler üye verileri sınırlandırır `ICommandWithParameters`-bağlama dayalı. (Giriş veya çıkış) parametre türü, OLE DB türü, kesinlik, Ölçek, durum ve uzunluğu belirtilen parametresi için ayarlar. Bu öznitelik, OLE DB Tüketici makroları BEGIN_PARAM_MAP ekler... END_PARAM_MAP. Her üye ile işaretle **db_param** haritadaki bir COLUMN_ENTRY biçiminde, bir giriş özniteliği dolduracaktır.

**db_param** ya da birlikte kullanılan [db_table](db-table.md) veya [db_command](db-command.md) öznitelikleri.

Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uygulandığında, derleyici sınıf için yeniden adlandıracağını \_ *YourClassName*erişimci burada *YourClassName* verdiğiniz addır sınıf ve derleyici adlı bir sınıf oluşturur ayrıca *YourClassName*, öğesinden türetildiğini \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, hem sınıflarını görürsünüz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, Northwind veritabanındaki SalesbyYear depolanan yordamı temel bir komut sınıfı oluşturur. Saklı yordamı ile ilk parametre ilişkilendirir `m_RETURN_VALUE` değişken ve bir output parametresi olarak tanımlar. Son iki (giriş) parametreleriyle ilişkilendirir `m_Beginning_Date` ve `m_Ending_Date`.

Aşağıdaki örnek ilişkilendirir `nOutput` değişkeni çıkış parametresi.

```cpp
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
|**İçin geçerlidir**|**sınıf**, **yapı**, üye, yöntem, yerel|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Öznitelikleri](ole-db-consumer-attributes.md)  
