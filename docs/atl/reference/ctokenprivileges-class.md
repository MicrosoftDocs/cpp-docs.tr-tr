---
title: CTokenPrivileges sınıfı
ms.date: 11/04/2016
f1_keywords:
- CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::Add
- ATLSECURITY/ATL::CTokenPrivileges::Delete
- ATLSECURITY/ATL::CTokenPrivileges::DeleteAll
- ATLSECURITY/ATL::CTokenPrivileges::GetCount
- ATLSECURITY/ATL::CTokenPrivileges::GetDisplayNames
- ATLSECURITY/ATL::CTokenPrivileges::GetLength
- ATLSECURITY/ATL::CTokenPrivileges::GetLuidsAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetNamesAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetPTOKEN_PRIVILEGES
- ATLSECURITY/ATL::CTokenPrivileges::LookupPrivilege
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
ms.openlocfilehash: 5f8379d20d8c8d525cd645e1d4aa0c751e16f531
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915526"
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges sınıfı

Bu sınıf, `TOKEN_PRIVILEGES` yapı için bir sarmalayıcıdır.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CTokenPrivileges
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CTokenPrivileges:: CTokenPrivileges](#ctokenprivileges)|Oluşturucu.|
|[CTokenPrivileges:: ~ CTokenPrivileges](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTokenPrivileges:: Add](#add)|`CTokenPrivileges` Nesnesine bir veya daha fazla ayrıcalık ekler.|
|[CTokenPrivileges::D Sil](#delete)|`CTokenPrivileges` Nesnesinden bir ayrıcalık siler.|
|[CTokenPrivileges::D eleteAll](#deleteall)|`CTokenPrivileges` Nesneden tüm ayrıcalıkları siler.|
|[CTokenPrivileges:: GetCount](#getcount)|`CTokenPrivileges` Nesnedeki ayrıcalık girişi sayısını döndürür.|
|[CTokenPrivileges:: GetDisplayNames](#getdisplaynames)|`CTokenPrivileges` Nesnesinde içerilen ayrıcalıkların görünen adlarını alır.|
|[CTokenPrivileges:: GetLength](#getlength)|`CTokenPrivileges` Nesnenin temsil ettiği `TOKEN_PRIVILEGES` yapıyı tutmak için gereken bayt cinsinden arabellek boyutunu döndürür.|
|[CTokenPrivileges:: Getluıdsandattributes](#getluidsandattributes)|`CTokenPrivileges` Nesnesinden yerel olarak benzersiz tanımlayıcılar (LUIDs) ve öznitelik bayraklarını alır.|
|[CTokenPrivileges:: GetNamesAndAttributes](#getnamesandattributes)|`CTokenPrivileges` Nesneden ayrıcalık adlarını ve öznitelik bayraklarını alır.|
|[CTokenPrivileges:: GetPTOKEN_PRIVILEGES](#getptoken_privileges)|`TOKEN_PRIVILEGES` Yapıya bir işaretçi döndürür.|
|[CTokenPrivileges:: LookupPrivilege](#lookupprivilege)|Verilen ayrıcalık adı ile ilişkili özniteliği alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CTokenPrivileges:: operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|`TOKEN_PRIVILEGES` Yapının işaretçisine bir değer yayınlar.|
|[CTokenPrivileges:: operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

[Erişim belirteci](/windows/desktop/SecAuthZ/access-tokens) bir işlemin veya iş parçacığının güvenlik bağlamını açıklayan ve bir Windows sisteminde oturum açan her kullanıcıya ayrılan bir nesnedir.

Erişim belirteci, her kullanıcıya verilen çeşitli güvenlik ayrıcalıklarını tanımlamakta kullanılır. Ayrıcalık, yerel olarak benzersiz tanımlayıcı ( [LUID](/windows/desktop/api/winnt/ns-winnt-luid)) ve tanımlayıcı dize olarak adlandırılan 64 bitlik bir sayıdan oluşur.

Sınıfı, TOKEN_PRIVILEGES yapısına yönelik bir sarmalayıcı ve 0 veya daha fazla ayrıcalık içerir. [](/windows/desktop/api/winnt/ns-winnt-token_privileges) `CTokenPrivileges` Ayrıcalıklar, sağlanan sınıf yöntemleri kullanılarak eklenebilir, silinebilir veya sorgulanabilir.

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/desktop/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="add"></a>CTokenPrivileges:: Add

`CTokenPrivileges` Erişim belirteci nesnesine bir veya daha fazla ayrıcalık ekler.

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
WINNT içinde tanımlandığı şekilde, ayrıcalığın adını belirten null ile sonlandırılmış bir dize işaretçisi. H üstbilgi dosyası.

*bEnable*<br/>
True ise ayrıcalık etkindir. Yanlış ise, ayrıcalık devre dışı bırakılır.

*rPrivileges*<br/>
Bir [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) yapısına başvuru. Ayrıcalıklar ve öznitelikler bu yapıdan kopyalanır ve `CTokenPrivileges` nesnesine eklenir.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntemin ilk formu, ayrıcalıklar başarıyla eklenirse true, aksi takdirde false döndürür.

##  <a name="ctokenprivileges"></a>CTokenPrivileges:: CTokenPrivileges

Oluşturucu.

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
Yeni nesneye atanacak nesne. `CTokenPrivileges`

*rPrivileges*<br/>
Yeni`CTokenPrivileges` nesnesine atanacak [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) yapısı.

### <a name="remarks"></a>Açıklamalar

Nesne `CTokenPrivileges` , isteğe bağlı olarak, bir `TOKEN_PRIVILEGES` yapı veya daha önce tanımlanmış `CTokenPrivileges` bir nesne kullanılarak oluşturulabilir.

##  <a name="dtor"></a>CTokenPrivileges:: ~ CTokenPrivileges

Yok edicisi.

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, ayrılan tüm kaynakları serbest bırakır.

##  <a name="delete"></a>CTokenPrivileges::D Sil

`CTokenPrivileges` Erişim belirteci nesnesinden bir ayrıcalığı siler.

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
WINNT içinde tanımlandığı şekilde, ayrıcalığın adını belirten null ile sonlandırılmış bir dize işaretçisi. H üstbilgi dosyası. Örneğin, bu parametre sabit SE_SECURITY_NAME veya buna karşılık gelen "SeSecurityPrivilege" dizesini belirtebilir.

### <a name="return-value"></a>Dönüş Değeri

Ayrıcalık başarıyla silinmişse true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kısıtlı belirteçler oluşturmaya yönelik bir araç olarak faydalıdır.

##  <a name="deleteall"></a>CTokenPrivileges::D eleteAll

`CTokenPrivileges` Erişim belirteci nesnesinden tüm ayrıcalıkları siler.

```
void DeleteAll() throw();
```

### <a name="remarks"></a>Açıklamalar

`CTokenPrivileges` Erişim belirteci nesnesinde bulunan tüm ayrıcalıkları siler.

##  <a name="getdisplaynames"></a>CTokenPrivileges:: GetDisplayNames

`CTokenPrivileges` Erişim belirteci nesnesinde içerilen ayrıcalıkların görünen adlarını alır.

```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pDisplayNames*<br/>
`CString` Nesne dizisine yönelik bir işaretçi. `CNames`bir typedef olarak tanımlanır: `CTokenPrivileges::CAtlArray<CString>`.

### <a name="remarks"></a>Açıklamalar

Parametresi `pDisplayNames` , nesnesindebulunan`CTokenPrivileges` ayrıcalıklara karşılık gelen görünen adları `CString` alacak nesneler dizisinin bir işaretçisidir. Bu yöntem yalnızca, WINNT 'in tanımlı ayrıcalıklar bölümünde belirtilen ayrıcalıkların görünen adlarını alır. Olsun.

Bu yöntem görüntülenebilen bir ad alır: Örneğin, öznitelik adı SE_REMOTE_SHUTDOWN_NAME ise görüntülenebilen ad "uzak sistemden kapanmaya zorla" olur. Sistem adını almak için [CTokenPrivileges:: GetNamesAndAttributes](#getnamesandattributes)kullanın.

##  <a name="getcount"></a>CTokenPrivileges:: GetCount

`CTokenPrivileges` Nesnedeki ayrıcalık girişi sayısını döndürür.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CTokenPrivileges` Nesnesinde içerilen ayrıcalıkların sayısını döndürür.

##  <a name="getlength"></a>CTokenPrivileges:: GetLength

`CTokenPrivileges` Nesnenin uzunluğunu döndürür.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

İçerdiği tüm ayrıcalık girişleri dahil olmak üzere, `TOKEN_PRIVILEGES` `CTokenPrivileges` nesne tarafından temsil edilen bir yapıyı tutmak için gereken bayt sayısını döndürür.

##  <a name="getluidsandattributes"></a>CTokenPrivileges:: Getluıdsandattributes

`CTokenPrivileges` Nesnesinden yerel olarak benzersiz tanımlayıcılar (LUIDs) ve öznitelik bayraklarını alır.

```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pPrivileges*<br/>
[LUID](/windows/desktop/api/winnt/ns-winnt-luid) nesnelerinin dizisine yönelik işaretçi. `CLUIDArray`, olarak `CAtlArray<LUID> CLUIDArray`tanımlanan bir typedef.

*pAttributes*<br/>
Bir DWORD nesneleri dizisine yönelik işaretçi. Bu parametre atlanırsa veya NULL ise, öznitelikler alınmadı. `CAttributes`, olarak `CAtlArray <DWORD> CAttributes`tanımlanan bir typedef.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CTokenPrivileges` erişim belirteci nesnesinde bulunan tüm ayrıcalıkların listesini alır ve bağımsız LUIDs ve (isteğe bağlı olarak) öznitelik bayraklarını dizi nesnelerine yerleştirir.

##  <a name="getnamesandattributes"></a>CTokenPrivileges:: GetNamesAndAttributes

`CTokenPrivileges` Nesneden Name ve Attribute bayraklarını alır.

```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pNames 'lar*<br/>
`CString` Nesne dizisine yönelik işaretçi. `CNames`, olarak `CAtlArray <CString> CNames`tanımlanan bir typedef.

*pAttributes*<br/>
Bir DWORD nesneleri dizisine yönelik işaretçi. Bu parametre atlanırsa veya NULL ise, öznitelikler alınmadı. `CAttributes`, olarak `CAtlArray <DWORD> CAttributes`tanımlanan bir typedef.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CTokenPrivileges` nesnesinde yer alan tüm ayrıcalıkların listesini, adını ve (isteğe bağlı olarak) öznitelik bayraklarını dizi nesnelerine yerleştirmeyecektir.

Bu yöntem, görüntülenebilen ad yerine öznitelik adını alır: Örneğin, öznitelik adı SE_REMOTE_SHUTDOWN_NAME ise, sistem adı "SeRemoteShutdownPrivilege" olur. Görüntülenebilen adı almak için [CTokenPrivileges:: GetDisplayNames](#getdisplaynames)metodunu kullanın.

##  <a name="getptoken_privileges"></a>CTokenPrivileges:: GetPTOKEN_PRIVILEGES

`TOKEN_PRIVILEGES` Yapıya bir işaretçi döndürür.

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) yapısına bir işaretçi döndürür.

##  <a name="lookupprivilege"></a>CTokenPrivileges:: LookupPrivilege

Verilen ayrıcalık adı ile ilişkili özniteliği alır.

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
WINNT içinde tanımlandığı şekilde, ayrıcalığın adını belirten null ile sonlandırılmış bir dize işaretçisi. H üstbilgi dosyası. Örneğin, bu parametre sabit SE_SECURITY_NAME veya buna karşılık gelen "SeSecurityPrivilege" dizesini belirtebilir.

*pdwAttributes*<br/>
Öznitelikleri alan bir değişkene yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Öznitelik başarıyla alınırsa true, aksi takdirde false döndürür.

##  <a name="operator_eq"></a>CTokenPrivileges:: operator =

Atama işleci.

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*rPrivileges*<br/>
`CTokenPrivileges` Nesneye atanacak [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) yapısı.

*sağ taraftan*<br/>
Nesneye `CTokenPrivileges` atanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTokenPrivileges` nesneyi döndürür.

##  <a name="operator_const_token_privileges__star"></a>CTokenPrivileges:: operator const TOKEN_PRIVILEGES\*

`TOKEN_PRIVILEGES` Yapının işaretçisine bir değer yayınlar.

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

Bir değeri [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) yapısına bir işaretçiye yayınlar.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik örneği](../../overview/visual-cpp-samples.md)<br/>
[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges)<br/>
[DEĞERINI](/windows/desktop/api/winnt/ns-winnt-luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/desktop/api/winnt/ns-winnt-luid_and_attributes)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
