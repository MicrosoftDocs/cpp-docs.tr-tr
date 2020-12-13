---
description: 'Daha fazla bilgi edinin: CSecurityDesc sınıfı'
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
ms.openlocfilehash: 66a2229aa4819059a353baf8b3802bb1263da2e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140786"
---
# <a name="csecuritydesc-class"></a>CSecurityDesc sınıfı

Bu sınıf, yapı için bir sarmalayıcıdır `SECURITY_DESCRIPTOR` .

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CSecurityDesc
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSecurityDesc:: CSecurityDesc](#csecuritydesc)|Oluşturucu.|
|[CSecurityDesc:: ~ CSecurityDesc](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSecurityDesc:: FromString](#fromstring)|Dize biçimli bir güvenlik tanımlayıcısını geçerli, işlevsel bir güvenlik tanımlayıcısına dönüştürür.|
|[CSecurityDesc:: GetControl](#getcontrol)|Güvenlik tanımlayıcısından denetim bilgilerini alır.|
|[CSecurityDesc:: GetDacl](#getdacl)|Güvenlik tanımlayıcısından isteğe bağlı erişim denetimi listesi (DACL) bilgilerini alır.|
|[CSecurityDesc:: GetGroup](#getgroup)|Güvenlik tanımlayıcısından birincil grup bilgilerini alır.|
|[CSecurityDesc:: GetOwner](#getowner)|Güvenlik tanımlayıcısından sahip bilgiler alır.|
|[CSecurityDesc:: GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|Yapıya bir işaretçi döndürür `SECURITY_DESCRIPTOR` .|
|[CSecurityDesc:: GetSacl](#getsacl)|Güvenlik tanımlayıcısından sistem erişim denetimi listesi (SACL) bilgilerini alır.|
|[CSecurityDesc:: ısdadclautodevralınmış](#isdaclautoinherited)|DACL 'nin otomatik yayılmayı destekleyecek şekilde yapılandırılıp yapılandırılmadığını belirler.|
|[CSecurityDesc:: ısdadclın,](#isdacldefaulted)|Güvenlik tanımlayıcısının varsayılan bir DACL ile yapılandırılıp yapılandırılmadığını belirler.|
|[CSecurityDesc:: Isdadsun](#isdaclpresent)|Güvenlik tanımlayıcısının bir DACL içerip içermeyeceğini belirler.|
|[CSecurityDesc:: ısdadclprotected](#isdaclprotected)|DACL 'nin değişiklikleri önleyecek şekilde yapılandırılıp yapılandırılmadığını belirler.|
|[CSecurityDesc:: ısgroupınreport](#isgroupdefaulted)|Güvenlik tanımlayıcısının grup güvenlik tanımlayıcısının (SID) varsayılan olarak ayarlandığını belirler.|
|[CSecurityDesc:: ısownerınbıas](#isownerdefaulted)|Güvenlik tanımlayıcısının sahip SID 'sinin varsayılan olarak ayarlandığını belirler.|
|[CSecurityDesc:: Issaclautodevralınmış](#issaclautoinherited)|SACL 'nin otomatik yayılmayı destekleyecek şekilde yapılandırılıp yapılandırılmadığını belirler.|
|[CSecurityDesc:: Issaclınbıas](#issacldefaulted)|Güvenlik tanımlayıcısının varsayılan SACL ile yapılandırılıp yapılandırılmadığını belirler.|
|[CSecurityDesc:: Issaclsun](#issaclpresent)|Güvenlik tanımlayıcısının bir SACL içerip içermeyeceğini belirler.|
|[CSecurityDesc:: ıssaclprotected](#issaclprotected)|SACL 'nin değişiklik yapılmasını engelleyecek şekilde yapılandırılıp yapılandırılmadığını belirler.|
|[CSecurityDesc:: ısselfgöreli](#isselfrelative)|Güvenlik tanımlayıcısının kendine bağlı biçimde olup olmadığını belirler.|
|[CSecurityDesc:: MakeAbsolute](#makeabsolute)|Güvenlik tanımlayıcısını mutlak biçime dönüştürmek için bu yöntemi çağırın.|
|[CSecurityDesc:: Makeselfgöreli](#makeselfrelative)|Güvenlik tanımlayıcısını kendine göreli biçime dönüştürmek için bu yöntemi çağırın.|
|[CSecurityDesc:: SetControl](#setcontrol)|Güvenlik tanımlayıcısının denetim bitlerini ayarlar.|
|[CSecurityDesc:: SetDacl](#setdacl)|Bir DACL 'deki bilgileri ayarlar. Güvenlik tanımlayıcısında zaten bir DACL varsa, bu, değiştirilmiştir.|
|[CSecurityDesc:: SetGroup](#setgroup)|Bir mutlak biçimdeki güvenlik tanımlayıcısının birincil grup bilgilerini ayarlar, birincil grup bilgilerini zaten mevcut olarak değiştirir.|
|[CSecurityDesc:: SetOwner](#setowner)|Bir mutlak biçimdeki güvenlik tanımlayıcısının sahip bilgilerini ayarlar, mevcut olan tüm sahip bilgilerini değiştirir.|
|[CSecurityDesc:: SetSacl](#setsacl)|SACL içindeki bilgileri ayarlar. Güvenlik tanımlayıcısında zaten bir SACL varsa, bu, değiştirilmiştir.|
|[CSecurityDesc:: ToString](#tostring)|Bir güvenlik tanımlayıcısını dize biçimine dönüştürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CSecurityDesc:: operator const SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|Yapıya bir işaretçi döndürür `SECURITY_DESCRIPTOR` .|
|[CSecurityDesc:: operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

`SECURITY_DESCRIPTOR`Yapı, bir nesneyle ilişkili güvenlik bilgilerini içerir. Uygulamalar, bir nesnenin güvenlik durumunu ayarlamak ve sorgulamak için bu yapıyı kullanır. Ayrıca bkz. [AtlGetSecurityDescriptor](security-global-functions.md#atlgetsecuritydescriptor).

Uygulamalar yapıyı doğrudan değiştirmemelidir; `SECURITY_DESCRIPTOR` bunun yerine, belirtilen sınıf yöntemlerini kullanmalıdır.

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

## <a name="csecuritydesccsecuritydesc"></a><a name="csecuritydesc"></a> CSecurityDesc:: CSecurityDesc

Oluşturucu.

```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
`CSecurityDesc` `SECURITY_DESCRIPTOR` Yeni nesneye atanacak nesne veya yapı `CSecurityDesc` .

### <a name="remarks"></a>Açıklamalar

`CSecurityDesc`Nesne, isteğe bağlı olarak, bir `SECURITY_DESCRIPTOR` Yapı veya daha önce tanımlanmış bir `CSecurityDesc` nesne kullanılarak oluşturulabilir.

## <a name="csecuritydesccsecuritydesc"></a><a name="dtor"></a> CSecurityDesc:: ~ CSecurityDesc

Yok edicisi.

```
virtual ~CSecurityDesc() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, ayrılan tüm kaynakları serbest bırakır.

## <a name="csecuritydescfromstring"></a><a name="fromstring"></a> CSecurityDesc:: FromString

Dize biçimli bir güvenlik tanımlayıcısını geçerli, işlevsel bir güvenlik tanımlayıcısına dönüştürür.

```
bool FromString(LPCTSTR pstr) throw(...);
```

### <a name="parameters"></a>Parametreler

*PSTR*<br/>
Dönüştürülecek [dize biçimli güvenlik tanımlayıcısını](/windows/win32/SecAuthZ/security-descriptor-string-format) içeren, null ile sonlandırılmış bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda true döndürür. Hata durumunda bir özel durum oluşturur.

### <a name="remarks"></a>Açıklamalar

Dize [CSecurityDesc:: ToString](#tostring)kullanılarak oluşturulabilir. Güvenlik tanımlayıcısını bir dizeye dönüştürmek, depolamayı ve aktarmayı kolaylaştırır.

Bu yöntem [ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/win32/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptorw)çağırır.

## <a name="csecuritydescgetcontrol"></a><a name="getcontrol"></a> CSecurityDesc:: GetControl

Güvenlik tanımlayıcısından denetim bilgilerini alır.

```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```

### <a name="parameters"></a>Parametreler

*psdc*<br/>
`SECURITY_DESCRIPTOR_CONTROL`Güvenlik tanımlayıcısının denetim bilgilerini alan yapıya yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa true, başarısız olursa false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [GetSecurityDescriptorControl](/windows/win32/api/securitybaseapi/nf-securitybaseapi-getsecuritydescriptorcontrol)öğesini çağırır.

## <a name="csecuritydescgetdacl"></a><a name="getdacl"></a> CSecurityDesc:: GetDacl

Güvenlik tanımlayıcısından isteğe bağlı erişim denetimi listesi (DACL) bilgilerini alır.

```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pDacl*<br/>
`CDacl`Güvenlik TANıMLAYıCıSıNıN DACL 'sinin bir kopyasının depolandığı yapıya yönelik işaretçi. İsteğe bağlı bir ACL varsa, yöntem *pDacl* 'yi güvenlik tanımlayıcısının Isteğe bağlı ACL adresi olarak ayarlar. İsteğe bağlı bir ACL yoksa, hiçbir değer depolanmaz.

*Pbsun*<br/>
Belirtilen güvenlik tanımlayıcısındaki bir isteğe bağlı ACL varlığını gösteren bir değer işaretçisi. Güvenlik tanımlayıcısı isteğe bağlı bir ACL içeriyorsa, bu parametre true olarak ayarlanır. Güvenlik tanımlayıcısı isteğe bağlı bir ACL içermiyorsa, bu parametre false olarak ayarlanır.

*Pbvarsayılan*<br/>
`SECURITY_DESCRIPTOR_CONTROL`Güvenlik tanımlayıcısı için isteğe bağlı BIR ACL varsa, yapıdaki SE_DACL_DEFAULTED bayrağının değerine ayarlanan bayrak işaretçisi. Bu bayrak true ise, isteğe bağlı ACL varsayılan bir mekanizma tarafından alındı; false ise, isteğe bağlı ACL bir kullanıcı tarafından açıkça belirtilmiştir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa true, başarısız olursa false döndürür.

## <a name="csecuritydescgetgroup"></a><a name="getgroup"></a> CSecurityDesc:: GetGroup

Güvenlik tanımlayıcısından birincil grup bilgilerini alır.

```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*PSID*<br/>
CDacl 'de depolanan grubun bir kopyasını alan bir [CSID](../../atl/reference/csid-class.md) (güvenlik tanımlayıcısı) işaretçisi.

*Pbvarsayılan*<br/>
Yöntem döndürüldüğünde yapıdaki SE_GROUP_DEFAULTED bayrağının değerine ayarlanan bayrak işaretçisi `SECURITY_DESCRIPTOR_CONTROL` .

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa true, başarısız olursa false döndürür.

## <a name="csecuritydescgetowner"></a><a name="getowner"></a> CSecurityDesc:: GetOwner

Güvenlik tanımlayıcısından sahip bilgiler alır.

```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*PSID*<br/>
CDacl 'de depolanan grubun bir kopyasını alan bir [CSID](../../atl/reference/csid-class.md) (güvenlik tanımlayıcısı) işaretçisi.

*Pbvarsayılan*<br/>
Yöntem döndürüldüğünde yapıdaki SE_OWNER_DEFAULTED bayrağının değerine ayarlanan bayrak işaretçisi `SECURITY_DESCRIPTOR_CONTROL` .

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa true, başarısız olursa false döndürür.

## <a name="csecuritydescgetpsecurity_descriptor"></a><a name="getpsecurity_descriptor"></a> CSecurityDesc:: GetPSECURITY_DESCRIPTOR

Yapıya bir işaretçi döndürür `SECURITY_DESCRIPTOR` .

```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor) yapısına bir işaretçi döndürür.

## <a name="csecuritydescgetsacl"></a><a name="getsacl"></a> CSecurityDesc:: GetSacl

Güvenlik tanımlayıcısından sistem erişim denetimi listesi (SACL) bilgilerini alır.

```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSacl*<br/>
`CSacl`Güvenlik TANıMLAYıCıSıNıN SACL 'sinin kopyasının depolandığı yapıya yönelik işaretçi. Bir sistem ACL 'si varsa, yöntem *pSacl* 'yi güvenlik TANıMLAYıCıSıNıN sistem ACL 'sinin adresine ayarlar. Bir sistem ACL 'SI yoksa, hiçbir değer depolanmaz.

*Pbsun*<br/>
Belirtilen güvenlik tanımlayıcısındaki bir sistem ACL 'sinin varlığını göstermek için yöntemi ayarlayan bayrağa yönelik işaretçi. Güvenlik tanımlayıcısı bir sistem ACL 'SI içeriyorsa, bu parametre true olarak ayarlanır. Güvenlik tanımlayıcısı bir sistem ACL 'SI içermiyorsa, bu parametre false olarak ayarlanır.

*Pbvarsayılan*<br/>
`SECURITY_DESCRIPTOR_CONTROL`Güvenlik tanımlayıcısı için bir SISTEM ACL 'si varsa, yapıdaki SE_SACL_DEFAULTED bayrağının değerine ayarlanan bayrak işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa true, başarısız olursa false döndürür.

## <a name="csecuritydescisdaclautoinherited"></a><a name="isdaclautoinherited"></a> CSecurityDesc:: ısdadclautodevralınmış

İsteğe bağlı erişim denetimi listesinin (DACL) otomatik yayılmayı destekleyecek şekilde yapılandırılıp yapılandırılmadığını belirler.

```
bool IsDaclAutoInherited() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı, devralınabilir erişim denetimi girişlerinin (ACE 'Ler) varolan alt nesnelere otomatik yayılmasını desteklemek üzere ayarlanmış bir DACL içeriyorsa true döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Sistem, nesne ve var olan alt nesneleri için otomatik devralma algoritmasını gerçekleştirdiğinde bu biti ayarlar.

## <a name="csecuritydescisdacldefaulted"></a><a name="isdacldefaulted"></a> CSecurityDesc:: ısdadclın,

Güvenlik tanımlayıcısının varsayılan bir isteğe bağlı erişim denetimi listesi (DACL) ile yapılandırılıp yapılandırılmadığını belirler.

```
bool IsDaclDefaulted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı varsayılan bir DACL içeriyorsa true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrak, sistemin, erişim denetimi girişi (ACE) devralım açısından DACL 'yi nasıl değerlendirip değerlendirmeyeceğini etkileyebilir. Örneğin, bir nesnenin Oluşturucusu bir DACL belirtmezse, nesne, oluşturucunun erişim belirtecinden varsayılan DACL 'yi alır. SE_DACL_PRESENT bayrağı ayarlanmamışsa sistem bu bayrağı yoksayar.

Bu bayrak, nesne üzerindeki son DACL 'nin nasıl hesaplanması gerektiğini ve güvenli kılınabilir nesnenin güvenlik tanımlayıcısı denetiminde fiziksel olarak nasıl depolanmadığını belirlemede kullanılır.

Bu bayrağı ayarlamak için [CSecurityDesc:: SetDacl](#setdacl) yöntemini kullanın.

## <a name="csecuritydescisdaclpresent"></a><a name="isdaclpresent"></a> CSecurityDesc:: Isdadsun

Güvenlik tanımlayıcısının bir isteğe bağlı erişim denetimi listesi (DACL) içerip içermeyeceğini belirler.

```
bool IsDaclPresent() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı bir DACL içeriyorsa true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrak ayarlanmamışsa veya bu bayrak ayarlandıysa ve DACL NULL ise, güvenlik tanımlayıcısı herkese tam erişim sağlar.

Bu bayrak, güvenlik tanımlayıcısı güvenli kılınabilir bir nesneyle ilişkilendirilene kadar bir arayan tarafından belirtilen güvenlik bilgilerini tutmak için kullanılır. Güvenlik tanımlayıcısı güvenli kılınabilir bir nesneyle ilişkilendirildiğinde, SE_DACL_PRESENT bayrağı her zaman güvenlik tanımlayıcısı denetiminde ayarlanır.

Bu bayrağı ayarlamak için [CSecurityDesc:: SetDacl](#setdacl) yöntemini kullanın.

## <a name="csecuritydescisdaclprotected"></a><a name="isdaclprotected"></a> CSecurityDesc:: ısdadclprotected

İsteğe bağlı erişim denetimi listesinin (DACL) değişiklikleri engellemek için yapılandırılıp yapılandırılmadığını belirler.

```
bool IsDaclProtected() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

DACL, güvenlik tanımlayıcısının devralınabilir erişim denetimi girdileri (ACE 'Ler) tarafından değiştirilmesini engelleyecek şekilde yapılandırıldıysa, true döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için [CSecurityDesc:: SetDacl](#setdacl) yöntemini kullanın.

Bu yöntem, devralınabilir Ace 'Leri otomatik olarak yaymayı destekler.

## <a name="csecuritydescisgroupdefaulted"></a><a name="isgroupdefaulted"></a> CSecurityDesc:: ısgroupınreport

Güvenlik tanımlayıcısının grup güvenlik tanımlayıcısının (SID) varsayılan olarak ayarlandığını belirler.

```
bool IsGroupDefaulted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısının özgün sağlayıcısı yerine, güvenlik tanımlayıcısının Grup SID 'sini sağladıysa, varsayılan bir mekanizma true değerini döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için [CSecurityDesc:: SetGroup](#setgroup) metodunu kullanın.

## <a name="csecuritydescisownerdefaulted"></a><a name="isownerdefaulted"></a> CSecurityDesc:: ısownerınbıas

Güvenlik tanımlayıcısının sahip güvenlik tanımlayıcısının (SID) varsayılan olarak ayarlandığını belirler.

```
bool IsOwnerDefaulted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısının özgün sağlayıcısı yerine, güvenlik tanımlayıcısının sahip SID 'sini sağladıysa, varsayılan bir mekanizma için true döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için [CSecurityDesc:: SetOwner](#setowner) metodunu kullanın.

## <a name="csecuritydescissaclautoinherited"></a><a name="issaclautoinherited"></a> CSecurityDesc:: Issaclautodevralınmış

Sistem erişim denetimi listesinin (SACL) otomatik yayılmayı destekleyecek şekilde yapılandırılıp yapılandırılmadığını belirler.

```
bool IsSaclAutoInherited() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı, devralınabilir erişim denetimi girişlerinin (ACE 'Ler) varolan alt nesnelere otomatik yayılmasını desteklemek üzere ayarlanmış bir SACL içeriyorsa true döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Sistem, nesne ve var olan alt nesneleri için otomatik devralma algoritmasını gerçekleştirdiğinde bu biti ayarlar.

## <a name="csecuritydescissacldefaulted"></a><a name="issacldefaulted"></a> CSecurityDesc:: Issaclınbıas

Güvenlik tanımlayıcısının varsayılan sistem erişim denetimi listesi (SACL) ile yapılandırılıp yapılandırılmadığını belirler.

```
bool IsSaclDefaulted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı varsayılan SACL içeriyorsa true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrak sistemin, erişim denetimi girişi (ACE) devralım açısından SACL 'nin nasıl davrandığını etkileyebilir. SE_SACL_PRESENT bayrağı ayarlanmamışsa sistem bu bayrağı yoksayar.

Bu bayrağı ayarlamak için [CSecurityDesc:: SetSacl](#setsacl) metodunu kullanın.

## <a name="csecuritydescissaclpresent"></a><a name="issaclpresent"></a> CSecurityDesc:: Issaclsun

Güvenlik tanımlayıcısının bir sistem erişim denetimi listesi (SACL) içerip içermeyeceğini belirler.

```
bool IsSaclPresent() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı bir SACL içeriyorsa true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için [CSecurityDesc:: SetSacl](#setsacl) metodunu kullanın.

## <a name="csecuritydescissaclprotected"></a><a name="issaclprotected"></a> CSecurityDesc:: ıssaclprotected

Sistem erişim denetimi listesinin (SACL) değişiklikleri engellemek için yapılandırılıp yapılandırılmadığını belirler.

```
bool IsSaclProtected() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

SACL, güvenlik tanımlayıcısının devralınabilir erişim denetimi girdileri (ACE 'Ler) tarafından değiştirilmesini engelleyecek şekilde yapılandırıldıysa, true döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için [CSecurityDesc:: SetSacl](#setsacl) metodunu kullanın.

Bu yöntem, devralınabilir Ace 'Leri otomatik olarak yaymayı destekler.

## <a name="csecuritydescisselfrelative"></a><a name="isselfrelative"></a> CSecurityDesc:: ısselfgöreli

Güvenlik tanımlayıcısının kendine bağlı biçimde olup olmadığını belirler.

```
bool IsSelfRelative() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı, bitişik bir bellek bloğundaki tüm güvenlik bilgilerini içeren kendi kendine göreli biçimindeyse true değerini döndürür. Güvenlik tanımlayıcısı mutlak biçimindeyse yanlış döndürür. Daha fazla bilgi için bkz. [mutlak ve Self-Relative güvenlik tanımlayıcıları](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors).

## <a name="csecuritydescmakeabsolute"></a><a name="makeabsolute"></a> CSecurityDesc:: MakeAbsolute

Güvenlik tanımlayıcısını mutlak biçime dönüştürmek için bu yöntemi çağırın.

```
bool MakeAbsolute() throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Mutlak biçimdeki bir güvenlik tanımlayıcısı, bilgilerin kendisi yerine, içerdiği bilgilere yönelik işaretçiler içerir. Kendi kendine göreli biçimdeki bir güvenlik tanımlayıcısı, bir bellek öbeğiyle ilgili bilgileri içerir. Kendi kendine göreli bir güvenlik tanımlayıcısında, bir `SECURITY_DESCRIPTOR` Yapı her zaman bilgileri başlatır, ancak güvenlik tanımlayıcısının diğer bileşenleri yapıyı herhangi bir sırada izleyebilir. Kendi kendine göreli güvenlik tanımlayıcısının bileşenleri, bellek adreslerini kullanmak yerine, güvenlik tanımlayıcısının başından uzaklıklarla tanımlanır. Bu biçim, bir güvenlik tanımlayıcısının bir diskte depolanması veya bir iletişim protokolünün yoluyla iletilmesi gerektiğinde faydalıdır. Daha fazla bilgi için bkz. [mutlak ve Self-Relative güvenlik tanımlayıcıları](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors).

## <a name="csecuritydescmakeselfrelative"></a><a name="makeselfrelative"></a> CSecurityDesc:: Makeselfgöreli

Güvenlik tanımlayıcısını kendine göreli biçime dönüştürmek için bu yöntemi çağırın.

```
bool MakeSelfRelative() throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Mutlak biçimdeki bir güvenlik tanımlayıcısı, bilgilerin kendisini içermektense, içerdiği bilgilere yönelik işaretçiler içerir. Kendi kendine göreli biçimdeki bir güvenlik tanımlayıcısı, bir bellek öbeğiyle ilgili bilgileri içerir. Kendi kendine göreli bir güvenlik tanımlayıcısında, bir `SECURITY_DESCRIPTOR` Yapı her zaman bilgileri başlatır, ancak güvenlik tanımlayıcısının diğer bileşenleri yapıyı herhangi bir sırada izleyebilir. Güvenlik tanımlayıcısının bileşenleri, bellek adreslerini kullanmak yerine, güvenlik tanımlayıcısının başından uzaklıklardan belirlenir. Bu biçim, bir güvenlik tanımlayıcısının bir diskte depolanması veya bir iletişim protokolünün yoluyla iletilmesi gerektiğinde faydalıdır. Daha fazla bilgi için bkz. [mutlak ve Self-Relative güvenlik tanımlayıcıları](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors).

## <a name="csecuritydescoperator-"></a><a name="operator_eq"></a> CSecurityDesc:: operator =

Atama işleci.

```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*sağ taraftan*<br/>
`SECURITY_DESCRIPTOR` `CSecurityDesc` Nesneye atanacak yapı veya nesne `CSecurityDesc` .

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneyi döndürür `CSecurityDesc` .

## <a name="csecuritydescoperator-const-security_descriptor-"></a><a name="operator_const_security_descriptor__star"></a> CSecurityDesc:: operator const SECURITY_DESCRIPTOR *

Yapının işaretçisine bir değer yayınlar `SECURITY_DESCRIPTOR` .

```
operator const SECURITY_DESCRIPTOR *() const throw();
```

## <a name="csecuritydescsetcontrol"></a><a name="setcontrol"></a> CSecurityDesc:: SetControl

Güvenlik tanımlayıcısının denetim bitlerini ayarlar.

```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest,
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```

### <a name="parameters"></a>Parametreler

*ControlBitsOfInterest*<br/>
Ayarlanacak denetim bitlerini gösteren bir SECURITY_DESCRIPTOR_CONTROL maskesi. Ayarlanbilen bayrakların bir listesi için bkz. [SetSecurityDescriptorControl](/windows/win32/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol).

*ControlBitsToSet*<br/>
*ControlBitsOfInterest* maskesi tarafından belirtilen Denetim bitleri için yeni değerler gösteren bir SECURITY_DESCRIPTOR_CONTROL maskesi. Bu parametre *ControlBitsOfInterest* parametresi için listelenen bayrakların bir birleşimi olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [SetSecurityDescriptorControl](/windows/win32/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol)' i çağırır.

## <a name="csecuritydescsetdacl"></a><a name="setdacl"></a> CSecurityDesc:: SetDacl

İsteğe bağlı erişim denetimi listesindeki (DACL) bilgileri ayarlar. Güvenlik tanımlayıcısında zaten bir DACL varsa, bu, değiştirilmiştir.

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
`CDacl`Güvenlik tanımlayıcısı IÇIN DACL 'yi belirten bir nesneye başvuru. Bu parametre NULL olmamalıdır. Güvenlik tanımlayıcısında bir NULL DACL ayarlamak için yöntemin ilk formu, *Bsun* değeri false olarak kullanılmalıdır.

*Bsun*<br/>
Güvenlik tanımlayıcısında DACL 'nin varlığını belirten bir bayrak belirtir. Bu parametre true ise, yöntemi yapıda SE_DACL_PRESENT bayrağını ayarlar `SECURITY_DESCRIPTOR_CONTROL` ve *DACL* ve *bVarsayılan* Parametreler içindeki değerleri kullanır. Yanlış ise, yöntem SE_DACL_PRESENT bayrağını temizler ve *bVarsayılan* yok sayılır.

*bVarsayılan*<br/>
DACL kaynağını belirten bir bayrak belirtir. Bu bayrak true ise, DACL, bazı varsayılan mekanizmaya göre alınmıştır. False ise, DACL bir kullanıcı tarafından açıkça belirtilmiştir. Yöntemi bu değeri yapının SE_DACL_DEFAULTED bayrağıyla depolar `SECURITY_DESCRIPTOR_CONTROL` . Bu parametre belirtilmezse SE_DACL_DEFAULTED bayrağı temizlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Boş ve varolmayan bir DACL arasında önemli bir farklılık vardır. Bir DACL boş olduğunda, erişim denetimi girdisi içermez ve açıkça erişim hakkı verilmez. Sonuç olarak, nesneye erişim örtük olarak reddedilir. Bir nesne DACL olmadığında, diğer taraftan, nesneye hiçbir koruma atanmaz ve herhangi bir erişim isteği verilir.

## <a name="csecuritydescsetgroup"></a><a name="setgroup"></a> CSecurityDesc:: SetGroup

Bir mutlak biçimdeki güvenlik tanımlayıcısının birincil grup bilgilerini ayarlar, birincil grup bilgilerini zaten mevcut olarak değiştirir.

```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*SID*<br/>
Güvenlik tanımlayıcısının yeni birincil grubu için bir [CSID](../../atl/reference/csid-class.md) nesnesine başvuru. Bu parametre NULL olmamalıdır. Bir güvenlik tanımlayıcısı, bir DACL veya SACL 'ye sahip değil olarak işaretlenebilir, ancak bu, NULL SID (özel bir anlamı olan yerleşik bir SID) olsa bile, bir gruba ve sahibe sahip olmalıdır.

*bVarsayılan*<br/>
Birincil grup bilgisinin varsayılan mekanizmaya türetilip türetilmediğini belirtir. Bu değer true ise, varsayılan bilgiler olur ve yöntemi bu değeri yapıda SE_GROUP_DEFAULTED bayrağı olarak depolar `SECURITY_DESCRIPTOR_CONTROL` . Bu parametre sıfırsa SE_GROUP_DEFAULTED bayrağı temizlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

## <a name="csecuritydescsetowner"></a><a name="setowner"></a> CSecurityDesc:: SetOwner

Mutlak biçimdeki güvenlik tanımlayıcısının sahip bilgilerini ayarlar. Zaten mevcut olan tüm sahip bilgilerini değiştirir.

```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*SID*<br/>
Güvenlik tanımlayıcısının yeni birincil sahibi için [CSID](../../atl/reference/csid-class.md) nesnesi. Bu parametre NULL olmamalıdır.

*bVarsayılan*<br/>
Sahip bilgisinin bir varsayılan mekanizmaya türetilip türetilmediğini belirtir. Bu değer true ise, varsayılan bilgiler budur. Yöntemi bu değeri yapıda SE_OWNER_DEFAULTED bayrağı olarak depolar `SECURITY_DESCRIPTOR_CONTROL` . Bu parametre sıfırsa SE_OWNER_DEFAULTED bayrağı temizlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

## <a name="csecuritydescsetsacl"></a><a name="setsacl"></a> CSecurityDesc:: SetSacl

Bir sistem erişim denetimi listesindeki (SACL) bilgileri ayarlar. Güvenlik tanımlayıcısında zaten bir SACL varsa, bu, değiştirilmiştir.

```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*'Si*<br/>
`CSacl`Güvenlik TANıMLAYıCıSıNıN SACL 'sini belirten nesne işaretçisi. Bu parametre NULL olmamalı ve bir CSacl nesnesi olmalıdır. DACL 'lerin aksine, NULL ve boş SACL arasında bir fark yoktur, çünkü SACL nesneleri erişim hakları belirtmez, yalnızca denetim bilgileri.

*bVarsayılan*<br/>
SACL kaynağını belirten bir bayrak belirtir. Bu bayrak true ise, SACL bazı varsayılan mekanizmaya göre alınmıştır. Yanlış ise, SACL bir kullanıcı tarafından açıkça belirtilir. Yöntemi bu değeri yapının SE_SACL_DEFAULTED bayrağıyla depolar `SECURITY_DESCRIPTOR_CONTROL` . Bu parametre belirtilmezse SE_SACL_DEFAULTED bayrağı temizlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

## <a name="csecuritydesctostring"></a><a name="tostring"></a> CSecurityDesc:: ToString

Bir güvenlik tanımlayıcısını dize biçimine dönüştürür.

```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```

### <a name="parameters"></a>Parametreler

*PSTR*<br/>
[Dize biçimindeki güvenlik tanımlayıcısını](/windows/win32/SecAuthZ/security-descriptor-string-format)alacak şekilde, null ile sonlandırılmış bir dize işaretçisi.

*ortası*<br/>
Çıkış dizesine dahil edilecek güvenlik tanımlayıcısının bileşenlerini göstermek için SECURITY_INFORMATION bit bayraklarının birleşimini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Güvenlik tanımlayıcısı dize biçimindeyse, daha kolay depolanabilir veya iletilebilir. `CSecurityDesc::FromString`Dizeyi bir güvenlik tanımlayıcısına geri dönüştürmek için yöntemini kullanın.

*Sı* parametresi aşağıdaki SECURITY_INFORMATION bayraklarını içerebilir:

|Değer|Anlamı|
|-----------|-------------|
|OWNER_SECURITY_INFORMATION|Sahibini dahil edin.|
|GROUP_SECURITY_INFORMATION|Birincil grubu dahil edin.|
|DACL_SECURITY_INFORMATION|DACL 'yi ekleyin.|
|SACL_SECURITY_INFORMATION|SACL 'yi ekleyin.|

DACL NULL ise ve giriş güvenlik tanımlayıcısında SE_DACL_PRESENT denetim biti ayarlandıysa, yöntem başarısız olur.

DACL NULL ise ve giriş güvenlik tanımlayıcısında SE_DACL_PRESENT denetim biti ayarlanmamışsa, sonuçta elde edilen güvenlik açıklayıcı dizesinin D: bileşeni yoktur. Daha fazla ayrıntı için bkz. [güvenlik tanımlayıcısı dize biçimi](/windows/win32/SecAuthZ/security-descriptor-string-format) .

Bu yöntem [ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/win32/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptorw)çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik örneği](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel Işlevleri](../../atl/reference/security-global-functions.md)
