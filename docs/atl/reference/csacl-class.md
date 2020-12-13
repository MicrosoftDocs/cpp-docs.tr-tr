---
description: 'Daha fazla bilgi edinin: CSacl sınıfı'
title: CSacl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
ms.openlocfilehash: 504276d22da963b9e8ec407e88ca73d63dd71541
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140861"
---
# <a name="csacl-class"></a>CSacl sınıfı

Bu sınıf, bir SACL (sistem erişim denetimi listesi) yapısına yönelik bir sarmalayıcıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CSacl : public CAcl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSacl:: CSacl](#csacl)|Oluşturucu.|
|[CSacl:: ~ CSacl](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSacl:: AddAuditAce](#addauditace)|Nesnesine bir denetim erişim denetimi girişi (ACE) ekler `CSacl` .|
|[CSacl:: GetAceCount](#getacecount)|Nesnedeki erişim denetimi girişlerinin (ACE) sayısını döndürür `CSacl` .|
|[CSacl:: RemoveAce](#removeace)|Nesnesinden belirli bir ACE 'yi (erişim denetimi girişi) kaldırır `CSacl` .|
|[CSacl:: RemoveAllAces](#removeallaces)|Nesnesinde bulunan tüm Ace 'Leri kaldırır `CSacl` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CSacl:: operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

Bir SACL, bir etki alanı denetleyicisinin güvenlik olay günlüğünde denetim kayıtları üreten erişim denemeleri türlerini belirten erişim denetimi girdileri (ACE 'Ler) içerir. Bir SACL 'nin yalnızca erişim girişiminin gerçekleştiği etki alanı denetleyicisinde, nesnenin bir çoğaltmasını içeren her etki alanı denetleyicisinde değil, günlük girişleri oluşturmadığını unutmayın.

Bir nesnenin güvenlik tanımlayıcısına sahip SACL ayarlamak veya almak için, istenen iş parçacığının erişim belirtecinde SE_SECURITY_NAME ayrıcalığının etkinleştirilmesi gerekir. Yöneticiler grubu varsayılan olarak bu ayrıcalığa sahiptir ve diğer kullanıcılara veya gruplara verilebilir. Ayrıcalığa izin verilmesi gereken tek şey gerekli değildir: ayrıcalık tarafından tanımlanan işlem gerçekleştirilemediği için, bu ayrıcalık, etkin olması için güvenlik erişim belirtecinde etkinleştirilmelidir. Model ayrıcalıkların yalnızca belirli sistem işlemlerinde etkinleştirilmesini sağlar ve artık gerekli olmadığında devre dışı kalır. SE_SECURITY_NAME etkinleştirme örnekleri için bkz. [AtlGetSacl](security-global-functions.md#atlgetsacl) ve [AtlSetSacl](security-global-functions.md#atlsetsacl) .

Nesnesinden Ace 'Leri eklemek, kaldırmak, oluşturmak ve silmek için belirtilen sınıf yöntemlerini kullanın `SACL` . Ayrıca bkz. [AtlGetSacl](security-global-functions.md#atlgetsacl) ve [AtlSetSacl](security-global-functions.md#atlsetsacl).

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAcl](../../atl/reference/cacl-class.md)

`CSacl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

## <a name="csacladdauditace"></a><a name="addauditace"></a> CSacl:: AddAuditAce

Nesnesine bir denetim erişim denetimi girişi (ACE) ekler `CSacl` .

```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
[CSID](../../atl/reference/csid-class.md) nesnesi.

*AccessMask*<br/>
Belirtilen nesne için denetlenecek erişim haklarının maskesini belirtir `CSid` .

*bSuccess*<br/>
İzin verilen erişim girişimlerinin denetlenmesi gerekip gerekmediğini belirtir. Denetimi etkinleştirmek için bu bayrağı true olarak ayarlayın; Aksi takdirde, false olarak ayarlayın.

*bFailure*<br/>
Reddedilen erişim girişimlerinin denetlenmesi gerekip gerekmediğini belirtir. Denetimi etkinleştirmek için bu bayrağı true olarak ayarlayın; Aksi takdirde, false olarak ayarlayın.

*Asetat bayrakları*<br/>
ACE devralmayı denetleyen bit bayrakları kümesi.

*pObjectType*<br/>
Nesne türü.

*Pınheritedobjecttype*<br/>
Devralınan nesne türü.

### <a name="return-value"></a>Dönüş Değeri

ACE nesneye eklenirse TRUE `CSacl` , hata durumunda FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bir `CSacl` nesne, güvenlik olay günlüğünde denetim kayıtları üreten erişim denemeleri türlerini belirten erişim denetimi girdileri (ACE 'ler) içerir. Bu yöntem, nesnesine bir ACE ekler `CSacl` .

*Asetat bayrakları* parametresinde ayarlanbilen çeşitli bayrakların açıklaması için bkz. [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

## <a name="csaclcsacl"></a><a name="csacl"></a> CSacl:: CSacl

Oluşturucu.

```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
Var olan bir `ACL` (erişim denetimi listesi) yapısı.

### <a name="remarks"></a>Açıklamalar

`CSacl`Nesne, isteğe bağlı olarak, var olan bir `ACL` Yapı kullanılarak oluşturulabilir. Bu parametrenin bir sistem erişim denetimi listesi (SACL) olduğundan ve isteğe bağlı erişim denetimi listesi (DACL) olduğundan emin olun. Hata ayıklama yapılarında, bir DACL sağlanırsa bir onaylama gerçekleşmeyecektir. Sürüm, bir DACL 'den gelen tüm girdileri yok sayılır.

## <a name="csaclcsacl"></a><a name="dtor"></a> CSacl:: ~ CSacl

Yok edicisi.

```
~CSacl() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, tüm erişim denetimi girdileri (ACE 'Ler) dahil olmak üzere, nesne tarafından alınan tüm kaynakları serbest bırakır.

## <a name="csaclgetacecount"></a><a name="getacecount"></a> CSacl:: GetAceCount

Nesnedeki erişim denetimi girişlerinin (ACE) sayısını döndürür `CSacl` .

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnede bulunan ACE sayısını döndürür `CSacl` .

## <a name="csacloperator-"></a><a name="operator_eq"></a> CSacl:: operator =

Atama işleci.

```
CSacl& operator=(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
`ACL`Mevcut nesneye atanacak (erişim denetimi listesi).

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneye bir başvuru döndürür `CSacl` . `ACL`Parametrenin gerçekten bir sistem erişim denetimi listesi (SACL) olduğundan ve isteğe bağlı erişim denetimi listesi (DACL) olduğundan emin olun. Hata ayıklama Derlemeleriyle bir onaylama gerçekleşir ve yayın derlemeleri içinde `ACL` parametre yok sayılır.

## <a name="csaclremoveace"></a><a name="removeace"></a> CSacl:: RemoveAce

Nesnesinden belirli bir ACE 'yi (erişim denetimi girişi) kaldırır `CSacl` .

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Kaldırılacak ACE girişinin dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CAtlArray:: removeadresinden](../../atl/reference/catlarray-class.md#removeat)türetilir.

## <a name="csaclremoveallaces"></a><a name="removeallaces"></a> CSacl:: RemoveAllAces

Nesnesinde yer alan erişim denetimi girişlerinin (ACE) tümünü kaldırır `CSacl` .

```cpp
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesnedeki her `ACE` yapıyı (varsa) kaldırır `CSacl` .

## <a name="see-also"></a>Ayrıca bkz.

[CAcl sınıfı](../../atl/reference/cacl-class.md)<br/>
[Cacls](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Ace 'ler](/windows/win32/SecAuthZ/access-control-entries)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel Işlevleri](../../atl/reference/security-global-functions.md)
