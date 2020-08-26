---
title: db_param (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_param
helpviewer_keywords:
- db_param attribute
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
ms.openlocfilehash: 008a7f1ea07e6c23ad6d812ac4fbf3b30ef1da89
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833081"
---
# <a name="db_param"></a>db_param

Belirtilen üye değişkenini bir giriş veya çıkış parametresiyle ilişkilendirir ve değişkeni ayırır.

## <a name="syntax"></a>Söz dizimi

```cpp
[ db_param(ordinal, paramtype="DBPARAMIO_INPUT", dbtype, precision, scale, status, length) ]
```

### <a name="parameters"></a>Parametreler

*numarasını*<br/>
Verilerin bağlanacağı satır kümesindeki bir alana karşılık gelen sütun numarası (DBCOLUMNıNFO sıra).

*parametre türü*<br/>
Seçim Parametresi için ayarlanacak tür. Sağlayıcılar yalnızca temel alınan veri kaynağı tarafından desteklenen parametre g/ç türlerini destekler. Tür bir veya daha fazla DBPARAMıOENUM değeri birleşimidir:

- Giriş parametresi DBPARAMIO_INPUT.

- Bir çıkış parametresi DBPARAMIO_OUTPUT.

- DBPARAMIO_NOTPARAM erişimcisinin parametresi yok. `eParamIO`Satır erişimcilerinde bu değere ayarlandığında, kullanıcıya parametrelerin yoksayıldığını hatırlatır.

*DbType*<br/>
Seçim Sütun girişi için OLE DB [türü göstergesi](/previous-versions/windows/desktop/ms711251(v=vs.85)) .

*duyarlılık*<br/>
Seçim Sütun girişi için kullanılacak duyarlık. Ayrıntılar için bkz `bPrecision` . [dbbinding yapısının](/previous-versions/windows/desktop/ms716845(v=vs.85)) öğesinin açıklaması

*ölçek*<br/>
Seçim Sütun girişi için kullanılacak ölçek. Ayrıntılar için bkz `bScale` . [dbbinding yapısının](/previous-versions/windows/desktop/ms716845(v=vs.85)) öğesinin açıklaması

*durumlarına*<br/>
Seçim Bu sütunun durumunu tutmak için kullanılan bir üye değişkeni. Durum, sütun değerinin bir veri değeri mi yoksa NULL gibi başka bir değer mi olduğunu gösterir. Olası değerler için *OLE DB Programcı başvurusunda* [durum](/previous-versions/windows/desktop/ms722617(v=vs.85)) ' a bakın.

*uzunluklu*<br/>
Seçim Sütunun boyutunu bayt cinsinden tutmak için kullanılan bir üye değişkeni.

## <a name="remarks"></a>Açıklamalar

**db_param** komutlarda kullandığınız parametreleri tanımlar; Bu nedenle, ile kullanırsınız `db_command` . Örneğin, SQL sorgularında veya saklı yordamlarda parametreleri bağlamak için **db_param** kullanabilirsiniz. Saklı yordamdaki parametreler soru işareti (?) ile gösterilir ve veri üyelerini parametrelerin göründüğü sırada bağlamanız gerekir.

**db_param** , OLE DB tabanlı bağlamaya katılabilen üye verilerini ayırır `ICommandWithParameters` . Belirtilen parametre için parametre türünü (giriş veya çıkış), OLE DB türü, duyarlık, ölçek, durum ve uzunluğu ayarlar. Bu öznitelik OLE DB tüketici makrolarını ekler BEGIN_PARAM_MAP... END_PARAM_MAP. **Db_param** özniteliğiyle işaretlediğiniz her üye, haritadaki bir girişi bir COLUMN_ENTRY biçiminde kaplar.

**db_param** , [db_table](db-table.md) veya [db_command](db-command.md) öznitelikleriyle birlikte kullanılır.

Tüketici öznitelik sağlayıcısı bu özniteliği bir sınıfa uygularsa, derleyici sınıfı, sınıfın \_ verdiği addır ve ayrıca derleyici *,* *YourClassName*erişimcisinden türetilen *kendi ClassName* adlı bir sınıf oluşturur \_ *YourClassName*.  Sınıf Görünümü, her iki sınıfı da görürsünüz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, Northwind veritabanındaki SalesbyYear saklı yordamını temel alan bir komut sınıfı oluşturur. Saklı yordamdaki ilk parametreyi `m_RETURN_VALUE` değişkenle ilişkilendirir ve bunu bir çıktı parametresi olarak tanımlar. Son iki (giriş) parametresini ve ile ilişkilendirir `m_Beginning_Date` `m_Ending_Date` .

Aşağıdaki örnek, `nOutput` değişkeni bir çıkış parametresiyle ilişkilendirir.

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`** , üye, yöntem, yerel|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici öznitelikleri](ole-db-consumer-attributes.md)
