---
description: 'Daha fazla bilgi edinin: CTokenGroups sınıfı'
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
ms.openlocfilehash: 3d6633afbd649aa175196f1fae8e62afdf784f99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140354"
---
# <a name="ctokengroups-class"></a>CTokenGroups sınıfı

Bu sınıf, yapı için bir sarmalayıcıdır `TOKEN_GROUPS` .

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CTokenGroups
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CTokenGroups:: CTokenGroups](#ctokengroups)|Oluşturucu.|
|[CTokenGroups:: ~ CTokenGroups](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTokenGroups:: Add](#add)|Nesneye bir `CSid` veya varolan bir `TOKEN_GROUPS` Yapı ekler `CTokenGroups` .|
|[CTokenGroups::D Sil](#delete)|`CSid`Nesnesinden ilişkili özniteliklerini ve `CTokenGroups` nesneyi siler.|
|[CTokenGroups::D eleteAll](#deleteall)|Tüm `CSid` nesneleri ve ilişkili özniteliklerini `CTokenGroups` nesnesinden siler.|
|[CTokenGroups:: GetCount](#getcount)|`CSid`Nesnesinde içerilen nesne ve ilişkili özniteliklerin sayısını döndürür `CTokenGroups` .|
|[CTokenGroups:: GetLength](#getlength)|Nesnenin boyutunu döndürür `CTokenGroups` .|
|[CTokenGroups:: GetPTOKEN_GROUPS](#getptoken_groups)|Yapıya bir işaretçi alır `TOKEN_GROUPS` .|
|[CTokenGroups:: Getsıdsandattributes](#getsidsandattributes)|`CSid`Nesnesine ait nesneleri ve öznitelikleri alır `CTokenGroups` .|
|[CTokenGroups:: Lookupsıd](#lookupsid)|Bir nesneyle ilişkili öznitelikleri alır `CSid` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CTokenGroups:: operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|`CTokenGroups`Nesneyi yapıya bir işaretçiye yayınlar `TOKEN_GROUPS` .|
|[CTokenGroups:: operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

[Erişim belirteci](/windows/win32/SecAuthZ/access-tokens) bir işlemin veya iş parçacığının güvenlik bağlamını açıklayan ve bir Windows sisteminde oturum açan her kullanıcıya ayrılan bir nesnedir.

`CTokenGroups`Sınıfı, bir erişim belirtecinde grup güvenlik tanımlayıcıları (SID 'ler) hakkındaki bilgileri içeren [token_groups](/windows/win32/api/winnt/ns-winnt-token_groups) yapısına yönelik bir sarmalayıcıdır.

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

## <a name="ctokengroupsadd"></a><a name="add"></a> CTokenGroups:: Add

Nesneye bir `CSid` veya varolan bir `TOKEN_GROUPS` Yapı ekler `CTokenGroups` .

```cpp
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
Bir [CSID](../../atl/reference/csid-class.md) nesnesi.

*dwAttributes*<br/>
Nesneyle ilişkilendirilecek öznitelikler `CSid` .

*rTokenGroups*<br/>
[Token_groups](/windows/win32/api/winnt/ns-winnt-token_groups) yapısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntemler, nesnesine bir veya daha fazla `CSid` nesne ve ilişkili özniteliklerini ekler `CTokenGroups` .

## <a name="ctokengroupsctokengroups"></a><a name="ctokengroups"></a> CTokenGroups:: CTokenGroups

Oluşturucu.

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
`CTokenGroups`Nesnenin oluşturulacağı nesne veya [token_groups](/windows/win32/api/winnt/ns-winnt-token_groups) yapısı `CTokenGroups` .

### <a name="remarks"></a>Açıklamalar

`CTokenGroups`Nesne, isteğe bağlı olarak, bir `TOKEN_GROUPS` Yapı veya daha önce tanımlanmış bir `CTokenGroups` nesne kullanılarak oluşturulabilir.

## <a name="ctokengroupsctokengroups"></a><a name="dtor"></a> CTokenGroups:: ~ CTokenGroups

Yok edicisi.

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, ayrılan tüm kaynakları serbest bırakır.

## <a name="ctokengroupsdelete"></a><a name="delete"></a> CTokenGroups::D Sil

`CSid`Nesnesinden ilişkili özniteliklerini ve `CTokenGroups` nesneyi siler.

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
Güvenlik tanımlayıcısı (SID) ve özniteliklerinin kaldırılması gereken [CSID](../../atl/reference/csid-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`CSid`Kaldırılırsa true, aksi takdirde false döndürür.

## <a name="ctokengroupsdeleteall"></a><a name="deleteall"></a> CTokenGroups::D eleteAll

Tüm `CSid` nesneleri ve ilişkili özniteliklerini `CTokenGroups` nesnesinden siler.

```cpp
void DeleteAll() throw();
```

## <a name="ctokengroupsgetcount"></a><a name="getcount"></a> CTokenGroups:: GetCount

`CSid`İçinde yer alan nesne sayısını döndürür `CTokenGroups` .

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CSID](../../atl/reference/csid-class.md) nesnelerinin sayısını ve nesnesinde bulunan ilişkili özniteliklerini döndürür `CTokenGroups` .

## <a name="ctokengroupsgetlength"></a><a name="getlength"></a> CTokenGroups:: GetLength

Nesnenin boyutunu döndürür `CTokenGroup` .

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>Açıklamalar

Nesnenin bayt cinsinden toplam boyutunu döndürür `CTokenGroup` .

## <a name="ctokengroupsgetptoken_groups"></a><a name="getptoken_groups"></a> CTokenGroups:: GetPTOKEN_GROUPS

Yapıya bir işaretçi alır `TOKEN_GROUPS` .

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Erişim belirteci nesnesine ait [token_groups](/windows/win32/api/winnt/ns-winnt-token_groups) yapısına yönelik bir işaretçi alır `CTokenGroups` .

## <a name="ctokengroupsgetsidsandattributes"></a><a name="getsidsandattributes"></a> CTokenGroups:: Getsıdsandattributes

`CSid`Nesneleri ve (isteğe bağlı olarak) nesneye ait öznitelikleri alır `CTokenGroups` .

```cpp
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*PSID 'Ler*<br/>
Bir [CSID](../../atl/reference/csid-class.md) nesneleri dizisine yönelik işaretçi.

*pAttributes*<br/>
Bir DWORD dizisine yönelik işaretçi. Bu parametre atlanırsa veya NULL ise, öznitelikler alınmadı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CSid` nesnede bulunan tüm nesneleri numaralandırır `CTokenGroups` ve bu özniteliği ve (isteğe bağlı olarak) öznitelik bayraklarını dizi nesnelerine yerleştirir.

## <a name="ctokengroupslookupsid"></a><a name="lookupsid"></a> CTokenGroups:: Lookupsıd

Bir nesneyle ilişkili öznitelikleri alır `CSid` .

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
[CSID](../../atl/reference/csid-class.md) nesnesi.

*pdwAttributes*<br/>
Nesnenin özniteliğini kabul edecek bir DWORD işaretçisi `CSid` . Atlanırsa veya NULL ise, öznitelik alınmayacak.

### <a name="return-value"></a>Dönüş Değeri

`CSid`Bulunursa true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

*PdwAttributes* değerini null olarak ayarlamak, ' ın `CSid` özniteliğe erişmeden, varlığını onaylamamasının bir yolunu sağlar. Bu yöntemin erişim haklarını denetlemek için kullanılmamalıdır. Uygulamalar bunun yerine [CAccessToken:: CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) metodunu kullanmalıdır.

## <a name="ctokengroupsoperator-"></a><a name="operator_eq"></a> CTokenGroups:: operator =

Atama işleci.

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
`CTokenGroups`Nesneye atanacak nesne veya [token_groups](/windows/win32/api/winnt/ns-winnt-token_groups) yapısı `CTokenGroups` .

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneyi döndürür `CTokenGroups` .

## <a name="ctokengroupsoperator-const-token_groups-"></a><a name="operator_const_token_groups__star"></a> CTokenGroups:: operator const TOKEN_GROUPS *

Yapının işaretçisine bir değer yayınlar `TOKEN_GROUPS` .

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

[Token_groups](/windows/win32/api/winnt/ns-winnt-token_groups) yapısına bir işaretçiye değer yayınlar.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik örneği](../../overview/visual-cpp-samples.md)<br/>
[CSID sınıfı](../../atl/reference/csid-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel Işlevleri](../../atl/reference/security-global-functions.md)
