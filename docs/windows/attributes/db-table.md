---
title: db_table (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_table
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
ms.openlocfilehash: 3ab548261d6ebcb9d3d7f7e352c8afe3b33db06f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023873"
---
# <a name="dbtable"></a>db_table

Bir OLE DB tablosu açılır.

## <a name="syntax"></a>Sözdizimi

```cpp
[ db_table(db_table, name, source_name, hresult) ]
```

#### <a name="parameters"></a>Parametreler

*db_table*<br/>
Bir veritabanı tablosu (örneğin, "Ürünler") adını belirten dize.

*name*<br/>
(İsteğe bağlı) Tablo ile çalışmak için kullandığınız işleyici adı. Birden fazla satır sonuçlarını döndürmek istiyorsanız bu parametreyi belirtmelisiniz. **db_table** belirtilen sahip bir değişken oluşturur *adı* çapraz satır kümesi veya birden çok eylem sorguları yürütmek için kullanılabilir.

*source_name*<br/>
(İsteğe bağlı) `CSession` Değişkeni veya bir sınıf örneğini `db_source` özniteliği uygulanmış komutu yürütür. Bkz: [db_source](db-source.md).

*HRESULT*<br/>
(İsteğe bağlı) Bu veritabanı komutunun HRESULT alacak değişkeni tanımlar. Değişkeni mevcut değilse özniteliği tarafından otomatik olarak eklenecek.

## <a name="remarks"></a>Açıklamalar

**db_table** oluşturur bir [CTable](../../data/oledb/ctable-class.md) tablo açmak için bir OLE DB Tüketicisi tarafından kullanılan nesne. Bu öznitelik yalnızca sınıf düzeyinde kullanabilirsiniz; Satır içi kullanamazsınız. Kullanma `db_column` tablo sütunları değişkenlere; bağlamak için kullanın `db_param` sınırlandırmak için (parametre türü ve dolayısıyla parametrelerini ayarlayın).

Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uygulandığında, derleyici sınıf için yeniden adlandıracağını \_ *YourClassName*erişimci burada *YourClassName* verdiğiniz addır sınıf ve derleyici adlı bir sınıf oluşturur ayrıca *YourClassName*, öğesinden türetildiğini \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, hem sınıflarını görürsünüz.

## <a name="example"></a>Örnek

Aşağıdaki örnek Ürünler tablosu tarafından kullanılmak üzere açılır `CProducts`.

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

Bu öznitelik, bir uygulamada kullanılan bir örnek için örneklere bakın [AtlAgent](https://github.com/Microsoft/VCSamples) ve [MultiRead](https://github.com/Microsoft/VCSamples).

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Öznitelikleri](ole-db-consumer-attributes.md)
