---
title: Kayıt Alanı Değişim İşlevleri
ms.date: 09/17/2019
f1_keywords:
- AFXDB/RFX_Binary
- AFXDB/RFX_Bool
- AFXDB/RFX_Byte
- AFXDB/RFX_Date
- AFXDB/RFX_Double
- AFXDB/RFX_Int
- AFXDB/RFX_Long
- AFXDB/RFX_LongBinary
- AFXDB/RFX_Single
- AFXDB/RFX_Text
- AFXDB/RFX_Binary_Bulk
- AFXDB/RFX_Bool_Bulk
- AFXDB/RFX_Byte_Bulk
- AFXDB/RFX_Date_Bulk
- AFXDB/RFX_Double_Bulk
- AFXDB/RFX_Int_Bulk
- AFXDB/RFX_Long_Bulk
- AFXDB/RFX_Single_Bulk
- AFXDB/RFX_Text_Bulk
- AFXDB/DFX_Binary
- AFXDB/DFX_Bool
- AFXDB/DFX_Byte
- AFXDB/DFX_Currency
- AFXDB/DFX_DateTime
- AFXDB/DFX_Double
- AFXDB/DFX_Long
- AFXDB/DFX_LongBinary
- AFXDB/DFX_Short
- AFXDB/DFX_Single
- AFXDB/DFX_Text
helpviewer_keywords:
- DAO (Data Access Objects), record field exchange (DFX)
- ODBC, bulk RFX data exchange functions [MFC]
- RFX (record field exchange), ODBC classes
- DFX (DAO record field exchange), data exchange functions [MFC]
- DFX functions [MFC]
- bulk RFX functions [MFC]
- DFX (DAO record field exchange)
- RFX (record field exchange), DAO classes
- ODBC, RFX
- RFX (record field exchange), data exchange functions [MFC]
- RFX (record field exchange)
ms.assetid: 6e4c5c1c-acb7-4c18-bf51-bf7959a696cd
ms.openlocfilehash: bfd3ba64a33547b8a27e0f3bc896f39c94486464
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372984"
---
# <a name="record-field-exchange-functions"></a>Kayıt Alanı Değişim İşlevleri

Bu konu, bir kayıt kümesi nesnesi ile veri kaynağı arasındaki veri aktarımını otomatikleştirmek ve veriler üzerinde diğer işlemleri gerçekleştirmek için kullanılan Kayıt Alanı Değişimi (RFX, Bulk RFX ve DFX) işlevlerini listeler.

ODBC tabanlı sınıfları kullanıyorsanız ve toplu satır alma uyguladıysanız, veri kaynağı `DoBulkFieldExchange` sütununa `CRecordset` karşılık gelen her veri üyesi için Toplu RFX işlevlerini arayarak üye işlevini el ile geçersiz kılmanız gerekir.

ODBC tabanlı sınıflarda toplu satır alma uygulamadıysanız veya DAO tabanlı sınıfları (eski) kullanıyorsanız, ClassWizard kayıt `DoFieldExchange` setinizdeki `CRecordset` her `CDaoRecordset` alan veri üyesi için RFX işlevlerini (ODBC sınıfları için) veya DFX işlevlerini (DAO sınıfları için) çağırarak üye işlevini geçersiz kılar.

Kayıt alanı değişim fonksiyonları, çerçeve her `DoFieldExchange` `DoBulkFieldExchange`çağrıda bulunduğunda veri aktarımı veya . Her işlev belirli bir veri türünü aktarın.

