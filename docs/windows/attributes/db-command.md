---
title: db_command (C++ COM özniteliği)
ms.date: 07/10/2018
f1_keywords:
- vc-attr.db_command
helpviewer_keywords:
- db_command attribute
ms.assetid: 714c3e15-85d7-408b-9a7c-88505c3e5d24
ms.openlocfilehash: 136c82b2674f3c08f053de9676068c0fb4baac11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559477"
---
# <a name="dbcommand"></a>db_command

OLE DB komut oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
[ db_command(command, name, source_name, hresult, bindings, bulk_fetch)
]
```

### <a name="parameters"></a>Parametreler

*Komutu*<br/>
Bir komutu bir OLE DB komut metnini içeren dize. Basit bir örnektir:

```cpp
[ db_command ( command = "Select * from Products" ) ]
```

*Komut* söz dizimi aşağıdaki gibidir:

> bağlama parametresi blok 1 &nbsp; &nbsp;OLE DB komut bağlama parametresi bloğu 2 &nbsp; &nbsp;devamlılığın bloğunun OLE DB komutu bağlama parametresi 3...

A *bağlama parametresi blok* şu şekilde tanımlanır:

> **(\[**  *bindtype* **]** *szVar1* \[, *szVar2* \[, *nVar3* \[,...]]] **)**

burada:

- **(** veri bağlama bloğun başlangıcını işaretler.

- **\[** *bindtype* **]** büyük küçük harf duyarsız aşağıdaki dizelerini biri:

  - **\[db_column]** üye değişkenleri her bir satır kümesi sütununa bağlar.

  - **\[bindto]** (aynı  **\[db_column]**).

  - **\[Buna]** üye değişkenleri giriş parametresi olarak bağlar.

  - **\[out]** üye değişkenleri çıkış parametreleri olarak bağlar.

  - **\[Giriş, çıkış]** üye değişkenleri giriş/çıkış parametreleri olarak bağlar.

- *szVarX*, *nVarX* geçerli kapsam içinde bir üye değişkeni çözümlenir.

- **)** veri bağlama bloğunun sonunu işaretler.

Komut dizesi gibi bir veya daha fazla tanımlayıcıları içeriyorsa \[,], \[out], veya \[daraltma veya genişletme], **db_command** parametre eşleme oluşturur.

Komut dizesi gibi bir veya daha fazla parametre içeriyorsa \[db_column] veya \[bindto], **db_command** bir satır kümesi ve bu ilişkili değişkenler hizmet vermek üzere bir erişimci eşlemesi oluşturur. Bkz: [db_accessor](db-accessor.md) daha fazla bilgi için.

> [!NOTE]
> \[*bindtype*] söz dizimi ve *bağlamaları* parametresi geçerli değil kullanırken **db_command** sınıf düzeyinde.

Bağlama parametresi blokları bazı örnekleri aşağıda verilmiştir. Aşağıdaki örnek bağlar `m_au_fname` ve `m_au_lname` veri üyelerine `au_fname` ve `au_lname` sütunları pubs veritabanı yazarlar tablonun sırasıyla:

```cpp
TCHAR m_au_fname[21];
TCHAR m_au_lname[41];
TCHAR m_state[3] = 'CA';

