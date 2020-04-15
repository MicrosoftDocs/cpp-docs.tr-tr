---
title: CDBVariant Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDBVariant
- AFXDB/CDBVariant
- AFXDB/CDBVariant::CDBVariant
- AFXDB/CDBVariant::Clear
- AFXDB/CDBVariant::m_dwType
- AFXDB/CDBVariant::m_boolVal
- AFXDB/CDBVariant::m_chVal
- AFXDB/CDBVariant::m_dblVal
- AFXDB/CDBVariant::m_fltVal
- AFXDB/CDBVariant::m_iVal
- AFXDB/CDBVariant::m_lVal
- AFXDB/CDBVariant::m_pbinary
- AFXDB/CDBVariant::m_pdate
- AFXDB/CDBVariant::m_pstring
- AFXDB/CDBVariant::m_pstringA
- AFXDB/CDBVariant::m_pstringW
helpviewer_keywords:
- CDBVariant [MFC], CDBVariant
- CDBVariant [MFC], Clear
- CDBVariant [MFC], m_dwType
- CDBVariant [MFC], m_boolVal
- CDBVariant [MFC], m_chVal
- CDBVariant [MFC], m_dblVal
- CDBVariant [MFC], m_fltVal
- CDBVariant [MFC], m_iVal
- CDBVariant [MFC], m_lVal
- CDBVariant [MFC], m_pbinary
- CDBVariant [MFC], m_pdate
- CDBVariant [MFC], m_pstring
- CDBVariant [MFC], m_pstringA
- CDBVariant [MFC], m_pstringW
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
ms.openlocfilehash: 3c13c1a965014af271ce2911505742d9a50eedd7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376447"
---
# <a name="cdbvariant-class"></a>CDBVariant Sınıfı

