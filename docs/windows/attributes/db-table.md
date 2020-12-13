---
description: 'Hakkında daha fazla bilgi edinin: db_table'
title: db_table (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_table
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
ms.openlocfilehash: 3d871961a8ded6070127e5e562615018a4320162
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333043"
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
Seçim `CSession` `db_source` Komutun çalıştırıldığı özniteliğe uygulanan özniteliği olan bir sınıfın değişkeni veya örneği. Bkz. [db_source](db-source.md).

*HRESULT*<br/>
Seçim Bu veritabanı komutunun HRESULT 'sini alacak değişkeni tanımlar. Değişken yoksa, özniteliği tarafından otomatik olarak eklenir.

## <a name="remarks"></a>Açıklamalar

**db_table** , bir OLE DB tüketicisi tarafından tablo açmak için kullanılan bir [CTable](../../data/oledb/ctable-class.md) nesnesi oluşturur. Bu özniteliği yalnızca sınıf düzeyinde kullanabilirsiniz; satır içi kullanamazsınız. `db_column`Tablo sütunlarını değişkenlere bağlamak için kullanın; `db_param` parametreleri sınırlandırmak için kullanın (parametre türünü ve bu şekilde ayarlayın).

Tüketici öznitelik sağlayıcısı bu özniteliği bir sınıfa uygularsa, derleyici sınıfı, sınıfın \_ verdiği addır ve ayrıca derleyici *,* *YourClassName* erişimcisinden türetilen *kendi ClassName* adlı bir sınıf oluşturur \_ .  Sınıf Görünümü, her iki sınıfı da görürsünüz.

## <a name="example"></a>Örnek

Aşağıdaki örnek tarafından kullanılacak Ürünler tablosunu açar `CProducts` .

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`**|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici öznitelikleri](ole-db-consumer-attributes.md)
