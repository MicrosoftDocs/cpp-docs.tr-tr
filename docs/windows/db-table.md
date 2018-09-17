---
title: db_table | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_table
dev_langs:
- C++
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6e084a0f876d0b2598a5317e15057162c602474a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717126"
---
# <a name="dbtable"></a>db_table

Bir OLE DB tablosu açılır.

## <a name="syntax"></a>Sözdizimi

```cpp
[ db_table(
   db_table,
   name,
   source_name,
   hresult
) ]
```

#### <a name="parameters"></a>Parametreler

*db_table*  
Bir veritabanı tablosu (örneğin, "Ürünler") adını belirten dize.

*Adı*  
(İsteğe bağlı) Tablo ile çalışmak için kullandığınız işleyici adı. Birden fazla satır sonuçlarını döndürmek istiyorsanız bu parametreyi belirtmelisiniz. **db_table** belirtilen sahip bir değişken oluşturur *adı* çapraz satır kümesi veya birden çok eylem sorguları yürütmek için kullanılabilir.

*source_name*  
(İsteğe bağlı) `CSession` Değişkeni veya bir sınıf örneğini `db_source` özniteliği uygulanmış komutu yürütür. Bkz: [db_source](../windows/db-source.md).

*HRESULT*  
(İsteğe bağlı) Bu veritabanı komutunun HRESULT alacak değişkeni tanımlar. Değişkeni mevcut değilse özniteliği tarafından otomatik olarak eklenecek.

## <a name="remarks"></a>Açıklamalar

**db_table** oluşturur bir [CTable](../data/oledb/ctable-class.md) tablo açmak için bir OLE DB Tüketicisi tarafından kullanılan nesne. Bu öznitelik yalnızca sınıf düzeyinde kullanabilirsiniz; Satır içi kullanamazsınız. Kullanma `db_column` tablo sütunları değişkenlere; bağlamak için kullanın `db_param` sınırlandırmak için (parametre türü ve dolayısıyla parametrelerini ayarlayın).

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
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Öznitelikleri](../windows/ole-db-consumer-attributes.md)  
