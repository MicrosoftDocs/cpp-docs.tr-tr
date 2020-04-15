---
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
ms.openlocfilehash: 8b898990672f590f6047eef6fdfd1ed7eecb3f92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369822"
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>OLE DB Tüketici Şablonları için Makrolar ve Genel İşlevler

OLE DB Tüketici Şablonları aşağıdaki makroları ve genel işlevleri içerir:

## <a name="global-functions"></a>Küresel Fonksiyonlar

|||
|-|-|
|[AtlTraceErrorRecords](#atltraceerrorrecords)|Bir hata döndürülürse OLE DB Hata Kaydı bilgilerini boşaltma aygıtına boşaltır.|

## <a name="accessor-map-macros"></a>Accessor Harita Makroları

|||
|-|-|
|[BEGIN_ACCESSOR](#begin_accessor)|Erişime erişim girişinin başlangıcını işaretler.|
|[BEGIN_ACCESSOR_MAP](#begin_accessor_map)|Erişime erişime erişim eşlemi girişlerinin başlangıcını işaretler.|
|[END_ACCESSOR](#end_accessor)|Erişimci girişinin sonunu işaretler.|
|[END_ACCESSOR_MAP](#end_accessor_map)|Erişime erişime erişim eşlemi girişlerinin sonunu işaretler.|

## <a name="column-map-macros"></a>Sütun Haritası Makroları

|||
|-|-|
|[BEGIN_COLUMN_MAP](#begin_column_map)|Kullanıcı kayıt sınıfındaki sütun eşlemi girişlerinin başlangıcını işaretler.|
|[BLOB_ENTRY](#blob_entry)|İkili büyük bir nesneyi (BLOB) bağlamak için kullanılır.|
|[BLOB_ENTRY_LENGTH](#blob_entry_length)|BLOB veri sütununun uzunluğunu bildirir.|
|[BLOB_ENTRY_LENGTH_STATUS](#blob_entry_length_status)|BLOB veri sütununun uzunluğunu ve durumunu bildirir.|
|[BLOB_ENTRY_STATUS](#blob_entry_status)|BLOB veri sütununun durumunu bildirir.|
|[BLOB_NAME](#blob_name)|İkili büyük bir nesneyi sütun adına bağlamak için kullanılır.|
|[BLOB_NAME_LENGTH](#blob_name_length)|BLOB veri sütununun uzunluğunu bildirir.|
|[BLOB_NAME_LENGTH_STATUS](#blob_name_length_status)|BLOB veri sütununun uzunluğunu ve durumunu bildirir.|
|[BLOB_NAME_STATUS](#blob_name_status)|BLOB veri sütununun durumunu bildirir.|
|[BOOKMARK_ENTRY](#bookmark_entry)|Satır kümesinde yer imi girişini temsil eder. Yer imi girişi, özel bir sütun girişi türüdür.|
|[COLUMN_ENTRY](#column_entry)|Veritabanında belirli bir sütuna bir bağlama temsil eder.|
|[COLUMN_ENTRY_EX](#column_entry_ex)|Veritabanındaki belirli bir sütuna yapılan bir bağlamayı temsil eder. *Türü,* *uzunluğu,* *hassasiyeti,* *ölçeği*ve *durum parametrelerini* destekler.|
|[COLUMN_ENTRY_LENGTH](#column_entry_length)|Veritabanındaki belirli bir sütuna yapılan bir bağlamayı temsil eder. *Uzunluk* değişkenini destekler.|
|[COLUMN_ENTRY_LENGTH_STATUS](#column_entry_length_status)|Veritabanındaki belirli bir sütuna yapılan bir bağlamayı temsil eder. Durum ve *uzunluk* *parametrelerini* destekler.|
|[COLUMN_ENTRY_PS](#column_entry_ps)|Veritabanındaki belirli bir sütuna yapılan bir bağlamayı temsil eder. *Hassaslık* ve ölçek *parametrelerini* destekler.|
|[COLUMN_ENTRY_PS_LENGTH](#column_entry_ps_length)|Veritabanındaki belirli bir sütuna yapılan bir bağlamayı temsil eder. *Uzunluk* değişkeni, *kesinlik* ve *ölçek* parametrelerini destekler.|
|[COLUMN_ENTRY_PS_LENGTH_STATUS](#column_entry_ps_length_status)|Veritabanındaki belirli bir sütuna yapılan bir bağlamayı temsil eder. *Durum* ve *uzunluk* değişkenlerini, *kesinliği* ve ölçek parametrelerini destekler. *scale*|
|[COLUMN_ENTRY_PS_STATUS](#column_entry_ps_status)|Veritabanındaki belirli bir sütuna yapılan bir bağlamayı temsil eder. *Durum* değişkeni, *kesinlik* ve *ölçek* parametrelerini destekler.|
|[COLUMN_ENTRY_STATUS](#column_entry_status)|Veritabanındaki belirli bir sütuna yapılan bir bağlamayı temsil eder. *Durum* değişkenini destekler.|
|[COLUMN_ENTRY_TYPE](#column_entry_type)|Veritabanında belirli bir sütuna bir bağlama temsil eder. *Tür parametresini* destekler.|
|[COLUMN_ENTRY_TYPE_SIZE](#column_entry_type_size)|Veritabanındaki belirli bir sütuna yapılan bir bağlamayı temsil eder. Tür ve *boyut* *parametrelerini* destekler.|
|[COLUMN_NAME](#column_name)|Veritabanındaki belirli bir sütuna ada göre bağlanmayı temsil eder.|
|[COLUMN_NAME_EX](#column_name_ex)|Veritabanındaki belirli bir sütuna ada göre bağlanmayı temsil eder. Veri türü, boyutu, kesinliği, ölçeği, sütun uzunluğunu ve sütun durumunun belirtimini destekler.|
|[COLUMN_NAME_LENGTH](#column_name_length)|Veritabanındaki belirli bir sütuna ada göre bağlanmayı temsil eder. Sütun uzunluğu belirtimini destekler.|
|[COLUMN_NAME_LENGTH_STATUS](#column_name_length_status)|Veritabanındaki belirli bir sütuna ada göre bağlanmayı temsil eder. Sütun uzunluğu ve durumu belirtimini destekler.|
|[COLUMN_NAME_PS](#column_name_ps)|Veritabanındaki belirli bir sütuna ada göre bağlanmayı temsil eder. Hassasiyet ve ölçek belirtimini destekler.|
|[COLUMN_NAME_PS_LENGTH](#column_name_ps_length)|Veritabanındaki belirli bir sütuna ada göre bağlanmayı temsil eder. Kesinlik, ölçek ve sütun uzunluğu belirtimini destekler.|
|[COLUMN_NAME_PS_LENGTH_STATUS](#column_name_ps_length_status)|Veritabanındaki belirli bir sütuna ada göre bağlanmayı temsil eder. Kesinlik, ölçek, sütun uzunluğu ve sütun durumu belirtimini destekler.|
|[COLUMN_NAME_PS_STATUS](#column_name_ps_status)|Veritabanındaki belirli bir sütuna ada göre bağlanmayı temsil eder. Kesinlik, ölçek ve sütun durumu belirtimini destekler.|
|[COLUMN_NAME_STATUS](#column_name_status)|Veritabanındaki belirli bir sütuna ada göre bağlanmayı temsil eder. Sütun durumunun belirtimini destekler.|
|[COLUMN_NAME_TYPE](#column_name_type)|Veritabanındaki belirli bir sütuna ada göre bağlanmayı temsil eder. Veri türünün belirtimini destekler.|
|[COLUMN_NAME_TYPE_PS](#column_name_type_ps)|Veritabanındaki belirli bir sütuna ada göre bağlanmayı temsil eder. Veri türü, kesinlik ve ölçek belirtimini destekler.|
|[COLUMN_NAME_TYPE_SIZE](#column_name_type_size)|Veritabanındaki belirli bir sütuna ada göre bağlanmayı temsil eder. Veri türü ve boyutu belirtimini destekler.|
|[COLUMN_NAME_TYPE_STATUS](#column_name_type_status)|Veritabanındaki belirli bir sütuna ada göre bağlanmayı temsil eder. Veri türü ve sütun durumunun belirtimini destekler.|
|[END_COLUMN_MAP](#end_column_map)|Sütun eşlemi girişlerinin sonunu işaretler.|

## <a name="command-macros"></a>Komut Makroları

|||
|-|-|
|[DEFINE_COMMAND](#define_command)|[CCommand](../../data/oledb/ccommand-class.md) sınıfını kullanırken satır kümesini oluşturmak için kullanılacak komutu belirtir. Yalnızca belirtilen uygulama türüyle (ANSI veya Unicode) eşleşen dize türlerini kabul eder. DEFINE_COMMAND yerine [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) kullanmanız önerilir.|
|[DEFINE_COMMAND_EX](#define_command_ex)|[CCommand](../../data/oledb/ccommand-class.md) sınıfını kullanırken satır kümesini oluşturmak için kullanılacak komutu belirtir. ANSI ve Unicode uygulamalarını destekler.|

## <a name="parameter-map-macros"></a>Parametre Harita Makroları

|||
|-|-|
|[BEGIN_PARAM_MAP](#begin_param_map)|Kullanıcı kayıt sınıfındaki parametre eşlemi girişlerinin başlangıcını işaretler.|
|[END_PARAM_MAP](#end_param_map)|Parametre eşlemi girişlerinin sonunu işaretler.|
|[SET_PARAM_TYPE](#set_param_type)|SET_PARAM_TYPE makroyu izleyen COLUMN_ENTRY makroları giriş, çıktı veya giriş/çıkış olarak belirtir.|

### <a name="atltraceerrorrecords"></a><a name="atltraceerrorrecords"></a>AtlTraceErrorRecords

Bir hata döndürülürse OLE DB Hata Kaydı bilgilerini boşaltma aygıtına boşaltır.

#### <a name="syntax"></a>Sözdizimi

```cpp
inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);
```

#### <a name="parameters"></a>Parametreler

*Herr*<br/>
[içinde] OLE DB Tüketici Şablonu üye işlevi tarafından döndürülen bir HRESULT.

#### <a name="remarks"></a>Açıklamalar

*HErr* S_OK değilse, `AtlTraceErrorRecords` OLE DB Hata Kaydı bilgilerini döküm aygıtına (Çıktı penceresinin **hata ayıklama** sekmesi veya bir dosya) boşaltır. Sağlayıcıdan elde edilen Hata Kaydı bilgileri, her hata kaydı girişi için satır numarası, kaynak, açıklama, yardım dosyası, bağlam ve GUID içerir. `AtlTraceErrorRecords`bu bilgileri yalnızca hata ayıklama yapılarına döker. Sürüm oluşturur, bu optimize edilmiş boş bir saplama olduğunu. Daha fazla bilgi için [CDBErrorInfo Sınıfı'na](../../data/oledb/cdberrorinfo-class.md)bakın.

### <a name="begin_accessor"></a><a name="begin_accessor"></a>BEGIN_ACCESSOR

Erişime erişim girişinin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_ACCESSOR(num, bAuto)
```

#### <a name="parameters"></a>Parametreler

*sayı*<br/>
[içinde] Bu erişimci haritadaki erişimcinin sıfır ofset numarası.

*bOtomatik*<br/>
[içinde] Bu erişimcinin otomatik erişimci veya manuel erişimci olup olmadığını belirtir. **Doğruysa,** erişime giren otomatiktir; **yanlışsa,** erişime erişim kılavuzu el ile yapılır. Otomatik erişimci, taşıma işlemlerinde verilerin sizin için getirili anlamına gelir.

#### <a name="remarks"></a>Açıklamalar

Bir satır kümesinde birden çok erişimci söz konusu olduğunda, BEGIN_ACCESSOR_MAP belirtmeniz ve her bir aksesuar için BEGIN_ACCESSOR makroyu kullanmanız gerekir. BEGIN_ACCESSOR makrosu END_ACCESSOR makro suyla tamamlanır. BEGIN_ACCESSOR_MAP makrosu END_ACCESSOR_MAP makrosu yla tamamlanır.

#### <a name="example"></a>Örnek

[Bkz. BEGIN_ACCESSOR_MAP.](../../data/oledb/begin-accessor-map.md)

### <a name="begin_accessor_map"></a><a name="begin_accessor_map"></a>BEGIN_ACCESSOR_MAP

Erişime erişime erişim eşlemi girişlerinin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_ACCESSOR_MAP(x, num)
```

#### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Kullanıcı kayıt sınıfının adı.

*sayı*<br/>
[içinde] Bu erişimci haritadaki erişimci lerin sayısı.

#### <a name="remarks"></a>Açıklamalar

Bir satır kümesinde birden çok erişimci söz konusu olduğunda, başında BEGIN_ACCESSOR_MAP belirtmeniz ve her bir aksesuar için BEGIN_ACCESSOR makroyu kullanmanız gerekir. BEGIN_ACCESSOR makrosu END_ACCESSOR makro suyla tamamlanır. Erişime erişim haritası END_ACCESSOR_MAP makrosu ile tamamlanır.

Kullanıcı kaydında yalnızca bir erişiminiz varsa, makro [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)kullanın.

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

### <a name="end_accessor"></a><a name="end_accessor"></a>END_ACCESSOR

Erişimci girişinin sonunu işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_ACCESSOR()
```

#### <a name="remarks"></a>Açıklamalar

Bir satır kümesindeki birden çok erişimci için, BEGIN_ACCESSOR_MAP belirtmeniz ve her bir aksesuar için BEGIN_ACCESSOR makroyu kullanmanız gerekir. BEGIN_ACCESSOR makrosu END_ACCESSOR makro suyla tamamlanır. BEGIN_ACCESSOR_MAP makrosu END_ACCESSOR_MAP makrosu yla tamamlanır.

#### <a name="example"></a>Örnek

[Bkz. BEGIN_ACCESSOR_MAP.](../../data/oledb/begin-accessor-map.md)

### <a name="end_accessor_map"></a><a name="end_accessor_map"></a>END_ACCESSOR_MAP

Erişime erişime erişim eşlemi girişlerinin sonunu işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_ACCESSOR_MAP()
```

#### <a name="remarks"></a>Açıklamalar

Bir satır kümesindeki birden çok erişimci için, BEGIN_ACCESSOR_MAP belirtmeniz ve her bir aksesuar için BEGIN_ACCESSOR makroyu kullanmanız gerekir. BEGIN_ACCESSOR makrosu END_ACCESSOR makro suyla tamamlanır. BEGIN_ACCESSOR_MAP makrosu END_ACCESSOR_MAP makrosu yla tamamlanır.

#### <a name="example"></a>Örnek

[Bkz. BEGIN_ACCESSOR_MAP.](../../data/oledb/begin-accessor-map.md)

### <a name="begin_column_map"></a><a name="begin_column_map"></a>BEGIN_COLUMN_MAP

Sütun eşlemi girişinin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_COLUMN_MAP(x)
```

#### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Türetilen kullanıcı kayıt sınıfının `CAccessor`adı.

#### <a name="remarks"></a>Açıklamalar

Bu makro, bir satır kümesinde tek bir erişimci durumunda kullanılır. Bir satır setinde birden çok erişiminiz varsa, [BEGIN_ACCESSOR_MAP.](../../data/oledb/begin-accessor-map.md)

BEGIN_COLUMN_MAP makrosu END_COLUMN_MAP makrosu yla tamamlanır. Bu makro, kullanıcı kaydında yalnızca bir erişimci gerektiğinde kullanılır.

Sütunlar bağlamak istediğiniz satır kümesindeki alanlara karşılık gelir.

#### <a name="example"></a>Örnek

Örnek sütun ve parametre haritası aşağıda verilmiştir:

<!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->

### <a name="blob_entry"></a><a name="blob_entry"></a>BLOB_ENTRY

Bir ikili büyük nesne[(BLOB)](/previous-versions/windows/desktop/ms711511(v=vs.85))bağlamak için BEGIN_COLUMN_MAP ve END_COLUMN_MAP ile kullanılır.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_ENTRY(nOrdinal, IID, flags, data)
```

#### <a name="parameters"></a>Parametreler

*nOrdinal*<br/>
[içinde] Sütun numarası.

*ııd*<br/>
[içinde] Arabirim GUID, `IDD_ISequentialStream`gibi , BLOB almak için kullanılır.

*bayraklar*<br/>
[içinde] OLE Yapılandırılmış Depolama modeli (örneğin, `STGM_READ`) tarafından tanımlanan depolama modu bayrakları.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="example"></a>Örnek

Bkz. [BLOB'u Nasıl Alabiliyorum?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_length"></a><a name="blob_entry_length"></a>BLOB_ENTRY_LENGTH

Bir ikili büyük nesne[(BLOB)](/previous-versions/windows/desktop/ms711511(v=vs.85))bağlamak için BEGIN_COLUMN_MAP ve END_COLUMN_MAP ile kullanılır. [BLOB_ENTRY](../../data/oledb/blob-entry.md)benzer , bu makro da BLOB sütunbayt uzunluğu alır dışında.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_ENTRY_LENGTH(nOrdinal, IID, flags, data, length)
```

#### <a name="parameters"></a>Parametreler

*nOrdinal*<br/>
[içinde] Sütun numarası.

*ııd*<br/>
[içinde] Arabirim GUID, `IDD_ISequentialStream`gibi , BLOB almak için kullanılır.

*bayraklar*<br/>
[içinde] OLE Yapılandırılmış Depolama modeli (örneğin, `STGM_READ`) tarafından tanımlanan depolama modu bayrakları.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[çıkış] BLOB sütununun baytlarındaki (gerçek) uzunluk.

#### <a name="example"></a>Örnek

Bkz. [BLOB'u Nasıl Alabiliyorum?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_length_status"></a><a name="blob_entry_length_status"></a>BLOB_ENTRY_LENGTH_STATUS

Bir ikili büyük nesne[(BLOB)](/previous-versions/windows/desktop/ms711511(v=vs.85))bağlamak için BEGIN_COLUMN_MAP ve END_COLUMN_MAP ile kullanılır. [BLOB_ENTRY](../../data/oledb/blob-entry.md)benzer , bu makro da BLOB sütunun uzunluğu ve durumunu alır dışında.

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
[içinde] Sütun numarası.

*ııd*<br/>
[içinde] Arabirim GUID, `IDD_ISequentialStream`gibi , BLOB almak için kullanılır.

*bayraklar*<br/>
[içinde] OLE Yapılandırılmış Depolama modeli (örneğin, `STGM_READ`) tarafından tanımlanan depolama modu bayrakları.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[çıkış] BLOB sütununun baytlarındaki (gerçek) uzunluk.

*Durum*<br/>
[çıkış] BLOB veri sütununun durumu.

#### <a name="example"></a>Örnek

Bkz. [BLOB'u Nasıl Alabiliyorum?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_status"></a><a name="blob_entry_status"></a>BLOB_ENTRY_STATUS

Bir ikili büyük nesne[(BLOB)](/previous-versions/windows/desktop/ms711511(v=vs.85))bağlamak için BEGIN_COLUMN_MAP veya BEGIN_ACCESSOR_MAP ile kullanılır. [BLOB_ENTRY](../../data/oledb/blob-entry.md)benzer , bu makro da BLOB sütunun durumunu alır dışında.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_ENTRY_STATUS(nOrdinal, IID, flags, data, status)
```

#### <a name="parameters"></a>Parametreler

*nOrdinal*<br/>
[içinde] Sütun numarası.

*ııd*<br/>
[içinde] Arabirim GUID, `IDD_ISequentialStream`gibi , BLOB almak için kullanılır.

*bayraklar*<br/>
[içinde] OLE Yapılandırılmış Depolama modeli (örneğin, `STGM_READ`) tarafından tanımlanan depolama modu bayrakları.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Durum*<br/>
[çıkış] BLOB alanının durumu.

#### <a name="example"></a>Örnek

Bkz. [BLOB'u Nasıl Alabiliyorum?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_name"></a><a name="blob_name"></a>BLOB_NAME

Bir ikili büyük nesne[(BLOB)](/previous-versions/windows/desktop/ms711511(v=vs.85))bağlamak için BEGIN_COLUMN_MAP ve END_COLUMN_MAP ile kullanılır. [BLOB_ENTRY](../../data/oledb/blob-entry.md)benzer , ancak bu makro bir sütun numarası yerine bir sütun adı alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_NAME(pszName, IID, flags, data )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*ııd*<br/>
[içinde] Arabirim GUID, `IDD_ISequentialStream`gibi , BLOB almak için kullanılır.

*bayraklar*<br/>
[içinde] OLE Yapılandırılmış Depolama modeli (örneğin, `STGM_READ`) tarafından tanımlanan depolama modu bayrakları.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="example"></a>Örnek

Bkz. [BLOB'u Nasıl Alabiliyorum?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_name_length"></a><a name="blob_name_length"></a>BLOB_NAME_LENGTH

Bir ikili büyük nesne[(BLOB)](/previous-versions/windows/desktop/ms711511(v=vs.85))bağlamak için BEGIN_COLUMN_MAP ve END_COLUMN_MAP ile kullanılır. [BLOB_NAME](../../data/oledb/blob-name.md)benzer , bu makro da BLOB veri sütunun bayt uzunluk alır dışında.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_NAME_LENGTH(pszName, IID, flags, data, length )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*ııd*<br/>
[içinde] Arabirim GUID, `IDD_ISequentialStream`gibi , BLOB almak için kullanılır.

*bayraklar*<br/>
[içinde] OLE Yapılandırılmış Depolama modeli (örneğin, `STGM_READ`) tarafından tanımlanan depolama modu bayrakları.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[çıkış] BLOB sütununun baytlarındaki (gerçek) uzunluk.

### <a name="blob_name_length_status"></a><a name="blob_name_length_status"></a>BLOB_NAME_LENGTH_STATUS

Bir ikili büyük nesne[(BLOB)](/previous-versions/windows/desktop/ms711511(v=vs.85))bağlamak için BEGIN_COLUMN_MAP ve END_COLUMN_MAP ile kullanılır. [BLOB_NAME](../../data/oledb/blob-name.md)benzer , bu makro da BLOB veri sütununun uzunluğu ve durumunu alır dışında.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_NAME_LENGTH_STATUS(pszName, IID, flags, data, length, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*ııd*<br/>
[içinde] Arabirim GUID, `IDD_ISequentialStream`gibi , BLOB almak için kullanılır.

*bayraklar*<br/>
[içinde] OLE Yapılandırılmış Depolama modeli (örneğin, `STGM_READ`) tarafından tanımlanan depolama modu bayrakları.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[çıkış] BLOB sütununun baytlarındaki (gerçek) uzunluk.

*Durum*<br/>
[çıkış] BLOB alanının durumu.

### <a name="blob_name_status"></a><a name="blob_name_status"></a>BLOB_NAME_STATUS

Bir ikili büyük nesne[(BLOB)](/previous-versions/windows/desktop/ms711511(v=vs.85))bağlamak için BEGIN_COLUMN_MAP ve END_COLUMN_MAP ile kullanılır. [BLOB_NAME](../../data/oledb/blob-name.md)benzer , bu makro da BLOB veri sütununun durumunu alır dışında.

#### <a name="syntax"></a>Sözdizimi

```cpp
BLOB_NAME_STATUS(pszName, IID, flags, data, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*ııd*<br/>
[içinde] Arabirim GUID, `IDD_ISequentialStream`gibi , BLOB almak için kullanılır.

*bayraklar*<br/>
[içinde] OLE Yapılandırılmış Depolama modeli (örneğin, `STGM_READ`) tarafından tanımlanan depolama modu bayrakları.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Durum*<br/>
[çıkış] BLOB alanının durumu.

### <a name="bookmark_entry"></a><a name="bookmark_entry"></a>BOOKMARK_ENTRY

Yer imi sütununa bağlanır.

#### <a name="syntax"></a>Sözdizimi

```cpp
BOOKMARK_ENTRY(variable)
```

#### <a name="parameters"></a>Parametreler

*Değişken*<br/>
[içinde] Yer imi sütununa bağlanacak değişken.

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

Daha fazla bilgi için yer imleri ve [CBookmark](../../data/oledb/cbookmark-class.md) [Sınıf'ı kullanma'ya](using-bookmarks.md) bakın.

### <a name="column_entry"></a><a name="column_entry"></a>Column_entry

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY(nOrdinal, data)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcısı* [ReferansDBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) bakın.

*nOrdinal*<br/>
[içinde] Sütun numarası.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

makro COLUMN_ENTRY aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları arasında.

- [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makrolar arasında.

- [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları arasında.

#### <a name="example"></a>Örnek

Makro konuları, [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)örneklere bakın.

### <a name="column_entry_ex"></a><a name="column_entry_ex"></a>COLUMN_ENTRY_EX

Satır kümesinde veritabanındaki belirli sütuna yapılan bir bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_EX(nOrdinal, wType, nLength, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcısı* [ReferansDBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) bakın.

*nOrdinal*<br/>
[içinde] Sütun numarası.

*Wtype*<br/>
[içinde] Veri türü.

*nUzunluk*<br/>
[içinde] Baytlarda veri boyutu.

*nPrecision*<br/>
[içinde] Veri ve *wType* alırken kullanılacak maksimum `DBTYPE_NUMERIC`hassasiyet. Aksi takdirde, bu parametre yoksayılır.

*nÖlçek*<br/>
[içinde] Veri ve *wType* alırken kullanılacak `DBTYPE_NUMERIC` ölçek `DBTYPE_DECIMAL`veya .

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[içinde] Sütun uzunluğuna bağlanacak değişken.

*Durum*<br/>
[içinde] Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_ENTRY_EX makrosu aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları arasında.

- [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makrolar arasında.

- [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları arasında.

#### <a name="example"></a>Örnek

[Bkz. BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).

### <a name="column_entry_length"></a><a name="column_entry_length"></a>COLUMN_ENTRY_LENGTH

Satır kümesinde veritabanındaki belirli sütuna yapılan bir bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_LENGTH(nOrdinal, data, length)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcısı* [ReferansDBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) bakın.

*nOrdinal*<br/>
[içinde] Sütun numarası, bir ile başlayan. Yer imi sıfır sütununa karşılık gelir.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[içinde] Sütun uzunluğuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

Bu makro *uzunluk* değişkenini destekler. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları arasında.

- [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makrolar arasında.

- [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları arasında.

### <a name="column_entry_length_status"></a><a name="column_entry_length_status"></a>COLUMN_ENTRY_LENGTH_STATUS

Satır kümesinde veritabanındaki belirli sütuna yapılan bir bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_LENGTH_STATUS(nOrdinal, data, length, status)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcısı* [ReferansDBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) bakın.

*nOrdinal*<br/>
[içinde] Sütun numarası.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[içinde] Sütun uzunluğuna bağlanacak değişken.

*Durum*<br/>
[içinde] Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

Uzunluk ve durum değişkenlerini desteklemek istediğinizde bu makroyu kullanın. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları arasında.

- [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makrolar arasında.

- [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları arasında.

### <a name="column_entry_ps"></a><a name="column_entry_ps"></a>COLUMN_ENTRY_PS

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_PS(nOrdinal, nPrecision, nScale, data)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcısı* [ReferansDBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) bakın.

*nOrdinal*<br/>
[içinde] Sütun numarası.

*nPrecision*<br/>
[içinde] Bağlamak istediğiniz sütunun maksimum hassasiyeti.

*nÖlçek*<br/>
[içinde] Bağlamak istediğiniz sütunun ölçeği.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

Bağlamak istediğiniz sütunun kesinliğini ve ölçeğini belirtmenizi sağlar. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları arasında.

- [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makrolar arasında.

- [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları arasında.

### <a name="column_entry_ps_length"></a><a name="column_entry_ps_length"></a>COLUMN_ENTRY_PS_LENGTH

Satır kümesinde veritabanındaki belirli sütuna yapılan bir bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_PS_LENGTH(nOrdinal, nPrecision, nScale, data, length)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcısı* [ReferansDBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) bakın.

*nOrdinal*<br/>
[içinde] Sütun numarası, bir ile başlayan. Yer imi sıfır sütununa karşılık gelir.

*nPrecision*<br/>
[içinde] Bağlamak istediğiniz sütunun maksimum hassasiyeti.

*nÖlçek*<br/>
[içinde] Bağlamak istediğiniz sütunun ölçeği.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[içinde] Sütun uzunluğuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

Bağlamak istediğiniz sütunun kesinliğini ve ölçeğini belirtmenizi sağlar. Bu makro *uzunluk* değişkenini destekler. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları arasında.

- [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makrolar arasında.

- [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları arasında.

### <a name="column_entry_ps_length_status"></a><a name="column_entry_ps_length_status"></a>COLUMN_ENTRY_PS_LENGTH_STATUS

Satır kümesinde veritabanındaki belirli sütuna yapılan bir bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_PS_LENGTH_STATUS(nOrdinal, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcısı* [ReferansDBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) bakın.

*nOrdinal*<br/>
[içinde] Sütun numarası.

*nPrecision*<br/>
[içinde] Bağlamak istediğiniz sütunun maksimum hassasiyeti.

*nÖlçek*<br/>
[içinde] Bağlamak istediğiniz sütunun ölçeği.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[içinde] Sütun uzunluğuna bağlanacak değişken.

*Durum*<br/>
[içinde] Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

Bağlamak istediğiniz sütunun kesinliğini ve ölçeğini belirtmenizi sağlar. Uzunluk ve durum değişkenlerini desteklemek istediğinizde bu makroyu kullanın. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları arasında.

- [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makrolar arasında.

- [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları arasında.

### <a name="column_entry_ps_status"></a><a name="column_entry_ps_status"></a>COLUMN_ENTRY_PS_STATUS

Satır kümesinde veritabanındaki belirli sütuna yapılan bir bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_PS_STATUS(nOrdinal, nPrecision, nScale, data, status)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcısı* [ReferansDBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) bakın.

*nOrdinal*<br/>
[içinde] Sütun numarası.

*nPrecision*<br/>
[içinde] Bağlamak istediğiniz sütunun maksimum hassasiyeti.

*nÖlçek*<br/>
[içinde] Bağlamak istediğiniz sütunun ölçeği.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Durum*<br/>
[içinde] Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

Bağlamak istediğiniz sütunun kesinliğini ve ölçeğini belirtmenizi sağlar. Bu makro *durum* değişkenini destekler. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları arasında.

- [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makrolar arasında.

- [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları arasında.

### <a name="column_entry_status"></a><a name="column_entry_status"></a>COLUMN_ENTRY_STATUS

Satır kümesinde veritabanındaki belirli sütuna yapılan bir bağlamayı temsil eder.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_STATUS(nOrdinal, data, status)
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcısı* [ReferansDBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) bakın.

*nOrdinal*<br/>
[içinde] Sütun numarası.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Durum*<br/>
[içinde] Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

Bu makro *durum* değişkenini destekler. Aşağıdaki yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları arasında.

- [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makrolar arasında.

- [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları arasında.

### <a name="column_entry_type"></a><a name="column_entry_type"></a>COLUMN_ENTRY_TYPE

Veritabanındaki belirli bir sütuna yapılan bir bağlamayı temsil eder. *Tür parametresini* destekler.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_TYPE (nOrdinal, wType, data)
```

#### <a name="parameters"></a>Parametreler

*nOrdinal*<br/>
[içinde] Sütun numarası.

*Wtype*<br/>
[içinde] Sütun girişinin veri türü.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

Bu makro, veri türünü belirtme aracı sağlayan [COLUMN_ENTRY](../../data/oledb/column-entry.md) makronun özelleştirilmiş bir varyantıdır.

### <a name="column_entry_type_size"></a><a name="column_entry_type_size"></a>COLUMN_ENTRY_TYPE_SIZE

Veritabanındaki belirli bir sütuna yapılan bir bağlamayı temsil eder. Tür ve *boyut* *parametrelerini* destekler.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_ENTRY_TYPE_SIZE(nOrdinal, wType, nLength, data)
```

#### <a name="parameters"></a>Parametreler

*nOrdinal*<br/>
[içinde] Sütun numarası.

*Wtype*<br/>
[içinde] Sütun girişinin veri türü.

*nUzunluk*<br/>
[içinde] Baytlarda sütun girişinin boyutu.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

Bu makro, veri boyutu ve türü belirtme aracı sağlayan [COLUMN_ENTRY](../../data/oledb/column-entry.md) makronun özelleştirilmiş bir çeşididir.

### <a name="column_name"></a><a name="column_name"></a>Column_name

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder. [COLUMN_ENTRY](../../data/oledb/column-entry.md)benzer , ancak bu makro sütun numarası yerine sütun adını alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME(pszName, data)
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_* makrolar [COLUMN_ENTRY](../../data/oledb/column-entry.md)ile aynı yerlerde kullanılır:

- [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları arasında.

- [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makrolar arasında.

- [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları arasında.

### <a name="column_name_ex"></a><a name="column_name_ex"></a>COLUMN_NAME_EX

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder. [COLUMN_NAME](../../data/oledb/column-name.md)benzer , bu makro dışında da veri türü, boyut, kesinlik, ölçek, sütun uzunluğu ve sütun durumu alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_EX(pszName, wType, nLength, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*Wtype*<br/>
[içinde] Veri türü.

*nUzunluk*<br/>
[içinde] Baytlarda veri boyutu.

*nPrecision*<br/>
[içinde] Veri ve *wType* alırken kullanılacak maksimum `DBTYPE_NUMERIC`hassasiyet. Aksi takdirde, bu parametre yoksayılır.

*nÖlçek*<br/>
[içinde] Veri ve *wType* alırken kullanılacak `DBTYPE_NUMERIC` ölçek `DBTYPE_DECIMAL`veya .

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[içinde] Sütun uzunluğuna bağlanacak değişken.

*Durum*<br/>
[içinde] Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_* makroların nerede kullanıldığı hakkında bilgi için [COLUMN_NAME](../../data/oledb/column-name.md) bakın.

### <a name="column_name_length"></a><a name="column_name_length"></a>COLUMN_NAME_LENGTH

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder. [COLUMN_NAME](../../data/oledb/column-name.md)benzer , bu makro da sütun uzunluğu alır dışında.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_LENGTH(pszName, data, length)
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[içinde] Sütun uzunluğuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_* makroların nerede kullanıldığı hakkında bilgi için [COLUMN_NAME](../../data/oledb/column-name.md) bakın.

### <a name="column_name_length_status"></a><a name="column_name_length_status"></a>COLUMN_NAME_LENGTH_STATUS

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder. [COLUMN_NAME](../../data/oledb/column-name.md)benzer , bu makro dışında da sütun uzunluğu ve sütun durumu alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_LENGTH_STATUS(pszName, data, length, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[içinde] Sütun uzunluğuna bağlanacak değişken.

*Durum*<br/>
[içinde] Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_* makroların nerede kullanıldığı hakkında bilgi için [COLUMN_NAME](../../data/oledb/column-name.md) bakın.

### <a name="column_name_ps"></a><a name="column_name_ps"></a>COLUMN_NAME_PS

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder. [COLUMN_NAME](../../data/oledb/column-name.md)benzer , bu makro da hassas ve ölçek alır dışında.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_PS(pszName, nPrecision, nScale, data )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*nPrecision*<br/>
[içinde] Bağlamak istediğiniz sütunun maksimum hassasiyeti.

*nÖlçek*<br/>
[içinde] Bağlamak istediğiniz sütunun ölçeği.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_* makroların nerede kullanıldığı hakkında bilgi için [COLUMN_NAME](../../data/oledb/column-name.md) bakın.

### <a name="column_name_ps_length"></a><a name="column_name_ps_length"></a>COLUMN_NAME_PS_LENGTH

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder. [COLUMN_NAME](../../data/oledb/column-name.md)benzer , bu makro da kesinlik, ölçek ve sütun uzunluğu alır dışında.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_PS_LENGTH(pszName, nPrecision, nScale, data, length )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*nPrecision*<br/>
[içinde] Bağlamak istediğiniz sütunun maksimum hassasiyeti.

*nÖlçek*<br/>
[içinde] Bağlamak istediğiniz sütunun ölçeği.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[içinde] Sütun uzunluğuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_* makroların nerede kullanıldığı hakkında bilgi için [COLUMN_NAME](../../data/oledb/column-name.md) bakın.

### <a name="column_name_ps_length_status"></a><a name="column_name_ps_length_status"></a>COLUMN_NAME_PS_LENGTH_STATUS

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder. [COLUMN_NAME](../../data/oledb/column-name.md)benzer , bu makro dışında da kesinlik, ölçek, sütun uzunluğu ve sütun durumu alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_PS_LENGTH_STATUS(pszName, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*nPrecision*<br/>
[içinde] Bağlamak istediğiniz sütunun maksimum hassasiyeti.

*nÖlçek*<br/>
[içinde] Bağlamak istediğiniz sütunun ölçeği.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Uzun -luğu*<br/>
[içinde] Sütun uzunluğuna bağlanacak değişken.

*Durum*<br/>
[içinde] Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_* makroların nerede kullanıldığı hakkında bilgi için [COLUMN_NAME](../../data/oledb/column-name.md) bakın.

### <a name="column_name_ps_status"></a><a name="column_name_ps_status"></a>COLUMN_NAME_PS_STATUS

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder. [COLUMN_NAME](../../data/oledb/column-name.md)benzer , bu makro da kesinlik, ölçek ve sütun durumu alır dışında.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_PS_STATUS(pszName, nPrecision, nScale, data, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*nPrecision*<br/>
[içinde] Bağlamak istediğiniz sütunun maksimum hassasiyeti.

*nÖlçek*<br/>
[içinde] Bağlamak istediğiniz sütunun ölçeği.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Durum*<br/>
[içinde] Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_* makroların nerede kullanıldığı hakkında bilgi için [COLUMN_NAME](../../data/oledb/column-name.md) bakın.

### <a name="column_name_status"></a><a name="column_name_status"></a>COLUMN_NAME_STATUS

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder. [COLUMN_NAME](../../data/oledb/column-name.md)benzer , bu makro da sütun durumu alır dışında.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_STATUS(pszName, data, status )
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

*Durum*<br/>
[içinde] Sütun durumuna bağlanacak değişken.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_* makroların nerede kullanıldığı hakkında bilgi için [COLUMN_NAME](../../data/oledb/column-name.md) bakın.

### <a name="column_name_type"></a><a name="column_name_type"></a>COLUMN_NAME_TYPE

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder. [COLUMN_NAME](../../data/oledb/column-name.md)benzer , bu makro da veri türü alır dışında.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_TYPE(pszName, wType, data)
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*Wtype*<br/>
[içinde] Veri türü.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_* makroların nerede kullanıldığı hakkında bilgi için [COLUMN_NAME](../../data/oledb/column-name.md) bakın.

### <a name="column_name_type_ps"></a><a name="column_name_type_ps"></a>COLUMN_NAME_TYPE_PS

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder. [COLUMN_NAME](../../data/oledb/column-name.md)benzer , bu makro dışında da veri türü, kesinlik ve ölçek alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_TYPE_PS(pszName, wType, nPrecision, nScale, data)
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*Wtype*<br/>
[içinde] Veri türü.

*nPrecision*<br/>
[içinde] Veri ve *wType* alırken kullanılacak maksimum `DBTYPE_NUMERIC`hassasiyet. Aksi takdirde, bu parametre yoksayılır.

*nÖlçek*<br/>
[içinde] Veri ve *wType* alırken kullanılacak `DBTYPE_NUMERIC` ölçek `DBTYPE_DECIMAL`veya .

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_* makroların nerede kullanıldığı hakkında bilgi için [COLUMN_NAME](../../data/oledb/column-name.md) bakın.

### <a name="column_name_type_size"></a><a name="column_name_type_size"></a>COLUMN_NAME_TYPE_SIZE

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder. [COLUMN_NAME](../../data/oledb/column-name.md)benzer , bu makro dışında da veri türü ve boyutu alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_TYPE_SIZE(pszName, wType, nLength, data)
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*Wtype*<br/>
[içinde] Veri türü.

*nUzunluk*<br/>
[içinde] Baytlarda veri boyutu.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_* makroların nerede kullanıldığı hakkında bilgi için [COLUMN_NAME](../../data/oledb/column-name.md) bakın.

### <a name="column_name_type_status"></a><a name="column_name_type_status"></a>COLUMN_NAME_TYPE_STATUS

Satır kümesindeki belirli sütuna satır kümesiüzerinde bir bağlama temsil eder. [COLUMN_NAME](../../data/oledb/column-name.md)benzer , bu makro dışında da veri türü ve sütun durumu alır.

#### <a name="syntax"></a>Sözdizimi

```cpp
COLUMN_NAME_TYPE_STATUS(pszName, wType, status, data)
```

#### <a name="parameters"></a>Parametreler

*pszName*<br/>
[içinde] Sütun adına işaretçi. Ad bir Unicode dizesi olmalıdır. Örneğin, ismin önüne 'L' koyarak bunu başarabilirsiniz: `L"MyColumn"`.

*Wtype*<br/>
[içinde] Veri türü.

*Durum*<br/>
[içinde] Sütun durumuna bağlanacak değişken.

*Veri*<br/>
[içinde] Kullanıcı kaydındaki karşılık gelen veri üyesi.

#### <a name="remarks"></a>Açıklamalar

COLUMN_NAME_* makroların nerede kullanıldığı hakkında bilgi için [COLUMN_NAME](../../data/oledb/column-name.md) bakın.

### <a name="end_column_map"></a><a name="end_column_map"></a>END_COLUMN_MAP

Sütun eşlemi girişlerinin sonunu işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_COLUMN_MAP()
```

#### <a name="remarks"></a>Açıklamalar

Bir satır kümesinde tek bir aksesuarla kullanılır. BEGIN_COLUMN_MAP makrosu END_COLUMN_MAP makrosu yla tamamlanır.

#### <a name="example"></a>Örnek

[Bkz. BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md).

### <a name="define_command"></a><a name="define_command"></a>DEFINE_COMMAND

[CCommand](../../data/oledb/ccommand-class.md) sınıfını kullanırken satır kümesini oluşturmak için kullanılacak komutu belirtir. Yalnızca belirtilen uygulama türüyle (ANSI veya Unicode) eşleşen dize türlerini kabul eder.

> [!NOTE]
> DEFINE_COMMAND yerine [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) kullanmanız önerilir.

#### <a name="syntax"></a>Sözdizimi

```cpp
DEFINE_COMMAND(x, szCommand)
```

#### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Kullanıcı kaydı (komut) sınıfının adı.

*szKomut*<br/>
[içinde] [CCommand](../../data/oledb/ccommand-class.md)kullanırken satır kümesi oluşturmak için kullanılacak komut dizesi.

#### <a name="remarks"></a>Açıklamalar

CCommand komut metni belirtmezseniz belirttiğiniz komut dizesi varsayılan olarak [kullanılır::Açık](../../data/oledb/ccommand-open.md) yöntemi.

Bu makro, uygulamanızı ANSI veya Unicode dizeleri olarak oluşturursanız, UYGULAMANIZI Unicode olarak oluşturursanız ANSI dizeleri kabul eder. Eski ANSI veya Unicode uygulama türüne bakılmaksızın Unicode dizeleri kabul ettiği için, DEFINE_COMMAND yerine [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) kullanmanız önerilir.

#### <a name="example"></a>Örnek

[Bkz. BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).

### <a name="define_command_ex"></a><a name="define_command_ex"></a>DEFINE_COMMAND_EX

[CCommand](../../data/oledb/ccommand-class.md) sınıfını kullanırken satır kümesini oluşturmak için kullanılacak komutu belirtir. Unicode ve ANSI uygulamalarını destekler.

#### <a name="syntax"></a>Sözdizimi

```cpp
DEFINE_COMMAND_EX(x, wszCommand)
```

#### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Kullanıcı kaydı (komut) sınıfının adı.

*wszKomut*<br/>
[içinde] [CCommand](../../data/oledb/ccommand-class.md)kullanırken satır kümesi oluşturmak için kullanılacak komut dizesi.

#### <a name="remarks"></a>Açıklamalar

CCommand komut metni belirtmezseniz belirttiğiniz komut dizesi varsayılan olarak [kullanılır::Açık](../../data/oledb/ccommand-open.md) yöntemi.

Bu makro, uygulama türünden bağımsız olarak Unicode dizelerini kabul eder. Bu makro, Unicode'un yanı sıra ANSI uygulamalarını desteklediği için [DEFINE_COMMAND](../../data/oledb/define-command.md) tercih edilir.

#### <a name="example"></a>Örnek

[Bkz. BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).

### <a name="begin_param_map"></a><a name="begin_param_map"></a>BEGIN_PARAM_MAP

Parametre eşlemelerinin başlangıcını işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
BEGIN_PARAM_MAP(x)
```

#### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Kullanıcı kayıt sınıfının adı.

#### <a name="remarks"></a>Açıklamalar

Parametreler [komutlar](/previous-versions/windows/desktop/ms724608(v=vs.85))tarafından kullanılır.

#### <a name="example"></a>Örnek

[BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) makrosu için örneğe bakın.

### <a name="end_param_map"></a><a name="end_param_map"></a>END_PARAM_MAP

Parametre eşlemi girişlerinin sonunu işaretler.

#### <a name="syntax"></a>Sözdizimi

```cpp
END_PARAM_MAP()
```

#### <a name="example"></a>Örnek

[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) makrosu için örneğe bakın.

### <a name="set_param_type"></a><a name="set_param_type"></a>SET_PARAM_TYPE

Makro giriş, çıktı veya giriş/çıktı SET_PARAM_TYPE izleyen COLUMN_ENTRY makroları belirtir.

#### <a name="syntax"></a>Sözdizimi

```cpp
SET_PARAM_TYPE(type)
```

#### <a name="parameters"></a>Parametreler

*Türü*<br/>
[içinde] Parametre için ayarlanan tür.

#### <a name="remarks"></a>Açıklamalar

Sağlayıcılar, yalnızca temel veri kaynağı tarafından desteklenen parametre giriş/çıkış türlerini destekler. Tür, bir veya daha `DBPARAMIO` fazla değerin bir leşimidir (bkz. *OLE DB Programcısı*Referansı'ndaki [DBBINDING Yapıları):](/previous-versions/windows/desktop/ms716845(v=vs.85))

- `DBPARAMIO_NOTPARAM`Erişimcinin parametreleri yok. Genellikle, kullanıcıya `eParamIO` parametrelerin yoksayDığını hatırlatmak için satır erişimcilerde bu değere ayarlayabilirsiniz.

- `DBPARAMIO_INPUT`Giriş parametresi.

- `DBPARAMIO_OUTPUT`Bir çıkış parametresi.

- `DBPARAMIO_INPUT | DBPARAMIO_OUTPUT`Parametre hem giriş hem de çıktı parametresitir.

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

**Başlık:** atldbcli.h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları için Makrolar ve Genel İşlevler](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
