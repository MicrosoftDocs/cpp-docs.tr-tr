---
description: 'Hakkında daha fazla bilgi edinin: OLE DB tüketici şablonları için makrolar ve genel Işlevler'
title: OLE DB Tüketici Şablonları için Makrolar ve Genel İşlevler
ms.date: 02/11/2019
f1_keywords:
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
- BEGIN_ACCESSOR
- BEGIN_ACCESSOR_MAP
- END_ACCESSOR
- END_ACCESSOR_MAP
- BEGIN_COLUMN_MAP
- BLOB_ENTRY
- BLOB_ENTRY_LENGTH
- BLOB_ENTRY_LENGTH_STATUS
- BLOB_ENTRY_STATUS
- BLOB_NAME
- BLOB_NAME_LENGTH
- BLOB_NAME_LENGTH_STATUS
- BLOB_NAME_STATUS
- BOOKMARK_ENTRY
- COLUMN_ENTRY
- COLUMN_ENTRY_EX
- COLUMN_ENTRY_LENGTH
- COLUMN_ENTRY_LENGTH_STATUS
- COLUMN_ENTRY_PS
- COLUMN_ENTRY_PS_LENGTH
- COLUMN_ENTRY_PS_LENGTH_STATUS
- COLUMN_ENTRY_PS_STATUS
- COLUMN_ENTRY_STATUS
- COLUMN_ENTRY_TYPE
- COLUMN_ENTRY_TYPE_SIZE
- COLUMN_NAME
- COLUMN_NAME_EX
- COLUMN_NAME_LENGTH
- COLUMN_NAME_LENGTH_STATUS
- COLUMN_NAME_PS
- COLUMN_NAME_PS_LENGTH
- COLUMN_NAME_PS_LENGTH_STATUS
- COLUMN_NAME_PS_STATUS
- COLUMN_NAME_STATUS
- COLUMN_NAME_TYPE
- COLUMN_NAME_TYPE_PS
- COLUMN_NAME_TYPE_SIZE
- COLUMN_NAME_TYPE_STATUS
- END_COLUMN_MAP
- DEFINE_COMMAND
- DEFINE_COMMAND_EX
- BEGIN_PARAM_MAP
- END_PARAM_MAP
- SET_PARAM_TYPE
helpviewer_keywords:
- OLE DB consumer templates, macros
- macros, OLE DB consumer template
- AtlTraceErrorRecords function
- BEGIN_ACCESSOR macro, syntax
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR_MAP macro
- END_ACCESSOR macro
- END_ACCESSOR_MAP macro
- BEGIN_COLUMN_MAP macro
- BLOB_ENTRY macro
- BLOB_ENTRY_LENGTH macro
- BLOB_ENTRY_LENGTH_STATUS macro
- BLOB_ENTRY_STATUS macro
- BLOB_NAME macro
- BLOB_NAME_LENGTH macro
- BLOB_NAME_LENGTH_STATUS macro
- BLOB_NAME_STATUS macro
- BOOKMARK_ENTRY macro
- COLUMN_ENTRY macro
- COLUMN_ENTRY_EX macro
- COLUMN_ENTRY_LENGTH macro
- COLUMN_ENTRY_LENGTH_STATUS macro
- COLUMN_ENTRY_PS macro
- COLUMN_ENTRY_PS_LENGTH macro
- COLUMN_ENTRY_PS_LENGTH_STATUS macro
- COLUMN_ENTRY_PS_STATUS macro
- COLUMN_ENTRY_STATUS macro
- COLUMN_ENTRY_TYPE macro
- COLUMN_ENTRY_TYPE_SIZE macro
- COLUMN_NAME macro
- COLUMN_NAME_EX macro
- COLUMN_NAME_LENGTH macro
- COLUMN_NAME_LENGTH_STATUS macro
- COLUMN_NAME_PS macro
- COLUMN_NAME_PS_LENGTH macro
- COLUMN_NAME_PS_LENGTH_STATUS macro
- COLUMN_NAME_PS_STATUS macro
- COLUMN_NAME_STATUS macro
- COLUMN_NAME_TYPE macro
- COLUMN_NAME_TYPE_PS macro
- COLUMN_NAME_TYPE_SIZE macro
- COLUMN_NAME_TYPE_STATUS macro
- END_COLUMN_MAP macro
- DEFINE_COMMAND macro
- DEFINE_COMMAND_EX macro
- BEGIN_PARAM_MAP macro
- END_PARAM_MAP macro
- SET_PARAM_TYPE macro
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
ms.openlocfilehash: fb6e126483690e43ceaf3814f6c288ecfdc69da1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287079"
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>OLE DB Tüketici Şablonları için Makrolar ve Genel İşlevler

OLE DB tüketici şablonları aşağıdaki makroları ve genel işlevleri içerir:

## <a name="global-functions"></a>Genel Işlevler

