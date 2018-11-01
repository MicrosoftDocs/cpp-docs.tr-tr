---
title: Kayıt Alanı Değişim İşlevleri
ms.date: 11/04/2016
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
ms.openlocfilehash: 2970a722f79e9707f8721c1c8595bfd1d133f898
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525950"
---
# <a name="record-field-exchange-functions"></a>Kayıt Alanı Değişim İşlevleri

Bu konu kayıt alanı değişimi (RFX, toplu RFX ve DFX) listeler kendi veri kaynağı ile bir kayıt kümesi nesnesi arasındaki veri aktarımını otomatik hale getirmek ve diğer veriler üzerinde işlemler gerçekleştirmek için kullanılan işlevleri.

ODBC tabanlı sınıflar kullanıyorsanız ve toplu satır getirme uyguladıysanız, el ile tanımlamalısınız `DoBulkFieldExchange` üye işlevinin `CRecordset` bir veri kaynağı sütununa karşılık gelen her veri üyesi için Toplu RFX işlevleri çağırarak.

Toplu satır ODBC tabanlı sınıflarda getirme uygulanmadı ya da ClassWizard DAO dayalı sınıflar kullanıyorsanız, ardından kılar `DoFieldExchange` üye işlevinin `CRecordset` veya `CDaoRecordset` RFX işlevleri (ODBC sınıfları için çağırarak ) veya kümenizde her alanın veri üyesi için DFX işlevleri (için DAO sınıfları).

Kayıt alanı değişim işlevleri her zaman çerçevesi çağıran veri aktarımı `DoFieldExchange` veya `DoBulkFieldExchange`. Her işlev bir özel veri türü aktarır.

