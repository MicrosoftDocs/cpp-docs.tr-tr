---
title: db_accessor (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_accessor
helpviewer_keywords:
- db_accessor attribute
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
ms.openlocfilehash: 559838201e3d1c425b6b1bf7f3650d9635c44c97
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833146"
---
# <a name="db_accessor"></a>db_accessor

`db_column`Tabanlı bağlamaya katılan öznitelikleri gruplandırır `IAccessor` .

## <a name="syntax"></a>Söz dizimi

```cpp
[ db_accessor(num, auto) ]
```

#### <a name="parameters"></a>Parametreler

*sayı*<br/>
Erişimci numarasını belirtir (sıfır tabanlı bir tamsayı dizini). Erişimci numaralarını, tamsayılar veya tanımlanmış değerler kullanarak artan sırada belirtmeniz gerekir.

*auto*<br/>
Erişimcinin otomatik olarak alınıp alınmayacağını (TRUE) veya alınmadığını belirten bir Boole değeri (FALSE).

## <a name="remarks"></a>Açıklamalar

**db_accessor** `db_column` `db_param` , aynı sınıf veya işlev içindeki sonraki ve özniteliklerin temel alınan OLE DB erişimcisini tanımlar. **db_accessor** , üye düzeyinde kullanılabilir ve `db_column` OLE DB tabanlı bağlamaya katılan öznitelikleri gruplandırmak için kullanılır `IAccessor` . Ya da öznitelikleriyle birlikte kullanılır `db_table` `db_command` . Bu özniteliği çağırmak, [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [end_accessor](../../data/oledb/end-accessor.md) makrolarını çağırmaya benzerdir.

**db_accessor** bir satır kümesi oluşturur ve ilgili erişimci haritalarını bağlar. **Db_accessor**çağırmayın, erişimci 0 otomatik olarak oluşturulur ve tüm sütun bağlamaları bu erişimci bloğuna eşlenir.

**db_accessor** veritabanı sütun bağlamalarını bir veya daha fazla erişimcilere gruplandırır. Birden çok erişimci kullanmanız gereken senaryolara ilişkin bir tartışma için bkz. [bir satır kümesinde birden çok erişimci kullanma](../../data/oledb/using-multiple-accessors-on-a-rowset.md). Ayrıca, [Kullanıcı kayıtlarında](../../data/oledb/user-records.md)"birden çok erişimci Için Kullanıcı kaydı desteği" bölümüne bakın.

Tüketici öznitelik sağlayıcısı bu özniteliği bir sınıfa uygularsa, derleyici sınıfı, sınıfın \_ verdiği addır ve ayrıca derleyici *,* *YourClassName*erişimcisinden türetilen *kendi ClassName* adlı bir sınıf oluşturur \_ *YourClassName*.  Sınıf Görünümü, her iki sınıfı da görürsünüz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, Northwind veritabanından Orders tablosundaki sütunları iki erişimcide gruplamak için **db_accessor** kullanır. Erişimci 0 bir otomatik erişimdir ve erişimci 1 değildir.

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Öznitelik blokları|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici öznitelikleri](ole-db-consumer-attributes.md)
