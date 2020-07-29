---
title: CDBVariant sınıfı
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
ms.openlocfilehash: 45a478a5ca6cfb4d9b976a29eae2ae7d98fdd6ee
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223089"
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
|[Cdbvarıant:: CDBVariant](#cdbvariant)|Bir `CDBVariant` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cdbvarıant:: Clear](#clear)|Nesneyi temizler `CDBVariant` .|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDBVariant:: m_dwType](#m_dwtype)|Şu anda depolanan değerin veri türünü içerir. `DWORD` yazın.|

### <a name="public-union-members"></a>Genel birleşim üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDBVariant:: m_boolVal](#m_boolval)|**Bool**türünde bir değer içerir.|
|[CDBVariant:: m_chVal](#m_chval)|Türünde bir değer içerir **`unsigned char`** .|
|[CDBVariant:: m_dblVal](#m_dblval)|Türünde bir değer içerir **`double`** .|
|[CDBVariant:: m_fltVal](#m_fltval)|Türünde bir değer içerir **`float`** .|
|[CDBVariant:: m_iVal](#m_ival)|Türünde bir değer içerir **`short`** .|
|[CDBVariant:: m_lVal](#m_lval)|Türünde bir değer içerir **`long`** .|
|[CDBVariant:: m_pbinary](#m_pbinary)|Türünde bir nesne için bir işaretçi içerir `CLongBinary` .|
|[CDBVariant:: m_pdate](#m_pdate)|**TIMESTAMP_STRUCT**türünde bir nesne için bir işaretçi içerir.|
|[CDBVariant:: m_pstring](#m_pstring)|Türünde bir nesne için bir işaretçi içerir `CString` .|
|[CDBVariant:: m_pstringA](#m_pstringa)|Bir ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine bir işaretçi depolar.|
|[CDBVariant:: m_pstringW](#m_pstringw)|Geniş bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

`CDBVariant`taban sınıfına sahip değildir.

`CDBVariant`[Cotavariant](../../mfc/reference/colevariant-class.md)ile benzerdir; Ancak `CDBVariant` OLE kullanmaz. `CDBVariant`değerin veri türü hakkında endişelenmeden bir değer depolamanıza olanak sağlar. `CDBVariant`bir birleşimde depolanan geçerli değerin veri türünü izler.

Sınıf [CRecordset](../../mfc/reference/crecordset-class.md) , `CDBVariant` üç üye işlevdeki nesneleri kullanır: `GetFieldValue` , `GetBookmark` ve `SetBookmark` . Örneğin, `GetFieldValue` verileri bir sütunda dinamik olarak almanıza olanak sağlar. Sütunun veri türü çalışma zamanında bilinmeyebilir, çünkü `GetFieldValue` `CDBVariant` sütunun verilerini depolamak için bir nesnesi kullanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDBVariant`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="cdbvariantcdbvariant"></a><a name="cdbvariant"></a>Cdbvarıant:: CDBVariant

NULL bir `CDBVariant` nesne oluşturur.

```
CDBVariant();
```

### <a name="remarks"></a>Açıklamalar

[M_dwType](#m_dwtype) veri üyesini DBVT_NULL olarak ayarlar.

## <a name="cdbvariantclear"></a><a name="clear"></a>Cdbvarıant:: Clear

Nesneyi temizlemek için bu üye işlevini çağırın `CDBVariant` .

```cpp
void Clear();
```

### <a name="remarks"></a>Açıklamalar

[M_dwType](#m_dwtype) veri üyesinin değeri DBVT_DATE, DBVT_STRING veya DBVT_BINARY ise, `Clear` birleşim işaretçisi üyesiyle ilişkili belleği serbest bırakır. `Clear``m_dwType`DBVT_NULL olarak ayarlar.

`CDBVariant`Yıkıcı çağırır `Clear` .

## <a name="cdbvariantm_boolval"></a><a name="m_boolval"></a>CDBVariant:: m_boolVal

BOOL türünde bir değer depolar.

### <a name="remarks"></a>Açıklamalar

`m_boolVal`Veri üyesi bir birleşime aittir. Erişmeden önce `m_boolVal` , önce [CDBVariant:: m_dwType](#m_dwtype)değerini denetleyin. `m_dwType`DBVT_BOOL olarak ayarlandıysa, `m_boolVal` geçerli bir değer içerir; Aksi takdirde, erişilmesi `m_boolVal` güvenilir olmayan sonuçlar üretir.

## <a name="cdbvariantm_chval"></a><a name="m_chval"></a>CDBVariant:: m_chVal

Türünde bir değer depolar **`unsigned char`** .

### <a name="remarks"></a>Açıklamalar

`m_chVal`Veri üyesi bir birleşime aittir. Erişmeden önce `m_chVal` , önce [CDBVariant:: m_dwType](#m_dwtype)değerini denetleyin. `m_dwType`DBVT_UCHAR olarak ayarlandıysa, `m_chVal` geçerli bir değer içerir; Aksi takdirde, erişilmesi güvenilir olmayan `m_chVal` sonuçlar oluşturacaktır.

## <a name="cdbvariantm_dblval"></a><a name="m_dblval"></a>CDBVariant:: m_dblVal

Türünde bir değer depolar **`double`** .

### <a name="remarks"></a>Açıklamalar

`m_dblVal`Veri üyesi bir birleşime aittir. Erişmeden önce `m_dblVal` , önce [CDBVariant:: m_dwType](#m_dwtype)değerini denetleyin. `m_dwType`DBVT_DOUBLE olarak ayarlandıysa, `m_dblVal` geçerli bir değer içerir; Aksi takdirde, erişilmesi güvenilir olmayan `m_dblVal` sonuçlar oluşturacaktır.

## <a name="cdbvariantm_dwtype"></a><a name="m_dwtype"></a>CDBVariant:: m_dwType

Bu veri üyesi, şu anda `CDBVariant` nesnenin Union veri üyesinde depolanmış olan değer için veri türünü içerir.

### <a name="remarks"></a>Açıklamalar

Bu birleşime erişmeden önce, `m_dwType` hangi birleşim verisi üyesinin erişebileceğini belirleyebilmek için değerini denetlemeniz gerekir. Aşağıdaki tabloda, için olası değerler `m_dwType` ve ilgili UNION veri üyesi listelenmektedir.

|m_dwType|Birleşim veri üyesi|
|---------------|-----------------------|
|DBVT_NULL|Hiçbir birleşim üyesi erişim için geçerli değil.|
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

## <a name="cdbvariantm_fltval"></a><a name="m_fltval"></a>CDBVariant:: m_fltVal

Türünde bir değer depolar **`float`** .

### <a name="remarks"></a>Açıklamalar

`m_fltVal`Veri üyesi bir birleşime aittir. Erişmeden önce `m_fltVal` , önce [CDBVariant:: m_dwType](#m_dwtype)değerini denetleyin. `m_dwType`DBVT_SINGLE olarak ayarlandıysa, `m_fltVal` geçerli bir değer içerir; Aksi takdirde, erişilmesi güvenilir olmayan `m_fltVal` sonuçlar oluşturacaktır.

## <a name="cdbvariantm_ival"></a><a name="m_ival"></a>CDBVariant:: m_iVal

Türünde bir değer depolar **`short`** .

### <a name="remarks"></a>Açıklamalar

`m_iVal`Veri üyesi bir birleşime aittir. Erişmeden önce `m_iVal` , önce [CDBVariant:: m_dwType](#m_dwtype)değerini denetleyin. `m_dwType`DBVT_SHORT olarak ayarlandıysa, `m_iVal` geçerli bir değer içerir; Aksi takdirde, erişilmesi güvenilir olmayan `m_iVal` sonuçlar oluşturacaktır.

## <a name="cdbvariantm_lval"></a><a name="m_lval"></a>CDBVariant:: m_lVal

Türünde bir değer depolar **`long`** .

### <a name="remarks"></a>Açıklamalar

`m_lVal`Veri üyesi bir birleşime aittir. Erişmeden önce `m_lVal` , önce [CDBVariant:: m_dwType](#m_dwtype)değerini denetleyin. `m_dwType`DBVT_LONG olarak ayarlandıysa, `m_lVal` geçerli bir değer içerir; Aksi takdirde, erişilmesi güvenilir olmayan `m_lVal` sonuçlar oluşturacaktır.

## <a name="cdbvariantm_pbinary"></a><a name="m_pbinary"></a>CDBVariant:: m_pbinary

[CLongBinary](../../mfc/reference/clongbinary-class.md)türünde bir nesne için bir işaretçi depolar.

### <a name="remarks"></a>Açıklamalar

`m_pbinary`Veri üyesi bir birleşime aittir. Erişmeden önce `m_pbinary` , önce [CDBVariant:: m_dwType](#m_dwtype)değerini denetleyin. `m_dwType`DBVT_BINARY olarak ayarlandıysa, `m_pbinary` geçerli bir işaretçi içerir; Aksi takdirde, erişim `m_pbinary` güvenilmez sonuçlar üretir.

## <a name="cdbvariantm_pdate"></a><a name="m_pdate"></a>CDBVariant:: m_pdate

TIMESTAMP_STRUCT türündeki bir nesneye bir işaretçi depolar.

### <a name="remarks"></a>Açıklamalar

`m_pdate`Veri üyesi bir birleşime aittir. Erişmeden önce `m_pdate` , önce [CDBVariant:: m_dwType](#m_dwtype)değerini denetleyin. `m_dwType`DBVT_DATE olarak ayarlandıysa, `m_pdate` geçerli bir işaretçi içerir; Aksi takdirde, erişim `m_pdate` güvenilmez sonuçlar üretir.

TIMESTAMP_STRUCT veri türü hakkında daha fazla bilgi için, Windows SDK *ODBC Programmer 's başvurusunun* ek D bölümünde [C veri türleri](/sql/odbc/reference/appendixes/c-data-types) konusuna bakın.

## <a name="cdbvariantm_pstring"></a><a name="m_pstring"></a>CDBVariant:: m_pstring

[CString](../../atl-mfc-shared/reference/cstringt-class.md)türünde bir nesne için bir işaretçi depolar.

### <a name="remarks"></a>Açıklamalar

`m_pstring`Veri üyesi bir birleşime aittir. Erişmeden önce `m_pstring` , önce [CDBVariant:: m_dwType](#m_dwtype)değerini denetleyin. `m_dwType`DBVT_STRING olarak ayarlandıysa, `m_pstring` geçerli bir işaretçi içerir; Aksi takdirde, erişim `m_pstring` güvenilmez sonuçlar üretir.

## <a name="cdbvariantm_pstringa"></a><a name="m_pstringa"></a>CDBVariant:: m_pstringA

Bir ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine bir işaretçi depolar.

### <a name="remarks"></a>Açıklamalar

`m_pstringA`Veri üyesi bir birleşime aittir. Erişmeden önce `m_pstringA` , önce [CDBVariant:: m_dwType](#m_dwtype)değerini denetleyin. `m_dwType`DBVT_ASTRING olarak ayarlandıysa, `m_pstringA` geçerli bir işaretçi içerir; Aksi takdirde, erişim `m_pstringA` güvenilmez sonuçlar üretir.

## <a name="cdbvariantm_pstringw"></a><a name="m_pstringw"></a>CDBVariant:: m_pstringW

Geniş bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine bir işaretçi depolar.

### <a name="remarks"></a>Açıklamalar

`m_pstringW`Veri üyesi bir birleşime aittir. Erişmeden önce `m_pstringW` , önce [CDBVariant:: m_dwType](#m_dwtype)değerini denetleyin. `m_dwType`DBVT_WSTRING olarak ayarlandıysa, `m_pstringW` geçerli bir işaretçi içerir; Aksi takdirde, erişim `m_pstringW` güvenilmez sonuçlar üretir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset sınıfı](../../mfc/reference/crecordset-class.md)
