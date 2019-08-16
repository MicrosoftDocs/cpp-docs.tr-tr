---
title: CDacl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
ms.openlocfilehash: a37ef47a4ea89d9ec24fac417e5b715bd2602fd7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496924"
---
# <a name="cdacl-class"></a>CDacl sınıfı

Bu sınıf, bir DACL (isteğe bağlı erişim denetimi listesi) yapısına yönelik bir sarmalayıcıdır.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CDacl : public CAcl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDacl:: CDacl](#cdacl)|Oluşturucu.|
|[CDacl::~CDacl](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDacl:: Addallowedadce](#addallowedace)|`CDacl` Nesnesine izin verilen ACE (erişim denetimi girişi) ekler.|
|[CDacl::AddDeniedAce](#adddeniedace)|`CDacl` Nesnesine bir reddedildi ace ekler.|
|[CDacl:: GetAceCount](#getacecount)|`CDacl` Nesnedeki ACE sayısını (erişim denetimi girdileri) döndürür.|
|[CDacl:: RemoveAce](#removeace)|`CDacl` Nesnesinden belirli bir ACE 'yi (erişim denetimi girişi) kaldırır.|
|[CDacl:: RemoveAllAces](#removeallaces)|`CDacl` Nesnesinde bulunan tüm Ace 'leri kaldırır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CDacl:: operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

Bir nesnenin güvenlik tanımlayıcısı, bir DACL içerebilir. Bir DACL, nesneye erişebilen kullanıcıları ve grupları belirleyen sıfır veya daha fazla ACE (erişim denetimi girişleri) içerir. Bir DACL boşsa (yani sıfır Ace 'Leri içeriyorsa), erişim örtük olarak reddedilir. Ancak, bir nesnenin güvenlik tanımlayıcısının bir DACL 'si yoksa, nesne korumasız olur ve herkesin erişimi tamamlanmıştır.

Bir nesnenin DACL 'sini almak için nesnenin sahibi olmanız veya nesneye READ_CONTROL erişiminizin olması gerekir. Bir nesnenin DACL 'sini değiştirmek için, nesnesine WRITE_DAC erişiminizin olması gerekir.

`CDacl` Nesnesinden Ace 'ler oluşturmak, eklemek, kaldırmak ve silmek için belirtilen sınıf yöntemlerini kullanın. Ayrıca bkz. [AtlGetDacl](security-global-functions.md#atlgetdacl) ve [AtlSetDacl](security-global-functions.md#atlsetdacl).

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAcl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="addallowedace"></a>CDacl:: Addallowedadce

`CDacl` Nesnesine izin verilen ACE (erişim denetimi girişi) ekler.

```
bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
Bir [CSID](../../atl/reference/csid-class.md) nesnesi.

*AccessMask*<br/>
Belirtilen `CSid` nesne için izin verilen erişim haklarının maskesini belirtir.

*Asetat bayrakları*<br/>
ACE devralmayı denetleyen bit bayrakları kümesi.

*pObjectType*<br/>
Nesne türü.

*Pınheritedobjecttype*<br/>
Devralınan nesne türü.

### <a name="return-value"></a>Dönüş Değeri

Ace `CDacl` nesneye eklenirse true, hata durumunda FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CDacl` Nesne, nesnesine erişebilen kullanıcıları ve grupları belirleyen sıfır veya daha fazla ACE (erişim denetimi girişleri) içerir. Bu yöntem, `CDacl` nesnesine erişime izin veren bir ace ekler.

`AceFlags` Parametresinde ayarlayabilen çeşitli bayrakların açıklaması için bkz. [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

##  <a name="adddeniedace"></a>CDacl:: Adddenıedadce

`CDacl` Nesneye reddedilen ACE (erişim denetimi girişi) ekler.

```
bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rsıd*<br/>
A `CSid` nesne.

*AccessMask*<br/>
Belirtilen `CSid` nesne için izin verilmeyen erişim haklarının maskesini belirtir.

*Asetat bayrakları*<br/>
ACE devralmayı denetleyen bit bayrakları kümesi. Metodun ilk biçiminde varsayılan değer 0 ' dır.

*pObjectType*<br/>
Nesne türü.

*Pınheritedobjecttype*<br/>
Devralınan nesne türü.

### <a name="return-value"></a>Dönüş Değeri

Ace `CDacl` nesneye eklenirse true, hata durumunda FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`CDacl` Nesne, nesnesine erişebilen kullanıcıları ve grupları belirleyen sıfır veya daha fazla ACE (erişim denetimi girişleri) içerir. Bu yöntem, `CDacl` nesnesine erişimi reddeden bir ace ekler.

`AceFlags` Parametresinde ayarlayabilen çeşitli bayrakların açıklaması için bkz. [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

##  <a name="cdacl"></a>CDacl:: CDacl

Oluşturucu.

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
Var olan `ACL` bir (erişim denetimi listesi) yapısı.

### <a name="remarks"></a>Açıklamalar

Nesne `CDacl` , isteğe bağlı olarak, var olan `ACL` bir yapı kullanılarak oluşturulabilir. Yalnızca bir DACL (sistem erişimi-denetim listesi) değil, bu parametre olarak bir DACL (bir isteğe bağlı erişim denetimi listesi) geçtiğini unutmayın. Hata ayıklama yapılarında, SACL geçirilmesi bir onaylama yapılmasına neden olur. Yayın yapıları ' nda, SACL 'nin geçirilmesi ACL 'deki ACE (erişim denetimi girdileri) yoksayılmasına neden olur ve hata oluşmaz.

##  <a name="dtor"></a>  CDacl::~CDacl

Yok edicisi.

```
~CDacl () throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, [CDacl:: RemoveAllAces](#removeallaces)kullanarak tüm Ace 'ler (erişim-denetim girişleri) dahil olmak üzere, nesne tarafından alınan tüm kaynakları serbest bırakır.

##  <a name="getacecount"></a>CDacl:: GetAceCount

`CDacl` Nesnedeki ACE sayısını (erişim denetimi girdileri) döndürür.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CDacl` Nesnede bulunan ACE sayısını döndürür.

##  <a name="operator_eq"></a>CDacl:: operator =

Atama işleci.

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
Mevcut nesneye atanacak ACL (erişim denetimi listesi).

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CDacl` nesneye bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işleve yalnızca bir DACL (isteğe bağlı erişim denetimi listesi) iletdiğinizden emin olmanız gerekir. Bu işleve bir SACL (sistem erişim denetimi listesi) geçirmek hata ayıklama yapılarında bir onaylama yapılmasına neden olur, ancak yayın yapılarında hata vermez.

##  <a name="removeace"></a>CDacl:: RemoveAce

`CDacl` Nesnesinden belirli bir ACE 'yi (erişim denetimi girişi) kaldırır.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Kaldırılacak ACE girişinin dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CAtlArray:: removeadresinden](../../atl/reference/catlarray-class.md#removeat)türetilir.

##  <a name="removeallaces"></a>CDacl:: RemoveAllAces

`CDacl` Nesnesinde bulunan tüm Ace 'leri (erişim denetimi girdileri) kaldırır.

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesnesinde ( `ACE` varsa) her (erişim denetimi girişi) yapısını kaldırır. `CDacl`

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik örneği](../../overview/visual-cpp-samples.md)<br/>
[CAcl Sınıfı](../../atl/reference/cacl-class.md)<br/>
[Cacls](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Ace 'ler](/windows/win32/SecAuthZ/access-control-entries)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
