---
title: db_source (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd8facb38bc4d71445674eb64ad09ab14d0b636a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065895"
---
# <a name="dbsource"></a>db_source

Bir veri kaynağı için bir bağlantı oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
[ db_source(db_source, name, hresult) ]
```

### <a name="parameters"></a>Parametreler

*db_source*<br/>
Veri kaynağına bağlanmak için kullanılan bağlantı dizesi. Bağlantı dizesinin biçimi için bkz: [bağlantı dizelerini ve veri bağlantıları](/previous-versions/windows/desktop/ms718376) içinde SDK Microsoft Data Access Components (MDAC).

*Adı*<br/>
(İsteğe bağlı) Kullanırken **db_source** bir sınıfta *adı* sahip bir veri kaynağı nesnesinin bir örneğini **db_source** (bkz. örnek 1) uygulanan bir öznitelik. Kullanırken **db_source** satır bir yöntem uygulaması içinde *adı* verilere erişmek için kullanılan bir değişken (yöntemi yerel) (2 örneğe bakın) kaynak. Bu geçirdiğiniz *adı* için *source_name* parametresinin `db_command` veri kaynağı bir komut ile ilişkilendirilecek.

*HRESULT*<br/>
(İsteğe bağlı) Bu veritabanı komutunun HRESULT alacak değişkeni tanımlar. Değişkeni mevcut değilse özniteliği tarafından otomatik olarak eklenecek.

## <a name="remarks"></a>Açıklamalar

**db_source** oluşturur bir [CDataSource](../../data/oledb/cdatasource-class.md) ve [CSession](../../data/oledb/csession-class.md) birlikte bir OLE DB Tüketici veri kaynağı ile bağlantı temsil eden nesne.

Kullanırken **db_source** bir sınıfta `CSession` nesne sınıfının bir üyesi haline gelir.

Kullanırken **db_source** bir yöntemde, yöntemi kapsam içinde eklenen kodu yürütülür ve `CSession` nesnesi, yerel bir değişken olarak oluşturulur.

**db_source** bir sınıfa ya da bir yöntem içinde veri kaynağı özellikleri ekler. İle birlikte kullanılan `db_command` (hangi alır *db_source* *adı* parametre olarak kendi *source_name* parametresi).

Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uygulandığında, derleyici sınıf için yeniden adlandıracağını \_ *YourClassName*erişimci burada *YourClassName* verdiğiniz addır sınıf ve derleyici adlı bir sınıf oluşturur ayrıca *YourClassName*, öğesinden türetildiğini \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, hem sınıflarını görürsünüz.

Bu öznitelik, bir uygulamada kullanılan bir örnek için örneklere bakın [AtlAgent](https://github.com/Microsoft/VCSamples) ve [MultiRead](https://github.com/Microsoft/VCSamples).

## <a name="example"></a>Örnek

Bu örneği çağırır **db_source** veri kaynağı ile bağlantı oluşturmak için bir sınıf `ds` kullanarak Northwind veritabanı. `ds` dahili olarak kullanılan veri kaynağı için bir tanıtıcı `CMyCommand` sınıfı.

```cpp
// db_source_1.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[
  db_source(L"my_connection_string", name="ds"),
  db_command(L"select * from Products")
]
class CMyCommand {};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapı**, üye, yöntem, yerel|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Öznitelikleri](ole-db-consumer-attributes.md)
