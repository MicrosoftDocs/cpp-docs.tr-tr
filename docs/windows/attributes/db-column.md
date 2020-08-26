---
title: db_column (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_column
helpviewer_keywords:
- db_column attribute
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
ms.openlocfilehash: 98f546a243016fa85f6d71159ab2fc0a7963bae3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833121"
---
# <a name="db_column"></a>db_column

Belirtilen bir sütunu satır kümesindeki bir değişkene bağlar.

## <a name="syntax"></a>Söz dizimi

```cpp
[ db_column(ordinal, dbtype, precision, scale, status, length) ]
```

### <a name="parameters"></a>Parametreler

*numarasını*<br/>
`DBCOLUMNINFO`Verilerin bağlanacağı satır kümesindeki bir alana karşılık gelen sıralı sütun numarası (sıra sayısı) veya sütun adı (ANSI veya Unicode dizesi). Sayı kullanırsanız, ardışık sıra sayısını atlayabilirsiniz (örneğin: 1, 2, 3, 5). Kullandığınız OLE DB sağlayıcı destekliyorsa, ad boşluk içerebilir. Örneğin, aşağıdaki biçimlerden birini kullanabilirsiniz:

```cpp
[db_column("2")] TCHAR szCity[30];
[db_column(L"city_name")] TCHAR szCity[30];
```

*DbType*<br/>
Seçim Sütun girişi için OLE DB [türü göstergesi](/previous-versions/windows/desktop/ms711251(v=vs.85)) .

*duyarlılık*<br/>
Seçim Sütun girişi için kullanılacak duyarlık. Ayrıntılar için, `bPrecision` [dbbinding yapısının](/previous-versions/windows/desktop/ms716845(v=vs.85)) öğesinin açıklamasına bakın

*ölçek*<br/>
Seçim Sütun girişi için kullanılacak ölçek. Ayrıntılar için bkz `bScale` . [dbbinding yapısının](/previous-versions/windows/desktop/ms716845(v=vs.85)) öğesinin açıklaması

*durumlarına*<br/>
Seçim Bu sütunun durumunu tutmak için kullanılan bir üye değişkeni. Durum, sütun değerinin bir veri değeri mi yoksa NULL gibi başka bir değer mi olduğunu gösterir. Olası değerler için *OLE DB Programcı başvurusunda* [durum](/previous-versions/windows/desktop/ms722617(v=vs.85)) ' a bakın.

*uzunluklu*<br/>
Seçim Sütunun boyutunu bayt cinsinden tutmak için kullanılan bir üye değişkeni.

## <a name="remarks"></a>Açıklamalar

**db_column** , belirtilen tablo sütununu satır kümesindeki bir değişkene bağlar. OLE DB tabanlı bağlamaya katılabileceğiniz üye verilerini ayırır `IAccessor` . Bu öznitelik, normalde OLE DB tüketici makroları [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md), [end_column_map](../../data/oledb/end-column-map.md)ve [COLUMN_ENTRY](../../data/oledb/column-entry.md)kullanılarak tanımlanan sütun eşlemesini ayarlar. Bu, belirtilen sütunu bağlamak için OLE DB [Dbbinding yapısını](/previous-versions/windows/desktop/ms716845(v=vs.85)) işleyebilir. **Db_column** özniteliğiyle işaretlediğiniz her üye, sütun haritasında sütun girişi biçiminde bir giriş kaplayacaktır. Bu nedenle, bu özniteliği komut veya tablo sınıfında sütun haritasını yerleştireceğiniz yerde çağırabilirsiniz.

[Db_table](db-table.md) veya [db_command](db-command.md) öznitelikleriyle birlikte **db_column** kullanın.

Tüketici öznitelik sağlayıcısı bu özniteliği bir sınıfa uygularsa, derleyici sınıfı, sınıfın \_ verdiği addır ve ayrıca derleyici *,* *YourClassName*erişimcisinden türetilen *kendi ClassName* adlı bir sınıf oluşturur \_ *YourClassName*.  Sınıf Görünümü, her iki sınıfı da görürsünüz.

Bir uygulamada kullanılan bu özniteliğe bir örnek için bkz. [MultiRead](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer).

## <a name="example"></a>Örnek

Bu örnek, bir tablodaki bir sütunu **`long`** veri üyesine bağlar ve durum ve uzunluk alanlarını belirtir.

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

Bu örnek dört sütunu bir, bir **`long`** karakter dizesi, bir zaman damgası ve bir tamsayı ile `DB_NUMERIC` Bu sırayla bağlar.

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`** , üye, yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici öznitelikleri](ole-db-consumer-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)
