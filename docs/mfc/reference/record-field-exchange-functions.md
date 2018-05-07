---
title: Kayıt alanı değişim işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 564d797a30e4b2d8518c73c5f7589aae205b6907
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="record-field-exchange-functions"></a>Kayıt Alanı Değişim İşlevleri
Bu konu kayıt alanı değişimi (RFX, toplu RFX ve DFX) listeler bir kayıt kümesi nesnesi ve veri kaynağı arasındaki veri aktarımını otomatikleştirmek ve veriler üzerinde başka işlemler gerçekleştirmek için kullanılan işlevleri.  
  
 ODBC tabanlı sınıflar kullanıyorsanız ve toplu satır getirme uyguladıysanız, el ile geçersiz kılmanız gerekir `DoBulkFieldExchange` üye işlevini `CRecordset` bir veri kaynağı sütununa karşılık gelen her veri üyesi için Toplu RFX işlevleri çağırarak.  
  
 Toplu satır ODBC tabanlı sınıflarda getirme uygulanmadı ya da DAO tabanlı sınıflar kullanıyorsanız, ardından ClassWizard geçersiz kılar `DoFieldExchange` üye işlevini `CRecordset` veya `CDaoRecordset` RFX işlevleri (ODBC sınıfları için çağırarak ) veya kümenizde her alan veri üyesi için DFX işlevleri (için DAO sınıfları).  
  
 Kayıt alanı değişim işlevleri framework çağırması her zaman veri aktarımı `DoFieldExchange` veya `DoBulkFieldExchange`. Her işlev belirli bir veri türüne aktarır.  
  
 Bu işlevlerin nasıl kullanıldığı konusunda daha fazla bilgi için makalelerine bakın [kayıt alanı değişimi: nasıl RFX çalışır (ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md). Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Dinamik olarak bağlama verileri sütunlar için ayrıca RFX ya da DFX işlevleri kendiniz makalelerinde açıklandığı gibi çağırabilirsiniz [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). Ayrıca, Teknik Not açıklandığı gibi kendi özel RFX ya da DFX yordamları yazabilirsiniz [43](../../mfc/tn043-rfx-routines.md) (ODBC için) ve Teknik Not [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (için DAO).  
  
 RFX ve toplu RFX örneği için işlev içinde göründükleri gibi `DoFieldExchange` ve `DoBulkFieldExchange` İşlevler, bkz: [RFX_Text](#rfx_text) ve [RFX_Text_Bulk] #rfx_text_bulk). DFX işlevleri RFX işlevleri çok benzer.  
  
### <a name="rfx-functions-odbc"></a>RFX işlevleri (ODBC)  
  
|||  
|-|-|  
|[RFX_Binary](#rfx_binary)|Tür bayt dizileri aktarır [CLongBinary](cbytearray-class.md).|  
|[RFX_Bool](#rfx_bool)|Boole veri aktarır.|  
|[RFX_Byte](#rfx_byte)|Tek bir bayt veri aktarır.|  
|[RFX_Date](#rfx_date)|Saat ve tarih veri kullanarak aktarır [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya **TIMESTAMP_STRUCT**.|  
|[RFX_Double](#rfx_double)|Çift duyarlıklı kayan veri aktarır.|  
|[Rfx_ınt](#rfx_int)|Tamsayı veri aktarır.|  
|[RFX_Long](#rfx_long)|Tamsayı veri aktarımları uzun.|  
|[RFX_LongBinary](#rfx_longbinary)|Bir nesne ile ikili büyük nesne (BLOB) veri aktarımı [CLongBinary](clongbinary-class.md) sınıfı.|  
|[RFX_Single](#rfx_single)|Veri aktarımları kaydırın.|  
|[RFX_Text](#rfx_text)|Veri aktarımları dize.|  
  
### <a name="bulk-rfx-functions-odbc"></a>Toplu RFX işlevleri (ODBC)  
  
|||  
|-|-|  
|[RFX_Binary_Bulk](#rfx_binary_bulk)|Bayt veri dizileri aktarır.|  
|[RFX_Bool_Bulk](#rfx_bool_bulk)|Boole veri dizileri aktarır.|  
|[RFX_Byte_Bulk](#rfx_byte_bulk)|Tek Bayt dizileri aktarır.|  
|[RFX_Date_Bulk](#rfx_date_bulk)|Veri türü dizileri aktarır **TIMESTAMP_STRUCT**.|  
|[RFX_Double_Bulk](#rfx_double_bulk)|Çift duyarlıklı kayan nokta verisi dizileri aktarır.|  
|[Rfx_ınt_bulk](#rfx_int_bulk)|Tamsayı veri dizileri aktarır.|  
|[RFX_Long_Bulk](#rfx_long_bulk)|Diziler uzun tamsayı veri aktarır.|  
|[RFX_Single_Bulk](#rfx_single_bulk)|Kayan nokta veri dizileri aktarır.|  
|[RFX_Text_Bulk](#rfx_text_bulk)|Veri türü dizileri aktarır **LPSTR**.|  
  
### <a name="dfx-functions-dao"></a>DFX işlevleri (DAO)  
  
|||
|-|-|  
|[DFX_Binary](#dfx_binary)|Tür bayt dizileri aktarır [CLongBinary](cbytearray-class.md).|  
|[DFX_Bool](#dfx_bool)|Boole veri aktarır.|  
|[DFX_Byte](#dfx_byte)|Tek bir bayt veri aktarır.|  
|[DFX_Currency](#dfx_currency)|Para birimi veri türünde aktarır [COleCurrency](colecurrency-class.md).|  
|[DFX_DateTime](#dfx_datetime)|Saat ve tarih veri türü aktarır [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md).|  
|[DFX_Double](#dfx_double)|Çift duyarlıklı kayan veri aktarır.|  
|[DFX_Long](#dfx_long)|Tamsayı veri aktarımları uzun.|  
|[DFX_LongBinary](#dfx_longbinary)|Bir nesne ile ikili büyük nesne (BLOB) veri aktarımı `CLongBinary` sınıfı. DAO için kullanmanız önerilir [DFX_Binary](#dfx_binary) yerine.|  
|[DFX_Short](#dfx_short)|Tamsayı veri aktarımları kısa.|  
|[DFX_Single](#dfx_single)|Veri aktarımları kaydırın.|  
|[DFX_Text](#dfx_text)|Veri aktarımları dize.|  

 =============================================

## <a name="rfx_binary"></a>  RFX_Binary
Bayt dizileri alan veri üyeleri arasında aktarır bir `CRecordset` nesne ve ODBC türü veri kaynağında bir kayıt sütunlarının **uzun SQL_BINARY**, **SQL_VARBINARY**, veya **SQL_ LONGVARBINARY**.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Binary(  
   CFieldExchange* pFX,  
   const char* szName,  
   CByteArray& value,  
   int nMaxLength = 255);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye bakın [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı [CLongBinary](cbytearray-class.md), belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 `nMaxLength`  
 Dize veya dizinin aktarılan uzunluğu izin verilen en fazla. Varsayılan değer olan `nMaxLength` 255'tir. Geçerli değerler 1 `INT_MAX`. Bu alan miktarını framework verileri ayırır. En iyi performans için beklediğiniz en büyük veri öğesi uyabilecek kadar büyük bir değer geçirin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tür veri kaynağındaki türü gelen ve giden eşlendiği `CByteArray` kümesinde.  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

## <a name="rfx_bool"></a>  RFX_Bool
Alan veri üyeleri arasında Boole veri aktaran bir `CRecordset` nesne ve ODBC türü veri kaynağında bir kayıt sütunlarının **SQL_BIT**.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Bool(  
   CFieldExchange* pFX,  
   const char* szName,  
   BOOL& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye bakın [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı **BOOL**, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

## <a name="rfx_byte"></a>  RFX_Byte
Aktarımları tek bayt alan veri üyeleri arasında bir `CRecordset` nesne ve ODBC türü veri kaynağında bir kayıt sütunlarının **SQL_TINYINT**.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Byte(  
   CFieldExchange* pFX,  
   const char* szName,  
   BYTE& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye bakın [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı **bayt**, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

## <a name="rfx_date"></a>  RFX_Date
Aktarımları `CTime` veya **TIMESTAMP_STRUCT** alan veri üyeleri arasında veri bir `CRecordset` nesne ve ODBC türü veri kaynağında bir kayıt sütunlarının **SQL_DATE**, **SQL_TIME**, veya **SQL_TIMESTAMP**.  
  
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
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye bakın [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri; Transfer edilecek değer. Çeşitli sürümleri işlevi farklı veri türleri için değer alın:  
  
 İşlev'in ilk sürüm bir başvuru alır bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesi. Bir aktarımı için kayıt kümesi veri kaynağına, bu değeri belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 İşlevin ikinci sürüm bir başvuru alır bir **TIMESTAMP_STRUCT** yapısı. Bu yapı kendiniz çağrısından önce ayarlamanız gerekir. Hiçbiri iletişim kutusu veri değişimi (DDX) desteği veya kod Sihirbazı desteği bu sürümü için kullanılabilir değil. İşlevin üçüncü sürüm çalıştığını benzer şekilde ilk sürüm için bir başvuru alır dışında bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CTime` İşlevi sürümü bazı Ara işleme yükü getirir ve biraz kısıtlıdır aralığındadır. Ya da çok sınırlama faktörlerin bulursanız, işlevi ikinci sürümünü kullanın. Ancak, kod Sihirbazı'nı ve DDX destek yapınızı kendiniz oluşturmanız gereksinim eksikliği unutmayın.  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

## <a name="rfx_double"></a>  RFX_Double
Aktarımları **double float** alan veri üyeleri arasında veri bir `CRecordset` nesne ve ODBC türü veri kaynağında bir kayıt sütunlarının **SQL_DOUBLE**.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Double(  
   CFieldExchange* pFX,  
   const char* szName,  
   double& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye bakın [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı **çift**, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

## <a name="rfx_int"></a>  Rfx_ınt
Alan veri üyeleri arasında tamsayı veri aktaran bir `CRecordset` nesne ve ODBC türü veri kaynağında bir kayıt sütunlarının **SQL_SMALLINT**.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Int(  
   CFieldExchange* pFX,  
   const char* szName,  
   int& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye bakın [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı `int`, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

## <a name="rfx_long"></a>  RFX_Long
Alan veri üyeleri arasında uzun tamsayı veri aktaran bir `CRecordset` nesne ve ODBC türü veri kaynağında bir kayıt sütunlarının **SQL_INTEGER**.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Long(  
   CFieldExchange* pFX,  
   const char* szName,  
   LONG&   
value );  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye bakın [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı **uzun**, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  
  
## <a name="rfx_longbinary"></a>  RFX_LongBinary
Sınıfını kullanarak ikili büyük nesne (BLOB) veri aktarımları [CLongBinary](clongbinary-class.md) alan veri üyeleri arasında bir `CRecordset` nesne ve ODBC türü veri kaynağında bir kayıt sütunlarının **SQL_LONGVARBINARY**veya **SQL_LONGVARCHAR**.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_LongBinary(  
   CFieldExchange* pFX,  
   const char* szName,  
   CLongBinary& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye bakın [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı `CLongBinary`, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

## <a name="rfx_single"></a>  RFX_Single
Alan veri üyeleri arasında kayan nokta veri aktaran bir `CRecordset` nesne ve ODBC türü veri kaynağında bir kayıt sütunlarının **SQL_REAL**.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Single(  
   CFieldExchange* pFX,  
   const char* szName,  
   float& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye bakın [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı **float**, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  
  

## <a name="rfx_text"></a>  RFX_Text
Aktarımları `CString` alan veri üyeleri arasında veri bir `CRecordset` nesne ve ODBC türü veri kaynağında bir kayıt sütunlarının **SQL_LONGVARCHAR**, **SQL_CHAR**, **SQL_ VARCHAR**, **SQL_DECIMAL**, veya **SQL_NUMERIC**.  
  
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
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi `CFieldExchange`. Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye bakın [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı `CString`, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 `nMaxLength`  
 Dize veya dizinin aktarılan uzunluğu izin verilen en fazla. Varsayılan değer olan `nMaxLength` 255'tir. Geçerli değerler 1 `INT_MAX`). Bu alan miktarını framework verileri ayırır. En iyi performans için beklediğiniz en büyük veri öğesi uyabilecek kadar büyük bir değer geçirin.  
  
 *nColumnType*  
 Çoğunlukla parametreleri için kullanılır. Parametrenin veri türünü belirten bir tamsayı. Bir ODBC veri türü formun türüdür **SQL_XXX**.  
  
 `nScale`  
 ODBC türü değerleri için ölçek belirtir **SQL_DECIMAL** veya **SQL_NUMERIC**. `nScale` yalnızca parametre değerleri ayarlanıyor durumlarda faydalıdır. Daha fazla bilgi için "Duyarlık, Ölçek, uzunluğu ve görüntüleme boyutu" Ek D içinde konusuna *ODBC SDK Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu türdeki tüm veri kaynağındaki ve ondan eşlendiği `CString` kümesinde.  
  
### <a name="example"></a>Örnek  
 Bu örnek, çeşitli çağrıları gösterir `RFX_Text`. Ayrıca iki çağrıları fark `CFieldExchange::SetFieldType`. Parametrelerini çağrısı yazmalısınız `SetFieldType` ve kendi RFX çağrısı. Çıkış sütunu çağrısı ve onun ilişkili RFX çağrıları normalde bir kod Sihirbazı tarafından yazılır.  
  
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
ODBC veri kaynağını sütundan karşılık gelen bir dizideki birden çok sayıda bayt veri aktarır bir `CRecordset`-türetilmiş bir nesne içermelidir.  
  
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
 `pFX`  
 Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesnesi. Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. Daha fazla bilgi için bkz: [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 `prgByteVals`  
 Bir dizi için bir işaretçi **bayt** değerleri. Bu dizi kayıt kümesine veri kaynağından aktarılacak veri depolar.  
  
 `prgLengths`  
 Uzun dizisi için bir işaretçi. Bu dizi gösterdiği dizisindeki her bir değerin bayt cinsinden uzunluğu depolayacak `prgByteVals`. Unutmayın değeri **SQL_NULL_DATA** karşılık gelen veri öğesi bir Null değer içeriyorsa depolanır. Daha fazla ayrıntı için bkz: ODBC API işlevi **SQLBindCol** içinde *ODBC SDK Programcının Başvurusu*.  
  
 `nMaxLength`  
 İzin verilen en fazla uzunluğu gösterdiği dizisinde depolanan değerlerin `prgByteVals`. Veri değil kesilecek emin olmak için beklediğiniz en büyük veri öğesi uyabilecek kadar büyük bir değer geçirin.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri kaynağı sütun bir ODBC türünde olabilir **uzun SQL_BINARY**, **SQL_VARBINARY**, veya **SQL_LONGVARBINARY**. Kayıt kümesi türü işaretçisi bir alan veri üyesi tanımlamalısınız **bayt**.  
  
 Başlatır, `prgByteVals` ve `prgLengths` için **NULL**, sonra da işaret edecek şekilde diziler satır kümesi boyutuna eşit boyutlarıyla otomatik olarak ayrılır.  
  
> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından kayıt kümesi nesnesine aktarır. Kümenizin güncelleştirilebilir duruma getirmek için ODBC API işlevini kullanmak **SQLSetPos**.  
  
 Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

## <a name="rfx_bool_bulk"></a>  RFX_Bool_Bulk
Boole veri birden çok satır karşılık gelen bir dizide bir ODBC veri kaynağını sütundan aktarır bir `CRecordset`-türetilmiş bir nesne içermelidir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Bool_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   BOOL** prgBoolVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesnesi. Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. Daha fazla bilgi için bkz: [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 `prgBoolVals`  
 Bir dizi için bir işaretçi **BOOL** değerleri. Bu dizi kayıt kümesine veri kaynağından aktarılacak veri depolar.  
  
 `prgLengths`  
 Uzun dizisi için bir işaretçi. Bu dizi gösterdiği dizisindeki her bir değerin bayt cinsinden uzunluğu depolayacak `prgBoolVals`. Unutmayın değeri **SQL_NULL_DATA** karşılık gelen veri öğesi bir Null değer içeriyorsa depolanır. Daha fazla ayrıntı için bkz: ODBC API işlevi **SQLBindCol** içinde *ODBC SDK Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri kaynağı sütun bir ODBC türünde olmalıdır **SQL_BIT**. Kayıt kümesi türü işaretçisi bir alan veri üyesi tanımlamalısınız **BOOL**.  
  
 Başlatır, `prgBoolVals` ve `prgLengths` için **NULL**, sonra da işaret edecek şekilde diziler satır kümesi boyutuna eşit boyutlarıyla otomatik olarak ayrılır.  
  
> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından kayıt kümesi nesnesine aktarır. Kümenizin güncelleştirilebilir duruma getirmek için ODBC API işlevini kullanmak **SQLSetPos**.  
  
 Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

## <a name="rfx_byte_bulk"></a>  RFX_Byte_Bulk
ODBC veri kaynağını sütundan tek bayt birden çok satır karşılık gelen bir dizide aktarır bir `CRecordset`-türetilmiş bir nesne içermelidir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Byte_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   BYTE** prgByteVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesnesi. Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. Daha fazla bilgi için bkz: [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 `prgByteVals`  
 Bir dizi için bir işaretçi **bayt** değerleri. Bu dizi kayıt kümesine veri kaynağından aktarılacak veri depolar.  
  
 `prgLengths`  
 Uzun dizisi için bir işaretçi. Bu dizi gösterdiği dizisindeki her bir değerin bayt cinsinden uzunluğu depolayacak `prgByteVals`. Unutmayın değeri **SQL_NULL_DATA** karşılık gelen veri öğesi bir Null değer içeriyorsa depolanır. Daha fazla ayrıntı için bkz: ODBC API işlevi **SQLBindCol** içinde *ODBC SDK Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri kaynağı sütun bir ODBC türünde olmalıdır **SQL_TINYINT**. Kayıt kümesi türü işaretçisi bir alan veri üyesi tanımlamalısınız **bayt**.  
  
 Başlatır, `prgByteVals` ve `prgLengths` için **NULL**, sonra da işaret edecek şekilde diziler satır kümesi boyutuna eşit boyutlarıyla otomatik olarak ayrılır.  
  
> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından kayıt kümesi nesnesine aktarır. Kümenizin güncelleştirilebilir duruma getirmek için ODBC API işlevini kullanmak **SQLSetPos**.  
  
 Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  
  
## <a name="rfx_date_bulk"></a>  RFX_Date_Bulk
Birden çok satır aktarır **TIMESTAMP_STRUCT** karşılık gelen bir dizide bir ODBC veri kaynağını bir sütundan verileri bir `CRecordset`-türetilmiş bir nesne içermelidir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Date_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   TIMESTAMP_STRUCT** prgTSVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesnesi. Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. Daha fazla bilgi için bkz: [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 `prgTSVals`  
 Bir dizi için bir işaretçi **TIMESTAMP_STRUCT** değerleri. Bu dizi kayıt kümesine veri kaynağından aktarılacak veri depolar. Hakkında daha fazla bilgi için **TIMESTAMP_STRUCT** veri türü, ek D içinde "C veri türleri" konusuna bakın *ODBC SDK Programcının Başvurusu*.  
  
 `prgLengths`  
 Uzun dizisi için bir işaretçi. Bu dizi gösterdiği dizisindeki her bir değerin bayt cinsinden uzunluğu depolayacak `prgTSVals`. Unutmayın değeri **SQL_NULL_DATA** karşılık gelen veri öğesi bir Null değer içeriyorsa depolanır. Daha fazla ayrıntı için bkz: ODBC API işlevi **SQLBindCol** içinde *ODBC SDK Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri kaynağı sütun bir ODBC türünde olabilir **SQL_DATE**, **SQL_TIME**, veya **SQL_TIMESTAMP**. Kayıt kümesi türü işaretçisi bir alan veri üyesi tanımlamalısınız **TIMESTAMP_STRUCT**.  
  
 Başlatır, `prgTSVals` ve `prgLengths` için **NULL**, sonra da işaret edecek şekilde diziler satır kümesi boyutuna eşit boyutlarıyla otomatik olarak ayrılır.  
  
> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından kayıt kümesi nesnesine aktarır. Kümenizin güncelleştirilebilir duruma getirmek için ODBC API işlevini kullanmak **SQLSetPos**.  
  
 Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

## <a name="rfx_double_bulk"></a>  RFX_Double_Bulk
ODBC veri kaynağını sütundan karşılık gelen bir dizide birden çok sayıda çift duyarlıklı, kayan nokta veri aktarır bir `CRecordset`-türetilmiş bir nesne içermelidir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Double_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   double** prgDblVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesnesi. Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. Daha fazla bilgi için bkz: [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 `prgDblVals`  
 Bir dizi için bir işaretçi **çift** değerleri. Bu dizi kayıt kümesine veri kaynağından aktarılacak veri depolar.  
  
 `prgLengths`  
 Uzun dizisi için bir işaretçi. Bu dizi gösterdiği dizisindeki her bir değerin bayt cinsinden uzunluğu depolayacak `prgDblVals`. Unutmayın değeri **SQL_NULL_DATA** karşılık gelen veri öğesi bir Null değer içeriyorsa depolanır. Daha fazla ayrıntı için bkz: ODBC API işlevi **SQLBindCol** içinde *ODBC SDK Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri kaynağı sütun bir ODBC türünde olmalıdır **SQL_DOUBLE**. Kayıt kümesi türü işaretçisi bir alan veri üyesi tanımlamalısınız **çift**.  
  
 Başlatır, `prgDblVals` ve `prgLengths` için **NULL**, sonra da işaret edecek şekilde diziler satır kümesi boyutuna eşit boyutlarıyla otomatik olarak ayrılır.  
  
> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından kayıt kümesi nesnesine aktarır. Kümenizin güncelleştirilebilir duruma getirmek için ODBC API işlevini kullanmak **SQLSetPos**.  
  
 Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

## <a name="rfx_int_bulk"></a>  Rfx_ınt_bulk
Alan veri üyeleri arasında tamsayı veri aktaran bir `CRecordset` nesne ve ODBC türü veri kaynağında bir kayıt sütunlarının **SQL_SMALLINT**.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Int(  
   CFieldExchange* pFX,  
   const char* szName,  
   int& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CFieldExchange](cfieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. İşlemleri hakkında daha fazla bilgi için bir `CFieldExchange` nesnesi belirtebilirsiniz, makaleye bakın [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı `int`, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

## <a name="rfx_long_bulk"></a>  RFX_Long_Bulk
ODBC veri kaynağını sütundan karşılık gelen bir dizideki birden çok sayıda uzun tamsayı veri aktarır bir `CRecordset`-türetilmiş bir nesne içermelidir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Long_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   long** prgLongVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesnesi. Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. Daha fazla bilgi için bkz: [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 `prgLongVals`  
 Uzun dizisi için bir işaretçi. Bu dizi kayıt kümesine veri kaynağından aktarılacak veri depolar.  
  
 `prgLengths`  
 Uzun dizisi için bir işaretçi. Bu dizi gösterdiği dizisindeki her bir değerin bayt cinsinden uzunluğu depolayacak `prgLongVals`. Unutmayın değeri **SQL_NULL_DATA** karşılık gelen veri öğesi bir Null değer içeriyorsa depolanır. Daha fazla ayrıntı için bkz: ODBC API işlevi **SQLBindCol** içinde *ODBC SDK Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri kaynağı sütun bir ODBC türünde olmalıdır **SQL_INTEGER**. Kayıt kümesi türü işaretçisi bir alan veri üyesi tanımlamalısınız **uzun**.  
  
 Başlatır, `prgLongVals` ve `prgLengths` için **NULL**, sonra da işaret edecek şekilde diziler satır kümesi boyutuna eşit boyutlarıyla otomatik olarak ayrılır.  
  
> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından kayıt kümesi nesnesine aktarır. Kümenizin güncelleştirilebilir duruma getirmek için ODBC API işlevini kullanmak **SQLSetPos**.  
  
 Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

## <a name="rfx_single_bulk"></a>  RFX_Single_Bulk
Kayan nokta veri birden çok satır karşılık gelen bir dizide bir ODBC veri kaynağını sütundan aktarır bir `CRecordset`-türetilmiş bir nesne içermelidir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void RFX_Single_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   float** prgFltVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesnesi. Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. Daha fazla bilgi için bkz: [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 `prgFltVals`  
 Bir dizi için bir işaretçi **float** değerleri. Bu dizi kayıt kümesine veri kaynağından aktarılacak veri depolar.  
  
 `prgLengths`  
 Uzun dizisi için bir işaretçi. Bu dizi gösterdiği dizisindeki her bir değerin bayt cinsinden uzunluğu depolayacak `prgFltVals`. Unutmayın değeri **SQL_NULL_DATA** karşılık gelen veri öğesi bir Null değer içeriyorsa depolanır. Daha fazla ayrıntı için bkz: ODBC API işlevi **SQLBindCol** içinde *ODBC SDK Programcının Başvurusu*.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri kaynağı sütun bir ODBC türünde olmalıdır **SQL_REAL**. Kayıt kümesi türü işaretçisi bir alan veri üyesi tanımlamalısınız **float**.  
  
 Başlatır, `prgFltVals` ve `prgLengths` için **NULL**, sonra da işaret edecek şekilde diziler satır kümesi boyutuna eşit boyutlarıyla otomatik olarak ayrılır.  
  
> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından kayıt kümesi nesnesine aktarır. Kümenizin güncelleştirilebilir duruma getirmek için ODBC API işlevini kullanmak **SQLSetPos**.  
  
 Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  
  

## <a name="rfx_text_bulk"></a>  RFX_Text_Bulk
ODBC veri kaynağını sütundan karşılık gelen bir dizideki birden çok sayıda karakter veri aktarır bir `CRecordset`-türetilmiş bir nesne içermelidir.  
  
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
 `pFX`  
 Bir işaretçi bir [CFieldExchange](cfieldexchange-class.md) nesnesi. Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir. Daha fazla bilgi için bkz: [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Bir veri sütununun adı.  
  
 `prgStrVals`  
 Bir dizi için bir işaretçi **LPSTR** değerleri. Bu dizi kayıt kümesine veri kaynağından aktarılacak veri depolar. ODBC geçerli sürümü ile bu değerleri Unicode olamayacağını unutmayın.  
  
 `prgLengths`  
 Uzun dizisi için bir işaretçi. Bu dizi gösterdiği dizisindeki her bir değerin bayt cinsinden uzunluğu depolayacak `prgStrVals`. Bu süre null sonlandırma karakter dışlar. Unutmayın değeri **SQL_NULL_DATA** karşılık gelen veri öğesi bir Null değer içeriyorsa depolanır. Daha fazla ayrıntı için bkz: ODBC API işlevi **SQLBindCol** içinde *ODBC SDK Programcının Başvurusu*.  
  
 `nMaxLength`  
 İzin verilen en fazla uzunluğu gösterdiği dizisinde depolanan değerlerin `prgStrVals`, null sonlandırma karakter dahil olmak üzere. Veri değil kesilecek emin olmak için beklediğiniz en büyük veri öğesi uyabilecek kadar büyük bir değer geçirin.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri kaynağı sütun bir ODBC türünde olabilir **SQL_LONGVARCHAR**, **SQL_CHAR**, **SQL_VARCHAR**, **SQL_DECIMAL**, veya **SQL_NUMERIC**. Kayıt türünün bir alan veri üyesi tanımlamalısınız **LPSTR**.  
  
 Başlatır, `prgStrVals` ve `prgLengths` için **NULL**, sonra da işaret edecek şekilde diziler satır kümesi boyutuna eşit boyutlarıyla otomatik olarak ayrılır.  
  
> [!NOTE]
>  Toplu kayıt alanı değişimi yalnızca verileri veri kaynağından kayıt kümesi nesnesine aktarır. Kümenizin güncelleştirilebilir duruma getirmek için ODBC API işlevini kullanmak **SQLSetPos**.  
  
 Daha fazla bilgi için makalelere bakın [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Örnek  
 Çağrıları el ile yazmanız gerekir, `DoBulkFieldExchange` geçersiz kılar. Bu örnek bir çağrı gösterilmektedir `RFX_Text_Bulk`, çağrı yanı sıra `RFX_Long_Bulk`, veri aktarımı için. Bu çağrı için yapılan bir çağrı tarafından öncesinde [CFieldExchange::SetFieldType](CFieldExchange::SetFieldType.md). Parametreleri için Toplu RFX işlevleri yerine RFX işlevleri çağırmalıdır unutmayın.  
  
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
Bayt dizileri alan veri üyeleri arasında aktarır bir [CDaoRecordset](cdaorecordset-class.md) nesne ve bir kayıt veri kaynağında sütunlarının.  
  
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
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir.  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı [CLongBinary](cbytearray-class.md), belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 `nPreAllocSize`  
 Bu bellek miktarını framework preallocates. Verilerinizi daha büyükse, gerektiği gibi daha fazla alan ayrılmış framework olur. Daha iyi performans için bu boyut adetle sınırla önlemek için büyük bir değere ayarlayın. Varsayılan boyut AFXDAO tanımlanır. H dosyası olarak **AFX_DAO_BINARY_DEFAULT_SIZE**.  
  
 `dwBindOptions`  
 Değiştirilmiş kayıt kümesi alanları algılamak MFC'nin çift arabelleğe alma mekanizması yararlanmak olanak sağlayan bir seçenek. Varsayılan olarak, `AFX_DAO_DISABLE_FIELD_CACHE`olmayan kullanım iki kez arabelleğe alma yapar ve çağırmalısınız [SetFieldDirty](cdaorecordset-class.md#setfielddirty) ve [SetFieldNull](cdaorecordset-class.md#setfieldnull) kendiniz. Diğer olası değer `AFX_DAO_ENABLE_FIELD_CACHE`, kullanan iki kez arabelleğe alma ve sahip alanları işaretlemek için ek iş yapmak kirli veya Null. İkili verilerinizi görece küçük gerekmedikçe performans ve bellek nedeniyle, bu değer kaçının.  
  
> [!NOTE]
>  Tüm alanlar için varsayılan olarak ayarlayarak arabelleğe veri çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Açıklamalar  
 Veri türü arasında eşlenen **DAO_BYTES** DAO ve türü [CLongBinary](cbytearray-class.md) kümesinde.  
  
### <a name="example"></a>Örnek  
 Bkz: [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  

## <a name="dfx_bool"></a>  DFX_Bool
Alan veri üyeleri arasında Boole veri aktaran bir [CDaoRecordset](cdaorecordset-class.md) nesne ve bir kayıt veri kaynağında sütunlarının.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void AFXAPI DFX_Bool(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   BOOL& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir.  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı **BOOL**, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 `dwBindOptions`  
 Değiştirilmiş kayıt kümesi alanları algılamak MFC'nin çift arabelleğe alma mekanizması yararlanmak olanak sağlayan bir seçenek. Varsayılan olarak, `AFX_DAO_ENABLE_FIELD_CACHE`, iki kez arabelleğe alma kullanır. Olası bir değer `AFX_DAO_DISABLE_FIELD_CACHE`. Bu değer belirtirseniz, MFC hiçbir bu alanı denetimi yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.  
  
> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verilerin çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Açıklamalar  
 Veri türü arasında eşlenen **DAO_BOOL** DAO ve türü **BOOL** kümesinde.  
  
### <a name="example"></a>Örnek  
 Bkz: [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  

## <a name="dfx_byte"></a>  DFX_Byte
Aktarımları tek bayt alan veri üyeleri arasında bir [CDaoRecordset](cdaorecordset-class.md) nesne ve bir kayıt veri kaynağında sütunlarının.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void AFXAPI DFX_Byte(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   BYTE& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir.  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı **bayt**, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 `dwBindOptions`  
 Değiştirilmiş kayıt kümesi alanları algılamak MFC'nin çift arabelleğe alma mekanizması yararlanmak olanak sağlayan bir seçenek. Varsayılan olarak, `AFX_DAO_ENABLE_FIELD_CACHE`, iki kez arabelleğe alma kullanır. Olası bir değer `AFX_DAO_DISABLE_FIELD_CACHE`. Bu değer belirtirseniz, MFC hiçbir bu alanı denetimi yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.  
  
> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verilerin çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Açıklamalar  
 Veri türü arasında eşlenen **DAO_BYTES** DAO ve türü **bayt** kümesinde.  
  
### <a name="example"></a>Örnek  
 Bkz: [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  

## <a name="dfx_currency"></a>  DFX_Currency
Alan veri üyeleri arasında para birimi veri aktaran bir [CDaoRecordset](cdaorecordset-class.md) nesne ve bir kayıt veri kaynağında sütunlarının.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void AFXAPI DFX_Currency(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   COleCurrency& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir.  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Bir aktarımı için kayıt kümesi veri kaynağına, bu değer türü belirtilen veri üyeden alınır [COleCurrency](colecurrency-class.md). Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 `dwBindOptions`  
 Değiştirilmiş kayıt kümesi alanları algılamak MFC'nin çift arabelleğe alma mekanizması yararlanmak olanak sağlayan bir seçenek. Varsayılan olarak, `AFX_DAO_ENABLE_FIELD_CACHE`, iki kez arabelleğe alma kullanır. Olası bir değer `AFX_DAO_DISABLE_FIELD_CACHE`. Bu değer belirtirseniz, MFC hiçbir bu alanı denetimi yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.  
  
> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verilerin çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Açıklamalar  
 Veri türü arasında eşlenen **DAO_CURRENCY** DAO ve türü [COleCurrency](colecurrency-class.md) kümesinde.  
  
### <a name="example"></a>Örnek  
 Bkz: [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  

## <a name="dfx_datetime"></a>  DFX_DateTime
Alan veri üyeleri arasında saat ve tarih veri aktaran bir [CDaoRecordset](cdaorecordset-class.md) nesne ve bir kayıt veri kaynağında sütunlarının.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void AFXAPI DFX_DateTime(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   COleDateTime& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir.  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. İşlev bir başvuru alır bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi. Bir aktarımı için kayıt kümesi veri kaynağına, bu değeri belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 `dwBindOptions`  
 Değiştirilmiş kayıt kümesi alanları algılamak MFC'nin çift arabelleğe alma mekanizması yararlanmak olanak sağlayan bir seçenek. Varsayılan olarak, `AFX_DAO_ENABLE_FIELD_CACHE`, iki kez arabelleğe alma kullanır. Olası bir değer `AFX_DAO_DISABLE_FIELD_CACHE`. Bu değer belirtirseniz, MFC hiçbir bu alanı denetimi yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.  
  
> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verilerin çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Açıklamalar  
 Veri türü arasında eşlenen **DAO_DATE** DAO ve türü [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) kümesinde.  
  
> [!NOTE]
>  `COleDateTime` değiştirir [CTime](../../atl-mfc-shared/reference/ctime-class.md) ve **TIMESTAMP_STRUCT** bu amaçla DAO sınıfları'nda. `CTime` ve **TIMESTAMP_STRUCT** olan hala ODBC tabanlı veri erişim sınıfları için kullanılır.  
  
### <a name="example"></a>Örnek  
 Bkz: [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  

## <a name="dfx_double"></a>  DFX_Double
Aktarımları **double float** alan veri üyeleri arasında veri bir [CDaoRecordset](cdaorecordset-class.md) nesne ve bir kayıt veri kaynağında sütunlarının.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void AFXAPI DFX_Double(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   double& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir.  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı **çift**, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 `dwBindOptions`  
 Değiştirilmiş kayıt kümesi alanları algılamak MFC'nin çift arabelleğe alma mekanizması yararlanmak olanak sağlayan bir seçenek. Varsayılan olarak, `AFX_DAO_ENABLE_FIELD_CACHE`, iki kez arabelleğe alma kullanır. Olası bir değer `AFX_DAO_DISABLE_FIELD_CACHE`. Bu değer belirtirseniz, MFC hiçbir bu alanı denetimi yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.  
  
> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verilerin çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Açıklamalar  
 Veri türü arasında eşlenen **DAO_R8** DAO ve türü **double float** kümesinde.  
  
### <a name="example"></a>Örnek  
 Bkz: [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  

## <a name="dfx_long"></a>  DFX_Long
Alan veri üyeleri arasında uzun tamsayı veri aktaran bir [CDaoRecordset](cdaorecordset-class.md) nesne ve bir kayıt veri kaynağında sütunlarının.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void AFXAPI DFX_Long(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   long& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir.  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı **uzun**, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 `dwBindOptions`  
 Değiştirilmiş kayıt kümesi alanları algılamak MFC'nin çift arabelleğe alma mekanizması yararlanmak olanak sağlayan bir seçenek. Varsayılan olarak, `AFX_DAO_ENABLE_FIELD_CACHE`, iki kez arabelleğe alma kullanır. Olası bir değer `AFX_DAO_DISABLE_FIELD_CACHE`. Bu değer belirtirseniz, MFC hiçbir bu alanı denetimi yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.  
  
> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verilerin çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Açıklamalar  
 Veri türü arasında eşlenen **DAO_I4** DAO ve türü **uzun** kümesinde.  
  
### <a name="example"></a>Örnek  
 Bkz: [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  

## <a name="dfx_longbinary"></a>  DFX_LongBinary
**Önemli** kullanmanız önerilir [DFX_Binary](#dfx_binary) yerine bu işlev.  
  
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
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir.  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı [CLongBinary](clongbinary-class.md), belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 *dwPreAllocSize*  
 Bu bellek miktarını framework preallocates. Verilerinizi daha büyükse, gerektiği gibi daha fazla alan ayrılmış framework olur. Daha iyi performans için bu boyut adetle sınırla önlemek için büyük bir değere ayarlayın.  
  
 `dwBindOptions`  
 Değiştirilmiş kayıt kümesi alanları algılamak MFC'nin çift arabelleğe alma mekanizması yararlanmak olanak sağlayan bir seçenek. Varsayılan olarak, **AFX_DISABLE_FIELD_CACHE**, iki kez arabelleğe alma kullanmaz. Olası bir değer `AFX_DAO_ENABLE_FIELD_CACHE`. Kullanan iki kez arabelleğe alma ve sahip alanları işaretlemek için ek iş yapmak kirli veya Null. İkili verilerinizi görece küçük gerekmedikçe performans ve bellek nedeniyle, bu değer kaçının.  
  
> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verilerin çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Açıklamalar  
 `DFX_LongBinary` MFC ODBC sınıfları ile uyumluluk için sağlanır. `DFX_LongBinary` İşlevi sınıfını kullanarak ikili büyük nesne (BLOB) veri aktarımları `CLongBinary` alan veri üyeleri arasında bir [CDaoRecordset](cdaorecordset-class.md) nesne ve bir kayıt veri kaynağında sütunlarının. Veri türü arasında eşlenen **DAO_BYTES** DAO ve türü [CLongBinary](clongbinary-class.md) kümesinde.  
  
### <a name="example"></a>Örnek  
 Bkz: [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  

## <a name="dfx_short"></a>  DFX_Short
Alan veri üyeleri arasında tamsayı veri aktarımları kısa bir [CDaoRecordset](cdaorecordset-class.md) nesne ve bir kayıt veri kaynağında sütunlarının.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void AFXAPI DFX_Short(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   short& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir.  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı **kısa**, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 `dwBindOptions`  
 Değiştirilmiş kayıt kümesi alanları algılamak MFC'nin çift arabelleğe alma mekanizması yararlanmak olanak sağlayan bir seçenek. Varsayılan olarak, `AFX_DAO_ENABLE_FIELD_CACHE`, iki kez arabelleğe alma kullanır. Olası bir değer `AFX_DAO_DISABLE_FIELD_CACHE`. Bu değer belirtirseniz, MFC hiçbir bu alanı denetimi yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.  
  
> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verilerin çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Açıklamalar  
 Veri türü arasında eşlenen **DAO_I2** DAO ve türü **kısa** kümesinde.  
  
> [!NOTE]
>  `DFX_Short` eşdeğer olan [rfx_ınt](#rfx_int) ODBC tabanlı sınıflar için.  
  
### <a name="example"></a>Örnek  
 Bkz: [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  

## <a name="dfx_single"></a>  DFX_Single
Alan veri üyeleri arasında kayan nokta veri aktaran bir [CDaoRecordset](cdaorecordset-class.md) nesne ve bir kayıt veri kaynağında sütunlarının.  
  
### <a name="syntax"></a>Sözdizimi  
  
```
void AFXAPI DFX_Single(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   float& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir.  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı **float**, belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 `dwBindOptions`  
 Değiştirilmiş kayıt kümesi alanları algılamak MFC'nin çift arabelleğe alma mekanizması yararlanmak olanak sağlayan bir seçenek. Varsayılan olarak, `AFX_DAO_ENABLE_FIELD_CACHE`, iki kez arabelleğe alma kullanır. Olası bir değer `AFX_DAO_DISABLE_FIELD_CACHE`. Bu değer belirtirseniz, MFC hiçbir bu alanı denetimi yapar. Çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.  
  
> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verilerin çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Açıklamalar  
 Veri türü arasında eşlenen **DAO_R4** DAO ve türü **float** kümesinde.  
  
### <a name="example"></a>Örnek  
 Bkz: [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  

## <a name="dfx_text"></a>  DFX_Text
Aktarımları `CString` alan veri üyeleri arasında veri bir [CDaoRecordset](cdaorecordset-class.md) nesne ve bir kayıt veri kaynağında sütunlarının.  
  
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
 `pFX`  
 Sınıfın bir nesnesi için bir işaretçi [CDaoFieldExchange](cdaofieldexchange-class.md). Bu nesne bağlamı her işlev çağrısı için tanımlamak için bilgileri içerir.  
  
 `szName`  
 Bir veri sütununun adı.  
  
 *value*  
 Belirtilen veri üye depolanan değeri — transfer edilecek değer. Kayıt kümesinden veri kaynağına türünde değer aktarımı [CString](../../atl-mfc-shared/reference/cstringt-class.md), belirtilen veri üyeden alınır. Bir aktarımı için veri kaynağından kayıt kümesi için belirtilen veri üye değeri depolanır.  
  
 `nPreAllocSize`  
 Bu bellek miktarını framework preallocates. Verilerinizi daha büyükse, gerektiği gibi daha fazla alan ayrılmış framework olur. Daha iyi performans için bu boyut adetle sınırla önlemek için büyük bir değere ayarlayın.  
  
 `dwBindOptions`  
 Değiştirilmiş kayıt kümesi alanları algılamak MFC'nin çift arabelleğe alma mekanizması yararlanmak olanak sağlayan bir seçenek. Varsayılan olarak, `AFX_DAO_ENABLE_FIELD_CACHE`, iki kez arabelleğe alma kullanır. Olası bir değer `AFX_DAO_DISABLE_FIELD_CACHE`. Bu değer belirtirseniz, MFC hiçbir bu alanı denetimi yapar. Çağırmalısınız [SetFieldDirty](cdaorecordset-class.md#setfielddirty) ve [SetFieldNull](cdaorecordset-class.md#setfieldnull) kendiniz.  
  
> [!NOTE]
>  Varsayılan olarak ayarlayarak arabelleğe alınan verilerin çift olup olmadığını kontrol edebilirsiniz [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Açıklamalar  
 Veri türü arasında eşlenen **DAO_CHAR** DAO içinde (veya simgenin **_UNICODE** tanımlanan **DAO_WCHAR**) ve türü [CString](../../atl-mfc-shared/reference/cstringt-class.md) içinde kayıt kümesi.  n
  
### <a name="example"></a>Örnek  
 Bu örnek, çeşitli çağrıları gösterir `DFX_Text`. Ayrıca iki çağrıları fark [CDaoFieldExchange::SetFieldType](cdaofieldexchange-class.md#setfieldtype). İlk çağrıda yazmalısınız `SetFieldType` ve kendi **DFX** çağırın. İkinci çağrı ve onun ilişkili **DFX** çağrıları normalde sınıfı oluşturulan kod sihirbaz tarafından yazılmış.  
  
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
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [CRecordset::DoFieldExchange](crecordset-class.md#dofieldexchange)   
 [CRecordset::DoBulkFieldExchange](crecordset-class.md#dobulkfieldexchange)   
 [CDaoRecordset::DoFieldExchange](cdaorecordset-class.md#dofieldexchange)

