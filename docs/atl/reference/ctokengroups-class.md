---
title: CTokenGroups Sınıfı
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
ms.openlocfilehash: 1e9d21c59eb5efabf036fbc938a40de2c4b7a0b7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330557"
---
# <a name="ctokengroups-class"></a>CTokenGroups Sınıfı

Bu sınıf `TOKEN_GROUPS` yapı için bir sarmalayıcıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CTokenGroups
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CTokenGroups::CTokenGroups](#ctokengroups)|Oluşturucu.|
|[CTokenGroups::~CTokenGroups](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CTokenGroups::Ekle](#add)|Nesneye `CSid` bir `TOKEN_GROUPS` veya varolan yapı ekler. `CTokenGroups`|
|[CTokenGroups::Delete](#delete)|A `CSid` ve ilişkili özniteliklerini `CTokenGroups` nesneden siler.|
|[CTokenGroups::DeleteAll](#deleteall)|Tüm `CSid` nesneleri ve ilişkili özniteliklerini `CTokenGroups` nesneden siler.|
|[CTokenGroups::GetCount](#getcount)|Nesnede bulunan `CSid` nesnelerin ve ilişkili özniteliklerin sayısını döndürür. `CTokenGroups`|
|[CTokenGroups::GetLength](#getlength)|`CTokenGroups` Nesnenin boyutunu döndürür.|
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|`TOKEN_GROUPS` Yapıiçin bir işaretçi alır.|
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|`CTokenGroups` Nesneye `CSid` ait nesneleri ve öznitelikleri alır.|
|[CTokenGroups::LookupSid](#lookupsid)|Bir `CSid` nesneyle ilişkili öznitelikleri alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CTokenGroups::operatör const TOKEN_GROUPS *](#operator_const_token_groups__star)|Nesneyi `CTokenGroups` `TOKEN_GROUPS` yapıya işaretçiye atar.|
|[CTokenGroups::operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

[Erişim belirteci,](/windows/win32/SecAuthZ/access-tokens) bir işlemin veya iş parçacığının güvenlik bağlamını açıklayan ve windows sistemine oturum açmış her kullanıcıya ayrılan bir nesnedir.

Sınıf, `CTokenGroups` [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) yapısı için, bir erişim belirtecigrup güvenlik tanımlayıcıları (SID'ler) hakkında bilgi içeren bir paketleyicidir.

Windows'daki erişim denetimi modeline giriş için Windows SDK'daki [Access Denetimi'ne](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="ctokengroupsadd"></a><a name="add"></a>CTokenGroups::Ekle

Nesneye `CSid` bir `TOKEN_GROUPS` veya varolan yapı ekler. `CTokenGroups`

```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
CSid [nesnesi.](../../atl/reference/csid-class.md)

*dwÖzler*<br/>
`CSid` Nesneyle ilişkilendirilen öznitelikler.

*rTokenGroups*<br/>
[TOKEN_GROUPS bir](/windows/win32/api/winnt/ns-winnt-token_groups) yapı.

### <a name="remarks"></a>Açıklamalar

Bu yöntemler nesneye `CSid` `CTokenGroups` bir veya daha fazla nesne ve ilişkili öznitelikleri ekleyin.

## <a name="ctokengroupsctokengroups"></a><a name="ctokengroups"></a>CTokenGroups::CTokenGroups

Oluşturucu.

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
Nesneyi `CTokenGroups` [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) oluşturmak `CTokenGroups` için nesne veya TOKEN_GROUPS yapısı.

### <a name="remarks"></a>Açıklamalar

Nesne `CTokenGroups` isteğe bağlı olarak `TOKEN_GROUPS` bir yapı veya `CTokenGroups` daha önce tanımlanmış bir nesne kullanılarak oluşturulabilir.

## <a name="ctokengroupsctokengroups"></a><a name="dtor"></a>CTokenGroups::~CTokenGroups

Yıkıcı.

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, ayrılan tüm kaynakları serbest sağlar.

## <a name="ctokengroupsdelete"></a><a name="delete"></a>CTokenGroups::Delete

A `CSid` ve ilişkili özniteliklerini `CTokenGroups` nesneden siler.

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
Güvenlik tanımlayıcısı (SID) ve özniteliklerinin kaldırılması gereken [CSid](../../atl/reference/csid-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Yanlış yoksa `CSid` doğru olarak kaldırılırsa doğru döndürür.

## <a name="ctokengroupsdeleteall"></a><a name="deleteall"></a>CTokenGroups::DeleteAll

Tüm `CSid` nesneleri ve ilişkili özniteliklerini `CTokenGroups` nesneden siler.

```
void DeleteAll() throw();
```

## <a name="ctokengroupsgetcount"></a><a name="getcount"></a>CTokenGroups::GetCount

'de `CTokenGroups`bulunan `CSid` nesne sayısını verir.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CSid](../../atl/reference/csid-class.md) nesnelerinin sayısını ve nesnede bulunan `CTokenGroups` ilişkili özniteliklerini döndürür.

## <a name="ctokengroupsgetlength"></a><a name="getlength"></a>CTokenGroups::GetLength

`CTokenGroup` Nesnenin boyutunu döndürür.

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>Açıklamalar

Baytlar halinde `CTokenGroup` nesnenin toplam boyutunu döndürür.

## <a name="ctokengroupsgetptoken_groups"></a><a name="getptoken_groups"></a>CTokenGroups::GetPTOKEN_GROUPS

`TOKEN_GROUPS` Yapıiçin bir işaretçi alır.

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Erişim belirteci [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) nesnesine ait `CTokenGroups` TOKEN_GROUPS yapıiçin bir işaretçi alır.

## <a name="ctokengroupsgetsidsandattributes"></a><a name="getsidsandattributes"></a>CTokenGroups::GetSidsAndAttributes

`CSid` Nesneleri ve (isteğe bağlı olarak) `CTokenGroups` nesneye ait öznitelikleri alır.

```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSids*<br/>
[CSid](../../atl/reference/csid-class.md) nesnelerin bir dizi işaretçi.

*pAttributes*<br/>
Bir dizi DWORD'a işaretçi. Bu parametre atlanırsa veya NULL'sa, öznitelikler alınmaz.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CSid` `CTokenGroups` nesnede bulunan tüm nesneleri sıralar ve bunları yerve (isteğe bağlı olarak) atnitelik bayrakları dizi nesnelerine.

## <a name="ctokengroupslookupsid"></a><a name="lookupsid"></a>CTokenGroups::LookupSid

Bir `CSid` nesneyle ilişkili öznitelikleri alır.

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>Parametreler

*rSid*<br/>
[CSid nesnesi.](../../atl/reference/csid-class.md)

*pdwÖznitelikler*<br/>
Nesnenin özniteliğini kabul `CSid` edecek bir DWORD işaretçisi. Atlanırsa veya NULL'da varsa, öznitelik alınmaz.

### <a name="return-value"></a>Dönüş Değeri

Eğer bulunursa `CSid` doğru döndürür, aksi takdirde yanlış.

### <a name="remarks"></a>Açıklamalar

*PDwAttributes'ı* NULL'a ayarlamak, özniteliğe `CSid` erişmeden varlığı doğrulamanın bir yolunu sağlar. Bu yöntemin erişim haklarını denetlemek için kullanılmaması gerektiğini unutmayın. Uygulamalar bunun yerine [CAccessToken kullanmalıdır::CheckTokenÜyelik](../../atl/reference/caccesstoken-class.md#checktokenmembership) yöntemi.

## <a name="ctokengroupsoperator-"></a><a name="operator_eq"></a>CTokenGroups::operator =

Atama işleci.

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
Nesneye `CTokenGroups` [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) atamak için `CTokenGroups` nesne veya TOKEN_GROUPS yapısı.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTokenGroups` nesneyi döndürür.

## <a name="ctokengroupsoperator-const-token_groups-"></a><a name="operator_const_token_groups__star"></a>CTokenGroups::operatör const TOKEN_GROUPS *

`TOKEN_GROUPS` Yapıya bir işaretçiiçin bir değer atar.

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) yapısına bir işaretçi için bir değer atar.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik Örneği](../../overview/visual-cpp-samples.md)<br/>
[CSid Sınıfı](../../atl/reference/csid-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
