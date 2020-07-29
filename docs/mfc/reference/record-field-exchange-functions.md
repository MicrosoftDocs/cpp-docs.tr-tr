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
ms.openlocfilehash: f4f1b12795252b91a2c14877822e221ca86ab39e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214041"
---
# <a name="record-field-exchange-functions"></a>Kayıt Alanı Değişim İşlevleri

Bu konuda, verilerin bir kayıt kümesi nesnesi ve veri kaynağı arasında veri aktarımını otomatikleştirmek ve veriler üzerinde başka işlemler gerçekleştirmek için kullanılan kayıt alanı değişimi (RFX, toplu RFX ve DFX) işlevleri listelenmiştir.

ODBC tabanlı sınıfları kullanıyorsanız ve toplu satır getirmeyi uyguladıysanız, `DoBulkFieldExchange` `CRecordset` bir veri kaynağı sütununa karşılık gelen her bir veri ÜYESININ toplu RFX işlevlerini çağırarak öğesinin üye işlevini el ile geçersiz kılmanız gerekir.

ODBC tabanlı sınıflarda toplu satır getirmeyi gerçekleştirdiyseniz veya DAO tabanlı sınıfları (kullanım dışı) kullanıyorsanız, ClassWizard, `DoFieldExchange` `CRecordset` `CDaoRecordset` kayıt kümenizde her bir alan VERI üyesine yönelik RFX işlevlerini (ODBC sınıfları IÇIN) veya DFX işlevlerini (DAO sınıfları için) çağırarak veya ' nin üye işlevini geçersiz kılar.

Kayıt alanı değişimi işlevleri, Framework veya her çağırdığında veri aktarır `DoFieldExchange` `DoBulkFieldExchange` . Her işlev belirli bir veri türünü aktarır.

