---
description: 'Daha fazla bilgi edinin: CTokenPrivileges sınıfı'
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
ms.openlocfilehash: 22953c0d2aa8c4fa7dd0b79b001e46797bd3ca25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140315"
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges sınıfı

Bu sınıf, yapı için bir sarmalayıcıdır `TOKEN_PRIVILEGES` .

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

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
|[CTokenPrivileges:: Add](#add)|Nesnesine bir veya daha fazla ayrıcalık ekler `CTokenPrivileges` .|
|[CTokenPrivileges::D Sil](#delete)|Nesnesinden bir ayrıcalık siler `CTokenPrivileges` .|
|[CTokenPrivileges::D eleteAll](#deleteall)|Nesneden tüm ayrıcalıkları siler `CTokenPrivileges` .|
|[CTokenPrivileges:: GetCount](#getcount)|Nesnedeki ayrıcalık girişi sayısını döndürür `CTokenPrivileges` .|
|[CTokenPrivileges:: GetDisplayNames](#getdisplaynames)|Nesnesinde içerilen ayrıcalıkların görünen adlarını alır `CTokenPrivileges` .|
|[CTokenPrivileges:: GetLength](#getlength)|`TOKEN_PRIVILEGES`Nesnenin temsil ettiği yapıyı tutmak için gereken bayt cinsinden arabellek boyutunu döndürür `CTokenPrivileges` .|
|[CTokenPrivileges:: Getluıdsandattributes](#getluidsandattributes)|Nesnesinden yerel olarak benzersiz tanımlayıcılar (LUIDs) ve öznitelik bayraklarını alır `CTokenPrivileges` .|
|[CTokenPrivileges:: GetNamesAndAttributes](#getnamesandattributes)|Nesneden ayrıcalık adlarını ve öznitelik bayraklarını alır `CTokenPrivileges` .|
|[CTokenPrivileges:: GetPTOKEN_PRIVILEGES](#getptoken_privileges)|Yapıya bir işaretçi döndürür `TOKEN_PRIVILEGES` .|
|[CTokenPrivileges:: LookupPrivilege](#lookupprivilege)|Verilen ayrıcalık adı ile ilişkili özniteliği alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CTokenPrivileges:: operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|Yapının işaretçisine bir değer yayınlar `TOKEN_PRIVILEGES` .|
|[CTokenPrivileges:: operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

[Erişim belirteci](/windows/win32/SecAuthZ/access-tokens) bir işlemin veya iş parçacığının güvenlik bağlamını açıklayan ve bir Windows sisteminde oturum açan her kullanıcıya ayrılan bir nesnedir.

Erişim belirteci, her kullanıcıya verilen çeşitli güvenlik ayrıcalıklarını tanımlamakta kullanılır. Ayrıcalık, yerel olarak benzersiz tanımlayıcı ( [LUID](/windows/win32/api/winnt/ns-winnt-luid)) ve tanımlayıcı dize olarak adlandırılan 64 bitlik bir sayıdan oluşur.

`CTokenPrivileges`Sınıfı, [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) yapısına yönelik bir sarmalayıcıdır ve 0 veya daha fazla ayrıcalık içerir. Ayrıcalıklar, sağlanan sınıf yöntemleri kullanılarak eklenebilir, silinebilir veya sorgulanabilir.

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

## <a name="ctokenprivilegesadd"></a><a name="add"></a> CTokenPrivileges:: Add

Erişim belirteci nesnesine bir veya daha fazla ayrıcalık ekler `CTokenPrivileges` .

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
[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) yapısına başvuru. Ayrıcalıklar ve öznitelikler bu yapıdan kopyalanır ve `CTokenPrivileges` nesnesine eklenir.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntemin ilk formu, ayrıcalıklar başarıyla eklenirse true, aksi takdirde false döndürür.

## <a name="ctokenprivilegesctokenprivileges"></a><a name="ctokenprivileges"></a> CTokenPrivileges:: CTokenPrivileges

Oluşturucu.

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
`CTokenPrivileges`Yeni nesneye atanacak nesne.

*rPrivileges*<br/>
Yeni nesneye atanacak [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) yapısı `CTokenPrivileges` .

### <a name="remarks"></a>Açıklamalar

`CTokenPrivileges`Nesne, isteğe bağlı olarak, bir `TOKEN_PRIVILEGES` Yapı veya daha önce tanımlanmış bir `CTokenPrivileges` nesne kullanılarak oluşturulabilir.

## <a name="ctokenprivilegesctokenprivileges"></a><a name="dtor"></a> CTokenPrivileges:: ~ CTokenPrivileges

Yok edicisi.

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, ayrılan tüm kaynakları serbest bırakır.

## <a name="ctokenprivilegesdelete"></a><a name="delete"></a> CTokenPrivileges::D Sil

`CTokenPrivileges`Erişim belirteci nesnesinden bir ayrıcalığı siler.

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
WINNT içinde tanımlandığı şekilde, ayrıcalığın adını belirten null ile sonlandırılmış bir dize işaretçisi. H üstbilgi dosyası. Örneğin, bu parametre sabit SE_SECURITY_NAME veya karşılık gelen "SeSecurityPrivilege" dizesini belirtebilir.

### <a name="return-value"></a>Dönüş Değeri

Ayrıcalık başarıyla silinmişse true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kısıtlı belirteçler oluşturmaya yönelik bir araç olarak faydalıdır.

## <a name="ctokenprivilegesdeleteall"></a><a name="deleteall"></a> CTokenPrivileges::D eleteAll

`CTokenPrivileges`Erişim belirteci nesnesinden tüm ayrıcalıkları siler.

```cpp
void DeleteAll() throw();
```

### <a name="remarks"></a>Açıklamalar

Erişim belirteci nesnesinde bulunan tüm ayrıcalıkları siler `CTokenPrivileges` .

## <a name="ctokenprivilegesgetdisplaynames"></a><a name="getdisplaynames"></a> CTokenPrivileges:: GetDisplayNames

Erişim belirteci nesnesinde içerilen ayrıcalıkların görünen adlarını alır `CTokenPrivileges` .

```cpp
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pDisplayNames*<br/>
Nesne dizisine yönelik bir işaretçi `CString` . `CNames` bir typedef olarak tanımlanır: `CTokenPrivileges::CAtlArray<CString>` .

### <a name="remarks"></a>Açıklamalar

Parametresi, `pDisplayNames` `CString` nesnesinde bulunan ayrıcalıklara karşılık gelen görünen adları alacak nesneler dizisinin bir işaretçisidir `CTokenPrivileges` . Bu yöntem yalnızca, WINNT. H ' nin tanımlı ayrıcalıklar bölümünde belirtilen ayrıcalıkların görünen adlarını alır.

Bu yöntem görüntülenebilen bir ad alır: Örneğin, öznitelik adı SE_REMOTE_SHUTDOWN_NAME, görüntülenebilir ad "uzak sistemden kapanmaya zorla" dır. Sistem adını almak için [CTokenPrivileges:: GetNamesAndAttributes](#getnamesandattributes)kullanın.

## <a name="ctokenprivilegesgetcount"></a><a name="getcount"></a> CTokenPrivileges:: GetCount

Nesnedeki ayrıcalık girişi sayısını döndürür `CTokenPrivileges` .

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnesinde içerilen ayrıcalıkların sayısını döndürür `CTokenPrivileges` .

## <a name="ctokenprivilegesgetlength"></a><a name="getlength"></a> CTokenPrivileges:: GetLength

Nesnenin uzunluğunu döndürür `CTokenPrivileges` .

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`TOKEN_PRIVILEGES` `CTokenPrivileges` İçerdiği tüm ayrıcalık girişleri dahil olmak üzere, nesne tarafından temsil edilen bir yapıyı tutmak için gereken bayt sayısını döndürür.

## <a name="ctokenprivilegesgetluidsandattributes"></a><a name="getluidsandattributes"></a> CTokenPrivileges:: Getluıdsandattributes

Nesnesinden yerel olarak benzersiz tanımlayıcılar (LUIDs) ve öznitelik bayraklarını alır `CTokenPrivileges` .

```cpp
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pPrivileges*<br/>
[LUID](/windows/win32/api/winnt/ns-winnt-luid) nesnelerinin dizisine yönelik işaretçi. `CLUIDArray` , olarak tanımlanan bir typedef `CAtlArray<LUID> CLUIDArray` .

*pAttributes*<br/>
Bir DWORD nesneleri dizisine yönelik işaretçi. Bu parametre atlanırsa veya NULL ise, öznitelikler alınmadı. `CAttributes` , olarak tanımlanan bir typedef `CAtlArray <DWORD> CAttributes` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, erişim belirteci nesnesinde bulunan tüm ayrıcalıkların listesini alır `CTokenPrivileges` ve bağımsız LUIDs ve (isteğe bağlı olarak) öznitelik bayraklarını dizi nesnelerine yerleştirir.

## <a name="ctokenprivilegesgetnamesandattributes"></a><a name="getnamesandattributes"></a> CTokenPrivileges:: GetNamesAndAttributes

Nesneden Name ve Attribute bayraklarını alır `CTokenPrivileges` .

```cpp
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pNames 'lar*<br/>
Nesne dizisine yönelik işaretçi `CString` . `CNames` , olarak tanımlanan bir typedef `CAtlArray <CString> CNames` .

*pAttributes*<br/>
Bir DWORD nesneleri dizisine yönelik işaretçi. Bu parametre atlanırsa veya NULL ise, öznitelikler alınmadı. `CAttributes` , olarak tanımlanan bir typedef `CAtlArray <DWORD> CAttributes` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, nesnesinde yer alan tüm ayrıcalıkların listesini `CTokenPrivileges` , adını ve (isteğe bağlı olarak) öznitelik bayraklarını dizi nesnelerine yerleştirmeyecektir.

Bu yöntem, görüntülenebilen ad yerine öznitelik adını alır: Örneğin, öznitelik adı SE_REMOTE_SHUTDOWN_NAME, sistem adı "SeRemoteShutdownPrivilege" olur. Görüntülenebilen adı almak için [CTokenPrivileges:: GetDisplayNames](#getdisplaynames)metodunu kullanın.

## <a name="ctokenprivilegesgetptoken_privileges"></a><a name="getptoken_privileges"></a> CTokenPrivileges:: GetPTOKEN_PRIVILEGES

Yapıya bir işaretçi döndürür `TOKEN_PRIVILEGES` .

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) yapısına bir işaretçi döndürür.

## <a name="ctokenprivilegeslookupprivilege"></a><a name="lookupprivilege"></a> CTokenPrivileges:: LookupPrivilege

Verilen ayrıcalık adı ile ilişkili özniteliği alır.

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pszPrivilege*<br/>
WINNT içinde tanımlandığı şekilde, ayrıcalığın adını belirten null ile sonlandırılmış bir dize işaretçisi. H üstbilgi dosyası. Örneğin, bu parametre sabit SE_SECURITY_NAME veya karşılık gelen "SeSecurityPrivilege" dizesini belirtebilir.

*pdwAttributes*<br/>
Öznitelikleri alan bir değişkene yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Öznitelik başarıyla alınırsa true, aksi takdirde false döndürür.

## <a name="ctokenprivilegesoperator-"></a><a name="operator_eq"></a> CTokenPrivileges:: operator =

Atama işleci.

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*rPrivileges*<br/>
Nesneye atanacak [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) yapısı `CTokenPrivileges` .

*sağ taraftan*<br/>
`CTokenPrivileges`Nesneye atanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneyi döndürür `CTokenPrivileges` .

## <a name="ctokenprivilegesoperator-const-token_privileges-"></a><a name="operator_const_token_privileges__star"></a> CTokenPrivileges:: operator const TOKEN_PRIVILEGES \*

Yapının işaretçisine bir değer yayınlar `TOKEN_PRIVILEGES` .

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>Açıklamalar

[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) yapısına bir işaretçiye değer yayınlar.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik örneği](../../overview/visual-cpp-samples.md)<br/>
[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)<br/>
[DEĞERINI](/windows/win32/api/winnt/ns-winnt-luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel Işlevleri](../../atl/reference/security-global-functions.md)
