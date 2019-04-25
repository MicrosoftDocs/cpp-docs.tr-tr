---
title: CTokenGroups sınıfı
ms.date: 11/04/2016
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
ms.openlocfilehash: 934d746dafafb39c2ffc3477c59c95914d270196
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277363"
---
# <a name="ctokengroups-class"></a>CTokenGroups sınıfı

Bu sınıf için bir sarmalayıcı olan `TOKEN_GROUPS` yapısı.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CTokenGroups
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CTokenGroups::CTokenGroups](#ctokengroups)|Oluşturucu.|
|[CTokenGroups:: ~ CTokenGroups](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTokenGroups::Add](#add)|Ekler bir `CSid` veya mevcut `TOKEN_GROUPS` için yapı `CTokenGroups` nesne.|
|[CTokenGroups::Delete](#delete)|Siler bir `CSid` ve onun ilişkili öznitelikleri `CTokenGroups` nesne.|
|[CTokenGroups::DeleteAll](#deleteall)|Tüm siler `CSid` nesneleri ve bunların ilişkili öznitelikleri `CTokenGroups` nesne.|
|[CTokenGroups::GetCount](#getcount)|Sayısını döndürür `CSid` nesneler ve bulunan ilişkili öznitelikleri `CTokenGroups` nesne.|
|[CTokenGroups::GetLength](#getlength)|Boyutunu döndürür `CTokenGroups` nesne.|
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|Bir işaretçi alır `TOKEN_GROUPS` yapısı.|
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|Alır `CSid` nesneleri ve öznitelikleri ait `CTokenGroups` nesne.|
|[CTokenGroups::LookupSid](#lookupsid)|İle ilişkili özniteliklerini alır bir `CSid` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CTokenGroups::operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|Yayınları `CTokenGroups` nesne işaretçisi `TOKEN_GROUPS` yapısı.|
|[CTokenGroups::operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

Bir [erişim belirteci](/windows/desktop/SecAuthZ/access-tokens) bir işlem veya iş parçacığı güvenlik bağlamı açıklayan ve Windows sisteminde oturum açmış her kullanıcı için ayrılan bir nesnedir.

`CTokenGroups` İçin bir sarmalayıcı sınıftır [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) bir erişim belirteci grup güvenlik tanımlayıcılarını (SID'ler) hakkında bilgi içeren yapıya,.

Windows, erişim denetimi modeli için bir giriş için bkz [erişim denetimi](/windows/desktop/SecAuthZ/access-control) Windows SDK.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="add"></a>  CTokenGroups::Add

Ekler bir `CSid` veya mevcut `TOKEN_GROUPS` için yapı `CTokenGroups` nesne.

```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
A [CSID](../../atl/reference/csid-class.md) nesne.

*dwAttributes*<br/>
Öznitelikleri ile ilişkilendirilecek `CSid` nesne.

*rTokenGroups*<br/>
A [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) yapısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntemler bir veya daha fazla `CSid` nesneleri ve bunların ilişkili öznitelikleri `CTokenGroups` nesne.

##  <a name="ctokengroups"></a>  CTokenGroups::CTokenGroups

Oluşturucu.

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
`CTokenGroups` Nesne veya [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) yapısı oluşturmak hangi `CTokenGroups` nesne.

### <a name="remarks"></a>Açıklamalar

`CTokenGroups` Nesne isteğe bağlı olarak oluşturulabilir kullanarak bir `TOKEN_GROUPS` yapısı veya önceden tanımlanmış `CTokenGroups` nesne.

##  <a name="dtor"></a>  CTokenGroups:: ~ CTokenGroups

Yıkıcı.

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>Açıklamalar

Yok edici ayrılan tüm kaynakları serbest bırakır.

##  <a name="delete"></a>  CTokenGroups::Delete

Siler bir `CSid` ve onun ilişkili öznitelikleri `CTokenGroups` nesne.

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
[CSID](../../atl/reference/csid-class.md) nesnenin kendisi için öznitelikler ve güvenlik tanımlayıcısı (SID) kaldırılması gerekir.

### <a name="return-value"></a>Dönüş Değeri

Gerekirse true döndürür `CSid` yanlış aksi kaldırılır.

##  <a name="deleteall"></a>  CTokenGroups::DeleteAll

Tüm siler `CSid` nesneleri ve bunların ilişkili öznitelikleri `CTokenGroups` nesne.

```
void DeleteAll() throw();
```

##  <a name="getcount"></a>  CTokenGroups::GetCount

Sayısını döndürür `CSid` bulunan nesneleri `CTokenGroups`.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Sayısını döndürür [CSID](../../atl/reference/csid-class.md) nesneler ve bulunan öznitelikleriyle ilişkili `CTokenGroups` nesne.

##  <a name="getlength"></a>  CTokenGroups::GetLength

Boyutunu döndürür `CTokenGroup` nesne.

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>Açıklamalar

Toplam boyutunu döndürür `CTokenGroup` bayt nesne.

##  <a name="getptoken_groups"></a>  CTokenGroups::GetPTOKEN_GROUPS

Bir işaretçi alır `TOKEN_GROUPS` yapısı.

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi alır [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) ait yapısı `CTokenGroups` erişim belirteci nesnesi.

##  <a name="getsidsandattributes"></a>  CTokenGroups::GetSidsAndAttributes

Alır `CSid` nesneleri ve (isteğe bağlı olarak) ait öznitelikler `CTokenGroups` nesne.

```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSids*<br/>
Bir dizi işaretçi [CSID](../../atl/reference/csid-class.md) nesneleri.

*pAttributes*<br/>
DWORD bir dizi için işaretçi. Bu parametre belirtilmemişse veya NULL ise, öznitelikleri alınmamış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tüm listeleyeceksiniz `CSid` bulunan nesneleri `CTokenGroups` nesne ve bunları ve (isteğe bağlı olarak) özniteliği bayrakları dizi nesneleri yerleştirin.

##  <a name="lookupsid"></a>  CTokenGroups::LookupSid

İle ilişkili özniteliklerini alır bir `CSid` nesne.

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
[CSID](../../atl/reference/csid-class.md) nesne.

*pdwAttributes*<br/>
Hangi kabul edileceği bir DWORD işaretçisine `CSid` nesnenin öznitelik. Belirtilmemiş veya boş ise, öznitelik alınmayacak.

### <a name="return-value"></a>Dönüş Değeri

Gerekirse true döndürür `CSid` bulunursa false Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Ayarı *pdwAttributes* için NULL varlığını onaylayan bir yol sağlar `CSid` özniteliğe erişme olmadan. Bu yöntem erişim hakları denetlemek için kullanılmamalıdır olduğunu unutmayın. Uygulamaların yerine kullanması gereken [CAccessToken::CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) yöntemi.

##  <a name="operator_eq"></a>  CTokenGroups::operator =

Atama işleci.

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
`CTokenGroups` Nesne veya [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) atamak için yapı `CTokenGroups` nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CTokenGroups` nesne.

##  <a name="operator_const_token_groups__star"></a>  CTokenGroups::operator const TOKEN_GROUPS *

Bir işaretçi değerine çevirir `TOKEN_GROUPS` yapısı.

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

Bir işaretçi değerine çevirir [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) yapısı.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenliği örneği](../../overview/visual-cpp-samples.md)<br/>
[CSid Sınıfı](../../atl/reference/csid-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
