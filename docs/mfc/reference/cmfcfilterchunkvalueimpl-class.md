---
description: 'Daha fazla bilgi edinin: CMFCFilterChunkValueImpl sınıfı'
title: CMFCFilterChunkValueImpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::Clear
- AFXWIN/CMFCFilterChunkValueImpl::CopyChunk
- AFXWIN/CMFCFilterChunkValueImpl::CopyFrom
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkGUID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkPID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkType
- AFXWIN/CMFCFilterChunkValueImpl::GetString
- AFXWIN/CMFCFilterChunkValueImpl::GetValue
- AFXWIN/CMFCFilterChunkValueImpl::GetValueNoAlloc
- AFXWIN/CMFCFilterChunkValueImpl::IsValid
- AFXWIN/CMFCFilterChunkValueImpl::SetBoolValue
- AFXWIN/CMFCFilterChunkValueImpl::SetDwordValue
- AFXWIN/CMFCFilterChunkValueImpl::SetFileTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetInt64Value
- AFXWIN/CMFCFilterChunkValueImpl::SetIntValue
- AFXWIN/CMFCFilterChunkValueImpl::SetLongValue
- AFXWIN/CMFCFilterChunkValueImpl::SetSystemTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetTextValue
- AFXWIN/CMFCFilterChunkValueImpl::SetChunk
helpviewer_keywords:
- CMFCFilterChunkValueImpl [MFC], CMFCFilterChunkValueImpl
- CMFCFilterChunkValueImpl [MFC], Clear
- CMFCFilterChunkValueImpl [MFC], CopyChunk
- CMFCFilterChunkValueImpl [MFC], CopyFrom
- CMFCFilterChunkValueImpl [MFC], GetChunkGUID
- CMFCFilterChunkValueImpl [MFC], GetChunkPID
- CMFCFilterChunkValueImpl [MFC], GetChunkType
- CMFCFilterChunkValueImpl [MFC], GetString
- CMFCFilterChunkValueImpl [MFC], GetValue
- CMFCFilterChunkValueImpl [MFC], GetValueNoAlloc
- CMFCFilterChunkValueImpl [MFC], IsValid
- CMFCFilterChunkValueImpl [MFC], SetBoolValue
- CMFCFilterChunkValueImpl [MFC], SetDwordValue
- CMFCFilterChunkValueImpl [MFC], SetFileTimeValue
- CMFCFilterChunkValueImpl [MFC], SetInt64Value
- CMFCFilterChunkValueImpl [MFC], SetIntValue
- CMFCFilterChunkValueImpl [MFC], SetLongValue
- CMFCFilterChunkValueImpl [MFC], SetSystemTimeValue
- CMFCFilterChunkValueImpl [MFC], SetTextValue
- CMFCFilterChunkValueImpl [MFC], SetChunk
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
ms.openlocfilehash: f2db7fdf6d6d24cb906b3190d34310e1f6724194
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265473"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl sınıfı

Bu, hem öbek hem de özellik değeri çifti mantığını kolaylaştıran bir sınıftır.

## <a name="syntax"></a>Syntax

