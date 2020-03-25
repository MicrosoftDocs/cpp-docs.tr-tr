---
title: db_accessor (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_accessor
helpviewer_keywords:
- db_accessor attribute
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
ms.openlocfilehash: 1e9725dad39974b828d87bd8b4cdeac623f4e12f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214870"
---
# <a name="db_accessor"></a>db_accessor

Gruplar, `IAccessor`tabanlı bağlamaya katılan öznitelikleri `db_column`.

## <a name="syntax"></a>Sözdizimi

```cpp
[ db_accessor(num, auto) ]
```

#### <a name="parameters"></a>Parametreler

*numaraları*<br/>
Erişimci numarasını belirtir (sıfır tabanlı bir tamsayı dizini). Erişimci numaralarını, tamsayılar veya tanımlanmış değerler kullanarak artan sırada belirtmeniz gerekir.

*auto*<br/>
Erişimcinin otomatik olarak alınıp alınmayacağını (TRUE) veya alınmadığını belirten bir Boole değeri (FALSE).

## <a name="remarks"></a>Açıklamalar

**db_accessor** , sonraki `db_column` ve `db_param` öznitelikleri için temel OLE DB erişimcisini aynı sınıf veya işlev içinde tanımlar. **db_accessor** , üye düzeyinde kullanılabilir ve OLE DB `IAccessor`tabanlı bağlamaya katılan `db_column` özniteliklerini gruplandırmak için kullanılır. `db_table` ya da `db_command` öznitelikleriyle birlikte kullanılır. Bu özniteliği çağırmak, [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [end_accessor](../../data/oledb/end-accessor.md) makrolarını çağırmaya benzerdir.

**db_accessor** bir satır kümesi oluşturur ve ilgili erişimci haritalarını bağlar. **Db_accessor**çağırmayın, erişimci 0 otomatik olarak oluşturulur ve tüm sütun bağlamaları bu erişimci bloğuna eşlenir.

**db_accessor** veritabanı sütun bağlamalarını bir veya daha fazla erişimcilere gruplandırır. Birden çok erişimci kullanmanız gereken senaryolara ilişkin bir tartışma için bkz. [bir satır kümesinde birden çok erişimci kullanma](../../data/oledb/using-multiple-accessors-on-a-rowset.md). Ayrıca, [Kullanıcı kayıtlarında](../../data/oledb/user-records.md)"birden çok erişimci Için Kullanıcı kaydı desteği" bölümüne bakın.

Tüketici öznitelik sağlayıcısı bu özniteliği bir sınıfa uygularsa, derleyici sınıfı verdiğiniz ad *olan ClassName ' ın adını \_olarak*yeniden adlandırır ve derleyici *YourClassName* Ayrıca, \_*YourClassName*erişimcisinden türetilen, *YourClassName*adlı bir sınıf oluşturur.  Sınıf Görünümü, her iki sınıfı da görürsünüz.

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Öznitelik blokları|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Öznitelikleri](ole-db-consumer-attributes.md)
