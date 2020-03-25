---
title: db_source (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_source
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
ms.openlocfilehash: 6346a8d6f60313dc17bbcbad062aa888857f0b67
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167283"
---
# <a name="db_source"></a>db_source

Bir veri kaynağına bir bağlantı oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
[ db_source(db_source, name, hresult) ]
```

### <a name="parameters"></a>Parametreler

*db_source*<br/>
Veri kaynağına bağlanmak için kullanılan bağlantı dizesi. Bağlantı dizesinin biçimi için, Microsoft Data Access Components (MDAC) SDK 'sindeki [bağlantı dizeleri ve veri bağlantıları](/previous-versions/windows/desktop/ms718376(v=vs.85)) bölümüne bakın.

*ada*<br/>
Seçim Bir sınıfta **db_source** kullandığınızda *ad* , kendisine uygulanan **db_source** özniteliği olan bir veri kaynağı nesnesinin örneğidir (bkz. örnek 1). Yöntem uygulamasında **db_source** satır içi kullandığınızda *ad* , veri kaynağına erişmek için kullanılabilecek bir değişkendir (yönteme yereldir) (bkz. örnek 2). Veri kaynağını bir komutla ilişkilendirmek için bu *adı* `db_command` *source_name* parametresine geçirirsiniz.

*HRESULT*<br/>
Seçim Bu veritabanı komutunun HRESULT 'sini alacak değişkeni tanımlar. Değişken yoksa, özniteliği tarafından otomatik olarak eklenir.

## <a name="remarks"></a>Açıklamalar

**db_source** , birlikte OLE DB bir tüketici veri kaynağıyla bir bağlantıyı temsil eden bir [CDataSource](../../data/oledb/cdatasource-class.md) ve [CSession](../../data/oledb/csession-class.md) nesnesi oluşturur.

Bir sınıfta **db_source** kullandığınızda, `CSession` nesnesi sınıfının bir üyesi olur.

Bir yöntemde **db_source** kullandığınızda, eklenen kod yöntem kapsamı içinde yürütülür ve `CSession` nesnesi yerel bir değişken olarak oluşturulur.

**db_source** , bir sınıfa veya bir yöntem içinde veri kaynağı özellikleri ekler. `db_command` ( *db_source* *ad* parametresini *source_name* parametresi olarak alır) ile birlikte kullanılır.

Tüketici öznitelik sağlayıcısı bu özniteliği bir sınıfa uygularsa, derleyici sınıfı verdiğiniz ad *olan ClassName ' ın adını \_olarak*yeniden adlandırır ve derleyici *YourClassName* Ayrıca, \_*YourClassName*erişimcisinden türetilen, *YourClassName*adlı bir sınıf oluşturur.  Sınıf Görünümü, her iki sınıfı da görürsünüz.

Bir uygulamada kullanılan bu özniteliğe bir örnek için bkz. [MultiRead](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer).

## <a name="example"></a>Örnek

Bu örnek, Northwind veritabanını kullanarak `ds` veri kaynağıyla bağlantı oluşturmak için bir sınıftaki **db_source** çağırır. `ds`, `CMyCommand` sınıfında dahili olarak kullanılabilecek veri kaynağı için bir tanıtıcıdır.

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
|**Uygulama hedefi**|**sınıf**, **Yapı**, üye, yöntem, yerel|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Öznitelikleri](ole-db-consumer-attributes.md)
