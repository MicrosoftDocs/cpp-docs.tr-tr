---
title: CSacl Sınıfı
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
ms.openlocfilehash: 72b5c9fee3868286f9e4a0917f46aeb732349c62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331002"
---
# <a name="csacl-class"></a>CSacl Sınıfı

Bu sınıf, Bir SACL (sistem erişim denetim listesi) yapısı için bir sarmalayıcıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CSacl : public CAcl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSacl::CSacl](#csacl)|Oluşturucu.|
|[CSacl::~CSacl](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSacl::AddAuditAce](#addauditace)|`CSacl` Nesneye bir denetim erişim denetimi girişi (ACE) ekler.|
|[CSacl::GetAceCount](#getacecount)|`CSacl` Nesnedeki erişim denetimi girişlerinin (ACE' ler) sayısını verir.|
|[CSacl::RemoveAce](#removeace)|`CSacl` Nesneden belirli bir ACE (erişim denetimi girişi) kaldırır.|
|[CSacl::RemoveAllAces](#removeallaces)|`CSacl` Nesnede bulunan tüm ACE'leri kaldırır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CSacl::operatör =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

SACL, etki alanı denetleyicisinin güvenlik olay günlüğünde denetim kayıtları oluşturan erişim denemelerinin türlerini belirten erişim denetimi girişleri (ACE'ler) içerir. SACL'nin, nesnenin bir kopyasını içeren her etki alanı denetleyicisinde değil, yalnızca erişim girişiminin gerçekleştiği etki alanı denetleyicisinde günlük girişleri oluşturduğunu unutmayın.

Bir nesnenin güvenlik tanımlayıcısında SACL'yi ayarlamak veya almak için, istenen iş parçacığının erişim belirtecinde SE_SECURITY_NAME ayrıcalığı etkinleştirilmelidir. Yöneticiler grubunda varsayılan olarak verilen bu ayrıcalık vardır ve diğer kullanıcılara veya gruplara verilebilir. Verilen ayrıcalığın verilmesi gereken tek şey değildir: ayrıcalık tarafından tanımlanan işlem gerçekleştirilebilmesi için, etkinol için güvenlik erişim belirtecinde ayrıcalığın etkinleştirilmesi gerekir. Model, ayrıcalıkların yalnızca belirli sistem işlemleri için etkinleştirilmesine ve artık gerekmediğinde devre dışı bırakılmasına olanak tanır. SE_SECURITY_NAME etkinleştirme örnekleri için [AtlGetSacl](security-global-functions.md#atlgetsacl) ve [AtlSetSacl'a](security-global-functions.md#atlsetsacl) bakın.

Ace'leri nesneden eklemek, kaldırmak, oluşturmak ve silmek için sağlanan sınıf yöntemlerini `SACL` kullanın. Ayrıca bakınız [AtlGetSacl](security-global-functions.md#atlgetsacl) ve [AtlSetSacl](security-global-functions.md#atlsetsacl).

Windows'daki erişim denetimi modeline giriş için Windows SDK'daki [Access Denetimi'ne](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cacl](../../atl/reference/cacl-class.md)

`CSacl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="csacladdauditace"></a><a name="addauditace"></a>CSacl::AddAuditAce

`CSacl` Nesneye bir denetim erişim denetimi girişi (ACE) ekler.

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

*rSid*<br/>
[CSid nesnesi.](../../atl/reference/csid-class.md)

*Accessmask*<br/>
Belirtilen `CSid` nesne için denetlenecek erişim haklarının maskesini belirtir.

*bBaşarı*<br/>
İzin verilen erişim girişimlerinin denetlenip denetlenmeyeceğini belirtir. Denetimi etkinleştirmek için bu bayrağı doğru olarak ayarlayın; aksi takdirde, yanlış ayarlayın.

*bBaşarısızlık*<br/>
Reddedilen erişim girişimlerinin denetlenip denetlenmeyeceğini belirtir. Denetimi etkinleştirmek için bu bayrağı doğru olarak ayarlayın; aksi takdirde, yanlış ayarlayın.

*AceFlags*<br/>
ACE kalıtımını kontrol eden bit bayrakları kümesi.

*pObjectType*<br/>
Nesne türü.

*pInheritedObjectType*<br/>
Devralınan nesne türü.

### <a name="return-value"></a>Dönüş Değeri

ACE `CSacl` nesneye eklenirse TRUE döndürür, hata üzerine FALSE.

### <a name="remarks"></a>Açıklamalar

Nesne, `CSacl` güvenlik olayı günlüğünde denetim kayıtları oluşturan erişim denemelerinin türlerini belirten erişim denetimi girişleri (ACE'ler) içerir. Bu yöntem `CSacl` nesneye böyle bir ACE ekler.

*AceFlags* parametresinde ayarlanabilen çeşitli bayrakların açıklaması için [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) bakın.

## <a name="csaclcsacl"></a><a name="csacl"></a>CSacl::CSacl

Oluşturucu.

```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
Varolan `ACL` (erişim denetim listesi) yapısı.

### <a name="remarks"></a>Açıklamalar

Nesne `CSacl` isteğe bağlı olarak varolan `ACL` bir yapı kullanılarak oluşturulabilir. Bu parametrenin isteğe bağlı erişim kontrol listesi (DACL) değil, bir sistem erişim denetim listesi (SACL) olduğundan emin olun. Hata ayıklama yapılarda, bir DACL sağlanırsa bir iddia oluşur. Sürümde bir DACL herhangi bir girişleri oluşturur yoksayılır.

## <a name="csaclcsacl"></a><a name="dtor"></a>CSacl::~CSacl

Yıkıcı.

```
~CSacl() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, nesne tarafından edinilen tüm erişim denetimi girişleri (ACE'ler) dahil olmak üzere tüm kaynakları serbest bırakmaz.

## <a name="csaclgetacecount"></a><a name="getacecount"></a>CSacl::GetAceCount

`CSacl` Nesnedeki erişim denetimi girişlerinin (ACE' ler) sayısını verir.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CSacl` Nesnede bulunan ACE sayısını döndürür.

## <a name="csacloperator-"></a><a name="operator_eq"></a>CSacl::operatör =

Atama işleci.

```
CSacl& operator=(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
Varolan `ACL` nesneye atamak için (erişim denetim listesi).

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CSacl` nesneye bir başvuru verir. Parametrenin `ACL` isteğe bağlı erişim denetim listesi (DACL) değil, aslında bir sistem erişim denetim listesi (SACL) olduğundan emin olun. Hata ayıklama bir iddia oluşur ve sürümde `ACL` parametre yoksayılır oluşturur.

## <a name="csaclremoveace"></a><a name="removeace"></a>CSacl::RemoveAce

`CSacl` Nesneden belirli bir ACE (erişim denetimi girişi) kaldırır.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Kaldırmak için ACE girişine dizin.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CAtlArray türetilmiştir::RemoveAt](../../atl/reference/catlarray-class.md#removeat).

## <a name="csaclremoveallaces"></a><a name="removeallaces"></a>CSacl::RemoveAllAces

`CSacl` Nesnede bulunan tüm erişim denetimi girişlerini (ACE'ler) kaldırır.

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesnedeki `ACE` her yapıyı `CSacl` (varsa) kaldırır.

## <a name="see-also"></a>Ayrıca bkz.

[CAcl Sınıfı](../../atl/reference/cacl-class.md)<br/>
[Acl](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Ace](/windows/win32/SecAuthZ/access-control-entries)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
