---
title: Cmfcfilterchunkvalueımpl sınıfı | Microsoft Docs
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
ms.openlocfilehash: fdce28feddfca0789306a16f8dc6d047dc375120
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42464473"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>Cmfcfilterchunkvalueımpl sınıfı
Bu, öbek hem özellik değeri çiftinin mantığını basitleştirir bir sınıftır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Cmfcfilterchunkvalueımpl:: ~ Cmfcfilterchunkvalueımpl](#_dtorcmfcfilterchunkvalueimpl)|Nesne destructs.|  
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Bir nesne oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::Clear](#clear)|ChunkValue temizler.|  
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|Bu öbek, öbek özelliklerini açıklayan bir yapıya kopyalar.|  
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|Başka bir değer bu öbeğin değerini başlatır.|  
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|GUID öbeğin alır.|  
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|(Özellik kimliği) PID öbeğin alır.|  
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|Alır türü öbek.|  
|[CMFCFilterChunkValueImpl::GetString](#getstring)|Dize değerini alır.|  
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|Değeri, ayrılmış bir propvariant alır.|  
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|Değeri ayrılmamış döndürür (iç değer).|  
|[CMFCFilterChunkValueImpl::IsValid](#isvalid)|Bu özellik değeri geçerli olup olmadığını denetler.|  
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|Fazla Yüklendi. Özelliği, bir mantıksal anahtara göre ayarlar.|  
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|DWORD anahtarı tarafından özelliği ayarlar.|  
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Özelliği bir fıletıme anahtarına göre ayarlar.|  
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Özelliği bir Int64 anahtarına göre ayarlar.|  
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|İnt anahtar tarafından özelliği ayarlar.|  
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|LONG anahtar tarafından özelliği ayarlar.|  
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|Özelliği bir SYSTEMTIME anahtarına göre ayarlar.|  
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Özelliği, bir Unicode dize anahtarına göre ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|Öbek'ın ortak özelliklerini ayarlar yardımcı işlevi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanmak için yalnızca doğru türde bir Cmfcfilterchunkvalueımpl sınıfı oluşturun  
  
 Örnek:  
  
 Cmfcfilterchunkvalueımpl öbek;  
  
 hr = öbek. SetBoolValue(PKEY_IsAttachment, true);  
  
 veya  
  
 hr = öbek. SetFileTimeValue (PKEY_ItemDate, ftLastModified);  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ATL::IFilterChunkValue`  
  
 [Cmfcfilterchunkvalueımpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="clear"></a>  CMFCFilterChunkValueImpl::Clear  
 ChunkValue temizler.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="cmfcfilterchunkvalueimpl"></a>  CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl  
 Bir nesne oluşturur.  
  
```  
CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="_dtorcmfcfilterchunkvalueimpl"></a>  Cmfcfilterchunkvalueımpl:: ~ Cmfcfilterchunkvalueımpl  
 Nesne destructs.  
  
```  
virtual ~CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="copychunk"></a>  CMFCFilterChunkValueImpl::CopyChunk  
 Bu öbek, öbek özelliklerini açıklayan bir yapıya kopyalar.  
  
```  
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```  
  
### <a name="parameters"></a>Parametreler  
 *pStatChunk*  
 Hedef değer öbek özelliklerini açıklayan bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="copyfrom"></a>  CMFCFilterChunkValueImpl::CopyFrom  
 Başka bir değer bu öbeğin değerini başlatır.  
  
```  
void CopyFrom (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Parametreler  
 *pValue*  
 Kopyalanacak kaynak değeri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getchunkguid"></a>  CMFCFilterChunkValueImpl::GetChunkGUID  
 GUID öbeğin alır.  
  
```  
REFGUID GetChunkGUID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öbek tanımlayan bir GUID başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getchunkpid"></a>  CMFCFilterChunkValueImpl::GetChunkPID  
 (Özellik kimliği) PID öbeğin alır.  
  
```  
DWORD GetChunkPID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özellik kimliğini içeren bir DWORD değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getchunktype"></a>  CMFCFilterChunkValueImpl::GetChunkType  
 Öbek türünü alır.  
  
```  
CHUNKSTATE GetChunkType() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli öbekteki metin türünde özellik veya değer türü özellik olup olmadığını belirtir CHUNKSTATE numaralandırılmış değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getstring"></a>  CMFCFilterChunkValueImpl::GetString  
 Dize değerini alır.  
  
```  
CString &GetString();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öbek değeri içeren bir dize.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getvalue"></a>  CMFCFilterChunkValueImpl::GetValue  
 Değeri, ayrılmış bir propvariant alır.  
  
```  
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```  
  
### <a name="parameters"></a>Parametreler  
 *ppPropVariant*  
 Bu parametre, işlevi döndüğünde, öbek değeri içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 PROPVARIANT başarıyla ayrıldı ve Öbek değeri için başarıyla kopyalandı S_OK *ppPropVariant*; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getvaluenoalloc"></a>  CMFCFilterChunkValueImpl::GetValueNoAlloc  
 Ayrılmamış (iç değer) değeri döndürür.  
  
```  
PROPVARIANT GetValueNoAlloc ();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli öbek değeri döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isvalid"></a>  CMFCFilterChunkValueImpl::IsValid  
 Bu özellik değeri geçerli olup olmadığını denetler.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli öbek değeri geçerliyse TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setboolvalue"></a>  CMFCFilterChunkValueImpl::SetBoolValue  
 Fazla Yüklendi. Özelliği, bir mantıksal anahtara göre ayarlar.  
  
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
 Bir özelliğin anahtarını belirtir.  
  
 *bVal*  
 Ayarlanacak öbek değeri belirtir.  
  
 *chunkType*  
 Bayrakları bu öbeğin metin türü veya değer türü özellik içerip içermediğini belirtir. Bayrak değerleri CHUNKSTATE sabit listesinden alınmış alınır.  
  
 *Yerel ayar*  
 Dil ve metnin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Karakterleri geçerli öbekteki türetildiği kaynak metnin uzunluğu. Kaynak metni ve türetilmiş metin arasındaki ilişkiyi karakteri tek bir sıfır değeri belirtir. Sıfır dışında bir değeri, bu tür bir doğrudan yazışma bulunmadığını gösterir.  
  
 *cwcStartSource*  
 Türetilen bir öbek için kaynak metin kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbeğin geçerli öbekteki ayıran sonu türü. CHUNK_BREAKTYPE sabit değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setchunk"></a>  CMFCFilterChunkValueImpl::SetChunk  
 Öbek'ın ortak özelliklerini ayarlar yardımcı işlevi.  
  
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
 Bir özelliğin anahtarını belirtir.  
  
 *chunkType*  
 Bayrakları bu öbeğin metin türü veya değer türü özellik içerip içermediğini belirtir. Bayrak değerleri CHUNKSTATE sabit listesinden alınmış alınır.  
  
 *Yerel ayar*  
 Dil ve metnin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Karakterleri geçerli öbekteki türetildiği kaynak metnin uzunluğu. Kaynak metni ve türetilmiş metin arasındaki ilişkiyi karakteri tek bir sıfır değeri belirtir. Sıfır dışında bir değeri, bu tür bir doğrudan yazışma bulunmadığını gösterir.  
  
 *cwcStartSource*  
 Türetilen bir öbek için kaynak metin kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbeğin geçerli öbekteki ayıran sonu türü. CHUNK_BREAKTYPE sabit değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi halde hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setdwordvalue"></a>  CMFCFilterChunkValueImpl::SetDwordValue  
 Özelliği, DWORD anahtarı olarak ayarlayın.  
  
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
 Bir özelliğin anahtarını belirtir.  
  
 *dwVal*  
 Ayarlanacak öbek değeri belirtir.  
  
 *chunkType*  
 Bayrakları bu öbeğin metin türü veya değer türü özellik içerip içermediğini belirtir. Bayrak değerleri CHUNKSTATE sabit listesinden alınmış alınır.  
  
 *Yerel ayar*  
 Dil ve metnin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Karakterleri geçerli öbekteki türetildiği kaynak metnin uzunluğu. Kaynak metni ve türetilmiş metin arasındaki ilişkiyi karakteri tek bir sıfır değeri belirtir. Sıfır dışında bir değeri, bu tür bir doğrudan yazışma bulunmadığını gösterir.  
  
 *cwcStartSource*  
 Türetilen bir öbek için kaynak metin kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbeğin geçerli öbekteki ayıran sonu türü. CHUNK_BREAKTYPE sabit değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde bir hata kodu.  
  
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
 Bir özelliğin anahtarını belirtir.  
  
 *dtVal*  
 Ayarlanacak öbek değeri belirtir.  
  
 *chunkType*  
 Bayrakları bu öbeğin metin türü veya değer türü özellik içerip içermediğini belirtir. Bayrak değerleri CHUNKSTATE sabit listesinden alınmış alınır.  
  
 *Yerel ayar*  
 Dil ve metnin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Karakterleri geçerli öbekteki türetildiği kaynak metnin uzunluğu. Kaynak metni ve türetilmiş metin arasındaki ilişkiyi karakteri tek bir sıfır değeri belirtir. Sıfır dışında bir değeri, bu tür bir doğrudan yazışma bulunmadığını gösterir.  
  
 *cwcStartSource*  
 Türetilen bir öbek için kaynak metin kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbeğin geçerli öbekteki ayıran sonu türü. CHUNK_BREAKTYPE sabit değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde bir hata kodu.  
  
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
 Bir özelliğin anahtarını belirtir.  
  
 *nVal*  
 Ayarlanacak öbek değeri belirtir.  
  
 *chunkType*  
 Bayrakları bu öbeğin metin türü veya değer türü özellik içerip içermediğini belirtir. Bayrak değerleri CHUNKSTATE sabit listesinden alınmış alınır.  
  
 *Yerel ayar*  
 Dil ve metnin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Karakterleri geçerli öbekteki türetildiği kaynak metnin uzunluğu. Kaynak metni ve türetilmiş metin arasındaki ilişkiyi karakteri tek bir sıfır değeri belirtir. Sıfır dışında bir değeri, bu tür bir doğrudan yazışma bulunmadığını gösterir.  
  
 *cwcStartSource*  
 Türetilen bir öbek için kaynak metin kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbeğin geçerli öbekteki ayıran sonu türü. CHUNK_BREAKTYPE sabit değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde bir hata kodu.  
  
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
 Bir özelliğin anahtarını belirtir.  
  
 *nVal*  
 Ayarlanacak öbek değeri belirtir.  
  
 *chunkType*  
 Bayrakları bu öbeğin metin türü veya değer türü özellik içerip içermediğini belirtir. Bayrak değerleri CHUNKSTATE sabit listesinden alınmış alınır.  
  
 *Yerel ayar*  
 Dil ve metnin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Karakterleri geçerli öbekteki türetildiği kaynak metnin uzunluğu. Kaynak metni ve türetilmiş metin arasındaki ilişkiyi karakteri tek bir sıfır değeri belirtir. Sıfır dışında bir değeri, bu tür bir doğrudan yazışma bulunmadığını gösterir.  
  
 *cwcStartSource*  
 Türetilen bir öbek için kaynak metin kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbeğin geçerli öbekteki ayıran sonu türü. CHUNK_BREAKTYPE sabit değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde bir hata kodu.  
  
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
 Bir özelliğin anahtarını belirtir.  
  
 *lVal*  
 Ayarlanacak öbek değeri belirtir.  
  
 *chunkType*  
 Bayrakları bu öbeğin metin türü veya değer türü özellik içerip içermediğini belirtir. Bayrak değerleri CHUNKSTATE sabit listesinden alınmış alınır.  
  
 *Yerel ayar*  
 Dil ve metnin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Karakterleri geçerli öbekteki türetildiği kaynak metnin uzunluğu. Kaynak metni ve türetilmiş metin arasındaki ilişkiyi karakteri tek bir sıfır değeri belirtir. Sıfır dışında bir değeri, bu tür bir doğrudan yazışma bulunmadığını gösterir.  
  
 *cwcStartSource*  
 Türetilen bir öbek için kaynak metin kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbeğin geçerli öbekteki ayıran sonu türü. CHUNK_BREAKTYPE sabit değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde bir hata kodu.  
  
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
 Bir özelliğin anahtarını belirtir.  
  
 *SYSTEMTIME*  
 Ayarlanacak öbek değeri belirtir.  
  
 *chunkType*  
 Bayrakları bu öbeğin metin türü veya değer türü özellik içerip içermediğini belirtir. Bayrak değerleri CHUNKSTATE sabit listesinden alınmış alınır.  
  
 *Yerel ayar*  
 Dil ve metnin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Karakterleri geçerli öbekteki türetildiği kaynak metnin uzunluğu. Kaynak metni ve türetilmiş metin arasındaki ilişkiyi karakteri tek bir sıfır değeri belirtir. Sıfır dışında bir değeri, bu tür bir doğrudan yazışma bulunmadığını gösterir.  
  
 *cwcStartSource*  
 Türetilen bir öbek için kaynak metin kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbeğin geçerli öbekteki ayıran sonu türü. CHUNK_BREAKTYPE sabit değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settextvalue"></a>  CMFCFilterChunkValueImpl::SetTextValue  
 Özelliği, bir Unicode dize anahtarına göre ayarlar.  
  
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
 Bir özelliğin anahtarını belirtir.  
  
 *pszValue*  
 Ayarlanacak öbek değeri belirtir.  
  
 *chunkType*  
 Bayrakları bu öbeğin metin türü veya değer türü özellik içerip içermediğini belirtir. Bayrak değerleri CHUNKSTATE sabit listesinden alınmış alınır.  
  
 *Yerel ayar*  
 Dil ve metnin bir Öbek ile ilişkili alt dili. Öbek yerel belge Dizin Oluşturucu tarafından metnin uygun sözcük gerçekleştirmek için kullanılır. Öbek metin türü ne VT_LPWSTR, VT_LPSTR veya VT_BSTR veri türündeki bir değer türü ise, bu alan göz ardı edilir.  
  
 *cwcLenSource*  
 Karakterleri geçerli öbekteki türetildiği kaynak metnin uzunluğu. Kaynak metni ve türetilmiş metin arasındaki ilişkiyi karakteri tek bir sıfır değeri belirtir. Sıfır dışında bir değeri, bu tür bir doğrudan yazışma bulunmadığını gösterir.  
  
 *cwcStartSource*  
 Türetilen bir öbek için kaynak metin kaynak öbekte başladığı uzaklığı.  
  
 *chunkBreakType*  
 Önceki öbeğin geçerli öbekteki ayıran sonu türü. CHUNK_BREAKTYPE sabit değerlerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde bir hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
