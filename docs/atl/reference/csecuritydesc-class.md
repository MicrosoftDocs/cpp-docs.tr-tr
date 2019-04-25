---
title: CSecurityDesc sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::FromString
- ATLSECURITY/ATL::CSecurityDesc::GetControl
- ATLSECURITY/ATL::CSecurityDesc::GetDacl
- ATLSECURITY/ATL::CSecurityDesc::GetGroup
- ATLSECURITY/ATL::CSecurityDesc::GetOwner
- ATLSECURITY/ATL::CSecurityDesc::GetPSECURITY_DESCRIPTOR
- ATLSECURITY/ATL::CSecurityDesc::GetSacl
- ATLSECURITY/ATL::CSecurityDesc::IsDaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsDaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsDaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsDaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsGroupDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsOwnerDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsSaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsSaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::MakeAbsolute
- ATLSECURITY/ATL::CSecurityDesc::MakeSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::SetControl
- ATLSECURITY/ATL::CSecurityDesc::SetDacl
- ATLSECURITY/ATL::CSecurityDesc::SetGroup
- ATLSECURITY/ATL::CSecurityDesc::SetOwner
- ATLSECURITY/ATL::CSecurityDesc::SetSacl
- ATLSECURITY/ATL::CSecurityDesc::ToString
helpviewer_keywords:
- CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
ms.openlocfilehash: aadaa64a936aee867766dfc0f7a6e190c9691ca6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277974"
---
# <a name="csecuritydesc-class"></a>CSecurityDesc sınıfı