```
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Nesne yapıları kaldırır.|
|[CMFCFilterChunkValueImpl:: CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Nesnesini oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCFilterChunkValueImpl:: Clear](#clear)|ChunkValue öğesini temizler.|
|[CMFCFilterChunkValueImpl:: CopyChunk](#copychunk)|Bu öbeği bir öbekin özelliklerini açıklayan bir yapıya kopyalar.|
|[CMFCFilterChunkValueImpl:: CopyFrom](#copyfrom)|Bu öbek değerini diğer değerden başlatır.|
|[CMFCFilterChunkValueImpl:: GetChunkGUID](#getchunkguid)|Öbek GUID 'INI alır.|
|[CMFCFilterChunkValueImpl:: GetChunkPID](#getchunkpid)|Öbek PID (özellik KIMLIĞI) alır.|
|[CMFCFilterChunkValueImpl:: GetChunkType](#getchunktype)|Öbek türünü alır.|
|[CMFCFilterChunkValueImpl:: GetString](#getstring)|Dize değerini alır.|
|[CMFCFilterChunkValueImpl:: GetValue](#getvalue)|Değeri ayrılmış bir propvariant olarak alır.|
|[CMFCFilterChunkValueImpl:: Getvaluenoayırma](#getvaluenoalloc)|Ayrılmamış (iç değer) değeri döndürür.|
|[CMFCFilterChunkValueImpl:: IsValid](#isvalid)|Bu özellik değerinin geçerli olup olmadığını denetler.|
|[CMFCFilterChunkValueImpl:: SetBoolValue](#setboolvalue)|Fazla Yüklendi. Özelliği anahtara göre bir Boole değerine ayarlar.|
|[CMFCFilterChunkValueImpl:: SetDwordValue](#setdwordvalue)|Özelliği anahtara göre DWORD olarak ayarlar.|
|[CMFCFilterChunkValueImpl:: SetFileTimeValue](#setfiletimevalue)|Özelliği anahtar olarak bir filetime olarak ayarlar.|
|[CMFCFilterChunkValueImpl:: SetInt64Value](#setint64value)|Özelliği anahtara göre bir Int64 olarak ayarlar.|
|[CMFCFilterChunkValueImpl:: SetIntValue](#setintvalue)|Özelliği anahtar olarak bir int olarak ayarlar.|
|[CMFCFilterChunkValueImpl:: SetLongValue](#setlongvalue)|Özelliği anahtara göre bir LONG olarak ayarlar.|
|[CMFCFilterChunkValueImpl:: SetSystemTimeValue](#setsystemtimevalue)|Özelliği anahtara göre bir SystemTime olarak ayarlar.|
|[CMFCFilterChunkValueImpl:: SetTextValue](#settextvalue)|Özelliği, bir Unicode dizesine anahtar olarak ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCFilterChunkValueImpl:: SetChunk](#setchunk)|Öbekin ortak özelliklerini ayarlayan bir yardımcı işlevi.|

## <a name="remarks"></a>Açıklamalar

Kullanmak için doğru türde bir CMFCFilterChunkValueImpl sınıfı oluşturmanız yeterlidir

Örnek:

CMFCFilterChunkValueImpl öbeği;

HR = öbek. SetBoolValue (PKEY_IsAttachment, true);

veya

HR = öbek. SetFileTimeValue (PKEY_ItemDate, ftLastModified);

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ATL::IFilterChunkValue`

[CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cmfcfilterchunkvalueimplclear"></a><a name="clear"></a> CMFCFilterChunkValueImpl:: Clear

ChunkValue öğesini temizler.

```cpp
void Clear();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="cmfcfilterchunkvalueimpl"></a> CMFCFilterChunkValueImpl:: CMFCFilterChunkValueImpl

Nesnesini oluşturur.

```
CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="_dtorcmfcfilterchunkvalueimpl"></a> CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl

Nesne yapıları kaldırır.

```
virtual ~CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplcopychunk"></a><a name="copychunk"></a> CMFCFilterChunkValueImpl:: CopyChunk

Bu öbeği bir öbekin özelliklerini açıklayan bir yapıya kopyalar.

```
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```

### <a name="parameters"></a>Parametreler

*pStatChunk*<br/>
Öbekin özelliklerini açıklayan hedef değer işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplcopyfrom"></a><a name="copyfrom"></a> CMFCFilterChunkValueImpl:: CopyFrom

Bu öbek değerini diğer değerden başlatır.

```cpp
void CopyFrom (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>Parametreler

*pValue*<br/>
Kopyalamanın kaynak değerini belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplgetchunkguid"></a><a name="getchunkguid"></a> CMFCFilterChunkValueImpl:: GetChunkGUID

Öbek GUID 'INI alır.

```
REFGUID GetChunkGUID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öbeği tanımlayan bir GUID başvurusu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplgetchunkpid"></a><a name="getchunkpid"></a> CMFCFilterChunkValueImpl:: GetChunkPID

Öbek PID (özellik KIMLIĞI) alır.

```
DWORD GetChunkPID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özellik KIMLIĞINI içeren bir DWORD değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplgetchunktype"></a><a name="getchunktype"></a> CMFCFilterChunkValueImpl:: GetChunkType

Öbek türünü alır.

```
CHUNKSTATE GetChunkType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öbekin bir metin türü özelliği mi yoksa bir değer türü özelliği mi olduğunu belirten bir CHUNKSTATE numaralandırılmış değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplgetstring"></a><a name="getstring"></a> CMFCFilterChunkValueImpl:: GetString

Dize değerini alır.

```
CString &GetString();
```

### <a name="return-value"></a>Dönüş Değeri

Öbek değerini içeren bir dize.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplgetvalue"></a><a name="getvalue"></a> CMFCFilterChunkValueImpl:: GetValue

Değeri ayrılmış bir propvariant olarak alır.

```
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```

### <a name="parameters"></a>Parametreler

*ppPropVariant*<br/>
İşlev döndüğünde, bu parametre öbek değerini içerir.

### <a name="return-value"></a>Dönüş Değeri

PROPVARıANT başarıyla ayrıldıysa ve öbek değeri *Pppropvarıant*'a başarıyla kopyalanmışsa S_OK. Aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplgetvaluenoalloc"></a><a name="getvaluenoalloc"></a> CMFCFilterChunkValueImpl:: Getvaluenoayırma

Ayrılmayan (iç değer) değeri döndürür.

```
PROPVARIANT GetValueNoAlloc ();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öbek değerini döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplisvalid"></a><a name="isvalid"></a> CMFCFilterChunkValueImpl:: IsValid

Bu özellik değerinin geçerli olup olmadığını denetler.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öbek değeri geçerliyse TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetboolvalue"></a><a name="setboolvalue"></a> CMFCFilterChunkValueImpl:: SetBoolValue

Fazla Yüklendi. Özelliği anahtara göre bir Boole değerine ayarlar.

```
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);

HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    VARIANT_BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametreler

*PKEY*<br/>
Bir özellik anahtarı belirtir.

*bVal*<br/>
Ayarlanacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu öbekte bir metin türü veya değer türü özelliği içerip içermediğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*locale*<br/>
Metin öbeğiyle ilişkili dil ve alt dil. Öbek yerel ayarı, metnin doğru sözcük bölümünü gerçekleştirmek için belge Dizin oluşturucular tarafından kullanılır. Öbek metin türü veya veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan değer türünde değilse, bu alan yok sayılır.

*cwcLenSource*<br/>
Geçerli öbekten türetildiği kaynak metnin karakterlerinde uzunluğu. Sıfır değeri, kaynak metin ile türetilmiş metin arasındaki karakterle karakter yazışmaları anlamına gelir. Sıfır dışında bir değer, böyle bir doğrudan yazışın bulunmadığı anlamına gelir.

*cwcStartSource*<br/>
Türetilmiş bir öbek için kaynak metnin kaynak öbekte başladığı konum.

*chunkBreakType*<br/>
Önceki öbeği geçerli öbekten ayıran kesmenin türü. Değerler CHUNK_BREAKTYPE numaralandırmadır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetchunk"></a><a name="setchunk"></a> CMFCFilterChunkValueImpl:: SetChunk

Öbekin ortak özelliklerini ayarlayan bir yardımcı işlevi.

```
HRESULT SetChunk(
    REFPROPERTYKEY pkey,
    CHUNKSTATE chunkType=CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametreler

*PKEY*<br/>
Bir özellik anahtarı belirtir.

*chunkType*<br/>
Bayraklar, bu öbekte bir metin türü veya değer türü özelliği içerip içermediğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*locale*<br/>
Metin öbeğiyle ilişkili dil ve alt dil. Öbek yerel ayarı, metnin doğru sözcük bölümünü gerçekleştirmek için belge Dizin oluşturucular tarafından kullanılır. Öbek metin türü veya veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan değer türünde değilse, bu alan yok sayılır.

*cwcLenSource*<br/>
Geçerli öbekten türetildiği kaynak metnin karakterlerinde uzunluğu. Sıfır değeri, kaynak metin ile türetilmiş metin arasındaki karakterle karakter yazışmaları anlamına gelir. Sıfır dışında bir değer, böyle bir doğrudan yazışın bulunmadığı anlamına gelir.

*cwcStartSource*<br/>
Türetilmiş bir öbek için kaynak metnin kaynak öbekte başladığı konum.

*chunkBreakType*<br/>
Önceki öbeği geçerli öbekten ayıran kesmenin türü. Değerler CHUNK_BREAKTYPE numaralandırmadır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetdwordvalue"></a><a name="setdwordvalue"></a> CMFCFilterChunkValueImpl:: SetDwordValue

Özelliği anahtar olarak DWORD olarak ayarlayın.

```
HRESULT SetDwordValue(
    REFPROPERTYKEY pkey,
    DWORD dwVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametreler

*PKEY*<br/>
Bir özellik anahtarı belirtir.

*dwVal*<br/>
Ayarlanacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu öbekte bir metin türü veya değer türü özelliği içerip içermediğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*locale*<br/>
Metin öbeğiyle ilişkili dil ve alt dil. Öbek yerel ayarı, metnin doğru sözcük bölümünü gerçekleştirmek için belge Dizin oluşturucular tarafından kullanılır. Öbek metin türü veya veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan değer türünde değilse, bu alan yok sayılır.

*cwcLenSource*<br/>
Geçerli öbekten türetildiği kaynak metnin karakterlerinde uzunluğu. Sıfır değeri, kaynak metin ile türetilmiş metin arasındaki karakterle karakter yazışmaları anlamına gelir. Sıfır dışında bir değer, böyle bir doğrudan yazışın bulunmadığı anlamına gelir.

*cwcStartSource*<br/>
Türetilmiş bir öbek için kaynak metnin kaynak öbekte başladığı konum.

*chunkBreakType*<br/>
Önceki öbeği geçerli öbekten ayıran kesmenin türü. Değerler CHUNK_BREAKTYPE numaralandırmadır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetfiletimevalue"></a><a name="setfiletimevalue"></a> CMFCFilterChunkValueImpl:: SetFileTimeValue

Özelliği anahtar olarak bir filetime olarak ayarlayın.

```
HRESULT SetFileTimeValue(
    REFPROPERTYKEY pkey,
    FILETIME dtVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametreler

*PKEY*<br/>
Bir özellik anahtarı belirtir.

*dtVal*<br/>
Ayarlanacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu öbekte bir metin türü veya değer türü özelliği içerip içermediğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*locale*<br/>
Metin öbeğiyle ilişkili dil ve alt dil. Öbek yerel ayarı, metnin doğru sözcük bölümünü gerçekleştirmek için belge Dizin oluşturucular tarafından kullanılır. Öbek metin türü veya veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan değer türünde değilse, bu alan yok sayılır.

*cwcLenSource*<br/>
Geçerli öbekten türetildiği kaynak metnin karakterlerinde uzunluğu. Sıfır değeri, kaynak metin ile türetilmiş metin arasındaki karakterle karakter yazışmaları anlamına gelir. Sıfır dışında bir değer, böyle bir doğrudan yazışın bulunmadığı anlamına gelir.

*cwcStartSource*<br/>
Türetilmiş bir öbek için kaynak metnin kaynak öbekte başladığı konum.

*chunkBreakType*<br/>
Önceki öbeği geçerli öbekten ayıran kesmenin türü. Değerler CHUNK_BREAKTYPE numaralandırmadır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetint64value"></a><a name="setint64value"></a> CMFCFilterChunkValueImpl:: SetInt64Value

Özelliği anahtar olarak bir Int64 olarak ayarlayın.

```
HRESULT SetInt64Value(
    REFPROPERTYKEY pkey,
    __int64 nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametreler

*PKEY*<br/>
Bir özellik anahtarı belirtir.

*nVal*<br/>
Ayarlanacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu öbekte bir metin türü veya değer türü özelliği içerip içermediğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*locale*<br/>
Metin öbeğiyle ilişkili dil ve alt dil. Öbek yerel ayarı, metnin doğru sözcük bölümünü gerçekleştirmek için belge Dizin oluşturucular tarafından kullanılır. Öbek metin türü veya veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan değer türünde değilse, bu alan yok sayılır.

*cwcLenSource*<br/>
Geçerli öbekten türetildiği kaynak metnin karakterlerinde uzunluğu. Sıfır değeri, kaynak metin ile türetilmiş metin arasındaki karakterle karakter yazışmaları anlamına gelir. Sıfır dışında bir değer, böyle bir doğrudan yazışın bulunmadığı anlamına gelir.

*cwcStartSource*<br/>
Türetilmiş bir öbek için kaynak metnin kaynak öbekte başladığı konum.

*chunkBreakType*<br/>
Önceki öbeği geçerli öbekten ayıran kesmenin türü. Değerler CHUNK_BREAKTYPE numaralandırmadır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetintvalue"></a><a name="setintvalue"></a> CMFCFilterChunkValueImpl:: SetIntValue

Özelliği anahtar olarak bir int olarak ayarlayın.

```
HRESULT SetIntValue(
    REFPROPERTYKEY pkey,
    int nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametreler

*PKEY*<br/>
Bir özellik anahtarı belirtir.

*nVal*<br/>
Ayarlanacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu öbekte bir metin türü veya değer türü özelliği içerip içermediğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*locale*<br/>
Metin öbeğiyle ilişkili dil ve alt dil. Öbek yerel ayarı, metnin doğru sözcük bölümünü gerçekleştirmek için belge Dizin oluşturucular tarafından kullanılır. Öbek metin türü veya veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan değer türünde değilse, bu alan yok sayılır.

*cwcLenSource*<br/>
Geçerli öbekten türetildiği kaynak metnin karakterlerinde uzunluğu. Sıfır değeri, kaynak metin ile türetilmiş metin arasındaki karakterle karakter yazışmaları anlamına gelir. Sıfır dışında bir değer, böyle bir doğrudan yazışın bulunmadığı anlamına gelir.

*cwcStartSource*<br/>
Türetilmiş bir öbek için kaynak metnin kaynak öbekte başladığı konum.

*chunkBreakType*<br/>
Önceki öbeği geçerli öbekten ayıran kesmenin türü. Değerler CHUNK_BREAKTYPE numaralandırmadır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetlongvalue"></a><a name="setlongvalue"></a> CMFCFilterChunkValueImpl:: SetLongValue

Özelliği anahtara göre bir LONG olarak ayarlayın.

```
HRESULT SetLongValue(
    REFPROPERTYKEY pkey,
    long lVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametreler

*PKEY*<br/>
Bir özellik anahtarı belirtir.

*lVal*<br/>
Ayarlanacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu öbekte bir metin türü veya değer türü özelliği içerip içermediğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*locale*<br/>
Metin öbeğiyle ilişkili dil ve alt dil. Öbek yerel ayarı, metnin doğru sözcük bölümünü gerçekleştirmek için belge Dizin oluşturucular tarafından kullanılır. Öbek metin türü veya veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan değer türünde değilse, bu alan yok sayılır.

*cwcLenSource*<br/>
Geçerli öbekten türetildiği kaynak metnin karakterlerinde uzunluğu. Sıfır değeri, kaynak metin ile türetilmiş metin arasındaki karakterle karakter yazışmaları anlamına gelir. Sıfır dışında bir değer, böyle bir doğrudan yazışın bulunmadığı anlamına gelir.

*cwcStartSource*<br/>
Türetilmiş bir öbek için kaynak metnin kaynak öbekte başladığı konum.

*chunkBreakType*<br/>
Önceki öbeği geçerli öbekten ayıran kesmenin türü. Değerler CHUNK_BREAKTYPE numaralandırmadır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetsystemtimevalue"></a><a name="setsystemtimevalue"></a> CMFCFilterChunkValueImpl:: SetSystemTimeValue

Özelliği anahtara göre bir SystemTime olarak ayarlar.

```
HRESULT SetSystemTimeValue(
    REFPROPERTYKEY pkey,
    const SYSTEMTIME& systemTime,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametreler

*PKEY*<br/>
Bir özellik anahtarı belirtir.

*SYSTEMTIME*<br/>
Ayarlanacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu öbekte bir metin türü veya değer türü özelliği içerip içermediğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*locale*<br/>
Metin öbeğiyle ilişkili dil ve alt dil. Öbek yerel ayarı, metnin doğru sözcük bölümünü gerçekleştirmek için belge Dizin oluşturucular tarafından kullanılır. Öbek metin türü veya veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan değer türünde değilse, bu alan yok sayılır.

*cwcLenSource*<br/>
Geçerli öbekten türetildiği kaynak metnin karakterlerinde uzunluğu. Sıfır değeri, kaynak metin ile türetilmiş metin arasındaki karakterle karakter yazışmaları anlamına gelir. Sıfır dışında bir değer, böyle bir doğrudan yazışın bulunmadığı anlamına gelir.

*cwcStartSource*<br/>
Türetilmiş bir öbek için kaynak metnin kaynak öbekte başladığı konum.

*chunkBreakType*<br/>
Önceki öbeği geçerli öbekten ayıran kesmenin türü. Değerler CHUNK_BREAKTYPE numaralandırmadır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsettextvalue"></a><a name="settextvalue"></a> CMFCFilterChunkValueImpl:: SetTextValue

Özelliği, bir Unicode dizesine anahtar olarak ayarlar.

```
HRESULT SetTextValue(
    REFPROPERTYKEY pkey,
    LPCTSTR pszValue,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametreler

*PKEY*<br/>
Bir özellik anahtarı belirtir.

*pszValue*<br/>
Ayarlanacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu öbekte bir metin türü veya değer türü özelliği içerip içermediğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*locale*<br/>
Metin öbeğiyle ilişkili dil ve alt dil. Öbek yerel ayarı, metnin doğru sözcük bölümünü gerçekleştirmek için belge Dizin oluşturucular tarafından kullanılır. Öbek metin türü veya veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan değer türünde değilse, bu alan yok sayılır.

*cwcLenSource*<br/>
Geçerli öbekten türetildiği kaynak metnin karakterlerinde uzunluğu. Sıfır değeri, kaynak metin ile türetilmiş metin arasındaki karakterle karakter yazışmaları anlamına gelir. Sıfır dışında bir değer, böyle bir doğrudan yazışın bulunmadığı anlamına gelir.

*cwcStartSource*<br/>
Türetilmiş bir öbek için kaynak metnin kaynak öbekte başladığı konum.

*chunkBreakType*<br/>
Önceki öbeği geçerli öbekten ayıran kesmenin türü. Değerler CHUNK_BREAKTYPE numaralandırmadır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