[db_command (command = "SELECT au_fname([bindto]m_au_fname), au_lname([bindto]m_au_lname) " \
   "FROM dbo.authors " \
   "WHERE state = ?([in]m_state)")
]
```

*Adı*<br/>
(İsteğe bağlı) Satır kümesi ile çalışmak için kullandığınız işleyici adı. Belirtirseniz *adı*, **db_command** belirli bir sınıf oluşturur *adı*, kullanılabilen çapraz satır kümesi veya birden çok eylem sorgularını yürütmek için. Siz belirtmezseniz *adı*, sonuçların birden fazla satır kullanıcıya döndürülecek mümkün olmayacaktır.

*source_name*<br/>
(İsteğe bağlı) `CSession` Değişkeni veya bir sınıf örneğini `db_source` özniteliği uygulanmış komutu yürütür. Bkz: [db_source](db-source.md).

**db_command** denetimler için kullanılan değişkeni emin olmak için *source_name* belirtilen değişkeni işlevi veya genel kapsamlı bu nedenle geçerlidir.

*HRESULT*<br/>
(İsteğe bağlı) Bu veritabanı komutunun HRESULT alacak değişkeni tanımlar. Değişkeni mevcut değilse özniteliği tarafından otomatik olarak eklenecek.

*Bağlamaları*<br/>
(İsteğe bağlı) Bağlama parametrelerinde, OLE DB komutu ayrı sağlar.

İçin bir değer belirtirseniz *bağlamaları*, **db_command** ilişkili değer ayrıştırır ve değil ayrıştırmaz \[ *bindtype*] parametresi. Bu kullanım OLE DB sağlayıcısı sözdizimi kullanmanıza olanak tanır. Ayrıştırma, parametreleri, bağlama olmadan devre dışı bırakmak için belirtin `Bindings=""`.

İçin bir değer belirtmezseniz *bağlamaları*, **db_command** aranırken bağlama parametresi blok ayrıştırmaz '**(**' çizgidir **\[** _bindtype_**]** tarafından izlenen bir veya daha fazla önceden tanımlanmış C++ üye değişkenlerine tarafından izlenen parantez içine '**)**'. Ayraçlar arasındaki tüm metni ortaya çıkan komuttan kaldırılır ve bu parametreler, bu komut için sütun ve parametre bağlamaları oluşturmak için kullanılacak.

*bulk_fetch*<br/>
(İsteğe bağlı) Getirilecek satır sayısını belirten bir tamsayı değeri.

Varsayılan değer, tek satır getirme belirtir. 1 ' dir (satır türünde olacaktır [CRowset](../../data/oledb/crowset-class.md)).

Toplu satır getirme 1'den büyük bir değer belirtir. Toplu satır getirme başvuran birden çok satır işleyicilerini getirilecek yeteneği toplu satır kümeleri (satır türünde olacaktır [CBulkRowset](../../data/oledb/cbulkrowset-class.md) ve çağıracak `SetRows` belirtilen sayıda satırı ile).

Varsa *bulk_fetch* değerden daha az `SetRows` sıfır döndürür.

## <a name="remarks"></a>Açıklamalar

**db_command** oluşturur bir [CCommand](../../data/oledb/ccommand-class.md) bir komutu çalıştırmak için bir OLE DB Tüketicisi tarafından kullanılan nesne.

Kullanabileceğiniz **db_command** kapsamıyla; sınıf veya işlev temel fark kapsamındaysa `CCommand` nesne. İşlev kapsamı ile veri bağlamaları gibi işlevi sonunda sona erer. Sınıfı hem de işlev kapsamı kullanımları içeren OLE DB tüketici şablonu sınıfı `CCommand<>`, ancak şablon değişkenlerini işlevi ve sınıf çalışmaları için farklı. İşlev durumda bağlamaları yapılmaz bir `Accessor` , anımsatıcıyı yerel değişkenler sınıfı kullanım çıkarımlar sırada bir `CAccessor`-türetilmiş sınıf için bağımsız değişken olarak. Bir sınıf özniteliği kullanıldığında **db_command** ile birlikte çalışır **db_column**.

**db_command** bir sonuç kümesi döndürmüyor komutları yürütmek için kullanılabilir.

Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uygulandığında, derleyici sınıf için yeniden adlandıracağını \_ *YourClassName*erişimci burada *YourClassName* verdiğiniz addır sınıf ve derleyici adlı bir sınıf oluşturur ayrıca *YourClassName*, öğesinden türetildiğini \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, hem sınıflarını görürsünüz.

## <a name="example"></a>Örnek

Bu örnek, durum sütununu 'CA' eşleştiği bir tablodan ilk ve son adlarını seçen bir komutu tanımlar. **db_command** oluşturur ve üzerinde çağırabilirsiniz Sihirbazı tarafından oluşturulan işlevleri gibi bir satır okur [OpenAll ve CloseAll](../../data/oledb/consumer-wizard-generated-methods.md), yanı `CRowset` üye işlevleri gibi [MoveNext](../../data/oledb/crowset-movenext.md).

Bu kod, pubs veritabanına bağlar kendi bağlantı dizesi sağlamanız gerektiğini unutmayın. Geliştirme ortamında nasıl yapılacağı hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir veritabanı ve varolan nesnelere Gözat bağlanma](/sql/ssdt/how-to-connect-to-a-database-and-browse-existing-objects) ve [yeni bağlantı ekleme](/visualstudio/data-tools/add-new-connections).

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

## <a name="example"></a>Örnek

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

## <a name="example"></a>Örnek

Bu örnekte `db_source` bir veri kaynağı sınıfı üzerinde `CMySource`, ve `db_command` komut sınıflarda `CCommand1` ve `CCommand2`.

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapı**, üye, yöntem, yerel|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Öznitelikleri](ole-db-consumer-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)