| Ad | Açıklama |
|-|-|
|[AtlTraceErrorRecords](#atltraceerrorrecords)|Hata döndürülürse OLE DB hata kayıt bilgilerini döküm cihazına döker.|

## <a name="accessor-map-macros"></a>Erişimci eşleme makroları

| Ad | Açıklama |
|-|-|
|[BEGIN_ACCESSOR](#begin_accessor)|Erişimci girişinin başlangıcını işaretler.|
|[BEGIN_ACCESSOR_MAP](#begin_accessor_map)|Erişimci eşleme girdilerinin başlangıcını işaretler.|
|[END_ACCESSOR](#end_accessor)|Erişimci girişinin sonunu işaretler.|
|[END_ACCESSOR_MAP](#end_accessor_map)|Erişimci eşleme girdilerinin sonunu işaretler.|

## <a name="column-map-macros"></a>Sütun Haritası makroları

| Ad | Açıklama |
|-|-|
|[BEGIN_COLUMN_MAP](#begin_column_map)|Kullanıcı kayıt sınıfındaki sütun eşleme girdilerinin başlangıcını işaretler.|
|[BLOB_ENTRY](#blob_entry)|İkili büyük nesne (BLOB) bağlamak için kullanılır.|
|[BLOB_ENTRY_LENGTH](#blob_entry_length)|BLOB veri sütununun uzunluğunu raporlar.|
|[BLOB_ENTRY_LENGTH_STATUS](#blob_entry_length_status)|BLOB veri sütununun uzunluğunu ve durumunu raporlar.|
|[BLOB_ENTRY_STATUS](#blob_entry_status)|BLOB veri sütununun durumunu raporlar.|
|[BLOB_NAME](#blob_name)|Bir ikili büyük nesneyi sütun adına göre bağlamak için kullanılır.|
|[BLOB_NAME_LENGTH](#blob_name_length)|BLOB veri sütununun uzunluğunu raporlar.|
|[BLOB_NAME_LENGTH_STATUS](#blob_name_length_status)|BLOB veri sütununun uzunluğunu ve durumunu raporlar.|
|[BLOB_NAME_STATUS](#blob_name_status)|BLOB veri sütununun durumunu raporlar.|
|[BOOKMARK_ENTRY](#bookmark_entry)|Satır kümesindeki bir yer işareti girişini temsil eder. Yer işareti girişi, özel bir sütun girişi türüdür.|
|[COLUMN_ENTRY](#column_entry)|Veritabanında belirli bir sütuna bağlamayı temsil eder.|
|[COLUMN_ENTRY_EX](#column_entry_ex)|Veritabanındaki belirli bir sütuna olan bağlamayı temsil eder. *Tür*, *uzunluk*, *duyarlık*, *Ölçek* ve *durum* parametrelerini destekler.|
|[COLUMN_ENTRY_LENGTH](#column_entry_length)|Veritabanındaki belirli bir sütuna olan bağlamayı temsil eder. *Uzunluk* değişkenini destekler.|
|[COLUMN_ENTRY_LENGTH_STATUS](#column_entry_length_status)|Veritabanındaki belirli bir sütuna olan bağlamayı temsil eder. *Durum* ve *uzunluk* parametrelerini destekler.|
|[COLUMN_ENTRY_PS](#column_entry_ps)|Veritabanındaki belirli bir sütuna olan bağlamayı temsil eder. *Duyarlık* ve *Ölçek* parametrelerini destekler.|
|[COLUMN_ENTRY_PS_LENGTH](#column_entry_ps_length)|Veritabanındaki belirli bir sütuna olan bağlamayı temsil eder. *Length* değişkenini, *duyarlık* ve *Ölçek* parametrelerini destekler.|
|[COLUMN_ENTRY_PS_LENGTH_STATUS](#column_entry_ps_length_status)|Veritabanındaki belirli bir sütuna olan bağlamayı temsil eder. *Durum* ve *uzunluk* değişkenlerini, *duyarlık* ve *Ölçek* parametrelerini destekler.|
|[COLUMN_ENTRY_PS_STATUS](#column_entry_ps_status)|Veritabanındaki belirli bir sütuna olan bağlamayı temsil eder. *Durum* değişkenini, *duyarlık* ve *Ölçek* parametrelerini destekler.|
|[COLUMN_ENTRY_STATUS](#column_entry_status)|Veritabanındaki belirli bir sütuna olan bağlamayı temsil eder. *Durum* değişkenini destekler.|
|[COLUMN_ENTRY_TYPE](#column_entry_type)|Veritabanında belirli bir sütuna bağlamayı temsil eder. *Tür* parametresini destekler.|
|[COLUMN_ENTRY_TYPE_SIZE](#column_entry_type_size)|Veritabanındaki belirli bir sütuna olan bağlamayı temsil eder. *Tür* ve *Boyut* parametrelerini destekler.|
|[COLUMN_NAME](#column_name)|Veritabanında bir ada göre belirli bir sütuna bağlamayı temsil eder.|
|[COLUMN_NAME_EX](#column_name_ex)|Veritabanında bir ada göre belirli bir sütuna bağlamayı temsil eder. Veri türü, boyut, duyarlık, ölçek, sütun uzunluğu ve sütun durumunun belirtimini destekler.|
|[COLUMN_NAME_LENGTH](#column_name_length)|Veritabanında bir ada göre belirli bir sütuna bağlamayı temsil eder. Sütun uzunluğunun belirtimini destekler.|
|[COLUMN_NAME_LENGTH_STATUS](#column_name_length_status)|Veritabanında bir ada göre belirli bir sütuna bağlamayı temsil eder. Sütun uzunluğu ve durumunun belirtimini destekler.|
|[COLUMN_NAME_PS](#column_name_ps)|Veritabanında bir ada göre belirli bir sütuna bağlamayı temsil eder. Duyarlık ve ölçek belirtimini destekler.|
|[COLUMN_NAME_PS_LENGTH](#column_name_ps_length)|Veritabanında bir ada göre belirli bir sütuna bağlamayı temsil eder. Duyarlık, ölçek ve sütun uzunluğunun belirtimini destekler.|
|[COLUMN_NAME_PS_LENGTH_STATUS](#column_name_ps_length_status)|Veritabanında bir ada göre belirli bir sütuna bağlamayı temsil eder. Duyarlık, ölçek, sütun uzunluğu ve sütun durumunun belirtimini destekler.|
|[COLUMN_NAME_PS_STATUS](#column_name_ps_status)|Veritabanında bir ada göre belirli bir sütuna bağlamayı temsil eder. Duyarlık, ölçek ve sütun durumunun belirtimini destekler.|
|[COLUMN_NAME_STATUS](#column_name_status)|Veritabanında bir ada göre belirli bir sütuna bağlamayı temsil eder. Sütun durumunun belirtimini destekler.|
|[COLUMN_NAME_TYPE](#column_name_type)|Veritabanında bir ada göre belirli bir sütuna bağlamayı temsil eder. Veri türü belirtimini destekler.|
|[COLUMN_NAME_TYPE_PS](#column_name_type_ps)|Veritabanında bir ada göre belirli bir sütuna bağlamayı temsil eder. Veri türü, duyarlık ve ölçek belirtimini destekler.|
|[COLUMN_NAME_TYPE_SIZE](#column_name_type_size)|Veritabanında bir ada göre belirli bir sütuna bağlamayı temsil eder. Veri türü ve boyutunun belirtimini destekler.|
|[COLUMN_NAME_TYPE_STATUS](#column_name_type_status)|Veritabanında bir ada göre belirli bir sütuna bağlamayı temsil eder. Veri türü ve sütun durumunun belirtimini destekler.|
|[END_COLUMN_MAP](#end_column_map)|Sütun eşleme girdilerinin sonunu işaretler.|

## <a name="command-macros"></a>Komut makroları

| Ad | Açıklama |
|-|-|
|[DEFINE_COMMAND](#define_command)|[CCommand](../../data/oledb/ccommand-class.md) sınıfı kullanılırken satır kümesini oluşturmak için kullanılacak komutu belirtir. Yalnızca belirtilen uygulama türüyle eşleşen dize türlerini kabul eder (ANSI veya Unicode). DEFINE_COMMAND yerine [DEFINE_COMMAND_EX](#define_command_ex) kullanmanız önerilir.|
|[DEFINE_COMMAND_EX](#define_command_ex)|[CCommand](../../data/oledb/ccommand-class.md) sınıfı kullanılırken satır kümesini oluşturmak için kullanılacak komutu belirtir. ANSI ve Unicode uygulamalarını destekler.|

## <a name="parameter-map-macros"></a>Parametre eşleme makroları

| Ad | Açıklama |
|-|-|
|[BEGIN_PARAM_MAP](#begin_param_map)|Kullanıcı kayıt sınıfındaki parametre eşleme girdilerinin başlangıcını işaretler.|
|[END_PARAM_MAP](#end_param_map)|Parametre eşleme girdilerinin sonunu işaretler.|
|[SET_PARAM_TYPE](#set_param_type)|Giriş, çıkış veya giriş/çıkış olarak SET_PARAM_TYPE makrosunu izleyen COLUMN_ENTRY makroları belirtir.|

### <a name="atltraceerrorrecords"></a><a name="atltraceerrorrecords"></a> AtlTraceErrorRecords

Hata döndürülürse OLE DB hata kayıt bilgilerini döküm cihazına döker.

#### <a name="syntax"></a>Sözdizimi

```cpp
inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);
```

#### <a name="parameters"></a>Parametreler

*hErr*<br/>
'ndaki OLE DB Tüketici şablonu üye işlevi tarafından döndürülen bir HRESULT.

#### <a name="remarks"></a>Açıklamalar

*Herr* S_OK değilse, `AtlTraceErrorRecords` OLE DB hata kayıt bilgilerini döküm cihazına (çıktı penceresinin veya bir dosyanın **hata ayıklama** sekmesi) döker. Sağlayıcıdan elde edilen hata kayıt bilgileri, her bir hata kaydı girişi için satır numarası, kaynak, açıklama, yardım dosyası, bağlam ve GUID içerir. `AtlTraceErrorRecords` Bu bilgileri yalnızca hata ayıklama yapılarında döker. Yayın yapıları ' nda, en iyi duruma getirilmiş boş bir saplama olur. Daha fazla bilgi için bkz. [CDBErrorInfo sınıfı](../../data/oledb/cdberrorinfo-class.md).

### <a name="begin_accessor"></a><a name="begin_accessor"></a> BEGIN_ACCESSOR

Erişimci girişinin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_ACCESSOR(num, bAuto)
```

#### <a name="parameters"></a>Parametreler

*numaraları*<br/>
'ndaki Bu erişimci eşlemesindeki erişimcinin sıfır-fark numarası.

*bAuto*<br/>
'ndaki Bu erişimcinin bir otomatik erişimci mi yoksa el ile bir erişimci mi olduğunu belirtir. Eğer **`true`** , erişimci Auto ise, **`false`** erişimci el ile yapılır. Otomatik erişimci, veri taşıma işlemlerinde sizin için getirilir anlamına gelir.

#### <a name="remarks"></a>Açıklamalar

Bir satır kümesinde birden çok erişimci olması durumunda BEGIN_ACCESSOR_MAP belirtmeniz ve her bir erişimci için BEGIN_ACCESSOR makrosunu kullanmanız gerekir. BEGIN_ACCESSOR makrosu END_ACCESSOR makrosu ile tamamlanır. BEGIN_ACCESSOR_MAP makrosu END_ACCESSOR_MAP makrosu ile tamamlanır.

#### <a name="example"></a>Örnek

Bkz. [BEGIN_ACCESSOR_MAP](#begin_accessor_map).

### <a name="begin_accessor_map"></a><a name="begin_accessor_map"></a> BEGIN_ACCESSOR_MAP

Erişimci eşleme girdilerinin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_ACCESSOR_MAP(x, num)
```

#### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Kullanıcı kayıt sınıfının adı.

*numaraları*<br/>
'ndaki Bu erişimci eşlemesindeki erişimcilerinin sayısı.

#### <a name="remarks"></a>Açıklamalar

Bir satır kümesinde birden çok erişimci olması durumunda, başlangıçta BEGIN_ACCESSOR_MAP belirtmeniz ve her bir erişimci için BEGIN_ACCESSOR makrosunu kullanmanız gerekir. BEGIN_ACCESSOR makrosu END_ACCESSOR makrosu ile tamamlanır. Erişimci eşlemesi END_ACCESSOR_MAP makrosu ile tamamlanır.

Kullanıcı kaydında yalnızca bir erişimci varsa, [BEGIN_COLUMN_MAP](#begin_column_map)makrosunu kullanın.

#### <a name="example"></a>Örnek

```cpp
class CArtistsAccessor
{
public:
// Data Elements
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];
   short m_nAge;

// Output binding map
BEGIN_ACCESSOR_MAP(CArtistsAccessor, 2)
   BEGIN_ACCESSOR(0, true)
      COLUMN_ENTRY(1, m_szFirstName)
      COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false) // Not an auto accessor
      COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsAccessor, L" \
   SELECT \
      FirstName, \
      LastName, \
      Age \
      FROM Artists")
};
```

### <a name="end_accessor"></a><a name="end_accessor"></a> END_ACCESSOR

Erişimci girişinin sonunu işaretler.

#### <a name="syntax"></a>Syntax

```cpp
END_ACCESSOR()
```

#### <a name="remarks"></a>Açıklamalar

Bir satır kümesinde birden çok erişimci için, BEGIN_ACCESSOR_MAP belirtmeniz ve her bir erişimci için BEGIN_ACCESSOR makrosunu kullanmanız gerekir. BEGIN_ACCESSOR makrosu END_ACCESSOR makrosu ile tamamlanır. BEGIN_ACCESSOR_MAP makrosu END_ACCESSOR_MAP makrosu ile tamamlanır.

#### <a name="example"></a>Örnek

Bkz. [BEGIN_ACCESSOR_MAP](#begin_accessor_map).

### <a name="end_accessor_map"></a><a name="end_accessor_map"></a> END_ACCESSOR_MAP

Erişimci eşleme girdilerinin sonunu işaretler.

#### <a name="syntax"></a>Syntax

```cpp
END_ACCESSOR_MAP()
```

#### <a name="remarks"></a>Açıklamalar

Bir satır kümesinde birden çok erişimci için, BEGIN_ACCESSOR_MAP belirtmeniz ve her bir erişimci için BEGIN_ACCESSOR makrosunu kullanmanız gerekir. BEGIN_ACCESSOR makrosu END_ACCESSOR makrosu ile tamamlanır. BEGIN_ACCESSOR_MAP makrosu END_ACCESSOR_MAP makrosu ile tamamlanır.

#### <a name="example"></a>Örnek

Bkz. [BEGIN_ACCESSOR_MAP](#begin_accessor_map).

### <a name="begin_column_map"></a><a name="begin_column_map"></a> BEGIN_COLUMN_MAP

Sütun Haritası girişinin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_COLUMN_MAP(x)
```

#### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Öğesinden türetilen Kullanıcı kayıt sınıfının adı `CAccessor` .

#### <a name="remarks"></a>Açıklamalar

Bu makro, bir satır kümesinde tek bir erişimci olması durumunda kullanılır. Satır kümesinde birden çok erişimci varsa [BEGIN_ACCESSOR_MAP](#begin_accessor_map)kullanın.

BEGIN_COLUMN_MAP makrosu END_COLUMN_MAP makrosu ile tamamlanır. Bu makro, Kullanıcı kaydında yalnızca bir erişimci gerektiğinde kullanılır.

Sütunlar, bağlamak istediğiniz satır kümesindeki alanlara karşılık gelir.

#### <a name="example"></a>Örnek

Örnek bir sütun ve parametre eşlemesi aşağıda verilmiştir:

<!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->

### <a name="blob_entry"></a><a name="blob_entry"></a> BLOB_ENTRY

İkili büyük nesne ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) bağlamak için BEGIN_COLUMN_MAP ve end_column_map ile kullanılır.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_ENTRY(nOrdinal, IID, flags, data)
```

#### <a name="parameters"></a>Parametreler

*nOrdinal*<br/>
'ndaki Sütun numarası.

*'SI*<br/>
'ndaki BLOB 'u almak için kullanılan gibi arabirim GUID 'SI `IDD_ISequentialStream` .

*bayraklar*<br/>
'ndaki OLE yapılandırılmış depolama modeli tarafından tanımlanan depolama modu bayrakları (örneğin, `STGM_READ` ).

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="example"></a>Örnek

Bkz. [nasıl bır blob alabilirim?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_length"></a><a name="blob_entry_length"></a> BLOB_ENTRY_LENGTH

İkili büyük nesne ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) bağlamak için BEGIN_COLUMN_MAP ve end_column_map ile kullanılır. [BLOB_ENTRY](#blob_entry)benzer, bu makro blob sütununun bayt cinsinden uzunluğunu da alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_ENTRY_LENGTH(nOrdinal, IID, flags, data, length)
```

#### <a name="parameters"></a>Parametreler

*nOrdinal*<br/>
'ndaki Sütun numarası.

*'SI*<br/>
'ndaki BLOB 'u almak için kullanılan gibi arabirim GUID 'SI `IDD_ISequentialStream` .

*bayraklar*<br/>
'ndaki OLE yapılandırılmış depolama modeli tarafından tanımlanan depolama modu bayrakları (örneğin, `STGM_READ` ).

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
dışı BLOB sütununun bayt cinsinden (gerçek) uzunluğu.

#### <a name="example"></a>Örnek

Bkz. [nasıl bır blob alabilirim?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_length_status"></a><a name="blob_entry_length_status"></a> BLOB_ENTRY_LENGTH_STATUS

İkili büyük nesne ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) bağlamak için BEGIN_COLUMN_MAP ve end_column_map ile kullanılır. [BLOB_ENTRY](#blob_entry)benzer, bu makro blob sütununun uzunluğunu ve durumunu da alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_ENTRY_LENGTH_STATUS(
    nOrdinal,
    IID,
    flags,
    data,
    length,
    status )
```

#### <a name="parameters"></a>Parametreler

*nOrdinal*<br/>
'ndaki Sütun numarası.

*'SI*<br/>
'ndaki BLOB 'u almak için kullanılan gibi arabirim GUID 'SI `IDD_ISequentialStream` .

*bayraklar*<br/>
'ndaki OLE yapılandırılmış depolama modeli tarafından tanımlanan depolama modu bayrakları (örneğin, `STGM_READ` ).

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
dışı BLOB sütununun bayt cinsinden (gerçek) uzunluğu.

*durumlarına*<br/>
dışı BLOB veri sütununun durumu.

#### <a name="example"></a>Örnek

Bkz. [nasıl bır blob alabilirim?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_status"></a><a name="blob_entry_status"></a> BLOB_ENTRY_STATUS

İkili büyük nesne ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) bağlamak için BEGIN_COLUMN_MAP veya BEGIN_ACCESSOR_MAP ile kullanılır. [BLOB_ENTRY](#blob_entry)benzer, bu makro blob sütununun durumunu da alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_ENTRY_STATUS(nOrdinal, IID, flags, data, status)
```

#### <a name="parameters"></a>Parametreler

*nOrdinal*<br/>
'ndaki Sütun numarası.

*'SI*<br/>
'ndaki BLOB 'u almak için kullanılan gibi arabirim GUID 'SI `IDD_ISequentialStream` .

*bayraklar*<br/>
'ndaki OLE yapılandırılmış depolama modeli tarafından tanımlanan depolama modu bayrakları (örneğin, `STGM_READ` ).

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*durumlarına*<br/>
dışı BLOB alanının durumu.

#### <a name="example"></a>Örnek

Bkz. [nasıl bır blob alabilirim?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_name"></a><a name="blob_name"></a> BLOB_NAME

İkili büyük nesne ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) bağlamak için BEGIN_COLUMN_MAP ve end_column_map ile kullanılır. [BLOB_ENTRY](#blob_entry)benzer, bu makro sütun numarası yerine bir sütun adı alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_NAME(pszName, IID, flags, data )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*'SI*<br/>
'ndaki BLOB 'u almak için kullanılan gibi arabirim GUID 'SI `IDD_ISequentialStream` .

*bayraklar*<br/>
'ndaki OLE yapılandırılmış depolama modeli tarafından tanımlanan depolama modu bayrakları (örneğin, `STGM_READ` ).

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="example"></a>Örnek

Bkz. [nasıl bır blob alabilirim?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_name_length"></a><a name="blob_name_length"></a> BLOB_NAME_LENGTH

İkili büyük nesne ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) bağlamak için BEGIN_COLUMN_MAP ve end_column_map ile kullanılır. [BLOB_NAME](#blob_name)benzer, bu makro blob veri sütununun bayt cinsinden uzunluğunu da alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_NAME_LENGTH(pszName, IID, flags, data, length )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*'SI*<br/>
'ndaki BLOB 'u almak için kullanılan gibi arabirim GUID 'SI `IDD_ISequentialStream` .

*bayraklar*<br/>
'ndaki OLE yapılandırılmış depolama modeli tarafından tanımlanan depolama modu bayrakları (örneğin, `STGM_READ` ).

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
dışı BLOB sütununun bayt cinsinden (gerçek) uzunluğu.

### <a name="blob_name_length_status"></a><a name="blob_name_length_status"></a> BLOB_NAME_LENGTH_STATUS

İkili büyük nesne ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) bağlamak için BEGIN_COLUMN_MAP ve end_column_map ile kullanılır. [BLOB_NAME](#blob_name)benzer, bu makro blob veri sütununun uzunluğunu ve durumunu da alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_NAME_LENGTH_STATUS(pszName, IID, flags, data, length, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*'SI*<br/>
'ndaki BLOB 'u almak için kullanılan gibi arabirim GUID 'SI `IDD_ISequentialStream` .

*bayraklar*<br/>
'ndaki OLE yapılandırılmış depolama modeli tarafından tanımlanan depolama modu bayrakları (örneğin, `STGM_READ` ).

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
dışı BLOB sütununun bayt cinsinden (gerçek) uzunluğu.

*durumlarına*<br/>
dışı BLOB alanının durumu.

### <a name="blob_name_status"></a><a name="blob_name_status"></a> BLOB_NAME_STATUS

İkili büyük nesne ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))) bağlamak için BEGIN_COLUMN_MAP ve end_column_map ile kullanılır. [BLOB_NAME](#blob_name)benzer, bu makro blob veri sütununun durumunu da alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_NAME_STATUS(pszName, IID, flags, data, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*'SI*<br/>
'ndaki BLOB 'u almak için kullanılan gibi arabirim GUID 'SI `IDD_ISequentialStream` .

*bayraklar*<br/>
'ndaki OLE yapılandırılmış depolama modeli tarafından tanımlanan depolama modu bayrakları (örneğin, `STGM_READ` ).

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*durumlarına*<br/>
dışı BLOB alanının durumu.

### <a name="bookmark_entry"></a><a name="bookmark_entry"></a> BOOKMARK_ENTRY

Yer işareti sütununu bağlar.

#### <a name="syntax"></a>Sözdizimi

```cpp
BOOKMARK_ENTRY(variable)
```

#### <a name="parameters"></a>Parametreler

*değişken*<br/>
'ndaki Yer işareti sütununa bağlanacak değişken.

#### <a name="example"></a>Örnek

```cpp
class CArtistsBookmark
{
public:
// Data Elements
   CBookmark<4> m_bookmark;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

// Output binding map
BEGIN_COLUMN_MAP(CArtistsBookmark)
   BOOKMARK_ENTRY(m_bookmark)
   COLUMN_ENTRY(1, m_nAge)
   COLUMN_ENTRY(2, m_szFirstName)
   COLUMN_ENTRY(3, m_szLastName)
END_COLUMN_MAP()

   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_BOOKMARKS, true);
   }

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsBookmark, L" \
   SELECT \
      Age, \
      FirstName, \
      LastName \
      FROM Artists")
};
```

Daha fazla bilgi için bkz. [yer imlerini](using-bookmarks.md) ve [CBookmark sınıfını](../../data/oledb/cbookmark-class.md)kullanma.

### <a name="column_entry"></a><a name="column_entry"></a> COLUMN_ENTRY

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY(nOrdinal, data)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [dbbinding](/previous-versions/windows/desktop/ms716845(v=vs.85)) bölümüne bakın.

*nOrdinal*<br/>
'ndaki Sütun numarası.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

COLUMN_ENTRY makro aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](#begin_column_map) ve [end_column_map](#end_column_map) makroları arasında.

- [BEGIN_ACCESSOR](#begin_accessor) ve [end_accessor](#end_accessor) makroları arasında.

- [BEGIN_PARAM_MAP](#begin_param_map) ve [END_PARAM_MAP](#end_param_map) makroları arasında.

#### <a name="example"></a>Örnek

[BEGIN_COLUMN_MAP](#begin_column_map) ve [BEGIN_ACCESSOR_MAP](#begin_accessor_map)makro konularında örneklere bakın.

### <a name="column_entry_ex"></a><a name="column_entry_ex"></a> COLUMN_ENTRY_EX

Veritabanındaki belirli bir sütunun satır kümesindeki bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_EX(nOrdinal, wType, nLength, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [dbbinding](/previous-versions/windows/desktop/ms716845(v=vs.85)) bölümüne bakın.

*nOrdinal*<br/>
'ndaki Sütun numarası.

*wType*<br/>
'ndaki Veri türü.

*nLength*<br/>
'ndaki Bayt cinsinden veri boyutu.

*Nduyarlılık*<br/>
'ndaki Veri alınırken kullanılacak en büyük duyarlık ve *wType* vardır `DBTYPE_NUMERIC` . Aksi takdirde, bu parametre yoksayılır.

*nScale*<br/>
'ndaki Veri alınırken kullanılacak ölçek veya *wType* , `DBTYPE_NUMERIC` veya `DBTYPE_DECIMAL` .

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
'ndaki Sütun uzunluğuna bağlanacak değişken.

*durumlarına*<br/>
'ndaki Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_ENTRY_EX makro aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](#begin_column_map) ve [end_column_map](#end_column_map) makroları arasında.

- [BEGIN_ACCESSOR](#begin_accessor) ve [end_accessor](#end_accessor) makroları arasında.

- [BEGIN_PARAM_MAP](#begin_param_map) ve [END_PARAM_MAP](#end_param_map) makroları arasında.

#### <a name="example"></a>Örnek

Bkz. [BOOKMARK_ENTRY](#bookmark_entry).

### <a name="column_entry_length"></a><a name="column_entry_length"></a> COLUMN_ENTRY_LENGTH

Veritabanındaki belirli bir sütunun satır kümesindeki bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_LENGTH(nOrdinal, data, length)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [dbbinding](/previous-versions/windows/desktop/ms716845(v=vs.85)) bölümüne bakın.

*nOrdinal*<br/>
'ndaki Sütun numarası, bir ile başlar. Yer işareti sıfır sütununa karşılık gelir.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
'ndaki Sütun uzunluğuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

Bu makro *uzunluk* değişkenini destekler. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](#begin_column_map) ve [end_column_map](#end_column_map) makroları arasında.

- [BEGIN_ACCESSOR](#begin_accessor) ve [end_accessor](#end_accessor) makroları arasında.

- [BEGIN_PARAM_MAP](#begin_param_map) ve [END_PARAM_MAP](#end_param_map) makroları arasında.

### <a name="column_entry_length_status"></a><a name="column_entry_length_status"></a> COLUMN_ENTRY_LENGTH_STATUS

Veritabanındaki belirli bir sütunun satır kümesindeki bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_LENGTH_STATUS(nOrdinal, data, length, status)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [dbbinding](/previous-versions/windows/desktop/ms716845(v=vs.85)) bölümüne bakın.

*nOrdinal*<br/>
'ndaki Sütun numarası.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
'ndaki Sütun uzunluğuna bağlanacak değişken.

*durumlarına*<br/>
'ndaki Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

Uzunluk ve durum değişkenlerini desteklemek istediğinizde bu makroyu kullanın. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](#begin_column_map) ve [end_column_map](#end_column_map) makroları arasında.

- [BEGIN_ACCESSOR](#begin_accessor) ve [end_accessor](#end_accessor) makroları arasında.

- [BEGIN_PARAM_MAP](#begin_param_map) ve [END_PARAM_MAP](#end_param_map) makroları arasında.

### <a name="column_entry_ps"></a><a name="column_entry_ps"></a> COLUMN_ENTRY_PS

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_PS(nOrdinal, nPrecision, nScale, data)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [dbbinding](/previous-versions/windows/desktop/ms716845(v=vs.85)) bölümüne bakın.

*nOrdinal*<br/>
'ndaki Sütun numarası.

*Nduyarlılık*<br/>
'ndaki Bağlamak istediğiniz sütunun en büyük duyarlığı.

*nScale*<br/>
'ndaki Bağlamak istediğiniz sütunun ölçeği.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

Bağlamak istediğiniz sütunun hassasiyetini ve ölçeğini belirtmenize izin verir. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](#begin_column_map) ve [end_column_map](#end_column_map) makroları arasında.

- [BEGIN_ACCESSOR](#begin_accessor) ve [end_accessor](#end_accessor) makroları arasında.

- [BEGIN_PARAM_MAP](#begin_param_map) ve [END_PARAM_MAP](#end_param_map) makroları arasında.

### <a name="column_entry_ps_length"></a><a name="column_entry_ps_length"></a> COLUMN_ENTRY_PS_LENGTH

Veritabanındaki belirli bir sütunun satır kümesindeki bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_PS_LENGTH(nOrdinal, nPrecision, nScale, data, length)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [dbbinding](/previous-versions/windows/desktop/ms716845(v=vs.85)) bölümüne bakın.

*nOrdinal*<br/>
'ndaki Sütun numarası, bir ile başlar. Yer işareti sıfır sütununa karşılık gelir.

*Nduyarlılık*<br/>
'ndaki Bağlamak istediğiniz sütunun en büyük duyarlığı.

*nScale*<br/>
'ndaki Bağlamak istediğiniz sütunun ölçeği.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
'ndaki Sütun uzunluğuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

Bağlamak istediğiniz sütunun hassasiyetini ve ölçeğini belirtmenize izin verir. Bu makro *uzunluk* değişkenini destekler. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](#begin_column_map) ve [end_column_map](#end_column_map) makroları arasında.

- [BEGIN_ACCESSOR](#begin_accessor) ve [end_accessor](#end_accessor) makroları arasında.

- [BEGIN_PARAM_MAP](#begin_param_map) ve [END_PARAM_MAP](#end_param_map) makroları arasında.

### <a name="column_entry_ps_length_status"></a><a name="column_entry_ps_length_status"></a> COLUMN_ENTRY_PS_LENGTH_STATUS

Veritabanındaki belirli bir sütunun satır kümesindeki bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_PS_LENGTH_STATUS(nOrdinal, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [dbbinding](/previous-versions/windows/desktop/ms716845(v=vs.85)) bölümüne bakın.

*nOrdinal*<br/>
'ndaki Sütun numarası.

*Nduyarlılık*<br/>
'ndaki Bağlamak istediğiniz sütunun en büyük duyarlığı.

*nScale*<br/>
'ndaki Bağlamak istediğiniz sütunun ölçeği.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
'ndaki Sütun uzunluğuna bağlanacak değişken.

*durumlarına*<br/>
'ndaki Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

Bağlamak istediğiniz sütunun hassasiyetini ve ölçeğini belirtmenize izin verir. Uzunluk ve durum değişkenlerini desteklemek istediğinizde bu makroyu kullanın. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](#begin_column_map) ve [end_column_map](#end_column_map) makroları arasında.

- [BEGIN_ACCESSOR](#begin_accessor) ve [end_accessor](#end_accessor) makroları arasında.

- [BEGIN_PARAM_MAP](#begin_param_map) ve [END_PARAM_MAP](#end_param_map) makroları arasında.

### <a name="column_entry_ps_status"></a><a name="column_entry_ps_status"></a> COLUMN_ENTRY_PS_STATUS

Veritabanındaki belirli bir sütunun satır kümesindeki bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_PS_STATUS(nOrdinal, nPrecision, nScale, data, status)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [dbbinding](/previous-versions/windows/desktop/ms716845(v=vs.85)) bölümüne bakın.

*nOrdinal*<br/>
'ndaki Sütun numarası.

*Nduyarlılık*<br/>
'ndaki Bağlamak istediğiniz sütunun en büyük duyarlığı.

*nScale*<br/>
'ndaki Bağlamak istediğiniz sütunun ölçeği.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*durumlarına*<br/>
'ndaki Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

Bağlamak istediğiniz sütunun hassasiyetini ve ölçeğini belirtmenize izin verir. Bu makro *durum* değişkenini destekler. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](#begin_column_map) ve [end_column_map](#end_column_map) makroları arasında.

- [BEGIN_ACCESSOR](#begin_accessor) ve [end_accessor](#end_accessor) makroları arasında.

- [BEGIN_PARAM_MAP](#begin_param_map) ve [END_PARAM_MAP](#end_param_map) makroları arasında.

### <a name="column_entry_status"></a><a name="column_entry_status"></a> COLUMN_ENTRY_STATUS

Veritabanındaki belirli bir sütunun satır kümesindeki bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_STATUS(nOrdinal, data, status)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [dbbinding](/previous-versions/windows/desktop/ms716845(v=vs.85)) bölümüne bakın.

*nOrdinal*<br/>
'ndaki Sütun numarası.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*durumlarına*<br/>
'ndaki Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

Bu makro *durum* değişkenini destekler. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](#begin_column_map) ve [end_column_map](#end_column_map) makroları arasında.

- [BEGIN_ACCESSOR](#begin_accessor) ve [end_accessor](#end_accessor) makroları arasında.

- [BEGIN_PARAM_MAP](#begin_param_map) ve [END_PARAM_MAP](#end_param_map) makroları arasında.

### <a name="column_entry_type"></a><a name="column_entry_type"></a> COLUMN_ENTRY_TYPE

Veritabanındaki belirli bir sütuna olan bağlamayı temsil eder. *Tür* parametresini destekler.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_TYPE (nOrdinal, wType, data)
```

#### <a name="parameters"></a>Parametreler

*nOrdinal*<br/>
'ndaki Sütun numarası.

*wType*<br/>
'ndaki Sütun girişinin veri türü.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

Bu makro, veri türünü belirtmenin bir yolu sağlayan [COLUMN_ENTRY](#column_entry) makrosunun özelleşmiş bir değişkendir.

### <a name="column_entry_type_size"></a><a name="column_entry_type_size"></a> COLUMN_ENTRY_TYPE_SIZE

Veritabanındaki belirli bir sütuna olan bağlamayı temsil eder. *Tür* ve *Boyut* parametrelerini destekler.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_TYPE_SIZE(nOrdinal, wType, nLength, data)
```

#### <a name="parameters"></a>Parametreler

*nOrdinal*<br/>
'ndaki Sütun numarası.

*wType*<br/>
'ndaki Sütun girişinin veri türü.

*nLength*<br/>
'ndaki Bayt cinsinden sütun girişi boyutu.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

Bu makro, veri boyutu ve türünü belirtmek için bir yol sağlayan [COLUMN_ENTRY](#column_entry) makrosunun özelleştirilmiş bir değişkendir.

### <a name="column_name"></a><a name="column_name"></a> COLUMN_NAME

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder. [COLUMN_ENTRY](#column_entry)benzer, bu makronun sütun numarası yerine sütun adını almasının dışında.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME(pszName, data)
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_ * makroları [COLUMN_ENTRY](#column_entry)aynı yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](#begin_column_map) ve [end_column_map](#end_column_map) makroları arasında.

- [BEGIN_ACCESSOR](#begin_accessor) ve [end_accessor](#end_accessor) makroları arasında.

- [BEGIN_PARAM_MAP](#begin_param_map) ve [END_PARAM_MAP](#end_param_map) makroları arasında.

### <a name="column_name_ex"></a><a name="column_name_ex"></a> COLUMN_NAME_EX

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder. [Column_name](#column_name)benzer, bu makro veri türü, boyut, duyarlık, ölçek, sütun uzunluğu ve sütun durumunu da alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_EX(pszName, wType, nLength, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*wType*<br/>
'ndaki Veri türü.

*nLength*<br/>
'ndaki Bayt cinsinden veri boyutu.

*Nduyarlılık*<br/>
'ndaki Veri alınırken kullanılacak en büyük duyarlık ve *wType* vardır `DBTYPE_NUMERIC` . Aksi takdirde, bu parametre yoksayılır.

*nScale*<br/>
'ndaki Veri alınırken kullanılacak ölçek veya *wType* , `DBTYPE_NUMERIC` veya `DBTYPE_DECIMAL` .

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
'ndaki Sütun uzunluğuna bağlanacak değişken.

*durumlarına*<br/>
'ndaki Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_ * makroların nerede kullanıldığı hakkında bilgi için bkz. [column_name](#column_name) .

### <a name="column_name_length"></a><a name="column_name_length"></a> COLUMN_NAME_LENGTH

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder. [Column_name](#column_name)benzer, bu makro sütun uzunluğunu da alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_LENGTH(pszName, data, length)
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
'ndaki Sütun uzunluğuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_ * makroların nerede kullanıldığı hakkında bilgi için bkz. [column_name](#column_name) .

### <a name="column_name_length_status"></a><a name="column_name_length_status"></a> COLUMN_NAME_LENGTH_STATUS

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder. [Column_name](#column_name)benzer, bu makro sütun uzunluğunu ve sütun durumunu da alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_LENGTH_STATUS(pszName, data, length, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
'ndaki Sütun uzunluğuna bağlanacak değişken.

*durumlarına*<br/>
'ndaki Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_ * makroların nerede kullanıldığı hakkında bilgi için bkz. [column_name](#column_name) .

### <a name="column_name_ps"></a><a name="column_name_ps"></a> COLUMN_NAME_PS

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder. [Column_name](#column_name)benzer, bu makronun da duyarlık ve ölçek elde etmelerinin olması dışında.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_PS(pszName, nPrecision, nScale, data )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*Nduyarlılık*<br/>
'ndaki Bağlamak istediğiniz sütunun en büyük duyarlığı.

*nScale*<br/>
'ndaki Bağlamak istediğiniz sütunun ölçeği.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_ * makroların nerede kullanıldığı hakkında bilgi için bkz. [column_name](#column_name) .

### <a name="column_name_ps_length"></a><a name="column_name_ps_length"></a> COLUMN_NAME_PS_LENGTH

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder. [Column_name](#column_name)benzer, bu makronun da duyarlık, ölçek ve sütun uzunluğu olması gerekir.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_PS_LENGTH(pszName, nPrecision, nScale, data, length )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*Nduyarlılık*<br/>
'ndaki Bağlamak istediğiniz sütunun en büyük duyarlığı.

*nScale*<br/>
'ndaki Bağlamak istediğiniz sütunun ölçeği.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
'ndaki Sütun uzunluğuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_ * makroların nerede kullanıldığı hakkında bilgi için bkz. [column_name](#column_name) .

### <a name="column_name_ps_length_status"></a><a name="column_name_ps_length_status"></a> COLUMN_NAME_PS_LENGTH_STATUS

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder. [Column_name](#column_name)benzer, bu makronun de duyarlık, ölçek, sütun uzunluğu ve sütun durumu olması gerekir.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_PS_LENGTH_STATUS(pszName, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*Nduyarlılık*<br/>
'ndaki Bağlamak istediğiniz sütunun en büyük duyarlığı.

*nScale*<br/>
'ndaki Bağlamak istediğiniz sütunun ölçeği.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*length*<br/>
'ndaki Sütun uzunluğuna bağlanacak değişken.

*durumlarına*<br/>
'ndaki Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_ * makroların nerede kullanıldığı hakkında bilgi için bkz. [column_name](#column_name) .

### <a name="column_name_ps_status"></a><a name="column_name_ps_status"></a> COLUMN_NAME_PS_STATUS

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder. [Column_name](#column_name)benzer, bu makronun da duyarlık, ölçek ve sütun durumu olması gerekir.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_PS_STATUS(pszName, nPrecision, nScale, data, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*Nduyarlılık*<br/>
'ndaki Bağlamak istediğiniz sütunun en büyük duyarlığı.

*nScale*<br/>
'ndaki Bağlamak istediğiniz sütunun ölçeği.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*durumlarına*<br/>
'ndaki Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_ * makroların nerede kullanıldığı hakkında bilgi için bkz. [column_name](#column_name) .

### <a name="column_name_status"></a><a name="column_name_status"></a> COLUMN_NAME_STATUS

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder. [Column_name](#column_name)benzer, bu makro sütun durumunu da alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_STATUS(pszName, data, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

*durumlarına*<br/>
'ndaki Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_ * makroların nerede kullanıldığı hakkında bilgi için bkz. [column_name](#column_name) .

### <a name="column_name_type"></a><a name="column_name_type"></a> COLUMN_NAME_TYPE

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder. [Column_name](#column_name)benzer, bu makronun de veri türü olması gerekir.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_TYPE(pszName, wType, data)
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*wType*<br/>
'ndaki Veri türü.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_ * makroların nerede kullanıldığı hakkında bilgi için bkz. [column_name](#column_name) .

### <a name="column_name_type_ps"></a><a name="column_name_type_ps"></a> COLUMN_NAME_TYPE_PS

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder. [Column_name](#column_name)benzer, bu makro veri türünü, duyarlılığı ve ölçeği de alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_TYPE_PS(pszName, wType, nPrecision, nScale, data)
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*wType*<br/>
'ndaki Veri türü.

*Nduyarlılık*<br/>
'ndaki Veri alınırken kullanılacak en büyük duyarlık ve *wType* vardır `DBTYPE_NUMERIC` . Aksi takdirde, bu parametre yoksayılır.

*nScale*<br/>
'ndaki Veri alınırken kullanılacak ölçek veya *wType* , `DBTYPE_NUMERIC` veya `DBTYPE_DECIMAL` .

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_ * makroların nerede kullanıldığı hakkında bilgi için bkz. [column_name](#column_name) .

### <a name="column_name_type_size"></a><a name="column_name_type_size"></a> COLUMN_NAME_TYPE_SIZE

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder. [Column_name](#column_name)benzer şekilde, bu makro veri türünü ve boyutunu de alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_TYPE_SIZE(pszName, wType, nLength, data)
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*wType*<br/>
'ndaki Veri türü.

*nLength*<br/>
'ndaki Bayt cinsinden veri boyutu.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_ * makroların nerede kullanıldığı hakkında bilgi için bkz. [column_name](#column_name) .

### <a name="column_name_type_status"></a><a name="column_name_type_status"></a> COLUMN_NAME_TYPE_STATUS

Satır kümesindeki belirli bir sütuna yönelik bir bağlamayı temsil eder. [Column_name](#column_name)benzer, bu makronun de veri türü ve sütun durumu olması gerekir.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_TYPE_STATUS(pszName, wType, status, data)
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
'ndaki Sütun adı işaretçisi. Ad bir Unicode dize olmalıdır. Bunu, adın önüne bir ' L ' koyarak yapabilirsiniz, örneğin: `L"MyColumn"` .

*wType*<br/>
'ndaki Veri türü.

*durumlarına*<br/>
'ndaki Sütun durumuna bağlanacak değişken.

*data*<br/>
'ndaki Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_ * makroların nerede kullanıldığı hakkında bilgi için bkz. [column_name](#column_name) .

### <a name="end_column_map"></a><a name="end_column_map"></a> END_COLUMN_MAP

Sütun eşleme girdilerinin sonunu işaretler.

#### <a name="syntax"></a>Syntax

```cpp
END_COLUMN_MAP()
```

#### <a name="remarks"></a>Açıklamalar

Satır kümesinde tek bir erişimci ile kullanılır. BEGIN_COLUMN_MAP makrosu END_COLUMN_MAP makrosu ile tamamlanır.

#### <a name="example"></a>Örnek

Bkz. [BEGIN_COLUMN_MAP](#begin_column_map).

### <a name="define_command"></a><a name="define_command"></a> DEFINE_COMMAND

[CCommand](../../data/oledb/ccommand-class.md) sınıfı kullanılırken satır kümesini oluşturmak için kullanılacak komutu belirtir. Yalnızca belirtilen uygulama türüyle eşleşen dize türlerini kabul eder (ANSI veya Unicode).

> [!NOTE]
> DEFINE_COMMAND yerine [DEFINE_COMMAND_EX](#define_command_ex) kullanmanız önerilir.

#### <a name="syntax"></a>Sözdizimi

```cpp
DEFINE_COMMAND(x, szCommand)
```

#### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Kullanıcı kaydı (komut) sınıfının adı.

*szCommand*<br/>
'ndaki [CCommand](../../data/oledb/ccommand-class.md)kullanılırken satır kümesini oluşturmak için kullanılacak komut dizesi.

#### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [CCommand:: Open](./ccommand-class.md#open) yönteminde komut metni belirtmezseniz belirttiğiniz komut dizesi varsayılan olarak kullanılır.

Uygulamanızı ANSI olarak oluşturursanız bu makro ANSI dizelerini veya uygulamanızı Unicode olarak oluşturursanız Unicode dizelerini kabul eder. ANSI veya Unicode uygulama türünden bağımsız olarak, ilki Unicode dizelerini kabul ettiğinden, DEFINE_COMMAND yerine [DEFINE_COMMAND_EX](#define_command_ex) kullanmanız önerilir.

#### <a name="example"></a>Örnek

Bkz. [BOOKMARK_ENTRY](#bookmark_entry).

### <a name="define_command_ex"></a><a name="define_command_ex"></a> DEFINE_COMMAND_EX

[CCommand](../../data/oledb/ccommand-class.md) sınıfı kullanılırken satır kümesini oluşturmak için kullanılacak komutu belirtir. Unicode ve ANSI uygulamalarını destekler.

#### <a name="syntax"></a>Sözdizimi

```cpp
DEFINE_COMMAND_EX(x, wszCommand)
```

#### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Kullanıcı kaydı (komut) sınıfının adı.

*wszCommand*<br/>
'ndaki [CCommand](../../data/oledb/ccommand-class.md)kullanılırken satır kümesini oluşturmak için kullanılacak komut dizesi.

#### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [CCommand:: Open](./ccommand-class.md#open) yönteminde komut metni belirtmezseniz belirttiğiniz komut dizesi varsayılan olarak kullanılır.

Bu makro, uygulama türünden bağımsız olarak Unicode dizelerini kabul eder. Bu makro, UNICODE 'un yanı sıra ANSI uygulamalarını desteklediğinden [DEFINE_COMMAND](#define_command) üzerinde tercih edilir.

#### <a name="example"></a>Örnek

Bkz. [BOOKMARK_ENTRY](#bookmark_entry).

### <a name="begin_param_map"></a><a name="begin_param_map"></a> BEGIN_PARAM_MAP

Parametre eşleme girdilerinin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PARAM_MAP(x)
```

#### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Kullanıcı kayıt sınıfının adı.

#### <a name="remarks"></a>Açıklamalar

Parametreler [komutları](/previous-versions/windows/desktop/ms724608(v=vs.85))tarafından kullanılır.

#### <a name="example"></a>Örnek

[BEGIN_COLUMN_MAP](#begin_column_map) makrosunun örneğine bakın.

### <a name="end_param_map"></a><a name="end_param_map"></a> END_PARAM_MAP

Parametre eşleme girdilerinin sonunu işaretler.

#### <a name="syntax"></a>Syntax

```cpp
END_PARAM_MAP()
```

#### <a name="example"></a>Örnek

[BEGIN_PARAM_MAP](#begin_param_map) makrosunun örneğine bakın.

### <a name="set_param_type"></a><a name="set_param_type"></a> SET_PARAM_TYPE

Makro giriş, çıkış veya giriş/çıkış SET_PARAM_TYPE izleyen COLUMN_ENTRY makroları belirtir.

#### <a name="syntax"></a>Sözdizimi

```cpp
SET_PARAM_TYPE(type)
```

#### <a name="parameters"></a>Parametreler

*türüyle*<br/>
'ndaki Parametresi için ayarlanacak tür.

#### <a name="remarks"></a>Açıklamalar

Sağlayıcılar yalnızca temel alınan veri kaynağı tarafından desteklenen parametre giriş/çıkış türlerini destekler. Tür bir veya daha fazla `DBPARAMIO` değerin birleşimidir ( *OLE DB Programcı başvurusunda* [dbbinding yapılarına](/previous-versions/windows/desktop/ms716845(v=vs.85)) bakın):

- `DBPARAMIO_NOTPARAM` Erişimcinin parametresi yok. Genellikle, `eParamIO` kullanıcıdan parametre yoksayıldığını anımsatmak için bu değere satır erişimcilerinde ayarlanır.

- `DBPARAMIO_INPUT` Giriş parametresi.

- `DBPARAMIO_OUTPUT` Bir çıktı parametresi.

- `DBPARAMIO_INPUT | DBPARAMIO_OUTPUT` Parametresi hem giriş hem de çıkış parametresidir.

#### <a name="example"></a>Örnek

```cpp
class CArtistsProperty
{
public:
   short m_nReturn;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

BEGIN_PARAM_MAP(CArtistsProperty)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_nReturn)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_nAge)
END_PARAM_MAP()

BEGIN_COLUMN_MAP(CArtistsProperty)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
END_COLUMN_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsProperty, L" \
      { ? = SELECT Age FROM Artists WHERE Age < ? }")
};
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları için makrolar ve genel Işlevler](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
