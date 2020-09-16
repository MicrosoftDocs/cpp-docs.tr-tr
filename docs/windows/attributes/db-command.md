---
title: db_command (C++ COM özniteliği)
ms.date: 07/10/2018
f1_keywords:
- vc-attr.db_command
helpviewer_keywords:
- db_command attribute
ms.assetid: 714c3e15-85d7-408b-9a7c-88505c3e5d24
ms.openlocfilehash: 868ff862cc41543c8ebc7880a5d1a9a7e6b103f3
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684592"
---
# <a name="db_command"></a>db_command

Bir OLE DB komutu oluşturur.

## <a name="syntax"></a>Söz dizimi

```cpp
[ db_command(command, name, source_name, hresult, bindings, bulk_fetch)
]
```

### <a name="parameters"></a>Parametreler

*komutundaki*<br/>
OLE DB komutunun metnini içeren bir komut dizesi. Basit bir örnek:

```cpp
[ db_command ( command = "Select * from Products" ) ]
```

*Komut* söz dizimi aşağıdaki gibidir:

> bağlama parametresi bloğu 1 \
> &nbsp;&nbsp;OLE DB komutu \
> bağlama parametresi bloğu 2 \
> &nbsp;&nbsp;OLE DB komutunun devamı \
> bağlama parametresi bloğu 3 \
> ...

*Bağlama parametresi bloğu* aşağıdaki gibi tanımlanır:

> **( \[ ** *BindType* **]** *szVar1* \[ , *szVar2* \[ , *nVar3* \[ ,...]]] **)**

burada:

- **(** veri bağlama bloğunun başlangıcını işaretler.

- **\[***BindType* **]** , şu büyük/küçük harfe duyarsız dizelerden biridir:

  - ** \[ db_column]** , üye değişkenlerinin her birini bir satır kümesindeki bir sütuna bağlar.

  - ** \[ BindTo]** ( ** \[ db_column]**)).

  - ** \[ içinde]** üye değişkenlerini giriş parametreleri olarak bağlar.

  - ** \[ out]** üye değişkenlerini çıkış parametresi olarak bağlar.

  - ** \[ in, out]** üye değişkenlerini giriş/çıkış parametreleri olarak bağlar.

- *SzVarX*, *nvarx* , geçerli kapsam içindeki bir üye değişkenine çözümleniyor.

- **)** veri bağlama bloğunun sonunu işaretler.

