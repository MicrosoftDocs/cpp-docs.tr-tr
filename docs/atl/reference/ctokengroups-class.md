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
ms.openlocfilehash: 88096747f45d4a81c873837cdd4975da9d8c24e2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496289"
---
# <a name="ctokengroups-class"></a>CTokenGroups sınıfı

Bu sınıf, `TOKEN_GROUPS` yapı için bir sarmalayıcıdır.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

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
|[CTokenGroups:: Add](#add)|Nesneye bir `CSid` veya varolan `TOKEN_GROUPS` bir yapı ekler. `CTokenGroups`|
|[CTokenGroups::D Sil](#delete)|`CTokenGroups` Nesnesinden ilişkili özniteliklerini `CSid` ve nesneyi siler.|
|[CTokenGroups::D eleteAll](#deleteall)|Tüm `CSid` nesneleri ve ilişkili özniteliklerini `CTokenGroups` nesnesinden siler.|
|[CTokenGroups:: GetCount](#getcount)|Nesnesinde`CTokenGroups` içerilen nesne ve `CSid` ilişkili özniteliklerin sayısını döndürür.|
|[CTokenGroups:: GetLength](#getlength)|`CTokenGroups` Nesnenin boyutunu döndürür.|
|[CTokenGroups:: GetPTOKEN_GROUPS](#getptoken_groups)|`TOKEN_GROUPS` Yapıya bir işaretçi alır.|
|[CTokenGroups:: Getsıdsandattributes](#getsidsandattributes)|Nesnesineait`CTokenGroups` nesneleri ve öznitelikleri alır. `CSid`|
|[CTokenGroups:: Lookupsıd](#lookupsid)|Bir `CSid` nesneyle ilişkili öznitelikleri alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CTokenGroups:: operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|`CTokenGroups` Nesneyi `TOKEN_GROUPS` yapıya bir işaretçiye yayınlar.|
|[CTokenGroups:: operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

[Erişim belirteci](/windows/win32/SecAuthZ/access-tokens) bir işlemin veya iş parçacığının güvenlik bağlamını açıklayan ve bir Windows sisteminde oturum açan her kullanıcıya ayrılan bir nesnedir.

Sınıfı, bir erişim belirtecinde grup güvenlik tanımlayıcıları (SID 'ler) hakkındaki bilgileri içeren token_groups yapısına yönelik bir sarmalayıcıdır. [](/windows/win32/api/winnt/ns-winnt-token_groups) `CTokenGroups`

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="add"></a>CTokenGroups:: Add

Nesneye bir `CSid` veya varolan `TOKEN_GROUPS` bir yapı ekler. `CTokenGroups`

```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
Bir [CSID](../../atl/reference/csid-class.md) nesnesi.

*dwAttributes*<br/>
`CSid` Nesneyle ilişkilendirilecek öznitelikler.

*rTokenGroups*<br/>
Bir [token_groups](/windows/win32/api/winnt/ns-winnt-token_groups) yapısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntemler, `CTokenGroups` nesnesine bir veya `CSid` daha fazla nesne ve ilişkili özniteliklerini ekler.

##  <a name="ctokengroups"></a>CTokenGroups:: CTokenGroups

Oluşturucu.

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
Nesnesinin oluşturulacağı nesne veya token_groups yapısı. [](/windows/win32/api/winnt/ns-winnt-token_groups) `CTokenGroups` `CTokenGroups`

### <a name="remarks"></a>Açıklamalar

Nesne `CTokenGroups` , isteğe bağlı olarak, bir `TOKEN_GROUPS` yapı veya daha önce tanımlanmış `CTokenGroups` bir nesne kullanılarak oluşturulabilir.

##  <a name="dtor"></a>CTokenGroups:: ~ CTokenGroups

Yok edicisi.

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, ayrılan tüm kaynakları serbest bırakır.

##  <a name="delete"></a>CTokenGroups::D Sil

`CTokenGroups` Nesnesinden ilişkili özniteliklerini `CSid` ve nesneyi siler.

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
Güvenlik tanımlayıcısı (SID) ve özniteliklerinin kaldırılması gereken [CSID](../../atl/reference/csid-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Kaldırılırsa true `CSid` , aksi takdirde false döndürür.

##  <a name="deleteall"></a>CTokenGroups::D eleteAll

Tüm `CSid` nesneleri ve ilişkili özniteliklerini `CTokenGroups` nesnesinden siler.

```
void DeleteAll() throw();
```

##  <a name="getcount"></a>CTokenGroups:: GetCount

`CSid` İçinde`CTokenGroups`yer alan nesne sayısını döndürür.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CSID](../../atl/reference/csid-class.md) nesnelerinin sayısını ve `CTokenGroups` nesnesinde bulunan ilişkili özniteliklerini döndürür.

##  <a name="getlength"></a>CTokenGroups:: GetLength

`CTokenGroup` Nesnenin boyutunu döndürür.

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>Açıklamalar

`CTokenGroup` Nesnenin bayt cinsinden toplam boyutunu döndürür.

##  <a name="getptoken_groups"></a>CTokenGroups:: GetPTOKEN_GROUPS

`TOKEN_GROUPS` Yapıya bir işaretçi alır.

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

`CTokenGroups` Erişim belirteci nesnesine ait [token_groups](/windows/win32/api/winnt/ns-winnt-token_groups) yapısına yönelik bir işaretçi alır.

##  <a name="getsidsandattributes"></a>CTokenGroups:: Getsıdsandattributes

Nesneleri ve (isteğe bağlı olarak) `CTokenGroups` nesneye ait öznitelikleri alır. `CSid`

```
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

Bu yöntem, `CSid` `CTokenGroups` nesnede bulunan tüm nesneleri numaralandırır ve bu özniteliği ve (isteğe bağlı olarak) öznitelik bayraklarını dizi nesnelerine yerleştirir.

##  <a name="lookupsid"></a>CTokenGroups:: Lookupsıd

Bir `CSid` nesneyle ilişkili öznitelikleri alır.

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
[CSID](../../atl/reference/csid-class.md) nesnesi.

*pdwAttributes*<br/>
`CSid` Nesnenin özniteliğini kabul edecek bir DWORD işaretçisi. Atlanırsa veya NULL ise, öznitelik alınmayacak.

### <a name="return-value"></a>Dönüş Değeri

Bulunursa true `CSid` , aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

*PdwAttributes* değerini null olarak ayarlamak, ' ın özniteliğe erişmeden, `CSid` varlığını onaylamamasının bir yolunu sağlar. Bu yöntemin erişim haklarını denetlemek için kullanılmamalıdır. Uygulamalar bunun yerine [CAccessToken:: CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) metodunu kullanmalıdır.

##  <a name="operator_eq"></a>CTokenGroups:: operator =

Atama işleci.

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
Nesneyeatanacak`CTokenGroups` nesne veya token_groups yapısı. [](/windows/win32/api/winnt/ns-winnt-token_groups) `CTokenGroups`

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTokenGroups` nesneyi döndürür.

##  <a name="operator_const_token_groups__star"></a>CTokenGroups:: operator const TOKEN_GROUPS *

`TOKEN_GROUPS` Yapının işaretçisine bir değer yayınlar.

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

Bir değeri [token_groups](/windows/win32/api/winnt/ns-winnt-token_groups) yapısına bir işaretçiye yayınlar.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik örneği](../../overview/visual-cpp-samples.md)<br/>
[CSid Sınıfı](../../atl/reference/csid-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
