---
title: CDBVariant sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14e2e646a2b05ba8514f22fb9ffb027aa0a570c1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419652"
---
# <a name="cdbvariant-class"></a>CDBVariant sınıfı

MFC ODBC sınıfları için bir değişken veri türünü temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDBVariant
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDBVariant::CDBVariant](#cdbvariant)|Oluşturur bir `CDBVariant` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDBVariant::Clear](#clear)|Temizler `CDBVariant` nesne.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDBVariant::m_dwType](#m_dwtype)|Şu anda depolanan değeri veri türünü içerir. Tür `DWORD`.|

### <a name="public-union-members"></a>Genel birleşim üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDBVariant::m_boolVal](#m_boolval)|Türünde bir değer içeren **BOOL**.|
|[CDBVariant::m_chVal](#m_chval)|Türünde bir değer içeren **imzasız char**.|
|[CDBVariant::m_dblVal](#m_dblval)|Türünde bir değer içeren **çift**.|
|[CDBVariant::m_fltVal](#m_fltval)|Türünde bir değer içeren **float**.|
|[CDBVariant::m_iVal](#m_ival)|Türünde bir değer içeren **kısa**.|
|[CDBVariant::m_lVal](#m_lval)|Türünde bir değer içeren **uzun**.|
|[CDBVariant::m_pbinary](#m_pbinary)|Türü bir nesneye bir işaretçi içeren `CLongBinary`.|
|[CDBVariant::m_pdate](#m_pdate)|Türü bir nesneye bir işaretçi içeren **TIMESTAMP_STRUCT**.|
|[CDBVariant::m_pstring](#m_pstring)|Türü bir nesneye bir işaretçi içeren `CString`.|
|[CDBVariant::m_pstringA](#m_pstringa)|Bir ASCII yönelik bir işaretçi depolayan [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesne.|
|[CDBVariant::m_pstringW](#m_pstringw)|Bir geniş yönelik bir işaretçi depolayan [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesne.|

## <a name="remarks"></a>Açıklamalar

`CDBVariant` bir temel sınıfa sahip değil.

`CDBVariant` benzer [COleVariant](../../mfc/reference/colevariant-class.md); ancak `CDBVariant` OLE kullanmaz. `CDBVariant` bir değeri, değerin veri türü hakkında endişelenmeden depolamanıza olanak tanır. `CDBVariant` veri türü bir birleşim içinde depolanan geçerli değer izler.

Sınıf [CRecordset](../../mfc/reference/crecordset-class.md) yararlanan `CDBVariant` üç üye işlev nesneleri: `GetFieldValue`, `GetBookmark`, ve `SetBookmark`. Örneğin, `GetFieldValue` dinamik olarak bir sütundaki verileri getirme olanak tanır. Sütunun veri türünü çalışma zamanında bilinmiyor çünkü `GetFieldValue` kullanan bir `CDBVariant` sütunun verileri depolamak için nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDBVariant`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

##  <a name="cdbvariant"></a>  CDBVariant::CDBVariant

Bir NULL oluşturur `CDBVariant` nesne.

```
CDBVariant();
```

### <a name="remarks"></a>Açıklamalar

Kümeleri [m_dwType](#m_dwtype) DBVT_NULL için veri üyesi.

##  <a name="clear"></a>  CDBVariant::Clear

Temizlemek için bu üye işlevi çağrısı `CDBVariant` nesne.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Varsa değerini [m_dwType](#m_dwtype) veri üyesi olduğu DBVT_DATE, DBVT_STRING veya DBVT_BINARY, `Clear` birleşim işaretçi üye ile ilişkili belleği serbest bırakır. `Clear` Ayarlar `m_dwType` DBVT_NULL için.

`CDBVariant` Yıkıcı çağrıları `Clear`.

##  <a name="m_boolval"></a>  CDBVariant::m_boolVal

BOOL türünde bir değer depolar.

### <a name="remarks"></a>Açıklamalar

`m_boolVal` Veri üyesine ait bir birleşime. Erişmeden önce `m_boolVal`, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` DBVT_BOOL için sonra ayarlanır `m_boolVal` geçerli bir değer içerir; Aksi takdirde, erişim `m_boolVal` güvenilir olmayan sonuçlar oluşturabilir.

##  <a name="m_chval"></a>  CDBVariant::m_chVal

Türünde bir değer depolar **imzasız char**.

### <a name="remarks"></a>Açıklamalar

`m_chVal` Veri üyesine ait bir birleşime. Erişmeden önce `m_chVal`, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` DBVT_UCHAR için sonra ayarlanır `m_chVal` geçerli bir değer içeriyor; Aksi takdirde, erişim `m_chVal` güvenilir olmayan sonuçlar oluşturabilir.

##  <a name="m_dblval"></a>  CDBVariant::m_dblVal

Türünde bir değer depolar **çift**.

### <a name="remarks"></a>Açıklamalar

`m_dblVal` Veri üyesine ait bir birleşime. Erişmeden önce `m_dblVal`, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` DBVT_DOUBLE için sonra ayarlanır `m_dblVal` geçerli bir değer içeriyor; Aksi takdirde, erişim `m_dblVal` güvenilir olmayan sonuçlar oluşturabilir.

##  <a name="m_dwtype"></a>  CDBVariant::m_dwType

Bu veri üyesi içinde depolanan değeri veri türünü içeren `CDBVariant` nesnenin birleşim veri üyesi.

### <a name="remarks"></a>Açıklamalar

Bu birleşim erişmeden önce değerini denetlemelidir `m_dwType` erişmek için hangi birleşim veri üyesi belirlemek için. İçin olası değerler aşağıdaki tabloda `m_dwType` ve karşılık gelen birleşim veri üyesi.

|m_dwType|Birleşim veri üyesi|
|---------------|-----------------------|
|DBVT_NULL|Bileşim üyesi erişimi için geçerli değil.|
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

##  <a name="m_fltval"></a>  CDBVariant::m_fltVal

Türünde bir değer depolar **float**.

### <a name="remarks"></a>Açıklamalar

`m_fltVal` Veri üyesine ait bir birleşime. Erişmeden önce `m_fltVal`, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` DBVT_SINGLE için sonra ayarlanır `m_fltVal` geçerli bir değer içeriyor; Aksi takdirde, erişim `m_fltVal` güvenilir olmayan sonuçlar oluşturabilir.

##  <a name="m_ival"></a>  CDBVariant::m_iVal

Türünde bir değer depolar **kısa**.

### <a name="remarks"></a>Açıklamalar

`m_iVal` Veri üyesine ait bir birleşime. Erişmeden önce `m_iVal`, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` DBVT_SHORT için sonra ayarlanır `m_iVal` geçerli bir değer içeriyor; Aksi takdirde, erişim `m_iVal` güvenilir olmayan sonuçlar oluşturabilir.

##  <a name="m_lval"></a>  CDBVariant::m_lVal

Türünde bir değer depolar **uzun**.

### <a name="remarks"></a>Açıklamalar

`m_lVal` Veri üyesine ait bir birleşime. Erişmeden önce `m_lVal`, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` DBVT_LONG için sonra ayarlanır `m_lVal` geçerli bir değer içeriyor; Aksi takdirde, erişim `m_lVal` güvenilir olmayan sonuçlar oluşturabilir.

##  <a name="m_pbinary"></a>  CDBVariant::m_pbinary

Türü bir nesneye bir işaretçi depolayan [CLongBinary](../../mfc/reference/clongbinary-class.md).

### <a name="remarks"></a>Açıklamalar

`m_pbinary` Veri üyesine ait bir birleşime. Erişmeden önce `m_pbinary`, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` DBVT_BINARY için sonra ayarlanır `m_pbinary` geçerli bir işaretçi içerir; Aksi takdirde, erişim `m_pbinary` güvenilir olmayan sonuçlar oluşturabilir.

##  <a name="m_pdate"></a>  CDBVariant::m_pdate

TIMESTAMP_STRUCT türünde bir nesne için bir işaretçi depolar.

### <a name="remarks"></a>Açıklamalar

`m_pdate` Veri üyesine ait bir birleşime. Erişmeden önce `m_pdate`, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` DBVT_DATE için sonra ayarlanır `m_pdate` geçerli bir işaretçi içerir; Aksi takdirde, erişim `m_pdate` güvenilir olmayan sonuçlar oluşturabilir.

TIMESTAMP_STRUCT veri türü hakkında daha fazla bilgi için Ek Yardım konusuna [C veri türleri](/previous-versions/windows/desktop/ms714556\(v=vs.85\)) ek d *ODBC Programcının Başvurusu* Windows SDK.

##  <a name="m_pstring"></a>  CDBVariant::m_pstring

Türü bir nesneye bir işaretçi depolayan [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Açıklamalar

`m_pstring` Veri üyesine ait bir birleşime. Erişmeden önce `m_pstring`, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` DBVT_STRING için sonra ayarlanır `m_pstring` geçerli bir işaretçi içerir; Aksi takdirde, erişim `m_pstring` güvenilir olmayan sonuçlar oluşturabilir.

##  <a name="m_pstringa"></a>  CDBVariant::m_pstringA

Bir ASCII yönelik bir işaretçi depolayan [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

`m_pstringA` Veri üyesine ait bir birleşime. Erişmeden önce `m_pstringA`, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` DBVT_ASTRING için sonra ayarlanır `m_pstringA` geçerli bir işaretçi içerir; Aksi takdirde, erişim `m_pstringA` güvenilir olmayan sonuçlar oluşturabilir.

##  <a name="m_pstringw"></a>  CDBVariant::m_pstringW

Bir geniş yönelik bir işaretçi depolayan [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

`m_pstringW` Veri üyesine ait bir birleşime. Erişmeden önce `m_pstringW`, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` DBVT_WSTRING için sonra ayarlanır `m_pstringW` geçerli bir işaretçi içerir; Aksi takdirde, erişim `m_pstringW` güvenilir olmayan sonuçlar oluşturabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
