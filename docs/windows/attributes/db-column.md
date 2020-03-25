---
title: db_column (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_column
helpviewer_keywords:
- db_column attribute
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
ms.openlocfilehash: 4ce57443480e35e7a4c7b9e872e41777662ddc20
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167296"
---
# <a name="db_column"></a>db_column

Belirtilen bir sütunu satır kümesindeki bir değişkene bağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ db_column(ordinal, dbtype, precision, scale, status, length) ]
```

### <a name="parameters"></a>Parametreler

*numarasını*<br/>
Verilerin bağlanacağı satır kümesindeki bir alana karşılık gelen sıralı sütun numarası (`DBCOLUMNINFO` sıra sayısı) veya sütun adı (ANSI veya Unicode dizesi). Sayı kullanırsanız, ardışık sıra sayısını atlayabilirsiniz (örneğin: 1, 2, 3, 5). Kullandığınız OLE DB sağlayıcı destekliyorsa, ad boşluk içerebilir. Örneğin, aşağıdaki biçimlerden birini kullanabilirsiniz:

```cpp
[db_column("2")] TCHAR szCity[30];
[db_column(L"city_name")] TCHAR szCity[30];
```

*DbType*<br/>
Seçim Sütun girişi için OLE DB [türü göstergesi](/previous-versions/windows/desktop/ms711251(v=vs.85)) .

*duyarlılık*<br/>
Seçim Sütun girişi için kullanılacak duyarlık. Ayrıntılar için bkz. [Dbbinding yapısının](/previous-versions/windows/desktop/ms716845(v=vs.85)) `bPrecision` öğesinin açıklaması.

*ölçek*<br/>
Seçim Sütun girişi için kullanılacak ölçek. Ayrıntılar için bkz. [Dbbinding yapısının](/previous-versions/windows/desktop/ms716845(v=vs.85)) `bScale` öğesi açıklaması

*durumlarına*<br/>
Seçim Bu sütunun durumunu tutmak için kullanılan bir üye değişkeni. Durum, sütun değerinin bir veri değeri mi yoksa NULL gibi başka bir değer mi olduğunu gösterir. Olası değerler için *OLE DB Programcı başvurusunda* [durum](/previous-versions/windows/desktop/ms722617(v=vs.85)) ' a bakın.

*uzunluklu*<br/>
Seçim Sütunun boyutunu bayt cinsinden tutmak için kullanılan bir üye değişkeni.

## <a name="remarks"></a>Açıklamalar

**db_column** , belirtilen tablo sütununu satır kümesindeki bir değişkene bağlar. OLE DB `IAccessor`tabanlı bağlamaya katılabileceğiniz üye verilerini ayırır. Bu öznitelik, normalde OLE DB tüketici makroları [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md), [end_column_map](../../data/oledb/end-column-map.md)ve [COLUMN_ENTRY](../../data/oledb/column-entry.md)kullanılarak tanımlanan sütun eşlemesini ayarlar. Bu, belirtilen sütunu bağlamak için OLE DB [Dbbinding yapısını](/previous-versions/windows/desktop/ms716845(v=vs.85)) işleyebilir. **Db_column** özniteliğiyle işaretlediğiniz her üye, sütun haritasında sütun girişi biçiminde bir giriş kaplayacaktır. Bu nedenle, bu özniteliği komut veya tablo sınıfında sütun haritasını yerleştireceğiniz yerde çağırabilirsiniz.

[Db_table](db-table.md) veya [db_command](db-command.md) öznitelikleriyle birlikte **db_column** kullanın.

Tüketici öznitelik sağlayıcısı bu özniteliği bir sınıfa uygularsa, derleyici sınıfı verdiğiniz ad *olan ClassName ' ın adını \_olarak*yeniden adlandırır ve derleyici *YourClassName* Ayrıca, \_*YourClassName*erişimcisinden türetilen, *YourClassName*adlı bir sınıf oluşturur.  Sınıf Görünümü, her iki sınıfı da görürsünüz.

Bir uygulamada kullanılan bu özniteliğe bir örnek için bkz. [MultiRead](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer).

## <a name="example"></a>Örnek

Bu örnek, bir tablodaki sütunu **Long** veri üyesine bağlar ve durum ve uzunluk alanlarını belirtir.

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

Bu örnek dört sütunu bir **Long**, bir karakter dizesi, bir zaman damgası ve bir `DB_NUMERIC` tamsayı ile bu sırayla bağlar.

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
|**Uygulama hedefi**|**sınıf**, **Yapı**, üye, Yöntem|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Öznitelikleri](ole-db-consumer-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)