Bu sınıf için bir sarmalayıcı olan `SECURITY_DESCRIPTOR` yapısı.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CSecurityDesc
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSecurityDesc::CSecurityDesc](#csecuritydesc)|Oluşturucu.|
|[CSecurityDesc::~CSecurityDesc](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSecurityDesc::FromString](#fromstring)|Dize biçimi güvenlik tanımlayıcısı geçerli, işlevsel güvenlik niteleyicisine dönüştürür.|
|[CSecurityDesc::GetControl](#getcontrol)|Alır, bilgi güvenlik tanımlayıcısı denetler.|
|[CSecurityDesc::GetDacl](#getdacl)|Güvenlik tanımlayıcısından isteğe bağlı erişim denetimi listesini (DACL) bilgilerini alır.|
|[CSecurityDesc::GetGroup](#getgroup)|Birincil grup bilgilerini güvenlik tanımlayıcısını alır.|
|[CSecurityDesc::GetOwner](#getowner)|Güvenlik tanımlayıcısı sahibi bilgi alır.|
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|Bir işaretçi döndürür `SECURITY_DESCRIPTOR` yapısı.|
|[CSecurityDesc::GetSacl](#getsacl)|Güvenlik tanımlayıcısının sistem erişim denetimi listesini (SACL) bilgileri alır.|
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|DACL otomatik yayma destekleyecek şekilde yapılandırılıp yapılandırılmadığını belirler.|
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|Güvenlik tanımlayıcısı varsayılan bir DACL ile yapılandırıp yapılandırılmadığını belirler.|
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|Güvenlik tanımlayıcısının DACL içerip içermediğini belirler.|
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|DACL değişiklikleri önlemek için yapılandırılmış olup olmadığını belirler.|
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|Güvenlik Tanımlayıcısı'nın grup güvenlik tanımlayıcısını (SID) varsayılan olarak ayarlandığını belirler.|
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|Güvenlik Tanımlayıcısı'nın sahibi SID'si varsayılan olarak ayarlandığını belirler.|
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|SACL otomatik yayma destekleyecek şekilde yapılandırılıp yapılandırılmadığını belirler.|
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|Güvenlik tanımlayıcısının SACL varsayılan ile yapılandırıp yapılandırılmadığını belirler.|
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|Güvenlik tanımlayıcısının SACL içerip içermediğini belirler.|
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|SACL değişiklikleri önlemek için yapılandırılmış olup olmadığını belirler.|
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|Güvenlik tanımlayıcısı kendine bağlı biçimde olup olmadığını belirler.|
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|Mutlak biçimde güvenlik tanımlayıcısı dönüştürmek için bu yöntemi çağırın.|
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|Güvenlik tanımlayıcısı kendine bağlı biçimine dönüştürmek için bu yöntemi çağırın.|
|[CSecurityDesc::SetControl](#setcontrol)|Güvenlik tanımlayıcısının denetim bitlerini ayarlar.|
|[CSecurityDesc::SetDacl](#setdacl)|İçinde bir DACL bilgilerini ayarlar. Bir DACL, güvenlik tanımlayıcısı zaten varsa, değiştirilir.|
|[CSecurityDesc::SetGroup](#setgroup)|Zaten mevcut herhangi bir birincil grup bilgilerini değiştirerek bir mutlak biçimde güvenlik tanımlayıcısı birincil grup bilgilerini ayarlar.|
|[CSecurityDesc::SetOwner](#setowner)|Zaten mevcut herhangi bir sahiplik bilgilerini değiştirerek bir mutlak biçimde güvenlik tanımlayıcısı sahibi bilgilerini ayarlar.|
|[CSecurityDesc::SetSacl](#setsacl)|İçinde bir SACL bilgilerini ayarlar. Bir SACL, güvenlik tanımlayıcısı zaten varsa, değiştirilir.|
|[CSecurityDesc::ToString](#tostring)|Bir güvenlik tanımlayıcısının dize biçimine dönüştürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Const SECURITY_DESCRIPTOR CSecurityDesc::operator *](#operator_const_security_descriptor__star)|Bir işaretçi döndürür `SECURITY_DESCRIPTOR` yapısı.|
|[CSecurityDesc::operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

`SECURITY_DESCRIPTOR` Yapısı bir nesneyle ilişkilendirilmiş güvenlik bilgileri içerir. Uygulamalar bu yapı ayarlayın ve bir nesnenin güvenlik durumunu sorgulamak için kullanır. Ayrıca bkz: [AtlGetSecurityDescriptor](security-global-functions.md#atlgetsecuritydescriptor).

Uygulamaları değişiklik `SECURITY_DESCRIPTOR` yapısı doğrudan ve bunun yerine kullanması gereken sağlanan sınıfı yöntemleri.

Windows, erişim denetimi modeli için bir giriş için bkz [erişim denetimi](/windows/desktop/SecAuthZ/access-control) Windows SDK.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="csecuritydesc"></a>  CSecurityDesc::CSecurityDesc

Oluşturucu.

```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
`CSecurityDesc` Nesne veya `SECURITY_DESCRIPTOR` yeni atamak yapısı `CSecurityDesc` nesne.

### <a name="remarks"></a>Açıklamalar

`CSecurityDesc` Nesne isteğe bağlı olarak oluşturulabilir kullanarak bir `SECURITY_DESCRIPTOR` yapısı veya önceden tanımlanmış `CSecurityDesc` nesne.

##  <a name="dtor"></a>  CSecurityDesc:: ~ CSecurityDesc

Yıkıcı.

```
virtual ~CSecurityDesc() throw();
```

### <a name="remarks"></a>Açıklamalar

Yok edici ayrılan tüm kaynakları serbest bırakır.

##  <a name="fromstring"></a>  CSecurityDesc::FromString

Dize biçimi güvenlik tanımlayıcısı geçerli, işlevsel güvenlik niteleyicisine dönüştürür.

```
bool FromString(LPCTSTR pstr) throw(...);
```

### <a name="parameters"></a>Parametreler

*pstr*<br/>
İçeren null ile sonlandırılmış bir dize işaretçisine [dize biçimi güvenlik tanımlayıcısı](/windows/desktop/SecAuthZ/security-descriptor-string-format) dönüştürülecek.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true döndürür. Özel durum hatası oluşturur.

### <a name="remarks"></a>Açıklamalar

Dize kullanarak oluşturulabilir [CSecurityDesc::ToString](#tostring). Güvenlik tanımlayıcısı bir dizeye dönüştürme depolayıp iletmek kolaylaştırır.

Bu yöntemin çağırdığı [ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/desktop/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptora).

##  <a name="getcontrol"></a>  CSecurityDesc::GetControl

Alır, bilgi güvenlik tanımlayıcısı denetler.

```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```

### <a name="parameters"></a>Parametreler

*psdc*<br/>
İşaretçi bir `SECURITY_DESCRIPTOR_CONTROL` güvenlik tanımlayıcının denetim bilgileri alan yapısı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, yanlış başarısız olması durumunda true döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı [GetSecurityDescriptorControl](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-getsecuritydescriptorcontrol).

##  <a name="getdacl"></a>  CSecurityDesc::GetDacl

Güvenlik tanımlayıcısından isteğe bağlı erişim denetimi listesini (DACL) bilgilerini alır.

```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pDacl*<br/>
İşaretçi bir `CDacl` yapısı güvenlik tanımlayıcısı'nın DACL bir kopyasını saklamak için. İsteğe bağlı bir ACL yoksa, yöntem ayarlar *pDacl* güvenlik tanımlayıcısı'nın gizli ACL adresine. İsteğe bağlı bir ACL yoksa hiçbir değer depolanır.

*pbPresent*<br/>
Belirtilen bir güvenlik tanımlayıcısının isteğe bağlı bir ACL'de varlığını gösteren bir değer işaretçisi. Güvenlik tanımlayıcısının isteğe bağlı bir ACL içeriyorsa, bu parametre için true. Güvenlik tanımlayıcısının isteğe bağlı bir ACL içermiyor, bu parametre false olarak ayarlanır.

*pbDefaulted*<br/>
İşaretçi bir bayrak kümesi SE_DACL_DEFAULTED bayrağı değerine `SECURITY_DESCRIPTOR_CONTROL` isteğe bağlı bir ACL için güvenlik tanımlayıcısı varsa yapılandırın. Bu bayrak true ise, gizli ACL'yi varsayılan bir mekanizma tarafından alındı; false ise, gizli ACL, bir kullanıcı tarafından açıkça belirtildi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, yanlış başarısız olması durumunda true döndürür.

##  <a name="getgroup"></a>  CSecurityDesc::GetGroup

Birincil grup bilgilerini güvenlik tanımlayıcısını alır.

```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Psıd*<br/>
İşaretçi bir [CSID](../../atl/reference/csid-class.md) (güvenlik tanımlayıcısı) CDacl içinde depolanan Grup bir kopyasını alır.

*pbDefaulted*<br/>
İşaretçi bir bayrak kümesi SE_GROUP_DEFAULTED bayrağı değerine `SECURITY_DESCRIPTOR_CONTROL` yöntem döndürüldüğünde yapısı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, yanlış başarısız olması durumunda true döndürür.

##  <a name="getowner"></a>  CSecurityDesc::GetOwner

Güvenlik tanımlayıcısı sahibi bilgi alır.

```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*Psıd*<br/>
İşaretçi bir [CSID](../../atl/reference/csid-class.md) (güvenlik tanımlayıcısı) CDacl içinde depolanan Grup bir kopyasını alır.

*pbDefaulted*<br/>
İşaretçi bir bayrak kümesi SE_OWNER_DEFAULTED bayrağı değerine `SECURITY_DESCRIPTOR_CONTROL` yöntem döndürüldüğünde yapısı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, yanlış başarısız olması durumunda true döndürür.

##  <a name="getpsecurity_descriptor"></a>  CSecurityDesc::GetPSECURITY_DESCRIPTOR

Bir işaretçi döndürür `SECURITY_DESCRIPTOR` yapısı.

```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi döndürür [SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) yapısı.

##  <a name="getsacl"></a>  CSecurityDesc::GetSacl

Güvenlik tanımlayıcısının sistem erişim denetimi listesini (SACL) bilgileri alır.

```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSacl*<br/>
İşaretçi bir `CSacl` yapısı güvenlik tanımlayıcının SACL bir kopyasını saklamak için. Bir sistem ACL yoksa, yöntem ayarlar *pSacl* güvenlik tanımlayıcısı'nın sistem ACL adresine. Bir sistem ACL yoksa hiçbir değer depolanır.

*pbPresent*<br/>
Belirtilen güvenlik tanımlayıcısı bir sistemde ACL varlığını göstermek için bir bayrak yöntemi işaretçisine ayarlar. Güvenlik tanımlayıcısı bir sistem ACL içeriyorsa, bu parametre için true. Güvenlik tanımlayıcısı bir sistemi ACL içermiyor, bu parametre false olarak ayarlanır.

*pbDefaulted*<br/>
İşaretçi bir bayrak kümesi SE_SACL_DEFAULTED bayrağı değerine `SECURITY_DESCRIPTOR_CONTROL` bir sistem ACL için güvenlik tanımlayıcısı varsa yapısı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, yanlış başarısız olması durumunda true döndürür.

##  <a name="isdaclautoinherited"></a>  CSecurityDesc::IsDaclAutoInherited

İsteğe bağlı erişim denetimi listesini (DACL) otomatik yayma destekleyecek şekilde yapılandırılıp yapılandırılmadığını belirler.

```
bool IsDaclAutoInherited() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısının devralınabilir bir erişim denetimi girişinin (ACE'ler) mevcut alt nesneleri için otomatik yayılmasını desteklemek için ayarlanan bir DACL içeriyorsa true döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Nesne ve mevcut alt nesneleri için otomatik devralma algoritması gerçekleştirdiğinde, sistem bu bit ayarlar.

##  <a name="isdacldefaulted"></a>  CSecurityDesc::IsDaclDefaulted

Güvenlik tanımlayıcısı varsayılan isteğe bağlı erişim denetimi listesini (DACL) ile yapılandırıp yapılandırılmadığını belirler.

```
bool IsDaclDefaulted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısının DACL, varsayılan false aksi içeriyorsa true döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrak, sistem erişim denetimi girişi (ACE) devralma göre DACL nasıl işler etkileyebilir. Örneğin, bir nesne oluşturan bir DACL belirtmezse, nesne oluşturanın erişim belirtecinden ' % s'varsayılan DACL alır. SE_DACL_PRESENT bayrağı ayarlanmamışsa sistem bu bayrağı yoksayar.

Bu bayrak, nesne üzerinde son DACL nasıl hesaplanmasını belirlemek için kullanılır ve fiziksel olarak güvenli kılınabilir nesne güvenlik tanımlayıcısı denetiminde depolanmaz.

Bu bayrağı ayarlamak için kullanın [CSecurityDesc::SetDacl](#setdacl) yöntemi.

##  <a name="isdaclpresent"></a>  CSecurityDesc::IsDaclPresent

Güvenlik tanımlayıcısının isteğe bağlı erişim denetimi listesini (DACL) içerip içermediğini belirler.

```
bool IsDaclPresent() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısının DACL, yanlış Aksi takdirde içeriyorsa true döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrak ayarlanmamışsa veya NULL DACL Bu bayrak ayarlandığında ve güvenlik tanımlayıcısı herkes için tam erişim sağlar.

Bu bayrak, güvenlik tanımlayıcısı bir güvenli kılınabilir nesne ile ilişkili olduğu kadar çağıran tarafından belirtilen güvenlik bilgileri tutmak için kullanılır. Güvenlik tanımlayıcısı bir güvenli kılınabilir nesne ile ilişkili olduğunda SE_DACL_PRESENT bayrağını her zaman güvenlik tanımlayıcısı denetiminde ayarlanır.

Bu bayrağı ayarlamak için kullanın [CSecurityDesc::SetDacl](#setdacl) yöntemi.

##  <a name="isdaclprotected"></a>  CSecurityDesc::IsDaclProtected

İsteğe bağlı erişim denetimi listesini (DACL) değişiklikleri önlemek için yapılandırıp yapılandırılmadığını belirler.

```
bool IsDaclProtected() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısının devralınabilir bir erişim denetimi girdileri (ACE) tarafından değiştirilmesini önlemek üzere yapılandırılmış DACL true değerini döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için kullanın [CSecurityDesc::SetDacl](#setdacl) yöntemi.

Bu yöntem Devralınabilir ACE otomatik yayılmasını destekler.

##  <a name="isgroupdefaulted"></a>  CSecurityDesc::IsGroupDefaulted

Güvenlik Tanımlayıcısı'nın grup güvenlik tanımlayıcısını (SID) varsayılan olarak ayarlandığını belirler.

```
bool IsGroupDefaulted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

True döndürür özgün sağlayıcısı güvenlik tanımlayıcısı yerine varsayılan bir mekanizma güvenlik tanımlayıcının sağlanırsa, SID gruplandırın. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için kullanın [CSecurityDesc::SetGroup](#setgroup) yöntemi.

##  <a name="isownerdefaulted"></a>  CSecurityDesc::IsOwnerDefaulted

Güvenlik tanımlayıcı sahip güvenlik tanımlayıcısını (SID) varsayılan olarak ayarlandığını belirler.

```
bool IsOwnerDefaulted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısının özgün sağlayıcı yerine varsayılan bir mekanizma güvenlik tanımlayıcının sahibi SID'si sağlanırsa, true döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için kullanın [CSecurityDesc::SetOwner](#setowner) yöntemi.

##  <a name="issaclautoinherited"></a>  CSecurityDesc::IsSaclAutoInherited

Sistem erişim denetimi listesini (SACL) otomatik yayma destekleyecek şekilde yapılandırılıp yapılandırılmadığını belirler.

```
bool IsSaclAutoInherited() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısının devralınabilir bir erişim denetimi girişinin (ACE'ler) mevcut alt nesneleri için otomatik yayılmasını desteklemek için ayarlanan bir SACL içeriyorsa true döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Nesne ve mevcut alt nesneleri için otomatik devralma algoritması gerçekleştirdiğinde, sistem bu bit ayarlar.

##  <a name="issacldefaulted"></a>  CSecurityDesc::IsSaclDefaulted

Güvenlik tanımlayıcısı varsayılan sistem erişim denetimi listesi (SACL) ile yapılandırıp yapılandırılmadığını belirler.

```
bool IsSaclDefaulted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısının SACL, varsayılan false aksi içeriyorsa true döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrak, sistem erişim denetimi girişi (ACE) devralma göre SACL nasıl işler etkileyebilir. SE_SACL_PRESENT bayrağı ayarlanmamışsa sistem bu bayrağı yoksayar.

Bu bayrağı ayarlamak için kullanın [CSecurityDesc::SetSacl](#setsacl) yöntemi.

##  <a name="issaclpresent"></a>  CSecurityDesc::IsSaclPresent

Güvenlik tanımlayıcısının sistem erişim denetimi listesini (SACL) içerip içermediğini belirler.

```
bool IsSaclPresent() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısının SACL, yanlış Aksi takdirde içeriyorsa true döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için kullanın [CSecurityDesc::SetSacl](#setsacl) yöntemi.

##  <a name="issaclprotected"></a>  CSecurityDesc::IsSaclProtected

Sistem erişim denetimi listesini (SACL) değişiklikleri önlemek için yapılandırıp yapılandırılmadığını belirler.

```
bool IsSaclProtected() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

SACL güvenlik tanımlayıcısının devralınabilir bir erişim denetimi girdileri (ACE) tarafından değiştirilmesini önlemek için yapılandırılmışsa, true döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için kullanın [CSecurityDesc::SetSacl](#setsacl) yöntemi.

Bu yöntem Devralınabilir ACE otomatik yayılmasını destekler.

##  <a name="isselfrelative"></a>  CSecurityDesc::IsSelfRelative

Güvenlik tanımlayıcısı kendine bağlı biçimde olup olmadığını belirler.

```
bool IsSelfRelative() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı kendine bağlı biçimde bitişik bir bellek bloğu tüm güvenlik bilgileri ile eşitse true döndürür. Mutlak biçimde güvenlik tanımlayıcısı ise yanlış değerini döndürür. Daha fazla bilgi için [mutlak ve Self-Relative güvenlik tanımlayıcıları](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors).

##  <a name="makeabsolute"></a>  CSecurityDesc::MakeAbsolute

Mutlak biçimde güvenlik tanımlayıcısı dönüştürmek için bu yöntemi çağırın.

```
bool MakeAbsolute() throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, yanlış Aksi takdirde true değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Mutlak biçimde güvenlik tanımlayıcısı, bilgi yerine içerdiği bilgilere işaretçileri içerir. Güvenlik tanımlayıcısı kendine bağlı biçimde bitişik bir bellek bloğunu bilgileri içerir. Kendine bağlı güvenlik tanımlayıcısındaki bir `SECURITY_DESCRIPTOR` yapısı bilgileri her zaman başlar, ancak diğer güvenlik tanımlayıcısı kullanıcının herhangi bir sırada yapısı bileşenleri izleyebilirsiniz. Bellek adreslerini kullanmak yerine, kendine bağlı güvenlik tanımlayıcısı bileşenlerinin güvenlik tanımlayıcısı başından uzaklık tarafından tanımlanır. Bu biçim bir güvenlik tanımlayıcısının bir diskte depolanan veya bir iletişim protokolü aracılığıyla aktarılan yararlı olur. Daha fazla bilgi için [mutlak ve Self-Relative güvenlik tanımlayıcıları](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors).

##  <a name="makeselfrelative"></a>  CSecurityDesc::MakeSelfRelative

Güvenlik tanımlayıcısı kendine bağlı biçimine dönüştürmek için bu yöntemi çağırın.

```
bool MakeSelfRelative() throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, yanlış Aksi takdirde true değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Mutlak biçimde güvenlik tanımlayıcısı bilgilerini içeren yerine, içerdiği bilgilere işaretçileri içerir. Güvenlik tanımlayıcısı kendine bağlı biçimde bitişik bir bellek bloğunu bilgileri içerir. Kendine bağlı güvenlik tanımlayıcısındaki bir `SECURITY_DESCRIPTOR` yapısı bilgileri her zaman başlar, ancak diğer güvenlik tanımlayıcısı kullanıcının herhangi bir sırada yapısı bileşenleri izleyebilirsiniz. Bellek adreslerini kullanmak yerine, güvenlik tanımlayıcısı bileşenlerinin güvenlik tanımlayıcısı başından uzaklık tarafından tanımlanır. Bu biçim bir güvenlik tanımlayıcısının bir diskte depolanan veya bir iletişim protokolü aracılığıyla aktarılan yararlı olur. Daha fazla bilgi için [mutlak ve Self-Relative güvenlik tanımlayıcıları](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors).

##  <a name="operator_eq"></a>  CSecurityDesc::operator =

Atama işleci.

```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
`SECURITY_DESCRIPTOR` Yapısı veya `CSecurityDesc` atamak için nesneyi `CSecurityDesc` nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CSecurityDesc` nesne.

##  <a name="operator_const_security_descriptor__star"></a>  Const SECURITY_DESCRIPTOR CSecurityDesc::operator *

Bir işaretçi değerine çevirir `SECURITY_DESCRIPTOR` yapısı.

```
operator const SECURITY_DESCRIPTOR *() const throw();
```

##  <a name="setcontrol"></a>  CSecurityDesc::SetControl

Güvenlik tanımlayıcısının denetim bitlerini ayarlar.

```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest,
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```

### <a name="parameters"></a>Parametreler

*Controlbitsofınterest*<br/>
Ayarlanacak denetim bitlerini gösteren SECURITY_DESCRIPTOR_CONTROL maskesi. Ayarlanabilecek bayrakların listesi için bkz. [SetSecurityDescriptorControl](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol).

*ControlBitsToSet*<br/>
Tarafından belirtilen denetim bitleri için yeni değerler gösteren SECURITY_DESCRIPTOR_CONTROL maske *Controlbitsofınterest* maskesi. Bu parametre için listelenen bayrakların birleşimi olabilir *Controlbitsofınterest* parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı [SetSecurityDescriptorControl](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol).

##  <a name="setdacl"></a>  CSecurityDesc::SetDacl

İsteğe bağlı erişim denetimi listesini (DACL) bilgilerini ayarlar. Bir DACL, güvenlik tanımlayıcısı zaten varsa, değiştirilir.

```
inline void SetDacl(
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*DACL*<br/>
Başvuru bir `CDacl` güvenlik tanımlayıcısının DACL belirterek nesne. Bu parametre NULL olmamalıdır. Güvenlik tanımlayıcısı NULL DACL ayarlamak için yöntemin ilk formu ile kullanılmalıdır *bPresent* false olarak ayarlayın.

*bPresent*<br/>
Güvenlik tanımlayıcısındaki DACL varlığını gösteren bir bayrak belirtir. Bu parametre true ise, yöntem SE_DACL_PRESENT bayrağı ayarlar `SECURITY_DESCRIPTOR_CONTROL` yapısı ve değerleri kullanan *Dacl* ve *bDefaulted* parametreleri. False ise, yöntem SE_DACL_PRESENT bayrağını temizler ve *bDefaulted* göz ardı edilir.

*bDefaulted*<br/>
DACL kaynağını belirten bir bayrak belirtir. Bu bayrak true ise, DACL bazı varsayılan bir mekanizma tarafından alındı. False ise, bir kullanıcı tarafından açıkça DACL belirtilmedi. Yöntemi, bu değer SE_DACL_DEFAULTED bayrağı depolar `SECURITY_DESCRIPTOR_CONTROL` yapısı. Bu parametre belirtilmezse, SE_DACL_DEFAULTED bayrağı temizlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Varolmayan bir DACL ile boş bir arasındaki önemli bir fark yoktur. Bir DACL boş olduğunda, hiçbir erişim denetimi girdileri içerir ve erişim hakları açıkça verilmiş. Sonuç olarak, bir nesneye erişimi örtük olarak reddedildi. Bir nesne DACL varsa, diğer taraftan, koruma nesneye atanır ve herhangi bir erişim isteğinin verilir.

##  <a name="setgroup"></a>  CSecurityDesc::SetGroup

Zaten mevcut herhangi bir birincil grup bilgilerini değiştirerek bir mutlak biçimde güvenlik tanımlayıcısı birincil grup bilgilerini ayarlar.

```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*SID*<br/>
Başvuru bir [CSID](../../atl/reference/csid-class.md) güvenlik tanımlayıcısı'nın yeni birincil grubu için nesne. Bu parametre NULL olmamalıdır. Bir güvenlik tanımlayıcısının DACL veya SACL olmaması olarak işaretlenebilir, ancak bunlar bile bir grubu ve bir sahibi olması gerekir (yerleşik bir SID ile özel bir anlamı olan) NULL SID olan.

*bDefaulted*<br/>
Birincil grup bilgileri varsayılan bir mekanizma türetilmişti gösterir. Bu değer true ise, varsayılan bilgilerdir ve yöntem SE_GROUP_DEFAULTED bayrağı olarak bu değeri depolar. `SECURITY_DESCRIPTOR_CONTROL` yapısı. Bu parametre sıfır ise SE_GROUP_DEFAULTED bayrağı temizlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

##  <a name="setowner"></a>  CSecurityDesc::SetOwner

Bir mutlak biçimde güvenlik tanımlayıcısı sahibi bilgilerini ayarlar. Zaten mevcut herhangi bir sahiplik bilgilerini değiştirir.

```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*SID*<br/>
[CSID](../../atl/reference/csid-class.md) nesne için güvenlik tanımlayıcısı'nın yeni birincil sahibi. Bu parametre NULL olmamalıdır.

*bDefaulted*<br/>
Sahiplik bilgilerini varsayılan bir mekanizma türetilip türetilmediğini gösterir. Bu değer true ise, varsayılan bilgileri olur. Yöntemi, SE_OWNER_DEFAULTED bayrağı olarak bu değeri depolar. `SECURITY_DESCRIPTOR_CONTROL` yapısı. Bu parametre sıfır ise SE_OWNER_DEFAULTED bayrağı temizlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

##  <a name="setsacl"></a>  CSecurityDesc::SetSacl

Sistem erişim denetimi listesini (SACL) bilgilerini ayarlar. Bir SACL, güvenlik tanımlayıcısı zaten varsa, değiştirilir.

```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*SACL*<br/>
İşaretçi bir `CSacl` güvenlik tanımlayıcısının SACL belirterek nesne. Bu parametre NULL olmamalı ve CSacl nesnesi olmalıdır. DACL, NULL ve boş bir SACL arasında fark SACL nesneleri erişim hakları, yalnızca bilgi denetimini belirtmeyin gibi bulunur.

*bDefaulted*<br/>
SACL kaynağını belirten bir bayrak belirtir. Bu bayrak true ise, SACL bazı varsayılan bir mekanizma tarafından alındı. False ise, bir kullanıcı tarafından açıkça SACL belirtilmedi. Yöntemi, bu değer SE_SACL_DEFAULTED bayrağı depolar `SECURITY_DESCRIPTOR_CONTROL` yapısı. Bu parametre belirtilmezse, SE_SACL_DEFAULTED bayrağı temizlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

##  <a name="tostring"></a>  CSecurityDesc::ToString

Bir güvenlik tanımlayıcısının dize biçimine dönüştürür.

```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pstr*<br/>
Alacak null ile sonlandırılmış bir dize işaretçisi [dize biçimi güvenlik tanımlayıcısı](/windows/desktop/SecAuthZ/security-descriptor-string-format).

*sı*<br/>
Çıkış dizesine eklemek için güvenlik tanımlayıcısı bileşenlerini göstermek için SECURITY_INFORMATION bit bayrakları birleşimi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Güvenlik tanımlayıcısının dize biçiminde eklendiğinde, bunu daha kolay depolanan aktarılan veya. Kullanım `CSecurityDesc::FromString` bir güvenlik tanımlayıcısının dize dönüştürmek için yöntemi.

*Sı* parametresi, aşağıdaki SECURITY_INFORMATION bayraklar içerebilir:

|Değer|Açıklama|
|-----------|-------------|
|OWNER_SECURITY_INFORMATION|Sahibi içerir.|
|GROUP_SECURITY_INFORMATION|Birincil grup içerir.|
|DACL_SECURITY_INFORMATION|DACL içerir.|
|SACL_SECURITY_INFORMATION|SACL içerir.|

NULL DACL ve giriş güvenlik tanımlayıcısı SE_DACL_PRESENT denetimi biti ayarlanmış yöntemi başarısız olur.

NULL DACL ise ve SE_DACL_PRESENT denetim bit giriş güvenlik tanımlayıcısı ayarlı değil, sonuçta elde edilen güvenlik açıklayıcı dizesinin D: bileşen yok. Bkz: [güvenlik tanımlayıcısı dize biçiminde](/windows/desktop/SecAuthZ/security-descriptor-string-format) daha fazla ayrıntı için.

Bu yöntemin çağırdığı [ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/desktop/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptora).

## <a name="see-also"></a>Ayrıca bkz.

[Güvenliği örneği](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