MFC ODBC sınıfları için bir varyant veri türünü temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDBVariant
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDBVariant::CDBVariant](#cdbvariant)|Bir `CDBVariant` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDBVariant::Clear](#clear)|Nesneyi `CDBVariant` temizler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDBVariant::m_dwType](#m_dwtype)|Şu anda depolanan değerin veri türünü içerir. `DWORD` yazın.|

### <a name="public-union-members"></a>Kamu Sendikası Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDBVariant::m_boolVal](#m_boolval)|**BOOL**türünde bir değer içerir.|
|[CDBVariant::m_chVal](#m_chval)|Türü **imzasız char**bir değer içerir.|
|[CDBVariant::m_dblVal](#m_dblval)|**Çift**türübir değer içerir.|
|[CDBVariant::m_fltVal](#m_fltval)|Tür **float**bir değer içerir.|
|[CDBVariant::m_iVal](#m_ival)|**Kısa**tür değeri içerir.|
|[CDBVariant::m_lVal](#m_lval)|**Uzun**tür bir değer içerir.|
|[CDBVariant::m_pbinary](#m_pbinary)|Türünden `CLongBinary`bir nesneye işaretçi içerir.|
|[CDBVariant::m_pdate](#m_pdate)|**Tür TIMESTAMP_STRUCT**bir nesneye işaretçi içerir.|
|[CDBVariant::m_pstring](#m_pstring)|Türünden `CString`bir nesneye işaretçi içerir.|
|[CDBVariant::m_pstringA](#m_pstringa)|Bir ascii [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine işaretçi depolar.|
|[CDBVariant::m_pstringW](#m_pstringw)|Bir işaretçiyi geniş bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine depolar.|

## <a name="remarks"></a>Açıklamalar

`CDBVariant`taban sınıfa sahip değildir.

`CDBVariant`[COleVariant](../../mfc/reference/colevariant-class.md)benzer ; ancak, `CDBVariant` OLE kullanmaz. `CDBVariant`değerin veri türü hakkında endişelenmeden bir değer depolamanızı sağlar. `CDBVariant`birleşimde depolanan geçerli değerin veri türünü izler.

[CRecordset](../../mfc/reference/crecordset-class.md) sınıfı `CDBVariant` nesneleri üç üye işlevde kullanır: `GetFieldValue`, , `GetBookmark`ve `SetBookmark`. Örneğin, `GetFieldValue` bir sütundaki verileri dinamik olarak getirmenize olanak tanır. Sütunun veri türü çalışma zamanında `GetFieldValue` bilinmeyebileceğinden, `CDBVariant` sütunverilerini depolamak için bir nesne kullanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDBVariant`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="cdbvariantcdbvariant"></a><a name="cdbvariant"></a>CDBVariant::CDBVariant

NULL `CDBVariant` nesnesi oluşturur.

```
CDBVariant();
```

### <a name="remarks"></a>Açıklamalar

[m_dwType](#m_dwtype) veri üyesini DBVT_NULL ayarlar.

## <a name="cdbvariantclear"></a><a name="clear"></a>CDBVariant::Clear

`CDBVariant` Nesneyi temizlemek için bu üye işlevi arayın.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

[m_dwType](#m_dwtype) veri üyesinin değeri DBVT_DATE, DBVT_STRING veya `Clear` DBVT_BINARY ise, birleşim işaretçisi üyesiyle ilişkili belleği serbest bırakır. `Clear`DBVT_NULL `m_dwType` ayarlar.

`CDBVariant` Yıkıcı arıyor. `Clear`

## <a name="cdbvariantm_boolval"></a><a name="m_boolval"></a>CDBVariant::m_boolVal

BoOL tipi bir değer depolar.

### <a name="remarks"></a>Açıklamalar

Veri `m_boolVal` üyesi bir birliğe aittir. Erişmeden `m_boolVal`önce, önce [CDBVariant](#m_dwtype)değerini kontrol edin::m_dwType . DBVT_BOOL `m_dwType` olarak ayarlanırsa, `m_boolVal` geçerli bir değer içerir; aksi takdirde, `m_boolVal` erişim güvenilmez sonuçlar üretecektir.

## <a name="cdbvariantm_chval"></a><a name="m_chval"></a>CDBVariant::m_chVal

**İmzasız türdeki**bir değer depolar.

### <a name="remarks"></a>Açıklamalar

Veri `m_chVal` üyesi bir birliğe aittir. Erişmeden `m_chVal`önce, önce [CDBVariant](#m_dwtype)değerini kontrol edin::m_dwType . DBVT_UCHAR `m_dwType` olarak ayarlanmışsa, `m_chVal` geçerli bir değer içerir; aksi takdirde, `m_chVal` erişim güvenilmez sonuçlar üretecektir.

## <a name="cdbvariantm_dblval"></a><a name="m_dblval"></a>CDBVariant::m_dblVal

Bir değeri **çift tipte**depolar.

### <a name="remarks"></a>Açıklamalar

Veri `m_dblVal` üyesi bir birliğe aittir. Erişmeden `m_dblVal`önce, önce [CDBVariant](#m_dwtype)değerini kontrol edin::m_dwType . DBVT_DOUBLE `m_dwType` olarak ayarlanmışsa, `m_dblVal` geçerli bir değer içerir; aksi takdirde, `m_dblVal` erişim güvenilmez sonuçlar üretecektir.

## <a name="cdbvariantm_dwtype"></a><a name="m_dwtype"></a>CDBVariant::m_dwType

Bu veri üyesi, `CDBVariant` nesnenin birleşim veri üyesinde şu anda depolanan değer için veri türünü içerir.

### <a name="remarks"></a>Açıklamalar

Bu birleşime erişmeden önce, hangi birleşim veri üyesine `m_dwType` erişeceklerini belirlemek için değerini denetlemeniz gerekir. Aşağıdaki tabloda olası değerler `m_dwType` ve ilgili birlik veri üyesi listeleilmektedir.

|m_dwType|Birlik veri üyesi|
|---------------|-----------------------|
|DBVT_NULL|Hiçbir sendika üyesi erişim için geçerli değildir.|
|DBVT_BOOL|[m_boolVal](#m_boolval)|
|DBVT_UCHAR|[m_chVal](#m_chval)|
|DBVT_SHORT|[m_iVal](#m_ival)|
|DBVT_LONG|[m_lVal](#m_lval)|
|DBVT_SINGLE|[m_fltVal](#m_fltval)|
|DBVT_DOUBLE|[m_dblVal](#m_dblval)|
|DBVT_DATE|[m_pdate](#m_pdate)|
|DBVT_STRING|[m_pstring](#m_pstring)|
|DBVT_BINARY|[m_pbinary](#m_pbinary)|
|DBVT_ASTRING|[m_pstringA](#m_pstringa)|
|DBVT_WSTRING|[m_pstringW](#m_pstringw)|

## <a name="cdbvariantm_fltval"></a><a name="m_fltval"></a>CDBVariant::m_fltVal

Bir tür **float**değerini depolar.

### <a name="remarks"></a>Açıklamalar

Veri `m_fltVal` üyesi bir birliğe aittir. Erişmeden `m_fltVal`önce, önce [CDBVariant](#m_dwtype)değerini kontrol edin::m_dwType . DBVT_SINGLE `m_dwType` olarak ayarlanmışsa, `m_fltVal` geçerli bir değer içerir; aksi takdirde, `m_fltVal` erişim güvenilmez sonuçlar üretecektir.

## <a name="cdbvariantm_ival"></a><a name="m_ival"></a>CDBVariant::m_iVal

Bir değeri **kısa**türün depolar.

### <a name="remarks"></a>Açıklamalar

Veri `m_iVal` üyesi bir birliğe aittir. Erişmeden `m_iVal`önce, önce [CDBVariant](#m_dwtype)değerini kontrol edin::m_dwType . DBVT_SHORT `m_dwType` olarak ayarlanmışsa, `m_iVal` geçerli bir değer içerir; aksi takdirde, `m_iVal` erişim güvenilmez sonuçlar üretecektir.

## <a name="cdbvariantm_lval"></a><a name="m_lval"></a>CDBVariant::m_lVal

**Uzun**tür bir değer depolar.

### <a name="remarks"></a>Açıklamalar

Veri `m_lVal` üyesi bir birliğe aittir. Erişmeden `m_lVal`önce, önce [CDBVariant](#m_dwtype)değerini kontrol edin::m_dwType . DBVT_LONG `m_dwType` olarak ayarlanmışsa, `m_lVal` geçerli bir değer içerir; aksi takdirde, `m_lVal` erişim güvenilmez sonuçlar üretecektir.

## <a name="cdbvariantm_pbinary"></a><a name="m_pbinary"></a>CDBVariant::m_pbinary

[CLongBinary](../../mfc/reference/clongbinary-class.md)türünden bir nesneye işaretçi depolar.

### <a name="remarks"></a>Açıklamalar

Veri `m_pbinary` üyesi bir birliğe aittir. Erişmeden `m_pbinary`önce, önce [CDBVariant](#m_dwtype)değerini kontrol edin::m_dwType . DBVT_BINARY `m_dwType` olarak ayarlanmışsa, `m_pbinary` geçerli bir işaretçi içerir; aksi takdirde, `m_pbinary` erişim güvenilmez sonuçlar üretecektir.

## <a name="cdbvariantm_pdate"></a><a name="m_pdate"></a>CDBVariant::m_pdate

Bir işaretçiyi TIMESTAMP_STRUCT türünden bir nesneye depolar.

### <a name="remarks"></a>Açıklamalar

Veri `m_pdate` üyesi bir birliğe aittir. Erişmeden `m_pdate`önce, önce [CDBVariant](#m_dwtype)değerini kontrol edin::m_dwType . DBVT_DATE `m_dwType` olarak ayarlanmışsa, `m_pdate` geçerli bir işaretçi içerir; aksi takdirde, `m_pdate` erişim güvenilmez sonuçlar üretecektir.

TIMESTAMP_STRUCT veri türü hakkında daha fazla bilgi için, Windows SDK'daki *ODBC Programcısı Başvurusu'nun* Ek D'sindeki [C Veri Türleri](/sql/odbc/reference/appendixes/c-data-types) konusuna bakın.

## <a name="cdbvariantm_pstring"></a><a name="m_pstring"></a>CDBVariant::m_pstring

Bir işaretçiyi [CString](../../atl-mfc-shared/reference/cstringt-class.md)türünden bir nesneye depolar.

### <a name="remarks"></a>Açıklamalar

Veri `m_pstring` üyesi bir birliğe aittir. Erişmeden `m_pstring`önce, önce [CDBVariant](#m_dwtype)değerini kontrol edin::m_dwType . DBVT_STRING `m_dwType` olarak ayarlanmışsa, `m_pstring` geçerli bir işaretçi içerir; aksi takdirde, `m_pstring` erişim güvenilmez sonuçlar üretecektir.

## <a name="cdbvariantm_pstringa"></a><a name="m_pstringa"></a>CDBVariant::m_pstringA

Bir ascii [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine işaretçi depolar.

### <a name="remarks"></a>Açıklamalar

Veri `m_pstringA` üyesi bir birliğe aittir. Erişmeden `m_pstringA`önce, önce [CDBVariant](#m_dwtype)değerini kontrol edin::m_dwType . DBVT_ASTRING `m_dwType` olarak ayarlanmışsa, `m_pstringA` geçerli bir işaretçi içerir; aksi takdirde, `m_pstringA` erişim güvenilmez sonuçlar üretecektir.

## <a name="cdbvariantm_pstringw"></a><a name="m_pstringw"></a>CDBVariant::m_pstringW

Bir işaretçiyi geniş bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine depolar.

### <a name="remarks"></a>Açıklamalar

Veri `m_pstringW` üyesi bir birliğe aittir. Erişmeden `m_pstringW`önce, önce [CDBVariant](#m_dwtype)değerini kontrol edin::m_dwType . DBVT_WSTRING `m_dwType` olarak ayarlanmışsa, `m_pstringW` geçerli bir işaretçi içerir; aksi takdirde, `m_pstringW` erişim güvenilmez sonuçlar üretecektir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
