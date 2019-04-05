---
title: db_accessor (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_accessor
helpviewer_keywords:
- db_accessor attribute
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
ms.openlocfilehash: bfb287261fce4ebf189801c308f57513f2c9f113
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038310"
---
# <a name="dbaccessor"></a>db_accessor

Grupları `db_column` katılmak öznitelikleri `IAccessor`-bağlama dayalı.

## <a name="syntax"></a>Sözdizimi

```cpp
[ db_accessor(num, auto) ]
```

#### <a name="parameters"></a>Parametreler

*sayı*<br/>
Erişimci (bir tamsayı sıfır tabanlı dizini) belirtir. Artan erişimci sayıları tamsayı kullanarak azalan veya tanımlı değerler belirtmeniz gerekir.

*auto*<br/>
Erişimci otomatik olarak alınır (TRUE) veya (FALSE) alınmamış olduğunu belirten bir Boole değeri.

## <a name="remarks"></a>Açıklamalar

**db_accessor** tanımlar için temel alınan OLE DB erişimci sonraki `db_column` ve `db_param` öznitelikleri aynı sınıfın veya işlevin içinde. **db_accessor** üye düzeyinde kullanılabilir ve kullanılan grubuna `db_column` OLE DB içinde yer alan öznitelikleri `IAccessor`-bağlama dayalı. Ya da birlikte kullanılan `db_table` veya `db_command` öznitelikleri. Bu öznitelik çağırmak için arama benzer [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları.

**db_accessor** bir satır kümesi oluşturur ve karşılık gelen erişimci eşlenir bağlar. Değil çağırırsanız **db_accessor**erişimci 0 otomatik olarak oluşturulur ve tüm sütun bağlamaları için bu erişimci bloğu eşlenir.

**db_accessor** grupları veritabanı sütun bağlamaları içine bir veya daha fazla erişimcileri. Gerektiği çoklu erişimci kullanılacak senaryolarda bir tartışma için bkz [üzerinde bir satır kümesinde çoklu erişimci kullanarak](../../data/oledb/using-multiple-accessors-on-a-rowset.md). Ayrıca, "Kullanıcı kaydı desteği için çoklu erişimci" bkz [kullanıcı kayıtlarını](../../data/oledb/user-records.md).

Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uygulandığında, derleyici sınıf için yeniden adlandıracağını \_ *YourClassName*erişimci burada *YourClassName* verdiğiniz addır sınıf ve derleyici adlı bir sınıf oluşturur ayrıca *YourClassName*, öğesinden türetildiğini \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, hem sınıflarını görürsünüz.

## <a name="example"></a>Örnek

Aşağıdaki örnekte **db_accessor** Northwind'deki Siparişler tablosunda iki erişimci Northwind veritabanına Grup sütunları için. Otomatik erişimci erişimci 0 olduğu ve erişimcisi 1 değil.

```cpp
// cpp_attr_ref_db_accessor.cpp
// compile with: /LD /link /OPT:NOREF
#define _ATL_ATTRIBUTES
#include <atlbase.h>
#include <atldbcli.h>

[ db_command(L"SELECT LastName, FirstName FROM Orders") ]
class CEmployees {
public:
   [ db_accessor(0, TRUE) ];
   [ db_column("1") ] LONG m_OrderID;
   [ db_column("2") ] TCHAR m_CustomerID[6];
   [ db_column("4") ] DBTIMESTAMP m_OrderDate;

   [ db_accessor(1, FALSE) ];
   [ db_column("8") ] CURRENCY m_Freight;
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|Öznitelik blokları|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Öznitelikleri](ole-db-consumer-attributes.md)