Bu işlevlerin nasıl kullanıldığı hakkında daha fazla bilgi için makalelere göz atın [kayıt alanı değişimi: nasıl RFX çalışır (ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md). Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Dinamik olarak bağlama veri sütunlar için de RFX veya DFX işlevleri kendiniz makalelerinde açıklandığı gibi çağırabilirsiniz [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). Ayrıca, Teknik Not açıklandığı gibi kendi özel RFX veya DFX rutinleri yazabilirsiniz [43](../../mfc/tn043-rfx-routines.md) (ODBC için) ve Teknik Not [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (DAO için).

RFX ve toplu RFX örneği için işlevleri gibi görünürler `DoFieldExchange` ve `DoBulkFieldExchange` işlevleri, [RFX_Text](#rfx_text) ve #rfx_text_bulk [RFX_Text_Bulk]). DFX işlevleri RFX işlevleri için oldukça benzerdir.

### <a name="rfx-functions-odbc"></a>RFX işlevleri (ODBC)

|||
|-|-|
|[RFX_Binary](#rfx_binary)|Türünde bayt dizilerini aktarır [CByteArray](cbytearray-class.md).|
|[RFX_Bool](#rfx_bool)|Boole veri aktarır.|
|[RFX_Byte](#rfx_byte)|Tek bir bayt veri aktarır.|
|[RFX_Date](#rfx_date)|Aktarımı saat ve tarih verilerini kullanan [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya TIMESTAMP_STRUCT.|
|[RFX_Double](#rfx_double)|Çift duyarlıklı kayan veri aktarır.|
|[Rfx_ınt](#rfx_int)|Tamsayı veri aktarır.|
|[RFX_Long](#rfx_long)|Tamsayı veri aktarımları uzun.|
|[RFX_LongBinary](#rfx_longbinary)|Bir nesne ile ikili büyük nesne (BLOB) veri aktarımı [CLongBinary](clongbinary-class.md) sınıfı.|
|[RFX_Single](#rfx_single)|Veri aktarımları kaydırın.|
|[RFX_Text](#rfx_text)|Veri aktarımları dize.|

### <a name="bulk-rfx-functions-odbc"></a>Toplu RFX işlevleri (ODBC)

|||
|-|-|
|[RFX_Binary_Bulk](#rfx_binary_bulk)|Dizileri bayt veri aktarır.|
|[RFX_Bool_Bulk](#rfx_bool_bulk)|Boole veri dizileri aktarır.|
|[RFX_Byte_Bulk](#rfx_byte_bulk)|Tek bayt dizilerini aktarır.|
|[RFX_Date_Bulk](#rfx_date_bulk)|Veri türü TIMESTAMP_STRUCT dizileri aktarır.|
|[RFX_Double_Bulk](#rfx_double_bulk)|Çift duyarlıklı, kayan nokta veri dizileri aktarır.|
|[Rfx_ınt_bulk](#rfx_int_bulk)|Tamsayı veri dizileri aktarır.|
|[RFX_Long_Bulk](#rfx_long_bulk)|Uzun tamsayı veri dizileri aktarır.|
|[RFX_Single_Bulk](#rfx_single_bulk)|Kayan nokta veri dizileri aktarır.|
|[RFX_Text_Bulk](#rfx_text_bulk)|Veri türü LPSTR dizileri aktarır.|

### <a name="dfx-functions-dao"></a>DFX işlevleri (DAO)

|||
|-|-|
|[DFX_Binary](#dfx_binary)|Türünde bayt dizilerini aktarır [CByteArray](cbytearray-class.md).|
|[DFX_Bool](#dfx_bool)|Boole veri aktarır.|
|[DFX_Byte](#dfx_byte)|Tek bir bayt veri aktarır.|
|[DFX_Currency](#dfx_currency)|Tür, para birimi veri aktarımları [COleCurrency](colecurrency-class.md).|
|[DFX_DateTime](#dfx_datetime)|Tür, saat ve tarih veri aktarımları [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md).|
|[DFX_Double](#dfx_double)|Çift duyarlıklı kayan veri aktarır.|
|[DFX_Long](#dfx_long)|Tamsayı veri aktarımları uzun.|
|[DFX_LongBinary](#dfx_longbinary)|Bir nesne ile ikili büyük nesne (BLOB) veri aktarımı `CLongBinary` sınıfı. DAO için kullanmanız önerilir [DFX_Binary](#dfx_binary) yerine.|
|[DFX_Short](#dfx_short)|Tamsayı veri aktarımları kısa.|
|[DFX_Single](#dfx_single)|Veri aktarımları kaydırın.|
|[DFX_Text](#dfx_text)|Veri aktarımları dize.|

=============================================

## <a name="rfx_binary"></a>  RFX_Binary

Alan veri üyeleri arasında bayt dizilerini aktaran bir `CRecordset` nesnesi ve bir kaydın, ODBC veri kaynağında sütunları uzun SQL_BINARY, SQL_VARBINARY veya SQL_LONGVARBINARY yazın.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Binary(
   CFieldExchange* pFX,
   const char* szName,
   CByteArray& value,
   int nMaxLength = 255);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye göz atın [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için [CByteArray](cbytearray-class.md), belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

*nMaxLength*<br/>
Aktarılan dizi ve dize uzunluğu izin verilen en fazla. Varsayılan değer olan *nMaxLength* 255'tir. INT_MAX 1 yasal değerlerdir. Framework bu alanı miktarı, verileri ayırır. En iyi performans için en büyük veri öğesi beklediğiniz tutabilecek kadar büyük bir değer geçirin.

### <a name="remarks"></a>Açıklamalar

Bu tür veri kaynağındaki türü gelen ve giden eşlenen `CByteArray` kümesinde.

### <a name="example"></a>Örnek

Bkz: [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_bool"></a>  RFX_Bool

Alan veri üyeleri arasında Boole veri aktaran bir `CRecordset` nesnesi ve bir kaydın, ODBC veri kaynağında sütunları SQL_BIT yazın.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Bool(
   CFieldExchange* pFX,
   const char* szName,
   BOOL& value);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye göz atın [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir aktarımı için kayıt kümesi veri kaynağına, BOOL, türü değeri, belirtilen veri üyesi alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

### <a name="example"></a>Örnek

Bkz: [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_byte"></a>  RFX_Byte

Bayt alan veri üyeleri arasındaki aktarımları tek bir `CRecordset` nesnesi ve bir kaydın, ODBC veri kaynağında sütunları SQL_TINYINT yazın.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Byte(
   CFieldExchange* pFX,
   const char* szName,
   BYTE& value);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye göz atın [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir aktarımı için kayıt kümesi veri kaynağına, belirtilen veri üyesi tür bayt değeri alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

### <a name="example"></a>Örnek

Bkz: [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_date"></a>  RFX_Date

Aktarımları `CTime` veya TIMESTAMP_STRUCT veri alan veri üyeleri arasında bir `CRecordset` nesnesi ve bir kaydın, ODBC veri kaynağında sütunları SQL_DATE, SQL_TIME veya SQL_TIMESTAMP yazın.

### <a name="syntax"></a>Sözdizimi

```
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

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye göz atın [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri; Transfer edilecek değer. İşlevin çeşitli sürümleri, farklı veri türleri için değer uygulayın:

İlk sürüm işlevin bir başvuru alır bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesne. Bir aktarımı için kayıt kümesi veri kaynağına, bu değer, belirtilen veri üyesi alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

İşlevin ikinci sürüm bir başvuru alır bir `TIMESTAMP_STRUCT` yapısı. Bu yapısına çağrısından önce kendiniz ayarlamalısınız. Her iki iletişim kutusu veri değişimi (DDX) desteği ve kod Sihirbazı desteği bu sürümü için kullanılabilir. İşlevin üçüncü sürümünü çalıştığını benzer şekilde ilk sürümü için bir başvuru alır dışında bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

`CTime` İşlevin sürümünü bazı Ara işleme yükü uygular ve biraz sınırlı aralığa sahip. Bu faktörlerin çok sınırlama bulursanız, işlevin ikinci sürümünü kullanın. Ancak, kod Sihirbazı'nı ve DDX destek yapıyı kendiniz ayarlamak gereksinim eksikliği unutmayın.

### <a name="example"></a>Örnek

Bkz: [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_double"></a>  RFX_Double

Aktarımları **double float** veri alan veri üyeleri arasında bir `CRecordset` nesnesi ve bir kaydın, ODBC veri kaynağında sütunları SQL_DOUBLE yazın.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Double(
   CFieldExchange* pFX,
   const char* szName,
   double& value);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye göz atın [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için **çift**, belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

### <a name="example"></a>Örnek

Bkz: [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_int"></a>  Rfx_ınt

Alan veri üyeleri arasında tamsayı veri aktaran bir `CRecordset` nesnesi ve bir kaydın, ODBC veri kaynağında sütunları SQL_SMALLINT yazın.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye göz atın [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için **int**, belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

### <a name="example"></a>Örnek

Bkz: [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_long"></a>  RFX_Long

Alan veri üyeleri arasında uzun tamsayı veri aktaran bir `CRecordset` nesnesi ve bir kaydın, ODBC veri kaynağında sütunları SQL_INTEGER yazın.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Long(
   CFieldExchange* pFX,
   const char* szName,
   LONG&
value );
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye göz atın [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için **uzun**, belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

### <a name="example"></a>Örnek

Bkz: [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_longbinary"></a>  RFX_LongBinary

Sınıfını kullanarak ikili büyük nesne (BLOB) veri aktarımı [CLongBinary](clongbinary-class.md) alan veri üyeleri arasında bir `CRecordset` nesnesi ve bir kaydın, ODBC veri kaynağında sütunları SQL_LONGVARBINARY veya SQL_LONGVARCHAR yazın.

### <a name="syntax"></a>Sözdizimi

```
void RFX_LongBinary(
   CFieldExchange* pFX,
   const char* szName,
   CLongBinary& value);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye göz atın [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için `CLongBinary`, belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

### <a name="example"></a>Örnek

Bkz: [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_single"></a>  RFX_Single

Kayan nokta veri alan veri üyeleri aktarımları bir `CRecordset` nesnesi ve bir kaydın, ODBC veri kaynağında sütunları SQL_REAL yazın.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Single(
   CFieldExchange* pFX,
   const char* szName,
   float& value);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye göz atın [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için **float**, belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

### <a name="example"></a>Örnek

Bkz: [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_text"></a>  RFX_Text

Aktarımları `CString` veri alan veri üyeleri arasında bir `CRecordset` nesnesi ve bir kaydın, ODBC veri kaynağında sütunları SQL_LONGVARCHAR, SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL veya SQL_NUMERIC yazın.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Text(
   CFieldExchange* pFX,
   const char* szName,
   CString& value,
   int nMaxLength = 255,
   int nColumnType = SQL_VARCHAR,
   short nScale = 0);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi `CFieldExchange`. Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye göz atın [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için `CString`, belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

*nMaxLength*<br/>
Aktarılan dizi ve dize uzunluğu izin verilen en fazla. Varsayılan değer olan *nMaxLength* 255'tir. Yasal INT_MAX 1 değerler). Framework bu alanı miktarı, verileri ayırır. En iyi performans için en büyük veri öğesi beklediğiniz tutabilecek kadar büyük bir değer geçirin.

*nColumnType*<br/>
Çoğunlukla parametreleri için kullanılır. Parametrenin veri türünü belirten bir tamsayı. Bir ODBC veri türü formun türüdür **SQL_XXX**.

*nScale*<br/>
Ölçek SQL_DECIMAL veya SQL_NUMERIC ODBC türündeki değerlerin belirtir. *nScale* yalnızca da parametre değerlerini belirlerken yararlı olur. Daha fazla bilgi için "Duyarlığı, Ölçek, uzunluğu ve görüntüleme boyutu" Ek D'ye konusuna *ODBC SDK Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Tüm bu türler, veri kaynağındaki ve ondan eşlenen `CString` kümesinde.

### <a name="example"></a>Örnek

Bu örnek, çeşitli çağrıları gösterir `RFX_Text`. Ayrıca iki çağrıları fark `CFieldExchange::SetFieldType`. Parametreler için çağrı yazmanız gereken `SetFieldType` ve kendi RFX çağrısı. Normalde, çıkış sütunu çağrı ve onun ilişkili RFX çağrıları kod Sihirbazı tarafından yazılır.

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

**Başlık:** afxdb.h

## <a name="rfx_binary_bulk"></a>  RFX_Binary_Bulk

ODBC veri kaynağında bir sütundan karşılık gelen bir dizi içinde birden çok sayıda bayt veri aktarır bir `CRecordset`-türetilmiş bir nesneye.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Binary_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesne. Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. Daha fazla bilgi için bkz [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*prgByteVals*<br/>
BAYT değerleri dizisi için bir işaretçi. Bu dizi için kayıt veri kaynağından aktarılacak veri depolar.

*prgLengths*<br/>
Uzun tamsayı dizisi için bir işaretçi. Bu dizi işaret ettiği dizideki her bir değerin bayt cinsinden uzunluğu depolayacak *prgByteVals*. Karşılık gelen veri öğesi Null bir değer içeriyorsa, ' % s'değeri SQL_NULL_DATA depolanır unutmayın. Daha fazla ayrıntı için bkz: ODBC API işlevini `SQLBindCol` içinde *ODBC SDK Programcının Başvurusu*.

*nMaxLength*<br/>
İzin verilen maksimum uzunluğu işaret ettiği dizisinde depolanan değerlerin *prgByteVals*. Veri yok kesilecek emin olmak için büyük veri öğesi beklediğiniz tutabilecek kadar büyük bir değer geçirin.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütunu uzun SQL_BINARY, SQL_VARBINARY veya SQL_LONGVARBINARY bir ODBC türlerine sahip olabilir. Kayıt türü işaretçi alan veri üyesi BAYTA tanımlamanız gerekir.

Başlatın, *prgByteVals* ve *prgLengths* null, ardından bunların işaret dizileri otomatik olarak satır kümesi boyutuna eşit boyutları ile ayrılır.

> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından recordset nesnesine aktarır. Kümenizin güncelleştirilebilir kolaylaştırmak için ODBC API işlevini kullanmalısınız `SQLSetPos`.

Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz: [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_bool_bulk"></a>  RFX_Bool_Bulk

ODBC veri kaynağında bir sütundan karşılık gelen bir dizi içinde birden çok satır Boolean veri aktarır bir `CRecordset`-türetilmiş bir nesneye.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Bool_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BOOL** prgBoolVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesne. Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. Daha fazla bilgi için bkz [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*prgBoolVals*<br/>
BOOL değerleri dizisi için bir işaretçi. Bu dizi için kayıt veri kaynağından aktarılacak veri depolar.

*prgLengths*<br/>
Uzun tamsayı dizisi için bir işaretçi. Bu dizi işaret ettiği dizideki her bir değerin bayt cinsinden uzunluğu depolayacak *prgBoolVals*. Karşılık gelen veri öğesi Null bir değer içeriyorsa, ' % s'değeri SQL_NULL_DATA depolanır unutmayın. Daha fazla ayrıntı için bkz: ODBC API işlevini `SQLBindCol` içinde *ODBC SDK Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütunu SQL_BIT bir ODBC türünde olması gerekir. Kayıt türü işaretçi alan veri üyesi BOOL değerine tanımlamanız gerekir.

Başlatın, *prgBoolVals* ve *prgLengths* null, ardından bunların işaret dizileri otomatik olarak satır kümesi boyutuna eşit boyutları ile ayrılır.

> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından recordset nesnesine aktarır. Kümenizin güncelleştirilebilir yapmak için ODBC API işlevini kullanmalısınız `SQLSetPos`.

Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz: [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_byte_bulk"></a>  RFX_Byte_Bulk

Birden çok satır tek baytlık bir ODBC veri kaynağını sütundan karşılık gelen bir dizide aktarır bir `CRecordset`-türetilmiş bir nesneye.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Byte_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesne. Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. Daha fazla bilgi için bkz [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*prgByteVals*<br/>
BAYT değerleri dizisi için bir işaretçi. Bu dizi için kayıt veri kaynağından aktarılacak veri depolar.

*prgLengths*<br/>
Uzun tamsayı dizisi için bir işaretçi. Bu dizi işaret ettiği dizideki her bir değerin bayt cinsinden uzunluğu depolayacak *prgByteVals*. Karşılık gelen veri öğesi Null bir değer içeriyorsa, ' % s'değeri SQL_NULL_DATA depolanır unutmayın. Daha fazla ayrıntı için bkz: ODBC API işlevini `SQLBindCol` içinde *ODBC SDK Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütunu SQL_TINYINT bir ODBC türünde olması gerekir. Kayıt türü işaretçi alan veri üyesi BAYTA tanımlamanız gerekir.

Başlatın, *prgByteVals* ve *prgLengths* null, ardından bunların işaret dizileri otomatik olarak satır kümesi boyutuna eşit boyutları ile ayrılır.

> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından recordset nesnesine aktarır. Kümenizin güncelleştirilebilir yapmak için ODBC API işlevini kullanmalısınız `SQLSetPos`.

Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz: [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_date_bulk"></a>  RFX_Date_Bulk

ODBC veri kaynağında bir sütundan karşılık gelen bir dizi içinde birden çok satır TIMESTAMP_STRUCT veri aktarır bir `CRecordset`-türetilmiş bir nesneye.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Date_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   TIMESTAMP_STRUCT** prgTSVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesne. Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. Daha fazla bilgi için bkz [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*prgTSVals*<br/>
Bir dizi TIMESTAMP_STRUCT değere bir işaretçi. Bu dizi için kayıt veri kaynağından aktarılacak veri depolar. TIMESTAMP_STRUCT veri türü hakkında daha fazla bilgi için ek D içinde "C veri türleri" konusuna bakın. *ODBC SDK Programcının Başvurusu*.

*prgLengths*<br/>
Uzun tamsayı dizisi için bir işaretçi. Bu dizi işaret ettiği dizideki her bir değerin bayt cinsinden uzunluğu depolayacak *prgTSVals*. Karşılık gelen veri öğesi Null bir değer içeriyorsa, ' % s'değeri SQL_NULL_DATA depolanır unutmayın. Daha fazla ayrıntı için bkz: ODBC API işlevini `SQLBindCol` içinde *ODBC SDK Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütunu SQL_DATE, SQL_TIME veya SQL_TIMESTAMP bir ODBC türlerine sahip olabilir. Kayıt türü işaretçi alan veri üyesi için TIMESTAMP_STRUCT tanımlamanız gerekir.

Başlatın, *prgTSVals* ve *prgLengths* null, ardından bunların işaret dizileri otomatik olarak satır kümesi boyutuna eşit boyutları ile ayrılır.

> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından recordset nesnesine aktarır. Kümenizin güncelleştirilebilir yapmak için ODBC API işlevini kullanmalısınız `SQLSetPos`.

Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz: [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_double_bulk"></a>  RFX_Double_Bulk

ODBC veri kaynağında bir sütundan karşılık gelen bir dizi içinde birden çok sayıda çift duyarlıklı, kayan nokta veri aktarır bir `CRecordset`-türetilmiş bir nesneye.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Double_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   double** prgDblVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesne. Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. Daha fazla bilgi için bkz [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*prgDblVals*<br/>
Bir dizi işaretçi **çift** değerleri. Bu dizi için kayıt veri kaynağından aktarılacak veri depolar.

*prgLengths*<br/>
Uzun tamsayı dizisi için bir işaretçi. Bu dizi işaret ettiği dizideki her bir değerin bayt cinsinden uzunluğu depolayacak *prgDblVals*. Karşılık gelen veri öğesi Null bir değer içeriyorsa, ' % s'değeri SQL_NULL_DATA depolanır unutmayın. Daha fazla ayrıntı için bkz: ODBC API işlevini `SQLBindCol` içinde *ODBC SDK Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütunu SQL_DOUBLE bir ODBC türünde olması gerekir. Kayıt kümesi işaretçi türüne bir alan veri üyesi tanımlamalıdır **çift**.

Başlatın, *prgDblVals* ve *prgLengths* null, ardından bunların işaret dizileri otomatik olarak satır kümesi boyutuna eşit boyutları ile ayrılır.

> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından recordset nesnesine aktarır. Kümenizin güncelleştirilebilir yapmak için ODBC API işlevini kullanmalısınız `SQLSetPos`.

Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz: [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_int_bulk"></a>  Rfx_ınt_bulk

Alan veri üyeleri arasında tamsayı veri aktaran bir `CRecordset` nesnesi ve bir kaydın, ODBC veri kaynağında sütunları SQL_SMALLINT yazın.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye göz atın [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için **int**, belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

### <a name="example"></a>Örnek

Bkz: [RFX_Text](#rfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_long_bulk"></a>  RFX_Long_Bulk

ODBC veri kaynağında bir sütundan karşılık gelen bir dizi içinde birden çok sayıda uzun tamsayı veri aktarır bir `CRecordset`-türetilmiş bir nesneye.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Long_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   long** prgLongVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesne. Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. Daha fazla bilgi için bkz [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*prgLongVals*<br/>
Uzun tamsayı dizisi için bir işaretçi. Bu dizi için kayıt veri kaynağından aktarılacak veri depolar.

*prgLengths*<br/>
Uzun tamsayı dizisi için bir işaretçi. Bu dizi işaret ettiği dizideki her bir değerin bayt cinsinden uzunluğu depolayacak *prgLongVals*. Karşılık gelen veri öğesi Null bir değer içeriyorsa, ' % s'değeri SQL_NULL_DATA depolanır unutmayın. Daha fazla ayrıntı için bkz: ODBC API işlevini `SQLBindCol` içinde *ODBC SDK Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütunu SQL_INTEGER bir ODBC türünde olması gerekir. Kayıt kümesi işaretçi türüne bir alan veri üyesi tanımlamalıdır **uzun**.

Başlatın, *prgLongVals* ve *prgLengths* null, ardından bunların işaret dizileri otomatik olarak satır kümesi boyutuna eşit boyutları ile ayrılır.

> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından recordset nesnesine aktarır. Kümenizin güncelleştirilebilir yapmak için ODBC API işlevini kullanmalısınız `SQLSetPos`.

Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz: [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_single_bulk"></a>  RFX_Single_Bulk

ODBC veri kaynağında bir sütundan karşılık gelen bir dizi içinde birden çok satır kayan nokta veri aktarır bir `CRecordset`-türetilmiş bir nesneye.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Single_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   float** prgFltVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesne. Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. Daha fazla bilgi için bkz [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*prgFltVals*<br/>
Bir dizi işaretçi **float** değerleri. Bu dizi için kayıt veri kaynağından aktarılacak veri depolar.

*prgLengths*<br/>
Uzun tamsayı dizisi için bir işaretçi. Bu dizi işaret ettiği dizideki her bir değerin bayt cinsinden uzunluğu depolayacak *prgFltVals*. Karşılık gelen veri öğesi Null bir değer içeriyorsa, ' % s'değeri SQL_NULL_DATA depolanır unutmayın. Daha fazla ayrıntı için bkz: ODBC API işlevini `SQLBindCol` içinde *ODBC SDK Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütunu SQL_REAL bir ODBC türünde olması gerekir. Kayıt kümesi işaretçi türüne bir alan veri üyesi tanımlamalıdır **float**.

Başlatın, *prgFltVals* ve *prgLengths* null, ardından bunların işaret dizileri otomatik olarak satır kümesi boyutuna eşit boyutları ile ayrılır.

> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından recordset nesnesine aktarır. Kümenizin güncelleştirilebilir yapmak için ODBC API işlevini kullanmalısınız `SQLSetPos`.

Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Bkz: [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

## <a name="rfx_text_bulk"></a>  RFX_Text_Bulk

Karakter verilerinin birden çok satır karşılık gelen bir dizide bir ODBC veri kaynağını sütundan aktarır bir `CRecordset`-türetilmiş bir nesneye.

### <a name="syntax"></a>Sözdizimi

```
void RFX_Text_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   LPSTR* prgStrVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesne. Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir. Daha fazla bilgi için bkz [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Bir veri sütununun adı.

*prgStrVals*<br/>
Bir dizi LPSTR değere bir işaretçi. Bu dizi için kayıt veri kaynağından aktarılacak veri depolar. ODBC geçerli sürümü ile bu değerleri Unicode olamayacağını unutmayın.

*prgLengths*<br/>
Uzun tamsayı dizisi için bir işaretçi. Bu dizi işaret ettiği dizideki her bir değerin bayt cinsinden uzunluğu depolayacak *prgStrVals*. Bu süre sonlandırma boş karakteri içermez. Karşılık gelen veri öğesi Null bir değer içeriyorsa, ' % s'değeri SQL_NULL_DATA depolanır unutmayın. Daha fazla ayrıntı için bkz: ODBC API işlevini `SQLBindCol` içinde *ODBC SDK Programcının Başvurusu*.

*nMaxLength*<br/>
İzin verilen maksimum uzunluğu işaret ettiği dizisinde depolanan değerlerin *prgStrVals*, sonlandırma boş karakteri dahil. Veri yok kesilecek emin olmak için büyük veri öğesi beklediğiniz tutabilecek kadar büyük bir değer geçirin.

### <a name="remarks"></a>Açıklamalar

Veri kaynak sütunu SQL_LONGVARCHAR, SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL veya SQL_NUMERIC bir ODBC türlerine sahip olabilir. Kayıt türünün LPSTR alan veri üyesi tanımlamanız gerekir.

Başlatın, *prgStrVals* ve *prgLengths* null, ardından bunların işaret dizileri otomatik olarak satır kümesi boyutuna eşit boyutları ile ayrılır.

> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından recordset nesnesine aktarır. Kümenizin güncelleştirilebilir yapmak için ODBC API işlevini kullanmalısınız `SQLSetPos`.

Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Örnek

Çağrıları el ile yazmanız gereken, `DoBulkFieldExchange` geçersiz kılar. Bu örnek, bir çağrı gösterir `RFX_Text_Bulk`, çağrı yanı sıra `RFX_Long_Bulk`, veri aktarımı için. Bu çağrılar için yapılan bir çağrı tarafından öncelenen [CFieldExchange::SetFieldType](CFieldExchange::SetFieldType.md). Parametreler için Toplu RFX işlevlerini yerine RFX işlevleri çağırmalıdır unutmayın.

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

**Başlık:** afxdb.h

## <a name="dfx_binary"></a>  DFX_Binary

Alan veri üyeleri arasında bayt dizilerini aktaran bir [CDaoRecordset](cdaorecordset-class.md) nesnesi ve veri kaynağındaki bir kaydın sütun.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI DFX_Binary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CByteArray& value,
   int nPreAllocSize = AFX_DAO_BINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir.

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için [CByteArray](cbytearray-class.md), belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

*nPreAllocSize*<br/>
Bu bellek miktarını framework preallocates. Verilerinizi daha büyükse framework ayrılmış gerektiğinde daha fazla alanı olur. Daha iyi performans için bu boyut yapıcıların önlemek için büyük bir değere ayarlayın. Varsayılan boyut AFXDAO içinde tanımlanır. H dosyası AFX_DAO_BINARY_DEFAULT_SIZE olarak.

*dwBindOptions*<br/>
Bir seçenek, değiştirilmiş kayıt alanları saptamak için MFC'nin çift arabelleğe alma mekanizması avantajlarından yararlanmanıza imkan sağlar. Varsayılan olarak, AFX_DAO_DISABLE_FIELD_CACHE, iki kez arabelleğe alma kullanmaz ve çağırmalısınız [SetFieldDirty](cdaorecordset-class.md#setfielddirty) ve [SetFieldNull](cdaorecordset-class.md#setfieldnull) kendiniz. Diğer olası değerini AFX_DAO_ENABLE_FIELD_CACHE, iki kez arabelleğe alma kullanır ve alanlar işaretlemek için ek iş yapması gerekmez kirli veya Null. İkili veri miktarının daha az olmadığı sürece bu değeri performans ve bellek nedenleriyle kaçının.

> [!NOTE]
>  Tüm alanlar için varsayılan olarak ayarlayarak arabelleğe alınan verileri çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Açıklamalar

Veri türü ve tür DAO_BYTES DAO içinde arasında eşlenen [CByteArray](cbytearray-class.md) kümesinde.

### <a name="example"></a>Örnek

Bkz: [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="dfx_bool"></a>  DFX_Bool

Alan veri üyeleri arasında Boole veri aktaran bir [CDaoRecordset](cdaorecordset-class.md) nesnesi ve veri kaynağındaki bir kaydın sütun.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI DFX_Bool(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BOOL& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir.

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir aktarımı için kayıt kümesi veri kaynağına, BOOL, türü değeri, belirtilen veri üyesi alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

*dwBindOptions*<br/>
Bir seçenek, değiştirilmiş kayıt alanları saptamak için MFC'nin çift arabelleğe alma mekanizması avantajlarından yararlanmanıza imkan sağlar. Varsayılan olarak, AFX_DAO_ENABLE_FIELD_CACHE, iki kez arabelleğe alma kullanır. Başka bir olası değer AFX_DAO_DISABLE_FIELD_CACHE değeridir. Bu değeri belirtirseniz, bu alana hiçbir denetim MFC yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.

> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verileri çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Açıklamalar

Veri türü DAO içinde DAO_BOOL kümesinde BOOL türü arasındaki eşlenir.

### <a name="example"></a>Örnek

Bkz: [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="dfx_byte"></a>  DFX_Byte

Bayt alan veri üyeleri arasındaki aktarımları tek bir [CDaoRecordset](cdaorecordset-class.md) nesnesi ve veri kaynağındaki bir kaydın sütun.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI DFX_Byte(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BYTE& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir.

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir aktarımı için kayıt kümesi veri kaynağına, belirtilen veri üyesi tür bayt değeri alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

*dwBindOptions*<br/>
Bir seçenek, değiştirilmiş kayıt alanları saptamak için MFC'nin çift arabelleğe alma mekanizması avantajlarından yararlanmanıza imkan sağlar. Varsayılan olarak, AFX_DAO_ENABLE_FIELD_CACHE, iki kez arabelleğe alma kullanır. Başka bir olası değer AFX_DAO_DISABLE_FIELD_CACHE değeridir. Bu değeri belirtirseniz, bu alana hiçbir denetim MFC yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.

> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verileri çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Açıklamalar

Veri türü DAO_BYTES DAO içinde tür bayt kümesinde arasındaki eşlenir.

### <a name="example"></a>Örnek

Bkz: [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="dfx_currency"></a>  DFX_Currency

Para birimi veri alan veri üyeleri aktarımları bir [CDaoRecordset](cdaorecordset-class.md) nesnesi ve veri kaynağındaki bir kaydın sütun.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI DFX_Currency(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleCurrency& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir.

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir aktarımı için kayıt kümesi veri kaynağına, bu değer türü belirtilen veri üyeden alınır [COleCurrency](colecurrency-class.md). Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

*dwBindOptions*<br/>
Bir seçenek, değiştirilmiş kayıt alanları saptamak için MFC'nin çift arabelleğe alma mekanizması avantajlarından yararlanmanıza imkan sağlar. Varsayılan olarak, AFX_DAO_ENABLE_FIELD_CACHE, iki kez arabelleğe alma kullanır. Başka bir olası değer AFX_DAO_DISABLE_FIELD_CACHE değeridir. Bu değeri belirtirseniz, bu alana hiçbir denetim MFC yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.

> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verileri çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Açıklamalar

Veri türü ve tür DAO_CURRENCY DAO içinde arasında eşlenen [COleCurrency](colecurrency-class.md) kümesinde.

### <a name="example"></a>Örnek

Bkz: [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="dfx_datetime"></a>  DFX_DateTime

Alan veri üyeleri arasında saat ve tarih veri aktaran bir [CDaoRecordset](cdaorecordset-class.md) nesnesi ve veri kaynağındaki bir kaydın sütun.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI DFX_DateTime(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleDateTime& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir.

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. İşlevi bir başvuru alır bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesne. Bir aktarımı için kayıt kümesi veri kaynağına, bu değer, belirtilen veri üyesi alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

*dwBindOptions*<br/>
Bir seçenek, değiştirilmiş kayıt alanları saptamak için MFC'nin çift arabelleğe alma mekanizması avantajlarından yararlanmanıza imkan sağlar. Varsayılan olarak, AFX_DAO_ENABLE_FIELD_CACHE, iki kez arabelleğe alma kullanır. Başka bir olası değer AFX_DAO_DISABLE_FIELD_CACHE değeridir. Bu değeri belirtirseniz, bu alana hiçbir denetim MFC yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.

> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verileri çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Açıklamalar

Veri türü ve tür DAO_DATE DAO içinde arasında eşlenen [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) kümesinde.

> [!NOTE]
>  `COleDateTime` değiştirir [CTime](../../atl-mfc-shared/reference/ctime-class.md) ve DAO sınıfları bu amaçla TIMESTAMP_STRUCT. `CTime` ve TIMESTAMP_STRUCT ODBC tabanlı veri erişim sınıfları için kullanılır.

### <a name="example"></a>Örnek

Bkz: [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="dfx_double"></a>  DFX_Double

Aktarımları **double float** veri alan veri üyeleri arasında bir [CDaoRecordset](cdaorecordset-class.md) nesnesi ve veri kaynağındaki bir kaydın sütun.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI DFX_Double(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   double& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir.

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için **çift**, belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

*dwBindOptions*<br/>
Bir seçenek, değiştirilmiş kayıt alanları saptamak için MFC'nin çift arabelleğe alma mekanizması avantajlarından yararlanmanıza imkan sağlar. Varsayılan olarak, AFX_DAO_ENABLE_FIELD_CACHE, iki kez arabelleğe alma kullanır. Başka bir olası değer AFX_DAO_DISABLE_FIELD_CACHE değeridir. Bu değeri belirtirseniz, bu alana hiçbir denetim MFC yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.

> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verileri çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Açıklamalar

Veri türü ve DAO DAO_R8 türünde arasında eşlenen **double float** kümesinde.

### <a name="example"></a>Örnek

Bkz: [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="dfx_long"></a>  DFX_Long

Alan veri üyeleri arasında uzun tamsayı veri aktaran bir [CDaoRecordset](cdaorecordset-class.md) nesnesi ve veri kaynağındaki bir kaydın sütun.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI DFX_Long(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   long& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir.

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için **uzun**, belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

*dwBindOptions*<br/>
Bir seçenek, değiştirilmiş kayıt alanları saptamak için MFC'nin çift arabelleğe alma mekanizması avantajlarından yararlanmanıza imkan sağlar. Varsayılan olarak, AFX_DAO_ENABLE_FIELD_CACHE, iki kez arabelleğe alma kullanır. Başka bir olası değer AFX_DAO_DISABLE_FIELD_CACHE değeridir. Bu değeri belirtirseniz, bu alana hiçbir denetim MFC yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.

> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verileri çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Açıklamalar

Veri türü ve DAO DAO_I4 türünde arasında eşlenen **uzun** kümesinde.

### <a name="example"></a>Örnek

Bkz: [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="dfx_longbinary"></a>  DFX_LongBinary

**Önemli** kullanmanız önerilir [DFX_Binary](#dfx_binary) bu işlevi yerine.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI DFX_LongBinary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CLongBinary& value,
   DWORD dwPreAllocSize = AFX_DAO_LONGBINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir.

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için [CLongBinary](clongbinary-class.md), belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

*dwPreAllocSize*<br/>
Bu bellek miktarını framework preallocates. Verilerinizi daha büyükse framework ayrılmış gerektiğinde daha fazla alanı olur. Daha iyi performans için bu boyut yapıcıların önlemek için büyük bir değere ayarlayın.

*dwBindOptions*<br/>
Bir seçenek, değiştirilmiş kayıt alanları saptamak için MFC'nin çift arabelleğe alma mekanizması avantajlarından yararlanmanıza imkan sağlar. Varsayılan olarak, AFX_DISABLE_FIELD_CACHE, iki kez arabelleğe alma kullanmaz. Başka bir olası değer AFX_DAO_ENABLE_FIELD_CACHE değeridir. Kullanan iki kez arabelleğe alma ve sahip alanları işaretlemek için ek iş yapması kirli veya Null. İkili veri miktarının daha az olmadığı sürece bu değeri performans ve bellek nedenleriyle kaçının.

> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verileri çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Açıklamalar

`DFX_LongBinary` MFC ODBC sınıfları ile uyumluluk için sağlanır. `DFX_LongBinary` İşlevi sınıfını kullanarak ikili büyük nesne (BLOB) veri aktarımı `CLongBinary` alan veri üyeleri arasında bir [CDaoRecordset](cdaorecordset-class.md) nesnesi ve veri kaynağındaki bir kaydın sütun. Veri türü ve tür DAO_BYTES DAO içinde arasında eşlenen [CLongBinary](clongbinary-class.md) kümesinde.

### <a name="example"></a>Örnek

Bkz: [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="dfx_short"></a>  DFX_Short

Alan veri üyeleri arasında tamsayı veri aktarımları kısa bir [CDaoRecordset](cdaorecordset-class.md) nesnesi ve veri kaynağındaki bir kaydın sütun.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI DFX_Short(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   short& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir.

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için **kısa**, belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

*dwBindOptions*<br/>
Bir seçenek, değiştirilmiş kayıt alanları saptamak için MFC'nin çift arabelleğe alma mekanizması avantajlarından yararlanmanıza imkan sağlar. Varsayılan olarak, AFX_DAO_ENABLE_FIELD_CACHE, iki kez arabelleğe alma kullanır. Başka bir olası değer AFX_DAO_DISABLE_FIELD_CACHE değeridir. Bu değeri belirtirseniz, bu alana hiçbir denetim MFC yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.

> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verileri çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Açıklamalar

Veri türü ve DAO DAO_I2 türünde arasında eşlenen **kısa** kümesinde.

> [!NOTE]
>  `DFX_Short` eşdeğerdir [rfx_ınt](#rfx_int) ODBC tabanlı sınıflar için.

### <a name="example"></a>Örnek

Bkz: [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="dfx_single"></a>  DFX_Single

Kayan nokta veri alan veri üyeleri aktarımları bir [CDaoRecordset](cdaorecordset-class.md) nesnesi ve veri kaynağındaki bir kaydın sütun.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI DFX_Single(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   float& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir.

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için **float**, belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

*dwBindOptions*<br/>
Bir seçenek, değiştirilmiş kayıt alanları saptamak için MFC'nin çift arabelleğe alma mekanizması avantajlarından yararlanmanıza imkan sağlar. Varsayılan olarak, AFX_DAO_ENABLE_FIELD_CACHE, iki kez arabelleğe alma kullanır. Başka bir olası değer AFX_DAO_DISABLE_FIELD_CACHE değeridir. Bu değeri belirtirseniz, bu alana hiçbir denetim MFC yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.

> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verileri çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Açıklamalar

Veri türü ve DAO DAO_R4 türünde arasında eşlenen **float** kümesinde.

### <a name="example"></a>Örnek

Bkz: [DFX_Text](#dfx_text).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="dfx_text"></a>  DFX_Text

Aktarımları `CString` veri alan veri üyeleri arasında bir [CDaoRecordset](cdaorecordset-class.md) nesnesi ve veri kaynağındaki bir kaydın sütun.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI DFX_Text(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CString& value,
   int nPreAllocSize = AFX_DAO_TEXT_DEFAULT_SIZE,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne, işlevin her bir çağrı bağlamının tanımlamak için bilgi içerir.

*szName*<br/>
Bir veri sütununun adı.

*value*<br/>
Belirtilen veri üyesi içinde depolanan değeri — transfer edilecek değer. Bir kayıt kümesi aktarımı, veri kaynağına türünün değeri için [CString](../../atl-mfc-shared/reference/cstringt-class.md), belirtilen veri üyesinden alınır. Bir aktarım için veri kaynağı kayıt kümesine, belirtilen veri üye değeri depolanır.

*nPreAllocSize*<br/>
Bu bellek miktarını framework preallocates. Verilerinizi daha büyükse framework ayrılmış gerektiğinde daha fazla alanı olur. Daha iyi performans için bu boyut yapıcıların önlemek için büyük bir değere ayarlayın.

*dwBindOptions*<br/>
Bir seçenek, değiştirilmiş kayıt alanları saptamak için MFC'nin çift arabelleğe alma mekanizması avantajlarından yararlanmanıza imkan sağlar. Varsayılan olarak, AFX_DAO_ENABLE_FIELD_CACHE, iki kez arabelleğe alma kullanır. Başka bir olası değer AFX_DAO_DISABLE_FIELD_CACHE değeridir. Bu değeri belirtirseniz, bu alana hiçbir denetim MFC yapar. Çağırmalısınız [SetFieldDirty](cdaorecordset-class.md#setfielddirty) ve [SetFieldNull](cdaorecordset-class.md#setfieldnull) kendiniz.

> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verileri çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Açıklamalar

Veri türü DAO içinde DAO_CHAR arasında eşlenir (veya _UNICODE tanımlanmış olması durumunda, DAO_WCHAR) ve türü [CString](../../atl-mfc-shared/reference/cstringt-class.md) kümesinde.  n

### <a name="example"></a>Örnek

Bu örnek, çeşitli çağrıları gösterir `DFX_Text`. Ayrıca iki çağrıları fark [CDaoFieldExchange::SetFieldType](cdaofieldexchange-class.md#setfieldtype). İlk çağrıda yazmanız gereken `SetFieldType` ve kendi **DFX** çağırın. İkinci çağrı ve onun ilişkili **DFX** çağrıları kod Sihirbazı tarafından oluşturulan sınıf normal olarak yazılır.

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

**Başlık:** afxdao.h

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](mfc-macros-and-globals.md)<br/>
[CRecordset::DoFieldExchange](crecordset-class.md#dofieldexchange)<br/>
[CRecordset::DoBulkFieldExchange](crecordset-class.md#dobulkfieldexchange)<br/>
[CDaoRecordset::DoFieldExchange](cdaorecordset-class.md#dofieldexchange)