Bu işlevlerin nasıl kullanıldığı hakkında daha fazla bilgi için, bkz. [kayıt alanı değişimi: RFX nasıl çalışır (ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md). Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Dinamik olarak bağladığınız veri sütunları için, bir RFX veya DFX işlevlerini, makaleler [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)bölümünde açıklandığı gibi de çağırabilirsiniz. Ayrıca, teknik [not43](../../mfc/tn043-rfx-routines.md) (ODBC için) ve teknik [NOT53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (DAO için) bölümünde AÇıKLANDıĞı gibi kendı özel RFX veya DFX yordamlarını yazabilirsiniz.

Ve işlevlerinde göründükleri gibi RFX ve toplu RFX işlevlerinin bir örneği için `DoFieldExchange` `DoBulkFieldExchange` bkz. [RFX_Text](#rfx_text) ve [RFX_Text_Bulk] #rfx_text_bulk). DFX işlevleri RFX işlevlerine çok benzer.

### <a name="rfx-functions-odbc"></a>RFX Işlevleri (ODBC)

|||
|-|-|
|[RFX_Binary](#rfx_binary)|[CByteArray](cbytearray-class.md)türünde bayt dizilerini aktarır.|
|[RFX_Bool](#rfx_bool)|Boole verilerini aktarır.|
|[RFX_Byte](#rfx_byte)|Tek bir veri baytı aktarır.|
|[RFX_Date](#rfx_date)|[CTime](../../atl-mfc-shared/reference/ctime-class.md) veya TIMESTAMP_STRUCT kullanarak saat ve Tarih verilerini aktarır.|
|[RFX_Double](#rfx_double)|Çift duyarlıklı kayan verileri aktarır.|
|[RFX_Int](#rfx_int)|Tamsayı verilerini aktarır.|
|[RFX_Long](#rfx_long)|Uzun tamsayı verilerini aktarır.|
|[RFX_LongBinary](#rfx_longbinary)|İkili büyük nesne (BLOB) verilerini [CLongBinary](clongbinary-class.md) sınıfının bir nesnesiyle aktarır.|
|[RFX_Single](#rfx_single)|Kayan verileri aktarır.|
|[RFX_Text](#rfx_text)|Dize verilerini aktarır.|

### <a name="bulk-rfx-functions-odbc"></a>Toplu RFX Işlevleri (ODBC)

|||
|-|-|
|[RFX_Binary_Bulk](#rfx_binary_bulk)|Bayt veri dizilerini aktarır.|
|[RFX_Bool_Bulk](#rfx_bool_bulk)|Boole verileri dizilerini aktarır.|
|[RFX_Byte_Bulk](#rfx_byte_bulk)|Tek baytlık dizileri aktarır.|
|[RFX_Date_Bulk](#rfx_date_bulk)|TIMESTAMP_STRUCT türündeki veri dizilerini aktarır.|
|[RFX_Double_Bulk](#rfx_double_bulk)|Çift duyarlıklı, kayan nokta verilerinin dizilerini aktarır.|
|[RFX_Int_Bulk](#rfx_int_bulk)|Tamsayı veri dizilerini aktarır.|
|[RFX_Long_Bulk](#rfx_long_bulk)|Uzun tamsayı verilerinin dizilerini aktarır.|
|[RFX_Single_Bulk](#rfx_single_bulk)|Kayan nokta verilerinin dizilerini aktarır.|
|[RFX_Text_Bulk](#rfx_text_bulk)|LPSTR türünde veri dizilerini aktarır.|

### <a name="dfx-functions-dao"></a>DFX Işlevleri (DAO)

|||
|-|-|
|[DFX_Binary](#dfx_binary)|[CByteArray](cbytearray-class.md)türünde bayt dizilerini aktarır.|
|[DFX_Bool](#dfx_bool)|Boole verilerini aktarır.|
|[DFX_Byte](#dfx_byte)|Tek bir veri baytı aktarır.|
|[DFX_Currency](#dfx_currency)|[Copacurrency](colecurrency-class.md)türünde para birimi verilerini aktarır.|
|[DFX_DateTime](#dfx_datetime)|[Copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md)türünde zaman ve Tarih verisini aktarır.|
|[DFX_Double](#dfx_double)|Çift duyarlıklı kayan verileri aktarır.|
|[DFX_Long](#dfx_long)|Uzun tamsayı verilerini aktarır.|
|[DFX_LongBinary](#dfx_longbinary)|İkili büyük nesne (BLOB) verilerini sınıfının bir nesnesiyle aktarır `CLongBinary` . DAO için, bunun yerine [DFX_Binary](#dfx_binary) kullanmanız önerilir.|
|[DFX_Short](#dfx_short)|Kısa tamsayı verilerini aktarır.|
|[DFX_Single](#dfx_single)|Kayan verileri aktarır.|
|[DFX_Text](#dfx_text)|Dize verilerini aktarır.|

=============================================

## <a name="rfx_binary"></a><a name="rfx_binary"></a>RFX_Binary

Bir nesnenin alan veri üyeleri arasında bayt dizilerini `CRecordset` ve ODBC türü SQL_BINARY, SQL_VARBINARY veya SQL_LONGVARBINARY veri kaynağındaki bir kaydın sütunlarını aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Binary(
   CFieldExchange* pFX,
   const char* szName,
   CByteArray& value,
   int nMaxLength = 255);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Bir nesnenin belirtebileceğiniz işlemler hakkında daha fazla bilgi için `CFieldExchange` bkz. [kayıt alanı DEĞIŞIMI: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, [CByteArray](cbytearray-class.md)türündeki değer belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

*nMaxLength*<br/>
Aktarılmakta olan dize veya dizi için izin verilen en büyük uzunluk. *NMaxLength* varsayılan değeri 255 ' dir. Yasal değerler 1 ' dir INT_MAX. Framework, veriler için bu alan miktarını ayırır. En iyi performansı elde etmek için, tahmin ettiğiniz en büyük veri öğesine yetecek büyüklükte bir değer geçirin.

### <a name="remarks"></a>Açıklamalar

Bu türlerin veri kaynağındaki veriler, kayıt kümesindeki tür ve türünden eşleştirilir `CByteArray` .

### <a name="example"></a>Örnek

Bkz. [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_bool"></a><a name="rfx_bool"></a>RFX_Bool

Bir nesnenin alan veri üyeleri arasında Boole verileri `CRecordset` ve ODBC türü SQL_BIT veri kaynağındaki bir kaydın sütunlarını aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Bool(
   CFieldExchange* pFX,
   const char* szName,
   BOOL& value);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Bir nesnenin belirtebileceğiniz işlemler hakkında daha fazla bilgi için `CFieldExchange` bkz. [kayıt alanı DEĞIŞIMI: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, BOOL türündeki değer belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

Bkz. [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_byte"></a><a name="rfx_byte"></a>RFX_Byte

Bir nesnenin alan veri üyeleri arasında tek `CRecordset` bir bayt ve ODBC türü SQL_TINYINT veri kaynağındaki bir kaydın sütunlarını aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Byte(
   CFieldExchange* pFX,
   const char* szName,
   BYTE& value);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Bir nesnenin belirtebileceğiniz işlemler hakkında daha fazla bilgi için `CFieldExchange` bkz. [kayıt alanı DEĞIŞIMI: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, BYTE türündeki değer belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

Bkz. [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_date"></a><a name="rfx_date"></a>RFX_Date

`CTime`Bir nesnenin alan veri üyeleri arasında verileri `CRecordset` ve ODBC türü SQL_DATE, SQL_TIME veya SQL_TIMESTAMP veri kaynağındaki bir kaydın sütunlarını aktarır veya TIMESTAMP_STRUCT.

### <a name="syntax"></a>Söz dizimi

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

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Bir nesnenin belirtebileceğiniz işlemler hakkında daha fazla bilgi için `CFieldExchange` bkz. [kayıt alanı DEĞIŞIMI: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer; aktarılacak değer. İşlevin çeşitli sürümleri değer için farklı veri türleri alır:

İşlevin ilk sürümü bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru alır. Kayıt kümesinden veri kaynağına aktarım için, bu değer belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

İşlevin ikinci sürümü bir yapıya başvuru alır `TIMESTAMP_STRUCT` . Bu yapıyı çağrıdan önce kendiniz ayarlamanız gerekir. Bu sürümde hiçbir iletişim kutusu veri değişimi (DDX) desteği veya kod Sihirbazı desteği yok. İşlevin üçüncü sürümü, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine bir başvuru almak dışında ilk sürüme benzer şekilde çalışır.

### <a name="remarks"></a>Açıklamalar

`CTime`İşlevin sürümü, bazı ara işleme yükünü uygular ve biraz sınırlı bir aralığa sahiptir. Bu faktörlerden birini çok sınırlandırdıysanız, işlevin ikinci sürümünü kullanın. Ancak kod eksikliği ve DDX desteğinin yanı sıra yapıyı kendiniz ayarlamanıza gerek yoktur.

### <a name="example"></a>Örnek

Bkz. [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_double"></a><a name="rfx_double"></a>RFX_Double

Bir nesnenin alan veri üyeleri arasında **çift kayan** VERILERI `CRecordset` ve ODBC türü SQL_DOUBLE veri kaynağındaki bir kaydın sütunlarını aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Double(
   CFieldExchange* pFX,
   const char* szName,
   double& value);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Bir nesnenin belirtebileceğiniz işlemler hakkında daha fazla bilgi için `CFieldExchange` bkz. [kayıt alanı DEĞIŞIMI: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, türünün değeri, **`double`** belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

Bkz. [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_int"></a><a name="rfx_int"></a>RFX_Int

Bir nesnenin alan veri üyeleri arasında tamsayı verilerini `CRecordset` ve ODBC türü SQL_SMALLINT veri kaynağındaki bir kaydın sütunlarını aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Bir nesnenin belirtebileceğiniz işlemler hakkında daha fazla bilgi için `CFieldExchange` bkz. [kayıt alanı DEĞIŞIMI: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, türünün değeri, **`int`** belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

Bkz. [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_long"></a><a name="rfx_long"></a>RFX_Long

Bir nesnenin alan veri üyeleri arasında uzun tamsayı verilerini `CRecordset` ve ODBC türü SQL_INTEGER veri kaynağındaki bir kaydın sütunlarını aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Long(
   CFieldExchange* pFX,
   const char* szName,
   LONG&
value );
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Bir nesnenin belirtebileceğiniz işlemler hakkında daha fazla bilgi için `CFieldExchange` bkz. [kayıt alanı DEĞIŞIMI: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, türünün değeri, **`long`** belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

Bkz. [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_longbinary"></a><a name="rfx_longbinary"></a>RFX_LongBinary

Bir nesnenin alan veri üyeleri [CLongBinary](clongbinary-class.md) `CRecordset` ile bir KAYDıN sütunları ve ODBC türü SQL_LONGVARBINARY ya da sql_longvarchar veri kaynağındaki bir kaydın sütunlarını kullanarak, ikili büyük nesne (blob) verilerini aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_LongBinary(
   CFieldExchange* pFX,
   const char* szName,
   CLongBinary& value);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Bir nesnenin belirtebileceğiniz işlemler hakkında daha fazla bilgi için `CFieldExchange` bkz. [kayıt alanı DEĞIŞIMI: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, türünün değeri, `CLongBinary` belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

Bkz. [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_single"></a><a name="rfx_single"></a>RFX_Single

Kayan nokta verilerini nesnenin alan veri üyeleri arasında `CRecordset` ve ODBC türü SQL_REAL veri kaynağındaki bir kaydın sütunlarını aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Single(
   CFieldExchange* pFX,
   const char* szName,
   float& value);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Bir nesnenin belirtebileceğiniz işlemler hakkında daha fazla bilgi için `CFieldExchange` bkz. [kayıt alanı DEĞIŞIMI: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, türünün değeri, **`float`** belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

Bkz. [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_text"></a><a name="rfx_text"></a>RFX_Text

`CString` `CRecordset` ODBC türü SQL_LONGVARCHAR, SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL veya SQL_NUMERIC veri kaynağındaki bir nesnenin alan veri üyeleri ve bir kayıt sütunlarının arasına veri aktarır.

### <a name="syntax"></a>Söz dizimi

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

*Türk*<br/>
Sınıfının nesnesine yönelik bir işaretçi `CFieldExchange` . Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Bir nesnenin belirtebileceğiniz işlemler hakkında daha fazla bilgi için `CFieldExchange` bkz. [kayıt alanı DEĞIŞIMI: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, türünün değeri, `CString` belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

*nMaxLength*<br/>
Aktarılmakta olan dize veya dizi için izin verilen en büyük uzunluk. *NMaxLength* varsayılan değeri 255 ' dir. Yasal değerler 1 ' dir INT_MAX). Framework, veriler için bu alan miktarını ayırır. En iyi performansı elde etmek için, tahmin ettiğiniz en büyük veri öğesine yetecek büyüklükte bir değer geçirin.

*nColumnType*<br/>
Genellikle parametreler için kullanılır. Parametrenin veri türünü gösteren bir tamsayı. Tür, **SQL_XXX**formun ODBC veri türüdür.

*nScale*<br/>
ODBC türü SQL_DECIMAL veya SQL_NUMERIC değerlerinin ölçeğini belirler. *Nscale* yalnızca parametre değerleri ayarlanırken yararlıdır. Daha fazla bilgi için *ODBC SDK Programlayıcısının başvurusunun*ek D konusunun "duyarlık, ölçek, uzunluk ve görüntüleme boyutu" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Bu türlerin tümünün veri kaynağındaki veriler, kayıt kümesinden ve kaynağından eşleştirilir `CString` .

### <a name="example"></a>Örnek

Bu örnekte, için birkaç çağrı gösterilmektedir `RFX_Text` . Ayrıca, için iki çağrıya dikkat edin `CFieldExchange::SetFieldType` . Parametreler için, çağrısını `SetFieldType` ve RFX çağrısını yazmanız gerekir. Çıkış sütunu çağrısı ve onunla ilişkili RFX çağrıları normalde bir kod Sihirbazı tarafından yazılır.

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

**Üstbilgi:** Afxdb. h

## <a name="rfx_binary_bulk"></a><a name="rfx_binary_bulk"></a>RFX_Binary_Bulk

Bir ODBC veri kaynağından alınan bir sütundan birden çok satır baytlık verileri, türetilmiş bir nesnede karşılık gelen bir diziye aktarır `CRecordset` .

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Binary_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Daha fazla bilgi için bkz. [kayıt alanı değişimi: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*Prgbyteışları*<br/>
BAYT değerleri dizisine yönelik bir işaretçi. Bu dizi verileri veri kaynağından kayıt kümesine aktarılacak şekilde depolayacaktır.

*Prguzunluklar*<br/>
Uzun tamsayıların dizisine yönelik bir işaretçi. Bu dizi, değeri *Prgbyteler*tarafından işaret edilen dizideki her bir değerin bayt cinsinden depolar. Karşılık gelen veri öğesi null bir değer içeriyorsa SQL_NULL_DATA değerin depolanacağı değeri unutmayın. Daha fazla ayrıntı için bkz `SQLBindCol` . *ODBC SDK Programlayıcısının başvurusu*içindeki ODBC API işlevi.

*nMaxLength*<br/>
Dizide bulunan, *Prgbyteışları*tarafından işaret edilen değerlerin izin verilen en fazla uzunluğu. Verilerin kesilmemesini sağlamak için, istediğiniz en büyük veri öğesini karşılayacak büyüklükte bir değer geçirin.

### <a name="remarks"></a>Açıklamalar

Veri kaynağı sütununda SQL_BINARY, SQL_VARBINARY veya SQL_LONGVARBINARY ODBC türü bulunabilir. Kayıt kümesi, BYTE türü işaretçi türünde bir alan veri üyesi tanımlamalıdır.

*Prgbyteıse* ve *PRGUZUNLUKLERI* null değerine başladıysanız, işaret ettikleri diziler, satır kümesi boyutuna eşit boyutlarda otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi, verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarır. Kayıt kümenizin güncelleştirilebilir olması için ODBC API işlevini kullanmanız gerekir `SQLSetPos` .

Daha fazla bilgi için bkz. Makale [kayıt kümesi: kayıtları toplu (ODBC) halinde getirme](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz. [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_bool_bulk"></a><a name="rfx_bool_bulk"></a>RFX_Bool_Bulk

ODBC veri kaynağı sütunundaki birden çok satırı, türetilmiş bir nesnede karşılık gelen bir diziye aktarır `CRecordset` .

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Bool_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BOOL** prgBoolVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Daha fazla bilgi için bkz. [kayıt alanı değişimi: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*Prgbooltıcı*<br/>
BOOL değerleri dizisine yönelik bir işaretçi. Bu dizi verileri veri kaynağından kayıt kümesine aktarılacak şekilde depolayacaktır.

*Prguzunluklar*<br/>
Uzun tamsayıların dizisine yönelik bir işaretçi. Bu dizi, değeri *Prgbooltıcı*tarafından işaret edilen dizideki her bir değerin bayt cinsinden depolar. Karşılık gelen veri öğesi null bir değer içeriyorsa SQL_NULL_DATA değerin depolanacağı değeri unutmayın. Daha fazla ayrıntı için bkz `SQLBindCol` . *ODBC SDK Programlayıcısının başvurusu*içindeki ODBC API işlevi.

### <a name="remarks"></a>Açıklamalar

Veri kaynağı sütununda bir ODBC türü SQL_BIT olmalıdır. Kayıt kümesi, BOOL için işaretçi türünde bir alan veri üyesi tanımlamalıdır.

*Prgbooltıcı* ve *PRGUZUNLUKLERI* null olarak çalıştırırsanız, işaret ettikleri diziler, satır kümesi boyutuna eşit boyutlarda otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi, verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarır. Kayıt kümenizin güncelleştirilebilir olması için ODBC API işlevini kullanmanız gerekir `SQLSetPos` .

Daha fazla bilgi için bkz. Makale [kayıt kümesi: kayıtları toplu (ODBC) halinde getirme](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz. [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_byte_bulk"></a><a name="rfx_byte_bulk"></a>RFX_Byte_Bulk

ODBC veri kaynağındaki bir sütundan birden çok satırı, türetilmiş bir nesnede karşılık gelen bir diziye aktarır `CRecordset` .

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Byte_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Daha fazla bilgi için bkz. [kayıt alanı değişimi: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*Prgbyteışları*<br/>
BAYT değerleri dizisine yönelik bir işaretçi. Bu dizi verileri veri kaynağından kayıt kümesine aktarılacak şekilde depolayacaktır.

*Prguzunluklar*<br/>
Uzun tamsayıların dizisine yönelik bir işaretçi. Bu dizi, değeri *Prgbyteler*tarafından işaret edilen dizideki her bir değerin bayt cinsinden depolar. Karşılık gelen veri öğesi null bir değer içeriyorsa SQL_NULL_DATA değerin depolanacağı değeri unutmayın. Daha fazla ayrıntı için bkz `SQLBindCol` . *ODBC SDK Programlayıcısının başvurusu*içindeki ODBC API işlevi.

### <a name="remarks"></a>Açıklamalar

Veri kaynağı sütununda bir ODBC türü SQL_TINYINT olmalıdır. Kayıt kümesi, BYTE türü işaretçi türünde bir alan veri üyesi tanımlamalıdır.

*Prgbyteıse* ve *PRGUZUNLUKLERI* null değerine başladıysanız, işaret ettikleri diziler, satır kümesi boyutuna eşit boyutlarda otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi, verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarır. Kayıt kümenizin güncelleştirilebilir olması için ODBC API işlevini kullanmanız gerekir `SQLSetPos` .

Daha fazla bilgi için bkz. Makale [kayıt kümesi: kayıtları toplu (ODBC) halinde getirme](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz. [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_date_bulk"></a><a name="rfx_date_bulk"></a>RFX_Date_Bulk

TIMESTAMP_STRUCT verilerinin birden çok satırını, ODBC veri kaynağı sütunundan türetilmiş bir nesnede karşılık gelen bir diziye aktarır `CRecordset` .

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Date_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   TIMESTAMP_STRUCT** prgTSVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Daha fazla bilgi için bkz. [kayıt alanı değişimi: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*Prgtsler*<br/>
TIMESTAMP_STRUCT değerleri dizisine yönelik bir işaretçi. Bu dizi verileri veri kaynağından kayıt kümesine aktarılacak şekilde depolayacaktır. TIMESTAMP_STRUCT veri türü hakkında daha fazla bilgi için *ODBC SDK Programlayıcısının başvurusunun*ek D konusunun "C veri türleri" konusuna bakın.

*Prguzunluklar*<br/>
Uzun tamsayıların dizisine yönelik bir işaretçi. Bu dizi, baytlara göre işaret edilen dizideki her bir değerin bayt cinsinden uzunluğunu *depolar.* Karşılık gelen veri öğesi null bir değer içeriyorsa SQL_NULL_DATA değerin depolanacağı değeri unutmayın. Daha fazla ayrıntı için bkz `SQLBindCol` . *ODBC SDK Programlayıcısının başvurusu*içindeki ODBC API işlevi.

### <a name="remarks"></a>Açıklamalar

Veri kaynağı sütununda SQL_DATE, SQL_TIME veya SQL_TIMESTAMP ODBC türü bulunabilir. Kayıt kümesi TIMESTAMP_STRUCT işaretçi türünde bir alan veri üyesi tanımlamalıdır.

*Prgtsıse* ve *PRGUZUNLUKLARA* null olarak başladıysanız, işaret ettikleri diziler, satır kümesi boyutuna eşit boyutlarda otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi, verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarır. Kayıt kümenizin güncelleştirilebilir olması için ODBC API işlevini kullanmanız gerekir `SQLSetPos` .

Daha fazla bilgi için bkz. Makale [kayıt kümesi: kayıtları toplu (ODBC) halinde getirme](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz. [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_double_bulk"></a><a name="rfx_double_bulk"></a>RFX_Double_Bulk

Çift duyarlıklı, kayan noktalı verilerin birden çok satırını, ODBC veri kaynağı sütunundan, türetilmiş bir nesnede karşılık gelen bir diziye aktarır `CRecordset` .

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Double_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   double** prgDblVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Daha fazla bilgi için bkz. [kayıt alanı değişimi: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*Prgdbller*<br/>
Değer dizisine yönelik bir işaretçi **`double`** . Bu dizi verileri veri kaynağından kayıt kümesine aktarılacak şekilde depolayacaktır.

*Prguzunluklar*<br/>
Uzun tamsayıların dizisine yönelik bir işaretçi. Bu dizi, dizideki her değerin bayt cinsinden uzunluğunu, *Prgdbller*tarafından işaret edilen dizide depolar. Karşılık gelen veri öğesi null bir değer içeriyorsa SQL_NULL_DATA değerin depolanacağı değeri unutmayın. Daha fazla ayrıntı için bkz `SQLBindCol` . *ODBC SDK Programlayıcısının başvurusu*içindeki ODBC API işlevi.

### <a name="remarks"></a>Açıklamalar

Veri kaynağı sütununda bir ODBC türü SQL_DOUBLE olmalıdır. Kayıt kümesi, işaretçi türünde bir alan veri üyesi tanımlamalıdır **`double`** .

*Prgdbllerin* ve *PRGUZUNLUKLARıNıN* null olarak başlatılması durumunda işaret ettikleri diziler, satır kümesi boyutuna eşit boyutlarda otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi, verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarır. Kayıt kümenizin güncelleştirilebilir olması için ODBC API işlevini kullanmanız gerekir `SQLSetPos` .

Daha fazla bilgi için bkz. Makale [kayıt kümesi: kayıtları toplu (ODBC) halinde getirme](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz. [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_int_bulk"></a><a name="rfx_int_bulk"></a>RFX_Int_Bulk

Bir nesnenin alan veri üyeleri arasında tamsayı verilerini `CRecordset` ve ODBC türü SQL_SMALLINT veri kaynağındaki bir kaydın sütunlarını aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Bir nesnenin belirtebileceğiniz işlemler hakkında daha fazla bilgi için `CFieldExchange` bkz. [kayıt alanı DEĞIŞIMI: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, türünün değeri, **`int`** belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

### <a name="example"></a>Örnek

Bkz. [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_long_bulk"></a><a name="rfx_long_bulk"></a>RFX_Long_Bulk

ODBC veri kaynağı sütunundaki birden çok satırı, türetilmiş bir nesnede karşılık gelen bir diziye aktarır `CRecordset` .

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Long_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   long** prgLongVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Daha fazla bilgi için bkz. [kayıt alanı değişimi: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*Prglongışlar*<br/>
Uzun tamsayıların dizisine yönelik bir işaretçi. Bu dizi verileri veri kaynağından kayıt kümesine aktarılacak şekilde depolayacaktır.

*Prguzunluklar*<br/>
Uzun tamsayıların dizisine yönelik bir işaretçi. Bu dizi, dizideki her bir değerin bayt cinsinden uzunluğunu, *Prglongler*tarafından işaret edilen dizide depolar. Karşılık gelen veri öğesi null bir değer içeriyorsa SQL_NULL_DATA değerin depolanacağı değeri unutmayın. Daha fazla ayrıntı için bkz `SQLBindCol` . *ODBC SDK Programlayıcısının başvurusu*içindeki ODBC API işlevi.

### <a name="remarks"></a>Açıklamalar

Veri kaynağı sütununda bir ODBC türü SQL_INTEGER olmalıdır. Kayıt kümesi, işaretçi türünde bir alan veri üyesi tanımlamalıdır **`long`** .

*Prglongıse* ve *PRGUZUNLUKLERI* null değerine başladıysanız, işaret ettikleri diziler, satır kümesi boyutuna eşit boyutlarda otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi, verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarır. Kayıt kümenizin güncelleştirilebilir olması için ODBC API işlevini kullanmanız gerekir `SQLSetPos` .

Daha fazla bilgi için bkz. Makale [kayıt kümesi: kayıtları toplu (ODBC) halinde getirme](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz. [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_single_bulk"></a><a name="rfx_single_bulk"></a>RFX_Single_Bulk

Kayan nokta verilerinin birden çok satırını, ODBC veri kaynağı sütunundan türetilmiş bir nesnede karşılık gelen bir diziye aktarır `CRecordset` .

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Single_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   float** prgFltVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Daha fazla bilgi için bkz. [kayıt alanı değişimi: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*Prgfltler*<br/>
Değer dizisine yönelik bir işaretçi **`float`** . Bu dizi verileri veri kaynağından kayıt kümesine aktarılacak şekilde depolayacaktır.

*Prguzunluklar*<br/>
Uzun tamsayıların dizisine yönelik bir işaretçi. Bu dizi, baytlara *göre işaret*edilen dizideki her bir değerin bayt cinsinden uzunluğunu depolar. Karşılık gelen veri öğesi null bir değer içeriyorsa SQL_NULL_DATA değerin depolanacağı değeri unutmayın. Daha fazla ayrıntı için bkz `SQLBindCol` . *ODBC SDK Programlayıcısının başvurusu*içindeki ODBC API işlevi.

### <a name="remarks"></a>Açıklamalar

Veri kaynağı sütununda bir ODBC türü SQL_REAL olmalıdır. Kayıt kümesi, işaretçi türünde bir alan veri üyesi tanımlamalıdır **`float`** .

*Prgfltlerin* ve *PRGUZUNLUKLERININ* null olarak başlatılması durumunda işaret ettikleri diziler, satır kümesi boyutuna eşit boyutlarda otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi, verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarır. Kayıt kümenizin güncelleştirilebilir olması için ODBC API işlevini kullanmanız gerekir `SQLSetPos` .

Daha fazla bilgi için bkz. Makale [kayıt kümesi: kayıtları toplu (ODBC) halinde getirme](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz. [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="rfx_text_bulk"></a><a name="rfx_text_bulk"></a>RFX_Text_Bulk

ODBC veri kaynağındaki bir sütundan birden fazla karakter verisi satırını türetilmiş bir nesnede karşılık gelen bir diziye aktarır `CRecordset` .

### <a name="syntax"></a>Söz dizimi

```cpp
void RFX_Text_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   LPSTR* prgStrVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](cfieldexchange-class.md) nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir. Daha fazla bilgi için bkz. [kayıt alanı değişimi: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*Prgstrışlar*<br/>
LPSTR değerlerinin dizisine yönelik bir işaretçi. Bu dizi verileri veri kaynağından kayıt kümesine aktarılacak şekilde depolayacaktır. Geçerli ODBC sürümü ile bu değerlerin Unicode olamayacağını unutmayın.

*Prguzunluklar*<br/>
Uzun tamsayıların dizisine yönelik bir işaretçi. Bu dizi, baytlara *göre işaret*edilen dizideki her bir değerin bayt cinsinden uzunluğunu depolar. Bu uzunluk, null sonlandırma karakterini dışlar. Karşılık gelen veri öğesi null bir değer içeriyorsa SQL_NULL_DATA değerin depolanacağı değeri unutmayın. Daha fazla ayrıntı için bkz `SQLBindCol` . *ODBC SDK Programlayıcısının başvurusu*içindeki ODBC API işlevi.

*nMaxLength*<br/>
Null sonlandırma karakteri de dahil olmak üzere *Prgstrler*tarafından işaret edilen dizide depolanan değerlerin izin verilen en fazla uzunluğu. Verilerin kesilmemesini sağlamak için, istediğiniz en büyük veri öğesini karşılayacak büyüklükte bir değer geçirin.

### <a name="remarks"></a>Açıklamalar

Veri kaynağı sütununda bir ODBC türü SQL_LONGVARCHAR, SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL veya SQL_NUMERIC bulunabilir. Kayıt kümesi LPSTR türünde bir alan veri üyesi tanımlamalıdır.

*Prgstrıse* ve *PRGUZUNLUKLERI* null değerine başladıysanız, işaret ettikleri diziler, satır kümesi boyutuna eşit boyutlarda otomatik olarak tahsis edilir.

> [!NOTE]
> Toplu kayıt alanı değişimi, verileri yalnızca veri kaynağından kayıt kümesi nesnesine aktarır. Kayıt kümenizin güncelleştirilebilir olması için ODBC API işlevini kullanmanız gerekir `SQLSetPos` .

Daha fazla bilgi için bkz. Makale [kayıt kümesi: kayıtları toplu (ODBC) halinde getirme](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Çağrıları geçersiz kılmanızda el ile yazmanız gerekir `DoBulkFieldExchange` . Bu örnek, için bir çağrısı ve `RFX_Text_Bulk` `RFX_Long_Bulk` veri aktarımı için çağrısı gösterir. Bu çağrılar öncesinde [CFieldExchange:: set,](cfieldexchange-class.md#setfieldtype)öğesine yapılan bir çağrıdır. Parametreler için, toplu RFX işlevleri yerine RFX işlevlerini çağırmanız gerektiğini unutmayın.

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

**Üstbilgi:** Afxdb. h

## <a name="dfx_binary"></a><a name="dfx_binary"></a>DFX_Binary

Bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasındaki bayt dizilerini aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void AFXAPI DFX_Binary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CByteArray& value,
   int nPreAllocSize = AFX_DAO_BINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[Cdadofieldexchange](cdaofieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir.

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, [CByteArray](cbytearray-class.md)türündeki değer belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

*nPreAllocSize*<br/>
Çerçeve bu bellek miktarını önceden ayırır. Verileriniz daha büyükse, çerçeve gerektiğinde daha fazla alan ayıracaktır. Daha iyi performans için bu boyutu, realyerleri önleyecek büyüklükte bir değere ayarlayın. Varsayılan boyut, AFXDAO 'da tanımlanmıştır. H dosyasını AFX_DAO_BINARY_DEFAULT_SIZE.

*Dwbindoseçenekleri*<br/>
Değiştirilen kayıt kümesi alanlarını saptamak için MFC 'nin çift arabelleğe alma mekanizmasından yararlanmanıza olanak tanıyan bir seçenektir. AFX_DAO_DISABLE_FIELD_CACHE, varsayılan olarak çift arabelleğe alma kullanmaz ve [SetFieldDirty](cdaorecordset-class.md#setfielddirty) ve [SetFieldNull](cdaorecordset-class.md#setfieldnull) öğesini kendiniz çağırmanız gerekir. Diğer olası değer AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır ve alanları kirli veya null olarak işaretlemek için ek iş yapmanız gerekmez. Performans ve bellek nedenleriyle, ikili verileriniz görece küçük olmadığı takdirde bu değeri kullanmaktan kaçının.

> [!NOTE]
> Varsayılan olarak, [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)' i ayarlayarak, verilerin tüm alanlar için iki kez arabelleğe alınıp alınmayacağını kontrol edebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO içindeki tür DAO_BYTES ile eşlenir ve kayıt kümesinde [CByteArray](cbytearray-class.md) yazın.

### <a name="example"></a>Örnek

Bkz. [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="dfx_bool"></a><a name="dfx_bool"></a>DFX_Bool

Bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında Boole verileri aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void AFXAPI DFX_Bool(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BOOL& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[Cdadofieldexchange](cdaofieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir.

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, BOOL türündeki değer belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

*Dwbindoseçenekleri*<br/>
Değiştirilen kayıt kümesi alanlarını saptamak için MFC 'nin çift arabelleğe alma mekanizmasından yararlanmanıza olanak tanıyan bir seçenektir. Varsayılan AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Olası diğer değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanı denetlemez. `SetFieldDirty`' İ çağırmanız gerekir `SetFieldNull` .

> [!NOTE]
> Varsayılan olarak, [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)' i ayarlayarak verilerin iki kez arabelleğe alınıp alınmayacağını kontrol edebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO içindeki DAO_BOOL türü ile kayıt kümesinde BOOL türü arasında eşlenir.

### <a name="example"></a>Örnek

Bkz. [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="dfx_byte"></a><a name="dfx_byte"></a>DFX_Byte

Bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında tek bayt aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void AFXAPI DFX_Byte(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BYTE& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[Cdadofieldexchange](cdaofieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir.

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, BYTE türündeki değer belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

*Dwbindoseçenekleri*<br/>
Değiştirilen kayıt kümesi alanlarını saptamak için MFC 'nin çift arabelleğe alma mekanizmasından yararlanmanıza olanak tanıyan bir seçenektir. Varsayılan AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Olası diğer değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanı denetlemez. `SetFieldDirty`' İ çağırmanız gerekir `SetFieldNull` .

> [!NOTE]
> Varsayılan olarak, [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)' i ayarlayarak verilerin iki kez arabelleğe alınıp alınmayacağını kontrol edebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO içindeki tür DAO_BYTES ve kayıt kümesinde BYTE türü arasında eşlenir.

### <a name="example"></a>Örnek

Bkz. [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="dfx_currency"></a><a name="dfx_currency"></a>DFX_Currency

Bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında para birimi verilerini aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void AFXAPI DFX_Currency(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleCurrency& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[Cdadofieldexchange](cdaofieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir.

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, bu değer [Copacurrency](colecurrency-class.md)türünde belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

*Dwbindoseçenekleri*<br/>
Değiştirilen kayıt kümesi alanlarını saptamak için MFC 'nin çift arabelleğe alma mekanizmasından yararlanmanıza olanak tanıyan bir seçenektir. Varsayılan AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Olası diğer değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanı denetlemez. `SetFieldDirty`' İ çağırmanız gerekir `SetFieldNull` .

> [!NOTE]
> Varsayılan olarak, [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)' i ayarlayarak verilerin iki kez arabelleğe alınıp alınmayacağını kontrol edebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO içindeki tür DAO_CURRENCY ile eşlenir ve kayıt kümesine [Copacurrency](colecurrency-class.md) yazın.

### <a name="example"></a>Örnek

Bkz. [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="dfx_datetime"></a><a name="dfx_datetime"></a>DFX_DateTime

Bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında saat ve Tarih verilerini aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void AFXAPI DFX_DateTime(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleDateTime& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[Cdadofieldexchange](cdaofieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir.

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. İşlevi [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesine bir başvuru alır. Kayıt kümesinden veri kaynağına aktarım için, bu değer belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

*Dwbindoseçenekleri*<br/>
Değiştirilen kayıt kümesi alanlarını saptamak için MFC 'nin çift arabelleğe alma mekanizmasından yararlanmanıza olanak tanıyan bir seçenektir. Varsayılan AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Olası diğer değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanı denetlemez. `SetFieldDirty`' İ çağırmanız gerekir `SetFieldNull` .

> [!NOTE]
> Varsayılan olarak, [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)' i ayarlayarak verilerin iki kez arabelleğe alınıp alınmayacağını kontrol edebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO içindeki tür DAO_DATE ve kayıt kümesinde [Copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) türü arasında eşlenir.

> [!NOTE]
> `COleDateTime`DAO sınıflarında bu amaçla [CTime](../../atl-mfc-shared/reference/ctime-class.md) ve TIMESTAMP_STRUCT değiştirir. `CTime`ve TIMESTAMP_STRUCT, ODBC tabanlı veri erişim sınıfları için hala kullanılmaktadır.

### <a name="example"></a>Örnek

Bkz. [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="dfx_double"></a><a name="dfx_double"></a>DFX_Double

Bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında **çift kayan** veri aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void AFXAPI DFX_Double(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   double& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[Cdadofieldexchange](cdaofieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir.

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, türünün değeri, **`double`** belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

*Dwbindoseçenekleri*<br/>
Değiştirilen kayıt kümesi alanlarını saptamak için MFC 'nin çift arabelleğe alma mekanizmasından yararlanmanıza olanak tanıyan bir seçenektir. Varsayılan AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Olası diğer değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanı denetlemez. `SetFieldDirty`' İ çağırmanız gerekir `SetFieldNull` .

> [!NOTE]
> Varsayılan olarak, [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)' i ayarlayarak verilerin iki kez arabelleğe alınıp alınmayacağını kontrol edebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO içindeki DAO_R8 tür ile eşlenir ve kayıt kümesine **çift float** yazın.

### <a name="example"></a>Örnek

Bkz. [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="dfx_long"></a><a name="dfx_long"></a>DFX_Long

Bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında uzun tamsayı verilerini aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void AFXAPI DFX_Long(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   long& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[Cdadofieldexchange](cdaofieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir.

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, türünün değeri, **`long`** belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

*Dwbindoseçenekleri*<br/>
Değiştirilen kayıt kümesi alanlarını saptamak için MFC 'nin çift arabelleğe alma mekanizmasından yararlanmanıza olanak tanıyan bir seçenektir. Varsayılan AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Olası diğer değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanı denetlemez. `SetFieldDirty`' İ çağırmanız gerekir `SetFieldNull` .

> [!NOTE]
> Varsayılan olarak, [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)' i ayarlayarak verilerin iki kez arabelleğe alınıp alınmayacağını kontrol edebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO içindeki tür DAO_I4 ve kayıt kümesine tür arasında eşlenir **`long`** .

### <a name="example"></a>Örnek

Bkz. [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="dfx_longbinary"></a><a name="dfx_longbinary"></a>DFX_LongBinary

**Önemli** Bu işlev yerine [DFX_Binary](#dfx_binary) kullanmanız önerilir.

### <a name="syntax"></a>Söz dizimi

```cpp
void AFXAPI DFX_LongBinary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CLongBinary& value,
   DWORD dwPreAllocSize = AFX_DAO_LONGBINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[Cdadofieldexchange](cdaofieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir.

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına bir aktarım için, [CLongBinary](clongbinary-class.md)türündeki değer belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

*dwPreAllocSize*<br/>
Çerçeve bu bellek miktarını önceden ayırır. Verileriniz daha büyükse, çerçeve gerektiğinde daha fazla alan ayıracaktır. Daha iyi performans için bu boyutu, realyerleri önleyecek büyüklükte bir değere ayarlayın.

*Dwbindoseçenekleri*<br/>
Değiştirilen kayıt kümesi alanlarını saptamak için MFC 'nin çift arabelleğe alma mekanizmasından yararlanmanıza olanak tanıyan bir seçenektir. Varsayılan AFX_DISABLE_FIELD_CACHE, çift arabelleğe alma kullanmaz. Olası diğer değer AFX_DAO_ENABLE_FIELD_CACHE. Double arabelleğe almayı kullanır ve alanları kirli veya null olarak işaretlemek için ek iş yapmanız gerekmez. Performans ve bellek nedenleriyle, ikili verileriniz görece küçük olmadığı takdirde bu değeri kullanmaktan kaçının.

> [!NOTE]
> Varsayılan olarak, [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)' i ayarlayarak verilerin iki kez arabelleğe alınıp alınmayacağını kontrol edebilirsiniz.

### <a name="remarks"></a>Açıklamalar

`DFX_LongBinary`MFC ODBC sınıflarıyla uyumluluk için sağlanır. `DFX_LongBinary`İşlevi, `CLongBinary` bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında sınıfı kullanarak IKILI büyük nesne (blob) verilerini aktarır. Veriler, DAO içindeki tür DAO_BYTES ve kayıt kümesinde [CLongBinary](clongbinary-class.md) türü arasında eşlenir.

### <a name="example"></a>Örnek

Bkz. [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="dfx_short"></a><a name="dfx_short"></a>DFX_Short

Bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında kısa tamsayı verilerini aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void AFXAPI DFX_Short(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   short& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[Cdadofieldexchange](cdaofieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir.

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, türünün değeri, **`short`** belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

*Dwbindoseçenekleri*<br/>
Değiştirilen kayıt kümesi alanlarını saptamak için MFC 'nin çift arabelleğe alma mekanizmasından yararlanmanıza olanak tanıyan bir seçenektir. Varsayılan AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Olası diğer değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanı denetlemez. `SetFieldDirty`' İ çağırmanız gerekir `SetFieldNull` .

> [!NOTE]
> Varsayılan olarak, [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)' i ayarlayarak verilerin iki kez arabelleğe alınıp alınmayacağını kontrol edebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO içindeki tür DAO_I2 ve kayıt kümesine tür arasında eşlenir **`short`** .

> [!NOTE]
> `DFX_Short`, ODBC tabanlı sınıflar için [RFX_Int](#rfx_int) eşdeğerdir.

### <a name="example"></a>Örnek

Bkz. [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="dfx_single"></a><a name="dfx_single"></a>DFX_Single

Kayan nokta verilerini bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ile veri kaynağındaki bir kaydın sütunları arasında aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void AFXAPI DFX_Single(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   float& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[Cdadofieldexchange](cdaofieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir.

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, türünün değeri, **`float`** belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

*Dwbindoseçenekleri*<br/>
Değiştirilen kayıt kümesi alanlarını saptamak için MFC 'nin çift arabelleğe alma mekanizmasından yararlanmanıza olanak tanıyan bir seçenektir. Varsayılan AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Olası diğer değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanı denetlemez. `SetFieldDirty`' İ çağırmanız gerekir `SetFieldNull` .

> [!NOTE]
> Varsayılan olarak, [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)' i ayarlayarak verilerin iki kez arabelleğe alınıp alınmayacağını kontrol edebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO içindeki tür DAO_R4 ve kayıt kümesine tür arasında eşlenir **`float`** .

### <a name="example"></a>Örnek

Bkz. [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="dfx_text"></a><a name="dfx_text"></a>DFX_Text

Verileri `CString` bir [CDaoRecordset](cdaorecordset-class.md) nesnesinin alan veri üyeleri ve veri kaynağındaki bir kaydın sütunları arasında aktarır.

### <a name="syntax"></a>Söz dizimi

```cpp
void AFXAPI DFX_Text(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CString& value,
   int nPreAllocSize = AFX_DAO_TEXT_DEFAULT_SIZE,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[Cdadofieldexchange](cdaofieldexchange-class.md)sınıfının nesnesine yönelik bir işaretçi. Bu nesne, işlevin her bir çağrısının bağlamını tanımlamak için bilgiler içerir.

*szName*<br/>
Bir veri sütununun adı.

*deeri*<br/>
Belirtilen veri üyesinde depolanan değer — aktarılacak değer. Kayıt kümesinden veri kaynağına aktarım için, [CString](../../atl-mfc-shared/reference/cstringt-class.md)türündeki değer, belirtilen veri üyesinden alınır. Veri kaynağından kayıt kümesine aktarım için, değer belirtilen veri üyesinde depolanır.

*nPreAllocSize*<br/>
Çerçeve bu bellek miktarını önceden ayırır. Verileriniz daha büyükse, çerçeve gerektiğinde daha fazla alan ayıracaktır. Daha iyi performans için bu boyutu, realyerleri önleyecek büyüklükte bir değere ayarlayın.

*Dwbindoseçenekleri*<br/>
Değiştirilen kayıt kümesi alanlarını saptamak için MFC 'nin çift arabelleğe alma mekanizmasından yararlanmanıza olanak tanıyan bir seçenektir. Varsayılan AFX_DAO_ENABLE_FIELD_CACHE, çift arabelleğe alma kullanır. Olası diğer değer AFX_DAO_DISABLE_FIELD_CACHE. Bu değeri belirtirseniz, MFC bu alanı denetlemez. [SetFieldDirty](cdaorecordset-class.md#setfielddirty) ve [SetFieldNull](cdaorecordset-class.md#setfieldnull) ' i çağırmanız gerekir.

> [!NOTE]
> Varsayılan olarak, [CDaoRecordset:: m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields)' i ayarlayarak verilerin iki kez arabelleğe alınıp alınmayacağını kontrol edebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Veriler, DAO içindeki tür DAO_CHAR arasında eşlenir (veya sembol _UNICODE tanımlanmışsa, DAO_WCHAR) ve kayıt kümesinde [CString](../../atl-mfc-shared/reference/cstringt-class.md) yazın.  n

### <a name="example"></a>Örnek

Bu örnekte, için birkaç çağrı gösterilmektedir `DFX_Text` . Ayrıca, [Cdavofieldexchange:: Setıda](cdaofieldexchange-class.md#setfieldtype)öğesine yapılan iki çağrıya dikkat edin. İlk çağrıyı `SetFieldType` ve onun **DFX** çağrısını yazmanız gerekir. İkinci çağrı ve ilişkili **DFX** çağrıları, normalde sınıfı oluşturan kod Sihirbazı tarafından yazılır.

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

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
[CRecordset::D oFieldExchange](crecordset-class.md#dofieldexchange)<br/>
[CRecordset::D oBulkFieldExchange](crecordset-class.md#dobulkfieldexchange)<br/>
[CDaoRecordset::D oFieldExchange](cdaorecordset-class.md#dofieldexchange)
