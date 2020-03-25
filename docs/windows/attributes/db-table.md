---
title: db_table (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_table
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
ms.openlocfilehash: 2b3be55a4ea118ef3441d3ea93f63e19ebdb3d79
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167257"
---
# <a name="db_table"></a>db_table

Bir OLE DB tablosu açar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ db_table(db_table, name, source_name, hresult) ]
```

### <a name="parameters"></a>Parametreler

*db_table*<br/>
Bir veritabanı tablosunun adını belirten bir dize (örneğin, "Ürünler").

*ada*<br/>
Seçim Tabloyla çalışmak için kullandığınız tanıtıcının adı. Birden fazla sonuç satırı döndürmek istiyorsanız bu parametreyi belirtmeniz gerekir. **db_table** , satır kümesinde çapraz geçiş yapmak veya birden çok eylem sorgusu yürütmek için kullanılabilecek belirtilen *ada* sahip bir değişken oluşturur.

*source_name*<br/>
Seçim Komutun yürütüldüğü öğesine uygulanmış `db_source` özniteliği olan bir sınıfın `CSession` değişkeni veya örneği. Bkz. [db_source](db-source.md).

*HRESULT*<br/>
Seçim Bu veritabanı komutunun HRESULT 'sini alacak değişkeni tanımlar. Değişken yoksa, özniteliği tarafından otomatik olarak eklenir.

## <a name="remarks"></a>Açıklamalar

**db_table** , bir OLE DB tüketicisi tarafından tablo açmak için kullanılan bir [CTable](../../data/oledb/ctable-class.md) nesnesi oluşturur. Bu özniteliği yalnızca sınıf düzeyinde kullanabilirsiniz; satır içi kullanamazsınız. Tablo sütunlarını değişkenlere bağlamak için `db_column` kullanın; parametreleri sınırlandırmak için `db_param` kullanın (parametre türünü ve bu şekilde ayarlayın).

Tüketici öznitelik sağlayıcısı bu özniteliği bir sınıfa uygularsa, derleyici sınıfı verdiğiniz ad *olan ClassName ' ın adını \_olarak*yeniden adlandırır ve derleyici *YourClassName* Ayrıca, \_*YourClassName*erişimcisinden türetilen, *YourClassName*adlı bir sınıf oluşturur.  Sınıf Görünümü, her iki sınıfı da görürsünüz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CProducts`tarafından kullanılacak Ürünler tablosunu açar.

```cpp
// db_table.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_table(L"dbo.Products") ]
class CProducts {
   [ db_column("1") ] LONG m_ProductID;
};
```

Bir uygulamada kullanılan bu özniteliğe bir örnek için bkz. [MultiRead](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer).

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**sınıf**, **Yapı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Öznitelikleri](ole-db-consumer-attributes.md)
