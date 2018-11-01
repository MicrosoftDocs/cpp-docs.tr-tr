---
title: db_column (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_column
helpviewer_keywords:
- db_column attribute
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
ms.openlocfilehash: c9c060bda4198c199ea86f0e2a33adc3275b353b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555057"
---
# <a name="dbcolumn"></a>db_column

Belirtilen sütun, satır kümesindeki bir değişkene bağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ db_column(ordinal, dbtype, precision, scale, status, length) ]
```

#### <a name="parameters"></a>Parametreler

*Sıra*<br/>
Sıralı sütun sayısı (`DBCOLUMNINFO` sıralı) veya satır kümesi veri bağlanacak bir alana karşılık gelen sütun adı (ANSI veya Unicode dize). Sayı kullanıyorsanız, ardışık sıra sayıları atlayabilirsiniz (örneğin: 1, 2, 3, 5). OLE DB sağlayıcı destekliyorsa ad boşluk içeremez. Örneğin, aşağıdaki biçimlerden birini kullanabilirsiniz:

```cpp
[db_column("2")] TCHAR szCity[30];
[db_column(L"city_name")] TCHAR szCity[30];
```

*DbType*<br/>
(İsteğe bağlı) Bir OLE DB [türü göstergesi](/previous-versions/windows/desktop/ms711251) sütun girişi.

*Duyarlık*<br/>
(İsteğe bağlı) Sütun girişini kullanılacak hassasiyet. Ayrıntılar için açıklamasını görmek `bPrecision` öğesinin [IAccessor::CreateAccessor'ı yapısı](/previous-versions/windows/desktop/ms716845)

*Ölçek*<br/>
(İsteğe bağlı) Sütun girişi için kullanılacak ölçek. Ayrıntılar için açıklamasını görmek `bScale` öğesinin [IAccessor::CreateAccessor'ı yapısı](/previous-versions/windows/desktop/ms716845)

*Durumu*<br/>
(İsteğe bağlı) Bu sütun durumunu tutmak için kullanılan bir üye değişkeni. Durum sütun değeri veri değeri NULL gibi diğer bazı değeri olup olmadığını gösterir. Olası değerler için bkz. [durumu](/previous-versions/windows/desktop/ms722617) içinde *OLE DB Programcının Başvurusu*.

*Uzunluğu*<br/>
(İsteğe bağlı) Sütun boyutunu bayt cinsinden tutmak için kullanılan bir üye değişkeni.

## <a name="remarks"></a>Açıklamalar

**db_column** satır kümesindeki bir değişken için belirtilen tablo sütunu bağlar. OLE DB içinde yer alabilirler üye verileri sınırlandırır `IAccessor`-bağlama dayalı. Bu öznitelik normalde OLE DB Tüketici makroları kullanarak tanımlanan sütun eşlemesi ayarlar [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md), [END_COLUMN_MAP](../../data/oledb/end-column-map.md), ve [COLUMN_ENTRY](../../data/oledb/column-entry.md). Bunlar OLE DB işlemek [IAccessor::CreateAccessor'ı yapısı](/previous-versions/windows/desktop/ms716845) belirtilen sütun bağlamak için. Her üye ile işaretle **db_column** biçiminde bir sütunu giriş sütun eşlemesi içinde bir giriş özniteliği dolduracaktır. Bu nedenle, bu öznitelik Burada, sütun eşleme, diğer bir deyişle, komut veya tablo sınıfında koyabilirsiniz çağırın.

Kullanım **db_column** ya da birlikte [db_table](db-table.md) veya [db_command](db-command.md) öznitelikleri.

Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uygulandığında, derleyici sınıf için yeniden adlandıracağını \_ *YourClassName*erişimci burada *YourClassName* verdiğiniz addır sınıf ve derleyici adlı bir sınıf oluşturur ayrıca *YourClassName*, öğesinden türetildiğini \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, hem sınıflarını görürsünüz.

Bu öznitelik, bir uygulamada kullanılan örneklerini görmek için örnekleri [AtlAgent](https://github.com/Microsoft/VCSamples), ve [MultiRead](https://github.com/Microsoft/VCSamples).

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

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Öznitelikleri](ole-db-consumer-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)
