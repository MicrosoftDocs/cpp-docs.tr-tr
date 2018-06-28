---
title: CMFCFilterChunkValueImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1f2fcdedb6b01025b06e4384ec2c32e95d08b6e
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040135"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl sınıfı
Bu öbek ve özellik değeri çifti mantığı kolaylaştıran bir sınıftır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Nesne destructs.|  
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::Clear](#clear)|ChunkValue temizler.|  
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|Bu öbek bir öbek özelliklerini açıklayan bir yapısını kopyalar.|  
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|Diğer değerden bu öbek değer başlatır.|  
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|GUID öbek alır.|  
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|Öbek PID (özellik kimliği) alır.|  
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|Alır türü öbek.|  
|[CMFCFilterChunkValueImpl::GetString](#getstring)|Alır dize değeri.|  
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|Değeri ayrılmış bir propvariant alır.|  
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|Ayrılmış döndürür (iç değeri) değeri.|  
|[CMFCFilterChunkValueImpl::IsValid](#isvalid)|Bu özellik değeri geçerli olup olmadığını denetler.|  
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|Fazla Yüklendi. Bir mantıksal anahtar tarafından özelliği ayarlar.|  
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|Özelliği bir DWORD anahtarına göre ayarlar.|  
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Özelliği bir fıletıme anahtarına göre ayarlar.|  
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Özelliği bir Int64 anahtarına göre ayarlar.|  
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|Özelliği bir tamsayı anahtarına göre ayarlar|  
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|LONG anahtar tarafından özelliği ayarlar.|  
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|Özelliği bir SYSTEMTIME anahtarına göre ayarlar.|  
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Özelliği bir UNICODE dizesi anahtarına göre ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|Öbek ait ortak özellikleri ayarlar yardımcı bir işlev.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanmak için yalnızca doğru türde CMFCFilterChunkValueImpl sınıfı oluşturun  
  
 Örnek:  
  
 CMFCFilterChunkValueImpl öbek;  
  
 hr = öbek. SetBoolValue(PKEY_IsAttachment, true);  
  
 veya  
  
 hr = öbek. SetFileTimeValue (PKEY_ItemDate, ftLastModified);  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ATL::IFilterChunkValue`  
  
 [CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="clear"></a>  CMFCFilterChunkValueImpl::Clear  
 ChunkValue temizler.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="cmfcfilterchunkvalueimpl"></a>  CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl  
 Nesnesi oluşturur.  
  
```  
CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="_dtorcmfcfilterchunkvalueimpl"></a>  CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl  
 Nesne destructs.  
  
```  
virtual ~CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="copychunk"></a>  CMFCFilterChunkValueImpl::CopyChunk  
 Bu öbek bir öbek özelliklerini açıklayan bir yapısını kopyalar.  
  
```  
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```  
  
### <a name="parameters"></a>Parametreler  
 *pStatChunk*  
 Öbek özelliklerini açıklayan hedef değeri için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="copyfrom"></a>  CMFCFilterChunkValueImpl::CopyFrom  
 Diğer değerden bu öbek değer başlatır.  
  
```  
void CopyFrom (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Parametreler  
 *pValue*  
 Kopyalanacak kaynak değerini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getchunkguid"></a>  CMFCFilterChunkValueImpl::GetChunkGUID  
 GUID öbek alır.  
  
```  
REFGUID GetChunkGUID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öbek tanımlayan bir GUID referansı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getchunkpid"></a>  CMFCFilterChunkValueImpl::GetChunkPID  
 Öbek PID (özellik kimliği) alır.  
  
```  
DWORD GetChunkPID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özellik kimliği içeren bir DWORD değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getchunktype"></a>  CMFCFilterChunkValueImpl::GetChunkType  
 Öbek türünü alır.  
  
```  
CHUNKSTATE GetChunkType() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli öbek metin type özelliği ya da bir değer türü özelliği olup olmadığını belirtir numaralandırılan CHUNKSTATE değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getstring"></a>  CMFCFilterChunkValueImpl::GetString  
 Dize değerini alır.  
  
```  
CString &GetString();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öbek değerini içeren bir dize.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getvalue"></a>  CMFCFilterChunkValueImpl::GetValue  
 Değeri ayrılmış bir propvariant alır.  
  
```  
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```  
  
### <a name="parameters"></a>Parametreler  
 *ppPropVariant*  
 İşlevi döndüğünde, bu parametre öbek değer içeriyor.  
  
### <a name="return-value"></a>Dönüş Değeri  
 PROPVARIANT tahsis edildiğinde başarıyla ve Öbek değeri için başarıyla kopyalandı S_OK *ppPropVariant*; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getvaluenoalloc"></a>  CMFCFilterChunkValueImpl::GetValueNoAlloc  
 Ayrılmış (iç değeri) değeri döndürür.  
  
```  
PROPVARIANT GetValueNoAlloc ();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli öbek değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isvalid"></a>  CMFCFilterChunkValueImpl::IsValid  
 Bu özellik değeri geçerli olup olmadığını denetler.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Geçerli öbek değeri geçerliyse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setboolvalue"></a>  CMFCFilterChunkValueImpl::SetBoolValue  
 Fazla Yüklendi. Bir mantıksal anahtar tarafından özelliği ayarlar.  
  
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
 *PKEY*  
 Bir özellik anahtarı belirtir.  
  
 *bVal*  
 Ayarlanacak öbek değer belirtir.  
  
 *chunkType*  
 Bayrakları bu öbek bir metin yazın veya bir değer türü özelliği içerip içermediğini belirtir. Bayrak değeri CHUNKSTATE numaralandırma içinden alınır.  
  
 *Yerel ayar*  
 Dil ve metin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Geçerli öbek türetildiği kaynak metni karakter cinsinden uzunluğu. Sıfır değeri karakteri tek kaynak metni ve türetilen metin arasındaki ilişkiyi belirtir. Sıfır olmayan bir değer bu tür doğrudan yazışmaları bulunduğu anlamına gelir.  
  
 *cwcStartSource*  
 Türetilen bir öbek kaynak metni kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbek geçerli öbek ayıran sonu türü. CHUNK_BREAKTYPE numaralandırma içinden değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setchunk"></a>  CMFCFilterChunkValueImpl::SetChunk  
 Öbek ait ortak özellikleri ayarlar yardımcı bir işlev.  
  
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
 *PKEY*  
 Bir özellik anahtarı belirtir.  
  
 *chunkType*  
 Bayrakları bu öbek bir metin yazın veya bir değer türü özelliği içerip içermediğini belirtir. Bayrak değeri CHUNKSTATE numaralandırma içinden alınır.  
  
 *Yerel ayar*  
 Dil ve metin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Geçerli öbek türetildiği kaynak metni karakter cinsinden uzunluğu. Sıfır değeri karakteri tek kaynak metni ve türetilen metin arasındaki ilişkiyi belirtir. Sıfır olmayan bir değer bu tür doğrudan yazışmaları bulunduğu anlamına gelir.  
  
 *cwcStartSource*  
 Türetilen bir öbek kaynak metni kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbek geçerli öbek ayıran sonu türü. CHUNK_BREAKTYPE numaralandırma içinden değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setdwordvalue"></a>  CMFCFilterChunkValueImpl::SetDwordValue  
 DWORD anahtarına göre özelliğini ayarlayın.  
  
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
 *PKEY*  
 Bir özellik anahtarı belirtir.  
  
 *dwVal*  
 Ayarlanacak öbek değer belirtir.  
  
 *chunkType*  
 Bayrakları bu öbek bir metin yazın veya bir değer türü özelliği içerip içermediğini belirtir. Bayrak değeri CHUNKSTATE numaralandırma içinden alınır.  
  
 *Yerel ayar*  
 Dil ve metin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Geçerli öbek türetildiği kaynak metni karakter cinsinden uzunluğu. Sıfır değeri karakteri tek kaynak metni ve türetilen metin arasındaki ilişkiyi belirtir. Sıfır olmayan bir değer bu tür doğrudan yazışmaları bulunduğu anlamına gelir.  
  
 *cwcStartSource*  
 Türetilen bir öbek kaynak metni kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbek geçerli öbek ayıran sonu türü. CHUNK_BREAKTYPE numaralandırma içinden değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setfiletimevalue"></a>  CMFCFilterChunkValueImpl::SetFileTimeValue  
 Bir fıletıme anahtarına göre özelliğini ayarlayın.  
  
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
 *PKEY*  
 Bir özellik anahtarı belirtir.  
  
 *dtVal*  
 Ayarlanacak öbek değer belirtir.  
  
 *chunkType*  
 Bayrakları bu öbek bir metin yazın veya bir değer türü özelliği içerip içermediğini belirtir. Bayrak değeri CHUNKSTATE numaralandırma içinden alınır.  
  
 *Yerel ayar*  
 Dil ve metin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Geçerli öbek türetildiği kaynak metni karakter cinsinden uzunluğu. Sıfır değeri karakteri tek kaynak metni ve türetilen metin arasındaki ilişkiyi belirtir. Sıfır olmayan bir değer bu tür doğrudan yazışmaları bulunduğu anlamına gelir.  
  
 *cwcStartSource*  
 Türetilen bir öbek kaynak metni kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbek geçerli öbek ayıran sonu türü. CHUNK_BREAKTYPE numaralandırma içinden değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setint64value"></a>  CMFCFilterChunkValueImpl::SetInt64Value  
 Bir Int64 anahtarına göre özelliğini ayarlayın.  
  
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
 *PKEY*  
 Bir özellik anahtarı belirtir.  
  
 *nVal*  
 Ayarlanacak öbek değer belirtir.  
  
 *chunkType*  
 Bayrakları bu öbek bir metin yazın veya bir değer türü özelliği içerip içermediğini belirtir. Bayrak değeri CHUNKSTATE numaralandırma içinden alınır.  
  
 *Yerel ayar*  
 Dil ve metin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Geçerli öbek türetildiği kaynak metni karakter cinsinden uzunluğu. Sıfır değeri karakteri tek kaynak metni ve türetilen metin arasındaki ilişkiyi belirtir. Sıfır olmayan bir değer bu tür doğrudan yazışmaları bulunduğu anlamına gelir.  
  
 *cwcStartSource*  
 Türetilen bir öbek kaynak metni kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbek geçerli öbek ayıran sonu türü. CHUNK_BREAKTYPE numaralandırma içinden değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setintvalue"></a>  CMFCFilterChunkValueImpl::SetIntValue  
 İnt anahtar tarafından özelliğini ayarlayın  
  
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
 *PKEY*  
 Bir özellik anahtarı belirtir.  
  
 *nVal*  
 Ayarlanacak öbek değer belirtir.  
  
 *chunkType*  
 Bayrakları bu öbek bir metin yazın veya bir değer türü özelliği içerip içermediğini belirtir. Bayrak değeri CHUNKSTATE numaralandırma içinden alınır.  
  
 *Yerel ayar*  
 Dil ve metin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Geçerli öbek türetildiği kaynak metni karakter cinsinden uzunluğu. Sıfır değeri karakteri tek kaynak metni ve türetilen metin arasındaki ilişkiyi belirtir. Sıfır olmayan bir değer bu tür doğrudan yazışmaları bulunduğu anlamına gelir.  
  
 *cwcStartSource*  
 Türetilen bir öbek kaynak metni kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbek geçerli öbek ayıran sonu türü. CHUNK_BREAKTYPE numaralandırma içinden değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setlongvalue"></a>  CMFCFilterChunkValueImpl::SetLongValue  
 LONG anahtar tarafından özelliğini ayarlayın.  
  
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
 *PKEY*  
 Bir özellik anahtarı belirtir.  
  
 *lVal*  
 Ayarlanacak öbek değer belirtir.  
  
 *chunkType*  
 Bayrakları bu öbek bir metin yazın veya bir değer türü özelliği içerip içermediğini belirtir. Bayrak değeri CHUNKSTATE numaralandırma içinden alınır.  
  
 *Yerel ayar*  
 Dil ve metin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Geçerli öbek türetildiği kaynak metni karakter cinsinden uzunluğu. Sıfır değeri karakteri tek kaynak metni ve türetilen metin arasındaki ilişkiyi belirtir. Sıfır olmayan bir değer bu tür doğrudan yazışmaları bulunduğu anlamına gelir.  
  
 *cwcStartSource*  
 Türetilen bir öbek kaynak metni kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbek geçerli öbek ayıran sonu türü. CHUNK_BREAKTYPE numaralandırma içinden değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setsystemtimevalue"></a>  CMFCFilterChunkValueImpl::SetSystemTimeValue  
 Özelliği bir SYSTEMTIME anahtarına göre ayarlar.  
  
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
 *PKEY*  
 Bir özellik anahtarı belirtir.  
  
 *SYSTEMTIME*  
 Ayarlanacak öbek değer belirtir.  
  
 *chunkType*  
 Bayrakları bu öbek bir metin yazın veya bir değer türü özelliği içerip içermediğini belirtir. Bayrak değeri CHUNKSTATE numaralandırma içinden alınır.  
  
 *Yerel ayar*  
 Dil ve metin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Geçerli öbek türetildiği kaynak metni karakter cinsinden uzunluğu. Sıfır değeri karakteri tek kaynak metni ve türetilen metin arasındaki ilişkiyi belirtir. Sıfır olmayan bir değer bu tür doğrudan yazışmaları bulunduğu anlamına gelir.  
  
 *cwcStartSource*  
 Türetilen bir öbek kaynak metni kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbek geçerli öbek ayıran sonu türü. CHUNK_BREAKTYPE numaralandırma içinden değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settextvalue"></a>  CMFCFilterChunkValueImpl::SetTextValue  
 Özelliği bir UNICODE dizesi anahtarına göre ayarlar.  
  
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
 *PKEY*  
 Bir özellik anahtarı belirtir.  
  
 *pszValue*  
 Ayarlanacak öbek değer belirtir.  
  
 *chunkType*  
 Bayrakları bu öbek bir metin yazın veya bir değer türü özelliği içerip içermediğini belirtir. Bayrak değeri CHUNKSTATE numaralandırma içinden alınır.  
  
 *Yerel ayar*  
 Dil ve metin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Geçerli öbek türetildiği kaynak metni karakter cinsinden uzunluğu. Sıfır değeri karakteri tek kaynak metni ve türetilen metin arasındaki ilişkiyi belirtir. Sıfır olmayan bir değer bu tür doğrudan yazışmaları bulunduğu anlamına gelir.  
  
 *cwcStartSource*  
 Türetilen bir öbek kaynak metni kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbek geçerli öbek ayıran sonu türü. CHUNK_BREAKTYPE numaralandırma içinden değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
