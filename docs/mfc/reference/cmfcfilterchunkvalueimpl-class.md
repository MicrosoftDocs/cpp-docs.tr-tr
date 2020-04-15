---
title: CMFCFilterChunkValueImpl Sınıfı
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
ms.openlocfilehash: 2c90a873033516710077d31c8bb8af5fb5172ca6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367502"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl Sınıfı

Bu, hem yığın hem de özellik değeri çifti mantığını basitleştiren bir sınıftır.

## <a name="syntax"></a>Sözdizimi

```
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCFilterChunkValueImpl::~CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Nesneyi yok eder.|
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Nesneyi inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCFilterChunkValueImpl::Temizleyin](#clear)|ChunkValue temizler.|
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|Bu parçayı bir yığının özelliklerini açıklayan bir yapıya kopyalar.|
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|Bu öbek değerini diğer değerden başolarak laştırır.|
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|Yığın GUID alır.|
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|Yığın PID 'yi (özellik kimliği) alır.|
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|Yığın türü alır.|
|[CMFCFilterChunkValueImpl::GetString](#getstring)|Dize değerini alır.|
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|Değeri ayrılan bir propvariant olarak alır.|
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|Tahsis edilmemiş (iç değer) değeri verir.|
|[CMFCFilterChunkValueImpl::Geçerli](#isvalid)|Bu özellik değerinin geçerli olup olmadığını denetler.|
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|Fazla Yüklendi. Mülkü bir Boolean'a anahtarla ayarlar.|
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|Özelliği bir DWORD'e göre ayarlar.|
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Özelliği dosya zamanına göre ayarlar.|
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Özelliği bir int64'e göre ayarlar.|
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|Özelliği bir int'e anahtarla ayarlar.|
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|Özelliği bir UZUN'a göre ayarlar.|
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|Özelliği bir SystemTime'a göre ayarlar.|
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Özelliği bir Unicode dizesine göre ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|Ösyenin ortak özelliklerini ayarlayan bir yardımcı işlevi.|

## <a name="remarks"></a>Açıklamalar

Kullanmak için, sadece doğru tür bir CMFCFilterChunkValueImpl sınıf oluşturmak

Örnek:

CMFCFilterChunkValueImpl öbek;

hr = öbek. SetBoolValue(PKEY_IsAttachment, doğru);

or

hr = öbek. SetFileTimeValue(PKEY_ItemDate, ftLastModified);

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ATL::IFilterChunkValue`

[CMFCFiltreChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cmfcfilterchunkvalueimplclear"></a><a name="clear"></a>CMFCFilterChunkValueImpl::Temizleyin

ChunkValue temizler.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="cmfcfilterchunkvalueimpl"></a>CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl

Nesneyi inşa eder.

```
CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="_dtorcmfcfilterchunkvalueimpl"></a>CMFCFilterChunkValueImpl::~CMFCFilterChunkValueImpl

Nesneyi yok eder.

```
virtual ~CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplcopychunk"></a><a name="copychunk"></a>CMFCFilterChunkValueImpl::CopyChunk

Bu parçayı bir yığının özelliklerini açıklayan bir yapıya kopyalar.

```
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```

### <a name="parameters"></a>Parametreler

*pStatChunk*<br/>
Öskenin özelliklerini açıklayan hedef değerine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplcopyfrom"></a><a name="copyfrom"></a>CMFCFilterChunkValueImpl::CopyFrom

Bu öbek değerini diğer değerden başolarak laştırır.

```
void CopyFrom (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>Parametreler

*pDeğer*<br/>
Kopyalanması gereken kaynak değerini belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplgetchunkguid"></a><a name="getchunkguid"></a>CMFCFilterChunkValueImpl::GetChunkGUID

Yığın GUID alır.

```
REFGUID GetChunkGUID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Parçayı tanımlayan bir GUID'e başvuru.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplgetchunkpid"></a><a name="getchunkpid"></a>CMFCFilterChunkValueImpl::GetChunkPID

Yığın PID 'yi (özellik kimliği) alır.

```
DWORD GetChunkPID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özellik kimliğini içeren bir DWORD değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplgetchunktype"></a><a name="getchunktype"></a>CMFCFilterChunkValueImpl::GetChunkType

Yığın türünü alır.

```
CHUNKSTATE GetChunkType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öbek metin türü özelliği mi yoksa değer türü bir özellik mi olduğunu belirten bir CHUNKSTATE numaralandırılmış değer.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplgetstring"></a><a name="getstring"></a>CMFCFilterChunkValueImpl::GetString

Dize değerini alır.

```
CString &GetString();
```

### <a name="return-value"></a>Dönüş Değeri

Yığın değerini içeren bir dize.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplgetvalue"></a><a name="getvalue"></a>CMFCFilterChunkValueImpl::GetValue

Değeri ayrılan bir propvariant olarak alır.

```
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```

### <a name="parameters"></a>Parametreler

*ppPropVariant*<br/>
İşlev döndüğünde, bu parametre yığın değerini içerir.

### <a name="return-value"></a>Dönüş Değeri

S_OK PROPVARIANT başarıyla tahsis edildi ve yığın değeri başarıyla *ppPropVariant*kopyalandı; aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplgetvaluenoalloc"></a><a name="getvaluenoalloc"></a>CMFCFilterChunkValueImpl::GetValueNoAlloc

Tahsis edilmeyen (iç değer) değeri verir.

```
PROPVARIANT GetValueNoAlloc ();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öbek değerini verir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplisvalid"></a><a name="isvalid"></a>CMFCFilterChunkValueImpl::Geçerli

Bu özellik değerinin geçerli olup olmadığını denetler.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öbek değeri geçerliyse DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetboolvalue"></a><a name="setboolvalue"></a>CMFCFilterChunkValueImpl::SetBoolValue

Fazla Yüklendi. Mülkü bir Boolean'a anahtarla ayarlar.

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

*Pkey*<br/>
Özellik anahtarını belirtir.

*bVal*<br/>
Ayarlağacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu parçanın bir metin türü mü yoksa değer türü özelliği mi içerdiğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*Yerel ayar*<br/>
Bir metin yığınıyla ilişkili dil ve alt dil. Yığın yerel durum, belge dizini tarafından metnin düzgün sözcük bölmesini gerçekleştirmek için kullanılır. Öbek ne metin türü ne de veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan bir değer türüyse, bu alan yoksayılır.

*cwcLenSource*<br/>
Geçerli öbektilmiş kaynak metnin karakterleri uzunluk. Sıfır değeri, kaynak metin ve türetilen metin arasındaki karaktere göre yazışmaları belirtir. Sıfır olmayan bir değer, böyle bir doğrudan yazışmanın olmadığı anlamına gelir.

*cwcStartSource*<br/>
Türemiş bir öbek için kaynak metnin kaynak öbekte başladığı ofset.

*chunkBreakType*<br/>
Önceki parçayı geçerli yığından ayıran kesme türü. Değerler numaralandırma CHUNK_BREAKTYPE.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetchunk"></a><a name="setchunk"></a>CMFCFilterChunkValueImpl::SetChunk

Ösyenin ortak özelliklerini ayarlayan bir yardımcı işlevi.

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

*Pkey*<br/>
Özellik anahtarını belirtir.

*chunkType*<br/>
Bayraklar, bu parçanın bir metin türü mü yoksa değer türü özelliği mi içerdiğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*Yerel ayar*<br/>
Bir metin yığınıyla ilişkili dil ve alt dil. Yığın yerel durum, belge dizini tarafından metnin düzgün sözcük bölmesini gerçekleştirmek için kullanılır. Öbek ne metin türü ne de veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan bir değer türüyse, bu alan yoksayılır.

*cwcLenSource*<br/>
Geçerli öbektilmiş kaynak metnin karakterleri uzunluk. Sıfır değeri, kaynak metin ve türetilen metin arasındaki karaktere göre yazışmaları belirtir. Sıfır olmayan bir değer, böyle bir doğrudan yazışmanın olmadığı anlamına gelir.

*cwcStartSource*<br/>
Türemiş bir öbek için kaynak metnin kaynak öbekte başladığı ofset.

*chunkBreakType*<br/>
Önceki parçayı geçerli yığından ayıran kesme türü. Değerler numaralandırma CHUNK_BREAKTYPE.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetdwordvalue"></a><a name="setdwordvalue"></a>CMFCFilterChunkValueImpl::SetDwordValue

Özelliği bir DWORD'e göre ayarlayın.

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

*Pkey*<br/>
Özellik anahtarını belirtir.

*dwVal*<br/>
Ayarlağacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu parçanın bir metin türü mü yoksa değer türü özelliği mi içerdiğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*Yerel ayar*<br/>
Bir metin yığınıyla ilişkili dil ve alt dil. Yığın yerel durum, belge dizini tarafından metnin düzgün sözcük bölmesini gerçekleştirmek için kullanılır. Öbek ne metin türü ne de veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan bir değer türüyse, bu alan yoksayılır.

*cwcLenSource*<br/>
Geçerli öbektilmiş kaynak metnin karakterleri uzunluk. Sıfır değeri, kaynak metin ve türetilen metin arasındaki karaktere göre yazışmaları belirtir. Sıfır olmayan bir değer, böyle bir doğrudan yazışmanın olmadığı anlamına gelir.

*cwcStartSource*<br/>
Türemiş bir öbek için kaynak metnin kaynak öbekte başladığı ofset.

*chunkBreakType*<br/>
Önceki parçayı geçerli yığından ayıran kesme türü. Değerler numaralandırma CHUNK_BREAKTYPE.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetfiletimevalue"></a><a name="setfiletimevalue"></a>CMFCFilterChunkValueImpl::SetFileTimeValue

Özelliği bir dosya zamanı için anahtarla ayarlayın.

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

*Pkey*<br/>
Özellik anahtarını belirtir.

*dtVal*<br/>
Ayarlağacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu parçanın bir metin türü mü yoksa değer türü özelliği mi içerdiğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*Yerel ayar*<br/>
Bir metin yığınıyla ilişkili dil ve alt dil. Yığın yerel durum, belge dizini tarafından metnin düzgün sözcük bölmesini gerçekleştirmek için kullanılır. Öbek ne metin türü ne de veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan bir değer türüyse, bu alan yoksayılır.

*cwcLenSource*<br/>
Geçerli öbektilmiş kaynak metnin karakterleri uzunluk. Sıfır değeri, kaynak metin ve türetilen metin arasındaki karaktere göre yazışmaları belirtir. Sıfır olmayan bir değer, böyle bir doğrudan yazışmanın olmadığı anlamına gelir.

*cwcStartSource*<br/>
Türemiş bir öbek için kaynak metnin kaynak öbekte başladığı ofset.

*chunkBreakType*<br/>
Önceki parçayı geçerli yığından ayıran kesme türü. Değerler numaralandırma CHUNK_BREAKTYPE.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetint64value"></a><a name="setint64value"></a>CMFCFilterChunkValueImpl::SetInt64Value

Özelliği bir int64'e anahtarla ayarlayın.

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

*Pkey*<br/>
Özellik anahtarını belirtir.

*nVal*<br/>
Ayarlağacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu parçanın bir metin türü mü yoksa değer türü özelliği mi içerdiğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*Yerel ayar*<br/>
Bir metin yığınıyla ilişkili dil ve alt dil. Yığın yerel durum, belge dizini tarafından metnin düzgün sözcük bölmesini gerçekleştirmek için kullanılır. Öbek ne metin türü ne de veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan bir değer türüyse, bu alan yoksayılır.

*cwcLenSource*<br/>
Geçerli öbektilmiş kaynak metnin karakterleri uzunluk. Sıfır değeri, kaynak metin ve türetilen metin arasındaki karaktere göre yazışmaları belirtir. Sıfır olmayan bir değer, böyle bir doğrudan yazışmanın olmadığı anlamına gelir.

*cwcStartSource*<br/>
Türemiş bir öbek için kaynak metnin kaynak öbekte başladığı ofset.

*chunkBreakType*<br/>
Önceki parçayı geçerli yığından ayıran kesme türü. Değerler numaralandırma CHUNK_BREAKTYPE.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetintvalue"></a><a name="setintvalue"></a>CMFCFilterChunkValueImpl::SetIntValue

Özelliği bir int'e anahtarla ayarlayın.

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

*Pkey*<br/>
Özellik anahtarını belirtir.

*nVal*<br/>
Ayarlağacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu parçanın bir metin türü mü yoksa değer türü özelliği mi içerdiğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*Yerel ayar*<br/>
Bir metin yığınıyla ilişkili dil ve alt dil. Yığın yerel durum, belge dizini tarafından metnin düzgün sözcük bölmesini gerçekleştirmek için kullanılır. Öbek ne metin türü ne de veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan bir değer türüyse, bu alan yoksayılır.

*cwcLenSource*<br/>
Geçerli öbektilmiş kaynak metnin karakterleri uzunluk. Sıfır değeri, kaynak metin ve türetilen metin arasındaki karaktere göre yazışmaları belirtir. Sıfır olmayan bir değer, böyle bir doğrudan yazışmanın olmadığı anlamına gelir.

*cwcStartSource*<br/>
Türemiş bir öbek için kaynak metnin kaynak öbekte başladığı ofset.

*chunkBreakType*<br/>
Önceki parçayı geçerli yığından ayıran kesme türü. Değerler numaralandırma CHUNK_BREAKTYPE.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetlongvalue"></a><a name="setlongvalue"></a>CMFCFilterChunkValueImpl::SetLongValue

Özelliği bir UZUN'a göre ayarlayın.

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

*Pkey*<br/>
Özellik anahtarını belirtir.

*lVal*<br/>
Ayarlağacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu parçanın bir metin türü mü yoksa değer türü özelliği mi içerdiğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*Yerel ayar*<br/>
Bir metin yığınıyla ilişkili dil ve alt dil. Yığın yerel durum, belge dizini tarafından metnin düzgün sözcük bölmesini gerçekleştirmek için kullanılır. Öbek ne metin türü ne de veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan bir değer türüyse, bu alan yoksayılır.

*cwcLenSource*<br/>
Geçerli öbektilmiş kaynak metnin karakterleri uzunluk. Sıfır değeri, kaynak metin ve türetilen metin arasındaki karaktere göre yazışmaları belirtir. Sıfır olmayan bir değer, böyle bir doğrudan yazışmanın olmadığı anlamına gelir.

*cwcStartSource*<br/>
Türemiş bir öbek için kaynak metnin kaynak öbekte başladığı ofset.

*chunkBreakType*<br/>
Önceki parçayı geçerli yığından ayıran kesme türü. Değerler numaralandırma CHUNK_BREAKTYPE.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsetsystemtimevalue"></a><a name="setsystemtimevalue"></a>CMFCFilterChunkValueImpl::SetSystemTimeValue

Özelliği bir SystemTime'a göre ayarlar.

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

*Pkey*<br/>
Özellik anahtarını belirtir.

*Systemtıme*<br/>
Ayarlağacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu parçanın bir metin türü mü yoksa değer türü özelliği mi içerdiğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*Yerel ayar*<br/>
Bir metin yığınıyla ilişkili dil ve alt dil. Yığın yerel durum, belge dizini tarafından metnin düzgün sözcük bölmesini gerçekleştirmek için kullanılır. Öbek ne metin türü ne de veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan bir değer türüyse, bu alan yoksayılır.

*cwcLenSource*<br/>
Geçerli öbektilmiş kaynak metnin karakterleri uzunluk. Sıfır değeri, kaynak metin ve türetilen metin arasındaki karaktere göre yazışmaları belirtir. Sıfır olmayan bir değer, böyle bir doğrudan yazışmanın olmadığı anlamına gelir.

*cwcStartSource*<br/>
Türemiş bir öbek için kaynak metnin kaynak öbekte başladığı ofset.

*chunkBreakType*<br/>
Önceki parçayı geçerli yığından ayıran kesme türü. Değerler numaralandırma CHUNK_BREAKTYPE.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfilterchunkvalueimplsettextvalue"></a><a name="settextvalue"></a>CMFCFilterChunkValueImpl::SetTextValue

Özelliği bir Unicode dizesine göre ayarlar.

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

*Pkey*<br/>
Özellik anahtarını belirtir.

*pszValue*<br/>
Ayarlağacak öbek değerini belirtir.

*chunkType*<br/>
Bayraklar, bu parçanın bir metin türü mü yoksa değer türü özelliği mi içerdiğini gösterir. Bayrak değerleri CHUNKSTATE numaralandırmasından alınır.

*Yerel ayar*<br/>
Bir metin yığınıyla ilişkili dil ve alt dil. Yığın yerel durum, belge dizini tarafından metnin düzgün sözcük bölmesini gerçekleştirmek için kullanılır. Öbek ne metin türü ne de veri türü VT_LPWSTR, VT_LPSTR veya VT_BSTR olan bir değer türüyse, bu alan yoksayılır.

*cwcLenSource*<br/>
Geçerli öbektilmiş kaynak metnin karakterleri uzunluk. Sıfır değeri, kaynak metin ve türetilen metin arasındaki karaktere göre yazışmaları belirtir. Sıfır olmayan bir değer, böyle bir doğrudan yazışmanın olmadığı anlamına gelir.

*cwcStartSource*<br/>
Türemiş bir öbek için kaynak metnin kaynak öbekte başladığı ofset.

*chunkBreakType*<br/>
Önceki parçayı geçerli yığından ayıran kesme türü. Değerler numaralandırma CHUNK_BREAKTYPE.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde bir hata kodu.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