Bu işlevlerin nasıl kullanıldığı hakkında daha fazla bilgi için Kayıt [Alanı Değişimi: RFX Nasıl Çalışır (ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md)makalelerini incegörün. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

Dinamik olarak bağladığınız veri sütunları [için, Recordset: Dynamically Binding Data Columns (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)makalelerinde açıklandığı gibi RFX veya DFX işlevlerini kendiniz de arayabilirsiniz. Ayrıca, Teknik Not [43](../../mfc/tn043-rfx-routines.md) (ODBC için) ve Teknik Not [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) 'de (DAO için) açıklandığı gibi, kendi özel RFX veya DFX yordamlarınızı yazabilirsiniz.

RFX ve Toplu RFX `DoFieldExchange` `DoBulkFieldExchange` işlevlerinin bir örneği için, RFX_Text ve [RFX_Text_Bulk]#rfx_text_bulk) görün. [RFX_Text](#rfx_text) DFX işlevleri RFX işlevlerine çok benzer.

### <a name="rfx-functions-odbc"></a>RFX Fonksiyonları (ODBC)

|||
|-|-|
|[RFX_Binary](#rfx_binary)|[CByteArray](cbytearray-class.md)türü bayt dizileri aktarın.|
|[RFX_Bool](#rfx_bool)|Boolean verilerini aktarın.|
|[RFX_Byte](#rfx_byte)|Tek bir bayt veri aktarın.|
|[RFX_Date](#rfx_date)|[CTime](../../atl-mfc-shared/reference/ctime-class.md) veya TIMESTAMP_STRUCT kullanarak saat ve tarih verilerini aktarın.|
|[RFX_Double](#rfx_double)|Çift duyarlıklı float verileri aktarın.|
|[RFX_Int](#rfx_int)|Alıcı verilerini aktarın.|
|[RFX_Long](#rfx_long)|Uzun tümseci verilerini aktarın.|
|[RFX_LongBinary](#rfx_longbinary)|İkili büyük nesne (BLOB) verilerini [CLongBinary](clongbinary-class.md) sınıfının bir nesnesiyle aktarır.|
|[RFX_Single](#rfx_single)|Float verilerini aktarın.|
|[Rfx_text](#rfx_text)|Dize verilerini aktarın.|

### <a name="bulk-rfx-functions-odbc"></a>Toplu RFX Fonksiyonları (ODBC)

|||
|-|-|
|[RFX_Binary_Bulk](#rfx_binary_bulk)|Bayt veri dizilerini aktarıyor.|
|[RFX_Bool_Bulk](#rfx_bool_bulk)|Boolean veri dizilerini aktarıyor.|
|[RFX_Byte_Bulk](#rfx_byte_bulk)|Tek bayt dizilerini aktarın.|
|[RFX_Date_Bulk](#rfx_date_bulk)|Tür TIMESTAMP_STRUCT veri dizilerini aktarın.|
|[RFX_Double_Bulk](#rfx_double_bulk)|Çift duyarlıklı, kayan noktalı veri dizileri aktarıyor.|
|[RFX_Int_Bulk](#rfx_int_bulk)|Birdizi tümseci veri aktarıyor.|
|[RFX_Long_Bulk](#rfx_long_bulk)|Uzun tümseci veri dizilerini aktarıyor.|
|[RFX_Single_Bulk](#rfx_single_bulk)|Kayan nokta veri dizilerini aktarıyor.|
|[RFX_Text_Bulk](#rfx_text_bulk)|LPSTR türünden veri dizilerini aktarın.|

### <a name="dfx-functions-dao"></a>DFX Fonksiyonları (DAO)

|||
|-|-|
|[DFX_Binary](#dfx_binary)|[CByteArray](cbytearray-class.md)türü bayt dizileri aktarın.|
|[DFX_Bool](#dfx_bool)|Boolean verilerini aktarın.|
|[DFX_Byte](#dfx_byte)|Tek bir bayt veri aktarın.|
|[DFX_Currency](#dfx_currency)|[COleCurrency](colecurrency-class.md)türünden para birimi verilerini aktarır.|
|[DFX_DateTime](#dfx_datetime)|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)türünde saat ve tarih verilerini aktarır.|
|[DFX_Double](#dfx_double)|Çift duyarlıklı float verileri aktarın.|
|[DFX_Long](#dfx_long)|Uzun tümseci verilerini aktarın.|
|[DFX_LongBinary](#dfx_longbinary)|İkili büyük nesne (BLOB) verilerini sınıfın `CLongBinary` bir nesnesiyle aktarır. DAO için, bunun yerine [DFX_Binary](#dfx_binary) kullanmanız önerilir.|
|[DFX_Short](#dfx_short)|Kısa tümseci verilerini aktarın.|
|[DFX_Single](#dfx_single)|Float verilerini aktarın.|
|[DFX_Text](#dfx_text)|Dize verilerini aktarın.|

=============================================

## <a name="rfx_binary"></a><a name="rfx_binary"></a>RFX_Binary

Bir `CRecordset` nesnenin alan veri üyeleri ile ODBC türü SQL_BINARY, SQL_VARBINARY veya SQL_LONGVARBINARY veri kaynağındaki bir kaydın sütunları arasında bayt dizileri aktarıyor.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Binary(
   CFieldExchange* pFX,
   const char* szName,
   CByteArray& value,
   int nMaxLength = 255);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Bir `CFieldExchange` nesnenin belirtebileceği işlemler hakkında daha fazla bilgi için Kayıt [Alanı Değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım [için, CByteArray](cbytearray-class.md)türünün değeri belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

*nMaxLength*<br/>
Aktarılan dize veya dizinin izin verilen maksimum uzunluğu. *nMaxLength* varsayılan değeri 255'tir. Yasal değerler 1'den INT_MAX kadardır. Çerçeve, veriler için bu miktarda alan ayırır. En iyi performans için, beklediğiniz en büyük veri öğesini barındıracak kadar büyük bir değer geçirin.

### <a name="remarks"></a>Açıklamalar

Bu tür veri kaynağındaki veriler, kayıt kümesindeki `CByteArray` türe ve türüne eşlenir.

### <a name="example"></a>Örnek

[Bkz. RFX_Text.](#rfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_bool"></a><a name="rfx_bool"></a>RFX_Bool

Boolean verilerini bir `CRecordset` nesnenin alan veri üyeleri ile ODBC türü veri kaynağındaki bir kaydın sütunları arasında SQL_BIT aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Bool(
   CFieldExchange* pFX,
   const char* szName,
   BOOL& value);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Bir `CFieldExchange` nesnenin belirtebileceği işlemler hakkında daha fazla bilgi için Kayıt [Alanı Değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, BOOL türünün değeri belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

[Bkz. RFX_Text.](#rfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_byte"></a><a name="rfx_byte"></a>RFX_Byte

Bir `CRecordset` nesnenin alan veri üyeleri ile ODBC türü veri kaynağındaki bir kaydın sütunları arasında tek bayt aktarAn SQL_TINYINT.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Byte(
   CFieldExchange* pFX,
   const char* szName,
   BYTE& value);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Bir `CFieldExchange` nesnenin belirtebileceği işlemler hakkında daha fazla bilgi için Kayıt [Alanı Değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, BYTE türündeki değer, belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

[Bkz. RFX_Text.](#rfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_date"></a><a name="rfx_date"></a>RFX_Date

Bir `CTime` `CRecordset` nesnenin alan veri üyeleri ile ODBC türü SQL_DATE, SQL_TIME veya SQL_TIMESTAMP veri kaynağındaki bir kaydın sütunları arasında veri aktarır veya TIMESTAMP_STRUCT.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   CTime& value);

void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   TIMESTAMP_STRUCT& value);

void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   COleDateTime& value);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Bir `CFieldExchange` nesnenin belirtebileceği işlemler hakkında daha fazla bilgi için Kayıt [Alanı Değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer; aktarılacak değer. İşlevin çeşitli sürümleri değer için farklı veri türleri alır:

İşlevin ilk sürümü bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine bir başvuru alır. Kayıt kümesinden veri kaynağına aktarım için bu değer belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

İşlevin ikinci sürümü bir `TIMESTAMP_STRUCT` yapıya başvuru alır. Bu yapıyı aramadan önce kendiniz ayarlamalısınız. Bu sürüm için ne iletişim veri alışverişi (DDX) desteği ne de kod sihirbazı desteği kullanılabilir. İşlevin üçüncü sürümü, [coleDatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine bir başvuru alması dışında ilk sürüme benzer şekilde çalışır.

### <a name="remarks"></a>Açıklamalar

İşlevin `CTime` sürümü bazı ara işleme yükü empoze ve biraz sınırlı bir aralığı vardır. Bu faktörlerden birini çok sınırlayıcı bulursanız, işlevin ikinci sürümünü kullanın. Ancak kod sihirbazı ve DDX desteği eksikliği ve yapıyı kendiniz ayarlama gereksinimine dikkat edin.

### <a name="example"></a>Örnek

[Bkz. RFX_Text.](#rfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_double"></a><a name="rfx_double"></a>RFX_Double

Bir **double float** `CRecordset` nesnenin alan veri üyeleri ile ODBC türü veri kaynağındaki bir kaydın sütunları arasında çift float veri aktarAn SQL_DOUBLE.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Double(
   CFieldExchange* pFX,
   const char* szName,
   double& value);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Bir `CFieldExchange` nesnenin belirtebileceği işlemler hakkında daha fazla bilgi için Kayıt [Alanı Değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, tip **double**değeri, belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

[Bkz. RFX_Text.](#rfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_int"></a><a name="rfx_int"></a>RFX_Int

Bir `CRecordset` nesnenin alan veri üyeleri ile ODBC türü veri kaynağındaki bir kaydın sütunları arasında tamsayı verilerini aktaran SQL_SMALLINT.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Bir `CFieldExchange` nesnenin belirtebileceği işlemler hakkında daha fazla bilgi için Kayıt [Alanı Değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, **int**türü değeri, belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

[Bkz. RFX_Text.](#rfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_long"></a><a name="rfx_long"></a>RFX_Long

Bir `CRecordset` nesnenin alan veri üyeleri ile ODBC türü veri kaynağındaki bir kaydın sütunları arasında uzun tamsayı verileri aktarAn SQL_INTEGER.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Long(
   CFieldExchange* pFX,
   const char* szName,
   LONG&
value );
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Bir `CFieldExchange` nesnenin belirtebileceği işlemler hakkında daha fazla bilgi için Kayıt [Alanı Değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, **uzun**tür değeri belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

[Bkz. RFX_Text.](#rfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_longbinary"></a><a name="rfx_longbinary"></a>RFX_LongBinary

[CLongBinary](clongbinary-class.md) sınıfı kullanarak ikili büyük nesne (BLOB) verilerini `CRecordset` bir nesnenin alan veri üyeleri ile ODBC türü SQL_LONGVARBINARY veya SQL_LONGVARCHAR veri kaynağındaki bir kaydın sütunları arasında aktarır.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_LongBinary(
   CFieldExchange* pFX,
   const char* szName,
   CLongBinary& value);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Bir `CFieldExchange` nesnenin belirtebileceği işlemler hakkında daha fazla bilgi için Kayıt [Alanı Değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, `CLongBinary`türü, değeri, belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

[Bkz. RFX_Text.](#rfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_single"></a><a name="rfx_single"></a>RFX_Single

Kayan nokta verilerini bir `CRecordset` nesnenin alan veri üyeleri ile ODBC türü veri kaynağındaki bir kaydın sütunları arasında SQL_REAL.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Single(
   CFieldExchange* pFX,
   const char* szName,
   float& value);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Bir `CFieldExchange` nesnenin belirtebileceği işlemler hakkında daha fazla bilgi için Kayıt [Alanı Değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, tür **float**değeri, belirtilen veri üyesialınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

[Bkz. RFX_Text.](#rfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_text"></a><a name="rfx_text"></a>Rfx_text

ODBC türü SQL_LONGVARCHAR, `CRecordset` SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL veya SQL_NUMERIC veri kaynağında bir nesnenin alan veri üyeleri ve bir kaydın sütunları arasındaki verileri aktarın. `CString`

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Text(
   CFieldExchange* pFX,
   const char* szName,
   CString& value,
   int nMaxLength = 255,
   int nColumnType = SQL_VARCHAR,
   short nScale = 0);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
Sınıfın `CFieldExchange`bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Bir `CFieldExchange` nesnenin belirtebileceği işlemler hakkında daha fazla bilgi için Kayıt [Alanı Değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, `CString`türü, değeri, belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

*nMaxLength*<br/>
Aktarılan dize veya dizinin izin verilen maksimum uzunluğu. *nMaxLength* varsayılan değeri 255'tir. Yasal değerler 1-INT_MAX). Çerçeve, veriler için bu miktarda alan ayırır. En iyi performans için, beklediğiniz en büyük veri öğesini barındıracak kadar büyük bir değer geçirin.

*nSütun Tipi*<br/>
Parametreler için kullanılır. Parametrenin veri türünü gösteren bir alıcı. Türü, **formun**SQL_XXX bir ODBC veri türüdür.

*nÖlçek*<br/>
ODBC türü SQL_DECIMAL veya SQL_NUMERIC değerleri için ölçeği belirtir. *nScale* yalnızca parametre değerlerini ayarlarken kullanışlıdır. Daha fazla bilgi için, *ODBC SDK Programcısı Nın Referansı'nın*Ek D'sinde yer alan "Hassaslık, Ölçek, Uzunluk ve Görüntü Boyutu" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Tüm bu türlerin veri kaynağındaki veriler kayıt kümesine `CString` ve kayıt kümesinden eşlenir.

### <a name="example"></a>Örnek

Bu örnek, '' ye `RFX_Text`yapılan birkaç çağrıyı gösterir. Ayrıca iki arama `CFieldExchange::SetFieldType`da dikkat edin. Parametreler için çağrıyı `SetFieldType` ve RFX çağrısını yazmanız gerekir. Çıktı sütun çağrısı ve ilişkili RFX çağrıları normalde bir kod sihirbazı tarafından yazılır.

```cpp
void CCustomer::DoFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   // Macros such as RFX_Text() and RFX_Int() are dependent on the
   // type of the member variable, not the type of the field in the database.
   // ODBC will try to automatically convert the column value to the requested type
   RFX_Long(pFX, _T("[CustomerID]"), m_CustomerID);
   RFX_Text(pFX, _T("[ContactFirstName]"), m_ContactFirstName);
   RFX_Text(pFX, _T("[PostalCode]"), m_PostalCode);
   RFX_Text(pFX, _T("[L_Name]"), m_L_Name);
   RFX_Long(pFX, _T("[BillingID]"), m_BillingID);

   pFX->SetFieldType(CFieldExchange::inputParam);
   RFX_Text(pFX, _T("Param"), m_strParam);
}
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_binary_bulk"></a><a name="rfx_binary_bulk"></a>RFX_Binary_Bulk

ODBC veri kaynağının bir sütunundan birden çok bayt veri `CRecordset`satırını türetilmiş bir nesnedeki karşılık gelen diziye aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Binary_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Daha fazla bilgi için, kayıt [alanı değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*prgByteVals*<br/>
BYTE değerleri dizisiiçin bir işaretçi. Bu dizi, veri kaynağından kayıt kümesine aktarılacak verileri depolar.

*Prglengths*<br/>
Uzun tamsayılar dizisi için bir işaretçi. Bu dizi *prgByteVals*tarafından işaret edilen dizide her değerin baytuzunluğu depolayacak. Karşılık gelen veri öğesi Null değeri içeriyorsa, SQL_NULL_DATA değerinin depolanacağını unutmayın. Daha fazla bilgi için, `SQLBindCol` *ODBC SDK Programcısı Nın Başvurusu'ndaki ODBC*API işlevine bakın.

*nMaxLength*<br/>
*PrgByteVals*tarafından işaret edilen dizide depolanan değerlerin izin verilen maksimum uzunluğu. Verilerin kesildirilmediğinden emin olmak için, beklediğiniz en büyük veri öğesini barındıracak kadar büyük bir değer geçirin.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütununda SQL_BINARY, SQL_VARBINARY veya SQL_LONGVARBINARY ODBC türü olabilir. Kayıt kümesi, BYTE'ye tür işaretçisinin bir alan veri üyesini tanımlamalıdır.

*PrgByteVals* ve *prgLengths'ı* NULL'a başolarak ayarlarsanız, işaret ettikleri diziler satır kümesi boyutuna eşit boyutlara sahip olarak otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarAr. Kayıt setinizin güncelleştirilebilmesi için ODBC API `SQLSetPos`işlevini kullanmanız gerekir.

Daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md)makalelerini incegörün.

### <a name="example"></a>Örnek

[Bkz. RFX_Text_Bulk.](#rfx_text_bulk)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_bool_bulk"></a><a name="rfx_bool_bulk"></a>RFX_Bool_Bulk

ODBC veri kaynağının bir sütunundaki birden çok Boolean veri `CRecordset`satırını türetilmiş bir nesnedeki karşılık gelen diziye aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Bool_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BOOL** prgBoolVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Daha fazla bilgi için, kayıt [alanı değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*prgBoolVals*<br/>
BOOL değerleri dizisi için bir işaretçi. Bu dizi, veri kaynağından kayıt kümesine aktarılacak verileri depolar.

*Prglengths*<br/>
Uzun tamsayılar dizisi için bir işaretçi. Bu dizi *prgBoolVals*tarafından işaret edilen dizide her değerin baytuzunluğu depolayacak. Karşılık gelen veri öğesi Null değeri içeriyorsa, SQL_NULL_DATA değerinin depolanacağını unutmayın. Daha fazla bilgi için, `SQLBindCol` *ODBC SDK Programcısı Nın Başvurusu'ndaki ODBC*API işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütununda odbc türünde SQL_BIT olmalıdır. Kayıt kümesi, BOOL türü işaretçisinin bir alan veri üyesini tanımlamalıdır.

*PrgBoolVals* ve *prgLengths'ı* NULL'a başolarak ayarlarsanız, işaret ettikleri diziler satır kümesi boyutuna eşit boyutlara sahip olarak otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarAr. Kayıt setinizi güncelleştirilebilir hale getirmek için ODBC `SQLSetPos`API işlevini kullanmanız gerekir.

Daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md)makalelerini incegörün.

### <a name="example"></a>Örnek

[Bkz. RFX_Text_Bulk.](#rfx_text_bulk)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_byte_bulk"></a><a name="rfx_byte_bulk"></a>RFX_Byte_Bulk

ODBC veri kaynağının bir sütunundan birden çok satırlık tek bayt satırını türetilmiş bir `CRecordset`nesnedeki karşılık gelen diziye aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Byte_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Daha fazla bilgi için, kayıt [alanı değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*prgByteVals*<br/>
BYTE değerleri dizisiiçin bir işaretçi. Bu dizi, veri kaynağından kayıt kümesine aktarılacak verileri depolar.

*Prglengths*<br/>
Uzun tamsayılar dizisi için bir işaretçi. Bu dizi *prgByteVals*tarafından işaret edilen dizide her değerin baytuzunluğu depolayacak. Karşılık gelen veri öğesi Null değeri içeriyorsa, SQL_NULL_DATA değerinin depolanacağını unutmayın. Daha fazla bilgi için, `SQLBindCol` *ODBC SDK Programcısı Nın Başvurusu'ndaki ODBC*API işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütununda odbc türünde SQL_TINYINT olmalıdır. Kayıt kümesi, BYTE'ye tür işaretçisinin bir alan veri üyesini tanımlamalıdır.

*PrgByteVals* ve *prgLengths'ı* NULL'a başolarak ayarlarsanız, işaret ettikleri diziler satır kümesi boyutuna eşit boyutlara sahip olarak otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarAr. Kayıt setinizi güncelleştirilebilir hale getirmek için ODBC `SQLSetPos`API işlevini kullanmanız gerekir.

Daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md)makalelerini incegörün.

### <a name="example"></a>Örnek

[Bkz. RFX_Text_Bulk.](#rfx_text_bulk)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_date_bulk"></a><a name="rfx_date_bulk"></a>RFX_Date_Bulk

ODBC veri kaynağının bir sütunundaki birden çok TIMESTAMP_STRUCT veri `CRecordset`satırını türetilmiş bir nesnedeki karşılık gelen diziye aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Date_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   TIMESTAMP_STRUCT** prgTSVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Daha fazla bilgi için, kayıt [alanı değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*prgTSVals*<br/>
TIMESTAMP_STRUCT değerleri dizisiiçin bir işaretçi. Bu dizi, veri kaynağından kayıt kümesine aktarılacak verileri depolar. TIMESTAMP_STRUCT veri türü hakkında daha fazla bilgi için, *ODBC SDK Programcı ReferansEk*D'deki "C Veri Türleri" konusuna bakın.

*Prglengths*<br/>
Uzun tamsayılar dizisi için bir işaretçi. Bu *dizi, prgTSVals*tarafından işaret edilen dizide her değerin baytlarında uzunluk depolar. Karşılık gelen veri öğesi Null değeri içeriyorsa, SQL_NULL_DATA değerinin depolanacağını unutmayın. Daha fazla bilgi için, `SQLBindCol` *ODBC SDK Programcısı Nın Başvurusu'ndaki ODBC*API işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütununda SQL_DATE, SQL_TIME veya SQL_TIMESTAMP odbc türü olabilir. Kayıt kümesi, TIMESTAMP_STRUCT için tür işaretçisinin bir alan veri üyesini tanımlamalıdır.

*PrgTSVal'leri* ve *prgLengths'ı* NULL'a başolarak ayarlarsanız, işaret ettikleri diziler satır kümesi boyutuna eşit boyutlara sahip olarak otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarAr. Kayıt setinizi güncelleştirilebilir hale getirmek için ODBC `SQLSetPos`API işlevini kullanmanız gerekir.

Daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md)makalelerini incegörün.

### <a name="example"></a>Örnek

[Bkz. RFX_Text_Bulk.](#rfx_text_bulk)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_double_bulk"></a><a name="rfx_double_bulk"></a>RFX_Double_Bulk

Bir ODBC veri kaynağının sütunundan birden çok çift duyarlıklı, kayan nokta `CRecordset`veri satırını türetilmiş bir nesnedeki karşılık gelen diziye aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Double_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   double** prgDblVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Daha fazla bilgi için, kayıt [alanı değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*prgDblVals*<br/>
**Çift** değerler dizisiiçin bir işaretçi. Bu dizi, veri kaynağından kayıt kümesine aktarılacak verileri depolar.

*Prglengths*<br/>
Uzun tamsayılar dizisi için bir işaretçi. Bu dizi *prgDblVals*tarafından işaret edilen dizide her değerin baytuzunluğu depolayacak. Karşılık gelen veri öğesi Null değeri içeriyorsa, SQL_NULL_DATA değerinin depolanacağını unutmayın. Daha fazla bilgi için, `SQLBindCol` *ODBC SDK Programcısı Nın Başvurusu'ndaki ODBC*API işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütununda odbc türüne sahip olmalıdır SQL_DOUBLE. Kayıt kümesi, çift e-işaretçibir **double**alan veri üyesi tanımlamalıdır.

*PrgDblVals* ve *prgLengths'ı* NULL'a başolarak ayarlarsanız, işaret ettikleri diziler satır kümesi boyutuna eşit boyutlara sahip olarak otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarAr. Kayıt setinizi güncelleştirilebilir hale getirmek için ODBC `SQLSetPos`API işlevini kullanmanız gerekir.

Daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md)makalelerini incegörün.

### <a name="example"></a>Örnek

[Bkz. RFX_Text_Bulk.](#rfx_text_bulk)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_int_bulk"></a><a name="rfx_int_bulk"></a>RFX_Int_Bulk

Bir `CRecordset` nesnenin alan veri üyeleri ile ODBC türü veri kaynağındaki bir kaydın sütunları arasında tamsayı verilerini aktaran SQL_SMALLINT.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Bir `CFieldExchange` nesnenin belirtebileceği işlemler hakkında daha fazla bilgi için Kayıt [Alanı Değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, **int**türü değeri, belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

[Bkz. RFX_Text.](#rfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_long_bulk"></a><a name="rfx_long_bulk"></a>RFX_Long_Bulk

ODBC veri kaynağının bir sütunundan birden çok uzun tamsayı verisatırını türetilmiş bir `CRecordset`nesnedeki karşılık gelen diziye aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Long_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   long** prgLongVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Daha fazla bilgi için, kayıt [alanı değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*prgLongVals*<br/>
Uzun tamsayılar dizisi için bir işaretçi. Bu dizi, veri kaynağından kayıt kümesine aktarılacak verileri depolar.

*Prglengths*<br/>
Uzun tamsayılar dizisi için bir işaretçi. Bu dizi *prgLongVals*tarafından işaret edilen dizide her değerin baytuzunluğu depolayacak. Karşılık gelen veri öğesi Null değeri içeriyorsa, SQL_NULL_DATA değerinin depolanacağını unutmayın. Daha fazla bilgi için, `SQLBindCol` *ODBC SDK Programcısı Nın Başvurusu'ndaki ODBC*API işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütununda odbc türünde SQL_INTEGER olmalıdır. Kayıt kümesi, tür işaretçisinin bir alan veri üyesini **uzun**.

*PrgLongVals* ve *prgLengths'ı* NULL'a başharfle isterseniz, işaret ettikleri diziler satır kümesi boyutuna eşit boyutlara sahip olarak otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarAr. Kayıt setinizi güncelleştirilebilir hale getirmek için ODBC `SQLSetPos`API işlevini kullanmanız gerekir.

Daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md)makalelerini incegörün.

### <a name="example"></a>Örnek

[Bkz. RFX_Text_Bulk.](#rfx_text_bulk)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_single_bulk"></a><a name="rfx_single_bulk"></a>RFX_Single_Bulk

Bir ODBC veri kaynağının sütunundan birden çok kayan nokta veri `CRecordset`satırı satırını türetilmiş bir nesnedeki karşılık gelen diziye aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Single_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   float** prgFltVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Daha fazla bilgi için, kayıt [alanı değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*prgFltVals*<br/>
**Float** değerleri dizisi için bir işaretçi. Bu dizi, veri kaynağından kayıt kümesine aktarılacak verileri depolar.

*Prglengths*<br/>
Uzun tamsayılar dizisi için bir işaretçi. Bu dizi *prgFltVals*tarafından işaret edilen dizide her değerin baytuzunluğu depolayacak. Karşılık gelen veri öğesi Null değeri içeriyorsa, SQL_NULL_DATA değerinin depolanacağını unutmayın. Daha fazla bilgi için, `SQLBindCol` *ODBC SDK Programcısı Nın Başvurusu'ndaki ODBC*API işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütununda odbc SQL_REAL türü olmalıdır. Kayıt kümesi, float için tür işaretçibir alan veri üyesi **tanımlamalıdır.**

*PrgFltVals* ve *prgLengths'ı* NULL'a başharfle isterseniz, işaret ettikleri diziler satır kümesi boyutuna eşit boyutlara sahip olarak otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarAr. Kayıt setinizi güncelleştirilebilir hale getirmek için ODBC `SQLSetPos`API işlevini kullanmanız gerekir.

Daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md)makalelerini incegörün.

### <a name="example"></a>Örnek

[Bkz. RFX_Text_Bulk.](#rfx_text_bulk)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="rfx_text_bulk"></a><a name="rfx_text_bulk"></a>RFX_Text_Bulk

Birden çok karakter satırı satırını ODBC veri kaynağının sütunundan `CRecordset`türetilmiş bir nesnedeki karşılık gelen diziye aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void RFX_Text_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   LPSTR* prgStrVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir. Daha fazla bilgi için, kayıt [alanı değişimi makalesine bakın: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

*Szname*<br/>
Veri sütununun adı.

*prgStrVals*<br/>
LPSTR değerleri dizisi için bir işaretçi. Bu dizi, veri kaynağından kayıt kümesine aktarılacak verileri depolar. ODBC'nin geçerli sürümünde bu değerlerin Unicode olamayacağını unutmayın.

*Prglengths*<br/>
Uzun tamsayılar dizisi için bir işaretçi. Bu *dizi, prgStrVals*tarafından işaret edilen dizide her değerin baytlarında uzunluk depolanır. Bu uzunluk null sonlandırma karakterini dışlar. Karşılık gelen veri öğesi Null değeri içeriyorsa, SQL_NULL_DATA değerinin depolanacağını unutmayın. Daha fazla bilgi için, `SQLBindCol` *ODBC SDK Programcısı Nın Başvurusu'ndaki ODBC*API işlevine bakın.

*nMaxLength*<br/>
*PrgStrVals*tarafından işaret edilen dizide depolanan değerlerin izin verilen maksimum uzunluğu , null sonlandırma karakteri de dahil olmak üzere. Verilerin kesildirilmediğinden emin olmak için, beklediğiniz en büyük veri öğesini barındıracak kadar büyük bir değer geçirin.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütununda SQL_LONGVARCHAR, SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL veya SQL_NUMERIC odbc türü olabilir. Kayıt kümesi, LPSTR türünde bir alan veri üyesi tanımlamalıdır.

*PrgStrVals* ve *prgLengths'ı* NULL'a başolarak ayarlarsanız, işaret ettikleri diziler satır kümesi boyutuna eşit boyutlara sahip olarak otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarAr. Kayıt setinizi güncelleştirilebilir hale getirmek için ODBC `SQLSetPos`API işlevini kullanmanız gerekir.

Daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md)makalelerini incegörün.

### <a name="example"></a>Örnek

Geçersiz kılmaya aramaları el `DoBulkFieldExchange` ile yazmanız gerekir. Bu örnek, veri `RFX_Text_Bulk`aktarım için bir `RFX_Long_Bulk`çağrının yanı sıra , Bu aramalar CFieldExchange bir çağrı [öncesinde::SetFieldType](cfieldexchange-class.md#setfieldtype). Parametreler için Toplu RFX işlevleri yerine RFX işlevlerini aramanız gerektiğini unutmayın.

```cpp
void CMultiCustomer::DoBulkFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   RFX_Long_Bulk(pFX, _T("[CustomerID]"), &m_pCustomerID, &m_pcCustomerID);
   RFX_Text_Bulk(pFX, _T("[ContactFirstName]"), &m_pContactFirstName, &m_pcContactFirstName, 50);
   RFX_Text_Bulk(pFX, _T("[PostalCode]"), &m_pPostalCode, &m_pcPostalCode, 50);
   RFX_Text_Bulk(pFX, _T("[L_Name]"), &m_pL_Name, &m_pcL_Name, 50);
   RFX_Long_Bulk(pFX, _T("[BillingID]"), &m_pBillingID, &m_pcBillingID);

   pFX->SetFieldType(CFieldExchange::inputParam);
   RFX_Text(pFX, _T("Param"), m_strParam);
}
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="dfx_binary"></a><a name="dfx_binary"></a>DFX_Binary

[CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında bayt dizileri aktarıyor.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI DFX_Binary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CByteArray& value,
   int nPreAllocSize = AFX_DAO_BINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir.

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım [için, CByteArray](cbytearray-class.md)türünün değeri belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

*nPreAllocSize*<br/>
Çerçeve, bu bellek miktarını önceden ayırır. Verileriniz daha büyükse, çerçeve gerektiğinde daha fazla alan ayırır. Daha iyi performans için, bu boyutu gerçekleşmeleri engelleyecek kadar büyük bir değere ayarlayın. Varsayılan boyut AFXDAO tanımlanır. AFX_DAO_BINARY_DEFAULT_SIZE olarak H dosyası.

*dwBindSeçenekleri*<br/>
Değişen kayıt kümesi alanlarını algılamak için MFC'nin çift arabelleğe alma mekanizmasından yararlanmanızı sağlayan bir seçenek. Varsayılan, AFX_DAO_DISABLE_FIELD_CACHE, çift arabelleğe alma kullanmaz ve [SetFieldDirty](cdaorecordset-class.md#setfielddirty) ve [SetFieldNull](cdaorecordset-class.md#setfieldnull) kendiniz aramanız gerekir. Diğer olası değer, AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır ve alanları kirli veya Null işaretlemek için ekstra çalışma yapmanız gerekmez. Performans ve bellek nedenleriyle, ikili verileriniz nispeten küçük olmadıkça bu değerden kaçının.

> [!NOTE]
> [CDaoRecordset:m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)ayarlayarak varsayılan olarak tüm alanlar için verilerin çift arabelleğe alılıp eksentiflemeyeceğini denetleyebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO'daki tip DAO_BYTES ile kayıt kümesindeki [CByteArray](cbytearray-class.md) türü arasında eşlenir.

### <a name="example"></a>Örnek

[Bkz. DFX_Text.](#dfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="dfx_bool"></a><a name="dfx_bool"></a>DFX_Bool

Boolean verilerini bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI DFX_Bool(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BOOL& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir.

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, BOOL türünün değeri belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

*dwBindSeçenekleri*<br/>
Değişen kayıt kümesi alanlarını algılamak için MFC'nin çift arabelleğe alma mekanizmasından yararlanmanızı sağlayan bir seçenek. Varsayılan, AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Diğer olası değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanda hiçbir denetleme yapmaz. Kendin `SetFieldDirty` ve `SetFieldNull` kendin aramalısın.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)ayarlayarak verilerin varsayılan olarak çift arabelleğe alılıp eksentiflemeyeceğini denetleyebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO'daki tip DAO_BOOL ile kayıt kümesindeki BOOL türü arasında eşlenir.

### <a name="example"></a>Örnek

[Bkz. DFX_Text.](#dfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="dfx_byte"></a><a name="dfx_byte"></a>DFX_Byte

[CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında tek bayt aktarıyor.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI DFX_Byte(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BYTE& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir.

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, BYTE türündeki değer, belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

*dwBindSeçenekleri*<br/>
Değişen kayıt kümesi alanlarını algılamak için MFC'nin çift arabelleğe alma mekanizmasından yararlanmanızı sağlayan bir seçenek. Varsayılan, AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Diğer olası değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanda hiçbir denetleme yapmaz. Kendin `SetFieldDirty` ve `SetFieldNull` kendin aramalısın.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)ayarlayarak verilerin varsayılan olarak çift arabelleğe alılıp eksentiflemeyeceğini denetleyebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO'daki tip DAO_BYTES ile kayıt kümesinde BYTE türü arasında eşlenir.

### <a name="example"></a>Örnek

[Bkz. DFX_Text.](#dfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="dfx_currency"></a><a name="dfx_currency"></a>DFX_Currency

[CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki kaydın sütunları arasında para birimi verilerini aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI DFX_Currency(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleCurrency& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir.

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için bu değer, [COleCurrency](colecurrency-class.md)türünde belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

*dwBindSeçenekleri*<br/>
Değişen kayıt kümesi alanlarını algılamak için MFC'nin çift arabelleğe alma mekanizmasından yararlanmanızı sağlayan bir seçenek. Varsayılan, AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Diğer olası değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanda hiçbir denetleme yapmaz. Kendin `SetFieldDirty` ve `SetFieldNull` kendin aramalısın.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)ayarlayarak verilerin varsayılan olarak çift arabelleğe alılıp eksentiflemeyeceğini denetleyebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO'daki tip DAO_CURRENCY ile kayıt kümesindeki [COleCurrency](colecurrency-class.md) türü arasında eşlenir.

### <a name="example"></a>Örnek

[Bkz. DFX_Text.](#dfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="dfx_datetime"></a><a name="dfx_datetime"></a>DFX_DateTime

[CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki kaydın sütunları arasındaki saat ve tarih verilerini aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI DFX_DateTime(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleDateTime& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir.

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. İşlev bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine bir başvuru alır. Kayıt kümesinden veri kaynağına aktarım için bu değer belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

*dwBindSeçenekleri*<br/>
Değişen kayıt kümesi alanlarını algılamak için MFC'nin çift arabelleğe alma mekanizmasından yararlanmanızı sağlayan bir seçenek. Varsayılan, AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Diğer olası değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanda hiçbir denetleme yapmaz. Kendin `SetFieldDirty` ve `SetFieldNull` kendin aramalısın.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)ayarlayarak verilerin varsayılan olarak çift arabelleğe alılıp eksentiflemeyeceğini denetleyebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO'daki tip DAO_DATE ile kayıt kümesindeki [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) türü arasında eşlenir.

> [!NOTE]
> `COleDateTime`DAO sınıflarında bu amaçla [CTime](../../atl-mfc-shared/reference/ctime-class.md) ve TIMESTAMP_STRUCT'nin yerini alır. `CTime`ve TIMESTAMP_STRUCT hala ODBC tabanlı veri erişim sınıfları için kullanılır.

### <a name="example"></a>Örnek

[Bkz. DFX_Text.](#dfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="dfx_double"></a><a name="dfx_double"></a>DFX_Double

[CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında **çift float** veri aktarır.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI DFX_Double(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   double& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir.

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, tip **double**değeri, belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

*dwBindSeçenekleri*<br/>
Değişen kayıt kümesi alanlarını algılamak için MFC'nin çift arabelleğe alma mekanizmasından yararlanmanızı sağlayan bir seçenek. Varsayılan, AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Diğer olası değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanda hiçbir denetleme yapmaz. Kendin `SetFieldDirty` ve `SetFieldNull` kendin aramalısın.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)ayarlayarak verilerin varsayılan olarak çift arabelleğe alılıp eksentiflemeyeceğini denetleyebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO'daki tip DAO_R8 ile kayıt kümesindeki **çift float** türü arasında eşlenir.

### <a name="example"></a>Örnek

[Bkz. DFX_Text.](#dfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="dfx_long"></a><a name="dfx_long"></a>DFX_Long

[CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında uzun tamsayı verileri aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI DFX_Long(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   long& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir.

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, **uzun**tür değeri belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

*dwBindSeçenekleri*<br/>
Değişen kayıt kümesi alanlarını algılamak için MFC'nin çift arabelleğe alma mekanizmasından yararlanmanızı sağlayan bir seçenek. Varsayılan, AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Diğer olası değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanda hiçbir denetleme yapmaz. Kendin `SetFieldDirty` ve `SetFieldNull` kendin aramalısın.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)ayarlayarak verilerin varsayılan olarak çift arabelleğe alılıp eksentiflemeyeceğini denetleyebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO'daki tip DAO_I4 ile kayıt kümesindeki **uzun** yazı arasında eşlenir.

### <a name="example"></a>Örnek

[Bkz. DFX_Text.](#dfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="dfx_longbinary"></a><a name="dfx_longbinary"></a>DFX_LongBinary

**Önemli** Bu işlev yerine [DFX_Binary](#dfx_binary) kullanmanız önerilir.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI DFX_LongBinary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CLongBinary& value,
   DWORD dwPreAllocSize = AFX_DAO_LONGBINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir.

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım [için, CLongBinary](clongbinary-class.md)türünün değeri belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

*dwPreAllocSize*<br/>
Çerçeve, bu bellek miktarını önceden ayırır. Verileriniz daha büyükse, çerçeve gerektiğinde daha fazla alan ayırır. Daha iyi performans için, bu boyutu gerçekleşmeleri engelleyecek kadar büyük bir değere ayarlayın.

*dwBindSeçenekleri*<br/>
Değişen kayıt kümesi alanlarını algılamak için MFC'nin çift arabelleğe alma mekanizmasından yararlanmanızı sağlayan bir seçenek. Varsayılan, AFX_DISABLE_FIELD_CACHE, çift arabelleğe alma kullanmaz. Diğer olası değer AFX_DAO_ENABLE_FIELD_CACHE. Çift arabelleğe alma kullanır ve alanları kirli veya Null işaretlemek için ekstra iş yapmanız gerekmez. Performans ve bellek nedenleriyle, ikili verileriniz nispeten küçük olmadıkça bu değerden kaçının.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)ayarlayarak verilerin varsayılan olarak çift arabelleğe alılıp eksentiflemeyeceğini denetleyebilirsiniz.

### <a name="remarks"></a>Açıklamalar

`DFX_LongBinary`MFC ODBC sınıfları ile uyumluluk için sağlanır. İşlev, `DFX_LongBinary` [cdaoRecordset](cdaorecordset-class.md) nesnesinin alan `CLongBinary` veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasındaki sınıfı kullanarak ikili büyük nesne (BLOB) verilerini aktarır. Veriler, DAO'daki tip DAO_BYTES ile kayıt kümesindeki [CLongBinary](clongbinary-class.md) türü arasında eşlenir.

### <a name="example"></a>Örnek

[Bkz. DFX_Text.](#dfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="dfx_short"></a><a name="dfx_short"></a>DFX_Short

[CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında kısa tamsayı verileri aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI DFX_Short(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   short& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir.

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, **belirtilen**veri üyesinden kısa tür değeri alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

*dwBindSeçenekleri*<br/>
Değişen kayıt kümesi alanlarını algılamak için MFC'nin çift arabelleğe alma mekanizmasından yararlanmanızı sağlayan bir seçenek. Varsayılan, AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Diğer olası değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanda hiçbir denetleme yapmaz. Kendin `SetFieldDirty` ve `SetFieldNull` kendin aramalısın.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)ayarlayarak verilerin varsayılan olarak çift arabelleğe alılıp eksentiflemeyeceğini denetleyebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO'daki tür DAO_I2 ile kayıt kümesinde **kısa** tip arasında eşlenir.

> [!NOTE]
> `DFX_Short`ODBC tabanlı sınıflar için [RFX_Int](#rfx_int) eşdeğerdir.

### <a name="example"></a>Örnek

[Bkz. DFX_Text.](#dfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="dfx_single"></a><a name="dfx_single"></a>DFX_Single

Bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında kayan nokta verilerini aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI DFX_Single(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   float& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir.

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, tür **float**değeri, belirtilen veri üyesialınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

*dwBindSeçenekleri*<br/>
Değişen kayıt kümesi alanlarını algılamak için MFC'nin çift arabelleğe alma mekanizmasından yararlanmanızı sağlayan bir seçenek. Varsayılan, AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Diğer olası değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanda hiçbir denetleme yapmaz. Kendin `SetFieldDirty` ve `SetFieldNull` kendin aramalısın.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)ayarlayarak verilerin varsayılan olarak çift arabelleğe alılıp eksentiflemeyeceğini denetleyebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO'daki tip DAO_R4 ile kayıt kümesindeki tür **float** arasında eşlenir.

### <a name="example"></a>Örnek

[Bkz. DFX_Text.](#dfx_text)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="dfx_text"></a><a name="dfx_text"></a>DFX_Text

Verileri `CString` bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında aktarın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI DFX_Text(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CString& value,
   int nPreAllocSize = AFX_DAO_TEXT_DEFAULT_SIZE,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CDaoFieldExchange](cdaofieldexchange-class.md)sınıfının bir nesnesine işaretçi. Bu nesne, işlevin her çağrısı için bağlamı tanımlamak için bilgi içerir.

*Szname*<br/>
Veri sütununun adı.

*Değer*<br/>
Belirtilen veri üyesinde depolanan değer - aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, [CString](../../atl-mfc-shared/reference/cstringt-class.md)türünün değeri belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için değer belirtilen veri üyesinde depolanır.

*nPreAllocSize*<br/>
Çerçeve, bu bellek miktarını önceden ayırır. Verileriniz daha büyükse, çerçeve gerektiğinde daha fazla alan ayırır. Daha iyi performans için, bu boyutu gerçekleşmeleri engelleyecek kadar büyük bir değere ayarlayın.

*dwBindSeçenekleri*<br/>
Değişen kayıt kümesi alanlarını algılamak için MFC'nin çift arabelleğe alma mekanizmasından yararlanmanızı sağlayan bir seçenek. Varsayılan, AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Diğer olası değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanda hiçbir denetleme yapmaz. [SetFieldDirty](cdaorecordset-class.md#setfielddirty) ve [SetFieldNull'u](cdaorecordset-class.md#setfieldnull) kendin aramalısın.

> [!NOTE]
> [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)ayarlayarak verilerin varsayılan olarak çift arabelleğe alılıp eksentiflemeyeceğini denetleyebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO'daki DAO_CHAR türü (veya sembol _UNICODE tanımlanmışsa, DAO_WCHAR) ve kayıt kümesindeki [CString](../../atl-mfc-shared/reference/cstringt-class.md) türü arasında eşlenir.  n

### <a name="example"></a>Örnek

Bu örnek, '' ye `DFX_Text`yapılan birkaç çağrıyı gösterir. CDaoFieldExchange için iki arama da [dikkat::SetFieldType](cdaofieldexchange-class.md#setfieldtype). İlk aramayı `SetFieldType` ve **DFX** çağrısını yazmanız gerekir. İkinci arama ve ilişkili **DFX** çağrıları normalde sınıfı oluşturan kod sihirbazı tarafından yazılır.

```cpp
void CCustSet::DoFieldExchange(CDaoFieldExchange* pFX)
{
   pFX->SetFieldType(CDaoFieldExchange::param);
   DFX_Text(pFX, _T("Param"), m_strParam);
   pFX->SetFieldType(CDaoFieldExchange::outputColumn);
   DFX_Short(pFX, _T("EmployeeID"), m_EmployeeID);
   DFX_Text(pFX, _T("LastName"), m_LastName);
   DFX_Short(pFX, _T("Age"), m_Age);
   DFX_DateTime(pFX, _T("hire_date"), m_hire_date);
   DFX_DateTime(pFX, _T("termination_date"), m_termination_date);

   CDaoRecordset::DoFieldExchange(pFX);
}
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](mfc-macros-and-globals.md)<br/>
[CRecordset::DoFieldExchange](crecordset-class.md#dofieldexchange)<br/>
[CRecordset::DoBulkFieldExchange](crecordset-class.md#dobulkfieldexchange)<br/>
[CDaoRecordset::DoFieldExchange](cdaorecordset-class.md#dofieldexchange)
