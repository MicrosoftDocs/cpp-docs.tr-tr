---
title: CTokenPrivileges Sınıfı
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
ms.openlocfilehash: ceb9aeca6b99e7fc9d08625e11cbdb182fb3dc9e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330539"
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges Sınıfı

Bu sınıf `TOKEN_PRIVILEGES` yapı için bir sarmalayıcıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CTokenPrivileges
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|Oluşturucu.|
|[CTokenPrivileges::~CTokenPrivileges](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CTokenPrivileges::Ekle](#add)|`CTokenPrivileges` Nesneye bir veya daha fazla ayrıcalık ekler.|
|[CTokenPrivileges::Delete](#delete)|Nesneden bir ayrıcalığı `CTokenPrivileges` siler.|
|[CTokenPrivileges::DeleteAll](#deleteall)|Nesnedeki `CTokenPrivileges` tüm ayrıcalıkları siler.|
|[CTokenPrivileges::GetCount](#getcount)|`CTokenPrivileges` Nesnedeki ayrıcalık girişlerinin sayısını döndürür.|
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|`CTokenPrivileges` Nesnede bulunan ayrıcalıklar için görüntü adlarını alır.|
|[CTokenPrivileges::GetLength](#getlength)|Nesne tarafından temsil edilen `TOKEN_PRIVILEGES` yapıyı tutmak için gereken arabellek boyutunu baytolarak döndürür. `CTokenPrivileges`|
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|Yerel olarak benzersiz tanımlayıcıları (LUIDs) alır ve nesneden `CTokenPrivileges` bayraklar atfeder.|
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|Ayrıcalık adlarını alır ve `CTokenPrivileges` nesnelerden bayraklar atfeder.|
|[CTokenAyrıcalıklar::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|Yapıya bir `TOKEN_PRIVILEGES` işaretçi döndürür.|
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|Verilen bir ayrıcalık adı ile ilişkili özniteliği alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CTokenPrivileges::operatör const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|`TOKEN_PRIVILEGES` Yapıya bir işaretçiiçin bir değer atar.|
|[CTokenPrivileges::operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

[Erişim belirteci,](/windows/win32/SecAuthZ/access-tokens) bir işlemin veya iş parçacığının güvenlik bağlamını açıklayan ve windows sistemine oturum açmış her kullanıcıya ayrılan bir nesnedir.

Erişim belirteci, her kullanıcıya verilen çeşitli güvenlik ayrıcalıklarını açıklamak için kullanılır. Ayrıcalık, yerel olarak benzersiz tanımlayıcı [(LUID)](/windows/win32/api/winnt/ns-winnt-luid)adı verilen 64 bitlik bir sayı ve tanımlayıcı dizeden oluşur.

`CTokenPrivileges` Sınıf, [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) yapısı için bir paketleyicidir ve 0 veya daha fazla ayrıcalık içerir. Ayrıcalıklar, sağlanan sınıf yöntemleri kullanılarak eklenebilir, silinebilir veya sorgulanabilir.

Windows'daki erişim denetimi modeline giriş için Windows SDK'daki [Access Denetimi'ne](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="ctokenprivilegesadd"></a><a name="add"></a>CTokenPrivileges::Ekle

Erişim belirteci nesnesine `CTokenPrivileges` bir veya daha fazla ayrıcalık ekler.

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
WINNT'de tanımlandığı gibi ayrıcalığın adını belirten geçersiz sonlandırılmış bir dize işaretçi. H üstbilgi dosyası.

*bEtkinleştir*<br/>
Doğruysa, ayrıcalık etkinleştirilir. Yanlışsa, ayrıcalık devre dışı bırakılır.

*rAyrıcalıklar*<br/>
[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) bir yapıya atıfta bulunarak. Ayrıcalıklar ve öznitelikler bu yapıdan kopyalanır `CTokenPrivileges` ve nesneye eklenir.

### <a name="return-value"></a>Dönüş Değeri

Ayrıcalıklar başarıyla eklenirse, aksi takdirde bu yöntemin ilk biçimi doğru döndürür.

## <a name="ctokenprivilegesctokenprivileges"></a><a name="ctokenprivileges"></a>CTokenPrivileges::CTokenPrivileges

Oluşturucu.

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
Yeni `CTokenPrivileges` nesneye atayacak nesne.

*rAyrıcalıklar*<br/>
Yeni [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) `CTokenPrivileges` nesneye atamak için TOKEN_PRIVILEGES yapısı.

### <a name="remarks"></a>Açıklamalar

Nesne `CTokenPrivileges` isteğe bağlı olarak `TOKEN_PRIVILEGES` bir yapı veya `CTokenPrivileges` daha önce tanımlanmış bir nesne kullanılarak oluşturulabilir.

## <a name="ctokenprivilegesctokenprivileges"></a><a name="dtor"></a>CTokenPrivileges::~CTokenPrivileges

Yıkıcı.

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, ayrılan tüm kaynakları serbest sağlar.

## <a name="ctokenprivilegesdelete"></a><a name="delete"></a>CTokenPrivileges::Delete

Erişim belirteci `CTokenPrivileges` nesnesinden bir ayrıcalığı siler.

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
WINNT'de tanımlandığı gibi ayrıcalığın adını belirten geçersiz sonlandırılmış bir dize işaretçi. H üstbilgi dosyası. Örneğin, bu parametre sabit SE_SECURITY_NAME veya karşılık gelen dize, "SeSecurityPrivilege" belirtebilir.

### <a name="return-value"></a>Dönüş Değeri

Ayrıcalık başarıyla silindiyse doğru döndürür, aksi takdirde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, sınırlı belirteçleri oluşturmak için bir araç olarak yararlıdır.

## <a name="ctokenprivilegesdeleteall"></a><a name="deleteall"></a>CTokenPrivileges::DeleteAll

Erişim belirteci nesnesinden `CTokenPrivileges` tüm ayrıcalıkları siler.

```
void DeleteAll() throw();
```

### <a name="remarks"></a>Açıklamalar

Erişim belirteç nesnesinde `CTokenPrivileges` bulunan tüm ayrıcalıkları siler.

## <a name="ctokenprivilegesgetdisplaynames"></a><a name="getdisplaynames"></a>CTokenPrivileges::GetDisplayNames

Erişim belirteci nesnesinde `CTokenPrivileges` bulunan ayrıcalıklar için görüntü adlarını alır.

```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pDisplayNames*<br/>
`CString` Bir dizi nesne için bir işaretçi. `CNames`typedef olarak tanımlanır: `CTokenPrivileges::CAtlArray<CString>`.

### <a name="remarks"></a>Açıklamalar

Parametre, `pDisplayNames` nesnede bulunan ayrıcalıklara karşılık gelen görüntü adlarını alacak `CString` bir nesne `CTokenPrivileges` dizisine işaretçidir. Bu yöntem, yalnızca WINNT'nin Tanımlı Ayrıcalıklar bölümünde belirtilen ayrıcalıklar için görüntü adlarını alır. H.

Bu yöntem görüntülenebilir bir ad alır: örneğin, öznitelik adı SE_REMOTE_SHUTDOWN_NAME ise, görüntülenebilir ad "Uzak bir sistemden zorla kapatma." Sistem adını elde etmek için [CTokenPrivileges kullanın::GetNamesAndAttributes](#getnamesandattributes).

## <a name="ctokenprivilegesgetcount"></a><a name="getcount"></a>CTokenPrivileges::GetCount

`CTokenPrivileges` Nesnedeki ayrıcalık girişlerinin sayısını döndürür.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CTokenPrivileges` Nesnede bulunan ayrıcalıkların sayısını verir.

## <a name="ctokenprivilegesgetlength"></a><a name="getlength"></a>CTokenPrivileges::GetLength

`CTokenPrivileges` Nesnenin uzunluğunu döndürür.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

İçerdiği tüm ayrıcalık girişleri de `TOKEN_PRIVILEGES` dahil olmak `CTokenPrivileges` üzere nesne tarafından temsil edilen bir yapıyı tutmak için gereken bayt sayısını verir.

## <a name="ctokenprivilegesgetluidsandattributes"></a><a name="getluidsandattributes"></a>CTokenPrivileges::GetLuidsAndAttributes

Yerel olarak benzersiz tanımlayıcıları (LUIDs) alır ve nesneden `CTokenPrivileges` bayraklar atfeder.

```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pAyrıcalıklar*<br/>
[LUID](/windows/win32/api/winnt/ns-winnt-luid) nesnelerinbir dizi işaretçi. `CLUIDArray`olarak tanımlanan bir `CAtlArray<LUID> CLUIDArray`typedef'tir.

*pAttributes*<br/>
DWORD nesnelerinin bir dizi işaretçisi. Bu parametre atlanırsa veya NULL'sa, öznitelikler alınmaz. `CAttributes`olarak tanımlanan bir `CAtlArray <DWORD> CAttributes`typedef'tir.

### <a name="remarks"></a>Açıklamalar

Bu `CTokenPrivileges` yöntem, erişim belirteç nesnesinde bulunan tüm ayrıcalıkları sıralar ve tek tek LUID'leri ve (isteğe bağlı olarak) öznitelik bayraklarını dizi nesnelerine yerleştirilecektir.

## <a name="ctokenprivilegesgetnamesandattributes"></a><a name="getnamesandattributes"></a>CTokenPrivileges::GetNamesAndAttributes

`CTokenPrivileges` Ad ve öznitelik bayraklarını nesneden alır.

```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pNames*<br/>
Bir `CString` dizi nesneye işaretçi. `CNames`olarak tanımlanan bir `CAtlArray <CString> CNames`typedef'tir.

*pAttributes*<br/>
DWORD nesnelerinin bir dizi işaretçisi. Bu parametre atlanırsa veya NULL'sa, öznitelikler alınmaz. `CAttributes`olarak tanımlanan bir `CAtlArray <DWORD> CAttributes`typedef'tir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CTokenPrivileges` ad ve (isteğe bağlı olarak) öznitelik bayraklarını dizi nesnelerine yerleştirerek nesnede bulunan tüm ayrıcalıkları sayısala dönüştürür.

Bu yöntem görüntülenebilir ad yerine öznitelik adını alır: örneğin, öznitelik adı SE_REMOTE_SHUTDOWN_NAME ise, sistem adı "SeRemoteShutdownPrivilege." Görüntülenebilir adı elde etmek için [CTokenPrivileges::GetDisplayNames](#getdisplaynames)yöntemini kullanın.

## <a name="ctokenprivilegesgetptoken_privileges"></a><a name="getptoken_privileges"></a>CTokenAyrıcalıklar::GetPTOKEN_PRIVILEGES

Yapıya bir `TOKEN_PRIVILEGES` işaretçi döndürür.

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) yapısına bir işaretçi döndürür.

## <a name="ctokenprivilegeslookupprivilege"></a><a name="lookupprivilege"></a>CTokenPrivileges::LookupPrivilege

Verilen bir ayrıcalık adı ile ilişkili özniteliği alır.

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
WINNT'de tanımlandığı gibi ayrıcalığın adını belirten geçersiz sonlandırılmış bir dize işaretçi. H üstbilgi dosyası. Örneğin, bu parametre sabit SE_SECURITY_NAME veya karşılık gelen dize, "SeSecurityPrivilege" belirtebilir.

*pdwÖznitelikler*<br/>
Öznitelikleri alan bir değişkeni işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Öznitelik başarıyla alınırsa doğru döndürür, aksi takdirde yanlış.

## <a name="ctokenprivilegesoperator-"></a><a name="operator_eq"></a>CTokenPrivileges::operator =

Atama işleci.

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*rAyrıcalıklar*<br/>
Nesneye atamak için `CTokenPrivileges` [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) yapısı.

*Rhs*<br/>
Nesneye `CTokenPrivileges` atayacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTokenPrivileges` nesneyi döndürür.

## <a name="ctokenprivilegesoperator-const-token_privileges-"></a><a name="operator_const_token_privileges__star"></a>CTokenPrivileges::operatör const TOKEN_PRIVILEGES\*

`TOKEN_PRIVILEGES` Yapıya bir işaretçiiçin bir değer atar.

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) yapısına bir işaretçi için bir değer atar.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik Örneği](../../overview/visual-cpp-samples.md)<br/>
[Token_prıvıleges](/windows/win32/api/winnt/ns-winnt-token_privileges)<br/>
[Luıd](/windows/win32/api/winnt/ns-winnt-luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
