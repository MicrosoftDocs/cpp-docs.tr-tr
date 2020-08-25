---
title: db_source (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_source
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
ms.openlocfilehash: f17a4ea183a24f7bf4e88137f4536ca082efdf85
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831391"
---
# <a name="db_source"></a>db_source

Bir veri kaynağına bir bağlantı oluşturur.

## <a name="syntax"></a>Söz dizimi

```cpp
[ db_source(db_source, name, hresult) ]
```

### <a name="parameters"></a>Parametreler

*db_source*<br/>
Veri kaynağına bağlanmak için kullanılan bağlantı dizesi. Bağlantı dizesinin biçimi için, Microsoft Data Access Components (MDAC) SDK 'sindeki [bağlantı dizeleri ve veri bağlantıları](/previous-versions/windows/desktop/ms718376(v=vs.85)) bölümüne bakın.

*ada*<br/>
Seçim Bir sınıfta **db_source** kullandığınızda *ad* , kendisine uygulanan **db_source** özniteliği olan bir veri kaynağı nesnesinin örneğidir (bkz. örnek 1). Yöntem uygulamasında **db_source** satır içi kullandığınızda *ad* , veri kaynağına erişmek için kullanılabilecek bir değişkendir (yönteme yereldir) (bkz. örnek 2). Bu *adı* , *source_name* `db_command` veri kaynağını bir komutla ilişkilendirmek için source_name parametresine geçirirsiniz.

*HRESULT*<br/>
Seçim Bu veritabanı komutunun HRESULT 'sini alacak değişkeni tanımlar. Değişken yoksa, özniteliği tarafından otomatik olarak eklenir.

## <a name="remarks"></a>Açıklamalar

**db_source** , birlikte OLE DB bir tüketici veri kaynağıyla bir bağlantıyı temsil eden bir [CDataSource](../../data/oledb/cdatasource-class.md) ve [CSession](../../data/oledb/csession-class.md) nesnesi oluşturur.

Bir sınıfta **db_source** kullandığınızda, `CSession` nesne sınıfının bir üyesi olur.

Bir yöntemde **db_source** kullandığınızda, eklenen kod yöntem kapsamı içinde yürütülür ve `CSession` nesne yerel bir değişken olarak oluşturulur.

**db_source** , bir sınıfa veya bir yöntem içinde veri kaynağı özellikleri ekler. `db_command`( *Db_source* *ad* parametresini *source_name* parametresi olarak alır) ile birlikte kullanılır.

Tüketici öznitelik sağlayıcısı bu özniteliği bir sınıfa uygularsa, derleyici sınıfı, sınıfın \_ verdiği addır ve ayrıca derleyici *,* *YourClassName*erişimcisinden türetilen *kendi ClassName* adlı bir sınıf oluşturur \_ *YourClassName*.  Sınıf Görünümü, her iki sınıfı da görürsünüz.

Bir uygulamada kullanılan bu özniteliğe bir örnek için bkz. [MultiRead](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer).

## <a name="example"></a>Örnek

Bu örnek **db_source** `ds` , Northwind veritabanını kullanarak veri kaynağıyla bağlantı oluşturmak için bir sınıftaki db_source çağırır. `ds` , sınıfında dahili olarak kullanılabilecek veri kaynağı için bir tanıtıcıdır `CMyCommand` .

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`** , üye, yöntem, yerel|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici öznitelikleri](ole-db-consumer-attributes.md)