Komut dizesinde \[ , içinde], out] veya ın/out gibi bir veya daha fazla tanımlayıcı varsa \[ \[ **db_command** bir parametre eşlemesi oluşturur.

Komut dizesinde db_column] veya BindTo] gibi bir veya daha fazla parametre varsa \[ \[ **db_command** , bu bağlantılı değişkenlere hizmet vermek için bir satır kümesi ve erişimci haritası oluşturur. Daha fazla bilgi için bkz. [db_accessor](db-accessor.md) .

> [!NOTE]
> \[*BindType*] sınıf düzeyinde **db_command** kullanılırken sözdizimi ve *bağlamalar* parametresi geçerli değildir.

Bu parametre blokları bağlama örnekleri aşağıda verilmiştir. Aşağıdaki örnek, `m_au_fname` ve `m_au_lname` veri üyelerini, `au_fname` `au_lname` pubs veritabanındaki yazarlar tablosunun sırasıyla ve sütunlarına bağlar:

```cpp
TCHAR m_au_fname[21];
TCHAR m_au_lname[41];
TCHAR m_state[3] = 'CA';

[db_command (command = "SELECT au_fname([bindto]m_au_fname), au_lname([bindto]m_au_lname) " \
   "FROM dbo.authors " \
   "WHERE state = ?([in]m_state)")
]
```

*ada*<br/>
Seçim Satır kümesi ile birlikte çalışmak için kullandığınız tanıtıcının adı. *Ad*belirtirseniz **db_command** , belirtilen *ada*sahip bir sınıf oluşturur ve bu, satır kümesinde çapraz geçiş yapmak veya birden çok eylem sorgusu yürütmek için kullanılabilir. *Ad*belirtmezseniz, kullanıcıya birden fazla sonuç satırı döndürmek mümkün olmayacaktır.

*source_name*<br/>
Seçim `CSession` `db_source` Komutun çalıştırıldığı özniteliğe uygulanan özniteliği olan bir sınıfın değişkeni veya örneği. Bkz. [db_source](db-source.md).

**db_command** , *source_name* için kullanılan değişkenin geçerli olduğundan emin olmak için kontrol eder, bu nedenle belirtilen değişken işlev veya genel kapsam içinde olmalıdır.

*HRESULT*<br/>
Seçim Bu veritabanı komutunun HRESULT 'sini alacak değişkeni tanımlar. Değişken yoksa, özniteliği tarafından otomatik olarak eklenir.

*Lara*<br/>
Seçim OLE DB komutundan bağlama parametrelerini ayırmanızı sağlar.

*Bağlamalar*için bir değer belirtirseniz, **db_command** ilişkili değeri ayrıştırır ve \[ *BindType*] parametresini ayrıştırmaz. Bu kullanım OLE DB sağlayıcı sözdizimini kullanmanıza olanak sağlar. Ayrıştırmayı devre dışı bırakmak için, parametreleri bağlama olmadan öğesini belirtin `Bindings=""` .

*Bağlamalar*için bir değer belirtmezseniz, **db_command** bağlama parametre bloğunu ayrıştırarak, parantez içinde '**(**', sonra **\[** _BindType_**]** öğesini, ardından bir veya daha fazla önceden tanımlanmış C++ üye değişkenlerini ve ardından '**)**' sözcüğünü arayarak. Ayraçlar arasındaki tüm metinler, sonuçta elde edilen komuttan çıkarılır ve bu komut için sütun ve parametre bağlamaları oluşturmak için bu parametreler kullanılacaktır.

*bulk_fetch*<br/>
Seçim Getirilecek satır sayısını belirten bir tamsayı değeri.

Varsayılan değer 1 ' dir ve tek satır getirmeyi belirtir (satır kümesi [CRowset](../../data/oledb/crowset-class.md)türünde olacaktır).

1 ' den büyük bir değer, toplu satır getirmeyi belirtir. Toplu satır getirme, toplu satır kümelerinin birden çok satır tanıtıcısı getirme özelliğine başvurur (satır kümesi [CBulkRowset](../../data/oledb/cbulkrowset-class.md) türünde olacaktır ve `SetRows` belirtilen sayıda satır ile çağracaktır).

*Bulk_fetch* birden küçükse, `SetRows` sıfır döndürür.

## <a name="remarks"></a>Açıklamalar

**db_command** bir komut yürütmek için bir OLE DB tüketicisi tarafından kullanılan bir [CCommand](../../data/oledb/ccommand-class.md) nesnesi oluşturur.

**Db_command** , sınıf veya işlev kapsamıyla kullanabilirsiniz; Ana fark nesnenin kapsamıdır `CCommand` . İşlev kapsamında, bağlamalar gibi veriler işlev sonunda sonlandırılır. Hem sınıf hem de işlev kapsamı kullanımları OLE DB Tüketici şablonu sınıfını içerir `CCommand<>` , ancak şablon bağımsız değişkenleri işlev ve sınıf durumları için farklılık gösterir. İşlev durumunda bağlamalar, `Accessor` yerel değişkenleri içeren bir öğesine yapılır, ancak sınıf kullanımı `CAccessor` bağımsız değişken olarak bir türetilmiş sınıf çıkarsken. Sınıf özniteliği olarak kullanıldığında, **db_command** **db_column**ile birlikte çalışacaktır.

**db_command** , bir sonuç kümesi döndürmeyen komutları yürütmek için kullanılabilir.

Tüketici öznitelik sağlayıcısı bu özniteliği bir sınıfa uygularsa, derleyici sınıfı, sınıfın \_ verdiği addır ve ayrıca derleyici *,* *YourClassName*erişimcisinden türetilen *kendi ClassName* adlı bir sınıf oluşturur \_ *YourClassName*.  Sınıf Görünümü, her iki sınıfı da görürsünüz.

## <a name="examples"></a>Örnekler

Bu örnek, durum sütununun ' CA ' ile eşleştiği bir tablonun ilk ve son adlarını seçen bir komutu tanımlar. **db_command** , üzerinde [OpenAll ve CloseAll](../../data/oledb/consumer-wizard-generated-methods.md)gibi sihirbaz tarafından üretilen işlevleri ve MoveNext gibi üye işlevlerini çağırabilmeniz için bir satır kümesi oluşturup okur `CRowset` . [MoveNext](../../data/oledb/crowset-movenext.md)

Bu kodun, Pubs veritabanına bağlanan kendi Bağlantı dizenizi sağlamanızı gerektirdiğini unutmayın. Geliştirme ortamında bunun nasıl yapılacağı hakkında bilgi için bkz. [nasıl yapılır: veritabanına bağlanma ve var olan nesnelere gözatmaya](/sql/ssdt/how-to-connect-to-a-database-and-browse-existing-objects) ve [yeni bağlantılar ekleme](/visualstudio/data-tools/add-new-connections).

```cpp
// db_command.h
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

#pragma once

[  db_source(L"your connection string"), db_command(L" \
      SELECT au_lname, au_fname \
      FROM dbo.authors \
      WHERE state = 'CA'")  ]

struct CAuthors {
   // In order to fix several issues with some providers, the code below may bind
   // columns in a different order than reported by the provider

   DBSTATUS m_dwau_lnameStatus;
   DBSTATUS m_dwau_fnameStatus;
   DBLENGTH m_dwau_lnameLength;
   DBLENGTH m_dwau_fnameLength;

   [ db_column("au_lname", status="m_dwau_lnameStatus", length="m_dwau_lnameLength") ] TCHAR m_au_lname[41];
   [ db_column("au_fname", status="m_dwau_fnameStatus", length="m_dwau_fnameLength") ] TCHAR m_au_fname[21];

   [ db_param("7", paramtype="DBPARAMIO_INPUT") ] TCHAR m_state[3];

   void GetRowsetProperties(CDBPropSet* pPropSet) {
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   }
};
```

```cpp
// db_command.cpp
// compile with: /c
#include "db_command.h"

int main(int argc, _TCHAR* argv[]) {
   HRESULT hr = CoInitialize(NULL);

   // Instantiate rowset
   CAuthors rs;

   // Open rowset and move to first row
   strcpy_s(rs.m_state, sizeof(rs.m_state), _T("CA"));
   hr = rs.OpenAll();
   hr = rs.MoveFirst();

   // Iterate through the rowset
   while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET ) {
      // Print out the column information for each row
      printf("First Name: %s, Last Name: %s\n", rs.m_au_fname, rs.m_au_lname);
      hr = rs.MoveNext();
   }

   rs.CloseAll();
   CoUninitialize();
}
```

Bu örnek `db_source` , bir veri kaynağı sınıfında `CMySource` ve `db_command` komut sınıflarında `CCommand1` ve `CCommand2` ' de kullanılır.

```cpp
// db_command_2.cpp
// compile with: /c
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>
// class usage for both db_source and db_command

[  db_source(L"your connection string"), db_command(L" \
      SELECT au_lname, au_fname \
      FROM dbo.authors \
      WHERE state = 'CA'")  ]
struct CMySource {
   HRESULT OpenDataSource() {
      return S_OK;
   }
};

[db_command(command = "SELECT * FROM Products")]
class CCommand1 {};

[db_command(command = "SELECT FNAME, LNAME FROM Customers")]
class CCommand2 {};

int main() {
   CMySource s;
   HRESULT hr = s.OpenDataSource();
   if (SUCCEEDED(hr)) {
      CCommand1 c1;
      hr = c1.Open(s);

      CCommand2 c2;
      hr = c2.Open(s);
   }

   s.CloseDataSource();
}
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`** , üye, yöntem, yerel|
|**Tekrarlanabilir**|No|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici öznitelikleri](ole-db-consumer-attributes.md)<br/>
[Tek başına öznitelikler](stand-alone-attributes.md)
