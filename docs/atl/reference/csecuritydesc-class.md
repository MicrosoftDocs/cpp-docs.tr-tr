---
title: CSecurityDesc Sınıfı
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
ms.openlocfilehash: 926e4e0a795982479188d90ed866bf5e2584c187
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330976"
---
# <a name="csecuritydesc-class"></a>CSecurityDesc Sınıfı

Bu sınıf `SECURITY_DESCRIPTOR` yapı için bir sarmalayıcıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CSecurityDesc
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSecurityDesc::CSecurityDesc](#csecuritydesc)|Oluşturucu.|
|[CSecurityDesc::~CSecurityDesc](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSecurityDesc::FromString](#fromstring)|Dize biçiminde güvenlik tanımlayıcısı geçerli, işlevsel bir güvenlik tanımlayıcısına dönüştürür.|
|[CSecurityDesc::GetControl](#getcontrol)|Güvenlik tanımlayıcısından denetim bilgilerini alır.|
|[CSecurityDesc::GetDacl](#getdacl)|Güvenlik tanımlayıcısından isteğe bağlı erişim denetim listesi (DACL) bilgilerini alır.|
|[CSecurityDesc::GetGroup](#getgroup)|Birincil grup bilgilerini güvenlik tanımlayıcısından alır.|
|[CSecurityDesc::GetOwner](#getowner)|Güvenlik tanımlayıcısından sahibi informaton alır.|
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|Yapıya bir `SECURITY_DESCRIPTOR` işaretçi döndürür.|
|[CSecurityDesc::GetSacl](#getsacl)|Güvenlik tanımlayıcısından sistem erişim denetim listesi (SACL) bilgilerini alır.|
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|DACL'nin otomatik yayılmayı destekleyecek şekilde yapılandırıp yapılandırılmamasını belirler.|
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|Güvenlik tanımlayıcısının varsayılan dacl ile yapılandırıp yapılandırılmaz olduğunu belirler.|
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|Güvenlik tanımlayıcısının bir DACL içerip içermeyin ivedilikle belirleyin.|
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|DACL'nin değişiklikleri önlemek için yapılandırıp yapılandırılmamalarını belirler.|
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|Güvenlik tanımlayıcısının grup güvenlik tanımlayıcısının (SID) varsayılan olarak ayarlandığını belirler.|
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|Güvenlik tanımlayıcısının sahibi SID'nin varsayılan olarak ayarlandığını belirler.|
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|SACL'nin otomatik yayılmayı destekleyecek şekilde yapılandırıp yapılandırılmamasını belirler.|
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|Güvenlik tanımlayıcısının varsayılan bir SACL ile yapılandırıp yapılandırılmaz olmadığını belirler.|
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|Güvenlik tanımlayıcısının Bir SACL içerip içermediğini belirler.|
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|SACL'nin değişiklikleri önlemek için yapılandırıp yapılandırılmadı sını belirler.|
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|Güvenlik tanımlayıcısının kendi bağıl biçiminde olup olmadığını belirler.|
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|Güvenlik tanımlayıcısını mutlak biçime dönüştürmek için bu yöntemi çağırın.|
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|Güvenlik tanımlayıcısını kendi bağıl biçimine dönüştürmek için bu yöntemi çağırın.|
|[CSecurityDesc::SetControl](#setcontrol)|Güvenlik tanımlayıcısının denetim bitlerini ayarlar.|
|[CSecurityDesc::SetDacl](#setdacl)|Bilgileri DACL'de ayarlar. Güvenlik tanımlayıcısında zaten bir DACL varsa, değiştirilir.|
|[CSecurityDesc::SetGroup](#setgroup)|Zaten var olan birincil grup bilgilerini değiştirerek, mutlak biçim güvenlik tanımlayıcısının birincil grup bilgilerini ayarlar.|
|[CSecurityDesc::SetSahibi](#setowner)|Zaten mevcut olan tüm sahip bilgilerini değiştirerek, mutlak biçim güvenlik tanımlayıcısının sahibi bilgilerini ayarlar.|
|[CSecurityDesc::SetSacl](#setsacl)|Bilgileri SACL'de ayarlar. Güvenlik tanımlayıcısında zaten bir SACL varsa, değiştirilir.|
|[CSecurityDesc::ToString](#tostring)|Güvenlik tanımlayıcısını dize biçimine dönüştürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CSecurityDesc::operatör const SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|Yapıya bir `SECURITY_DESCRIPTOR` işaretçi döndürür.|
|[CSecurityDesc::operatör =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

Yapı, `SECURITY_DESCRIPTOR` bir nesneyle ilişkili güvenlik bilgilerini içerir. Uygulamalar, nesnenin güvenlik durumunu ayarlamak ve sorgulamak için bu yapıyı kullanır. Ayrıca bakınız [AtlGetSecurityDescriptor](security-global-functions.md#atlgetsecuritydescriptor).

Uygulamalar yapıyı `SECURITY_DESCRIPTOR` doğrudan değiştirmemeli ve bunun yerine sağlanan sınıf yöntemlerini kullanmalıdır.

Windows'daki erişim denetimi modeline giriş için Windows SDK'daki [Access Denetimi'ne](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="csecuritydesccsecuritydesc"></a><a name="csecuritydesc"></a>CSecurityDesc::CSecurityDesc

Oluşturucu.

```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
Yeni `CSecurityDesc` `CSecurityDesc` nesneye atayacak nesne veya `SECURITY_DESCRIPTOR` yapı.

### <a name="remarks"></a>Açıklamalar

Nesne `CSecurityDesc` isteğe bağlı olarak `SECURITY_DESCRIPTOR` bir yapı veya `CSecurityDesc` daha önce tanımlanmış bir nesne kullanılarak oluşturulabilir.

## <a name="csecuritydesccsecuritydesc"></a><a name="dtor"></a>CSecurityDesc::~CSecurityDesc

Yıkıcı.

```
virtual ~CSecurityDesc() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, ayrılan tüm kaynakları serbest sağlar.

## <a name="csecuritydescfromstring"></a><a name="fromstring"></a>CSecurityDesc::FromString

Dize biçiminde güvenlik tanımlayıcısı geçerli, işlevsel bir güvenlik tanımlayıcısına dönüştürür.

```
bool FromString(LPCTSTR pstr) throw(...);
```

### <a name="parameters"></a>Parametreler

*pstr*<br/>
Dönüştürülecek [dize biçimi güvenlik tanımlayıcısını](/windows/win32/SecAuthZ/security-descriptor-string-format) içeren null-sonlandırılan dize işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı da doğru döner. Hata için bir özel durum atar.

### <a name="remarks"></a>Açıklamalar

Dize [CSecurityDesc kullanılarak oluşturulabilir::ToString](#tostring). Güvenlik tanımlayıcısını bir dize ye dönüştürmek, depolamayı ve iletmeyi kolaylaştırır.

Bu yöntem [ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/win32/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptorw)çağırır.

## <a name="csecuritydescgetcontrol"></a><a name="getcontrol"></a>CSecurityDesc::GetControl

Güvenlik tanımlayıcısından denetim bilgilerini alır.

```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```

### <a name="parameters"></a>Parametreler

*psdc*<br/>
Güvenlik tanımlayıcısının denetim bilgilerini alan bir `SECURITY_DESCRIPTOR_CONTROL` yapıyı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa doğru döndürür, başarısız olursa yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [GetSecurityDescriptorControl](/windows/win32/api/securitybaseapi/nf-securitybaseapi-getsecuritydescriptorcontrol)çağırır.

## <a name="csecuritydescgetdacl"></a><a name="getdacl"></a>CSecurityDesc::GetDacl

Güvenlik tanımlayıcısından isteğe bağlı erişim denetim listesi (DACL) bilgilerini alır.

```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pDacl*<br/>
Güvenlik tanımlayıcısının DACL'sinin bir kopyasının depolandığı bir `CDacl` yapıyı işaretleyin. İhtiyari bir ACL varsa, yöntem *pDacl'u* güvenlik tanımlayıcısının isteğe bağlı ACL adresine ayarlar. İsteğe bağlı bir ACL yoksa, hiçbir değer depolanmaz.

*pbPresent*<br/>
Belirtilen güvenlik tanımlayıcısında isteğe bağlı bir ACL'nin varlığını gösteren bir değer işaretçisi. Güvenlik tanımlayıcısı isteğe bağlı bir ACL içeriyorsa, bu parametre doğru olarak ayarlanır. Güvenlik tanımlayıcısı isteğe bağlı bir ACL içermiyorsa, bu parametre yanlış olarak ayarlanır.

*pbVarsayılan*<br/>
Güvenlik tanımlayıcısı için isteğe bağlı bir `SECURITY_DESCRIPTOR_CONTROL` ACL varsa, yapıdaki SE_DACL_DEFAULTED bayrağının değerine ayarlanmış bir bayrağı işaretçi. Bu bayrak doğruysa, isteğe bağlı ACL varsayılan bir mekanizma tarafından alındı; yanlış sayılsa bile, isteğe bağlı ACL kullanıcı tarafından açıkça belirtilmiştir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa doğru döndürür, başarısız olursa yanlış.

## <a name="csecuritydescgetgroup"></a><a name="getgroup"></a>CSecurityDesc::GetGroup

Birincil grup bilgilerini güvenlik tanımlayıcısından alır.

```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSid*<br/>
CDacl'da depolanan grubun bir kopyasını alan bir [CSid](../../atl/reference/csid-class.md) (güvenlik tanımlayıcısı) işaretçisi.

*pbVarsayılan*<br/>
Yöntem döndüğünde `SECURITY_DESCRIPTOR_CONTROL` yapıdaki SE_GROUP_DEFAULTED bayrağının değerine ayarlanmış bir bayrağı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa doğru döndürür, başarısız olursa yanlış.

## <a name="csecuritydescgetowner"></a><a name="getowner"></a>CSecurityDesc::GetOwner

Güvenlik tanımlayıcısından sahibi informaton alır.

```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSid*<br/>
CDacl'da depolanan grubun bir kopyasını alan bir [CSid](../../atl/reference/csid-class.md) (güvenlik tanımlayıcısı) işaretçisi.

*pbVarsayılan*<br/>
Yöntem döndüğünde `SECURITY_DESCRIPTOR_CONTROL` yapıdaki SE_OWNER_DEFAULTED bayrağının değerine ayarlanan bir bayrağı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa doğru döndürür, başarısız olursa yanlış.

## <a name="csecuritydescgetpsecurity_descriptor"></a><a name="getpsecurity_descriptor"></a>CSecurityDesc::GetPSECURITY_DESCRIPTOR

Yapıya bir `SECURITY_DESCRIPTOR` işaretçi döndürür.

```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor) yapısına bir işaretçi döndürür.

## <a name="csecuritydescgetsacl"></a><a name="getsacl"></a>CSecurityDesc::GetSacl

Güvenlik tanımlayıcısından sistem erişim denetim listesi (SACL) bilgilerini alır.

```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pSacl*<br/>
Güvenlik tanımlayıcısının SACL'sinin bir kopyasının depolandığı bir `CSacl` yapıyı işaretleyin. Bir sistem ACL varsa, yöntem güvenlik tanımlayıcı sistemi ACL adresine *pSacl* ayarlar. Bir sistem ACL yoksa, hiçbir değer depolanır.

*pbPresent*<br/>
Belirtilen güvenlik tanımlayıcısında bir sistem ACL varlığını belirtmek için bir bayrak işaretçisi yöntemi ayarlar. Güvenlik tanımlayıcısı bir sistem ACL içeriyorsa, bu parametre doğru olarak ayarlanır. Güvenlik tanımlayıcısı bir sistem ACL içermiyorsa, bu parametre yanlış olarak ayarlanır.

*pbVarsayılan*<br/>
Güvenlik tanımlayıcısı için bir sistem ACL'si `SECURITY_DESCRIPTOR_CONTROL` varsa, yapıdaki SE_SACL_DEFAULTED bayrağının değerine ayarlanmış bir bayrağı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa doğru döndürür, başarısız olursa yanlış.

## <a name="csecuritydescisdaclautoinherited"></a><a name="isdaclautoinherited"></a>CSecurityDesc::IsDaclAutoInherited

İsteğe bağlı erişim kontrol listesinin (DACL) otomatik yayılmayı destekleyecek şekilde yapılandırıp yapılandırılmamasını belirler.

```
bool IsDaclAutoInherited() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı, varolan alt nesnelere devredilebilir erişim denetimi girişlerinin (ACE) otomatik olarak yayılmasını desteklemek üzere ayarlanmış bir DACL içeriyorsa doğru döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Sistem, nesne ve varolan alt nesneleri için otomatik devralma algoritmasını gerçekleştirirken bu biti ayarlar.

## <a name="csecuritydescisdacldefaulted"></a><a name="isdacldefaulted"></a>CSecurityDesc::IsDaclDefaulted

Güvenlik tanımlayıcısının varsayılan isteğe bağlı erişim denetim listesi (DACL) ile yapılandırıp yapılandırılmaz olduğunu belirler.

```
bool IsDaclDefaulted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı varsayılan dacl içeriyorsa, aksi takdirde yanlış döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrak, erişim denetimi girişi (ACE) kalıtımı yla ilgili olarak sistemin DACL'ye nasıl davrandığını etkileyebilir. Örneğin, bir nesnenin oluşturucusu bir DACL belirtmezse, nesne ilk önce gelenin erişim jetonundan varsayılan DACL'yi alır. SE_DACL_PRESENT bayrağı ayarlanmazsa sistem bu bayrağı yoksa.

Bu bayrak, nesneüzerindeki son DACL'nin nasıl hesaplanabildiğini belirlemek için kullanılır ve securable nesnenin güvenlik tanımlayıcı denetiminde fiziksel olarak depolanmaz.

Bu bayrağı ayarlamak için [CSecurityDesc::SetDacl](#setdacl) yöntemini kullanın.

## <a name="csecuritydescisdaclpresent"></a><a name="isdaclpresent"></a>CSecurityDesc::IsDaclPresent

Güvenlik tanımlayıcısının isteğe bağlı erişim denetim listesi (DACL) içerip içermeyişolduğunu belirler.

```
bool IsDaclPresent() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı bir DACL içeriyorsa, aksi takdirde yanlış döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrak ayarlı değilse veya bu bayrak ayarlanmışsa ve DACL NULL ise, güvenlik tanımlayıcısı herkese tam erişim sağlar.

Bu bayrak, güvenlik tanımlayıcısı securable bir nesne ile ilişkili olana kadar bir arayan tarafından belirtilen güvenlik bilgilerini tutmak için kullanılır. Güvenlik tanımlayıcısı bir securable nesneile ilişkilendirildikten sonra, SE_DACL_PRESENT bayrağı her zaman güvenlik tanımlayıcı denetiminde ayarlanır.

Bu bayrağı ayarlamak için [CSecurityDesc::SetDacl](#setdacl) yöntemini kullanın.

## <a name="csecuritydescisdaclprotected"></a><a name="isdaclprotected"></a>CSecurityDesc::IsDaclProtected

İsteğe bağlı erişim denetim listesinin (DACL) değişiklikleri önlemek için yapılandırıp yapılandırılmadı sını belirler.

```
bool IsDaclProtected() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

DACL, güvenlik tanımlayıcısının devredilebilir erişim denetimi girişleri (ACE'ler) tarafından değiştirilmesini önlemek için yapılandırılırsa doğru döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için [CSecurityDesc::SetDacl](#setdacl) yöntemini kullanın.

Bu yöntem, devredilebilir ACE'lerin otomatik olarak yayılmasını destekler.

## <a name="csecuritydescisgroupdefaulted"></a><a name="isgroupdefaulted"></a>CSecurityDesc::IsGroupDefaulted

Güvenlik tanımlayıcısının grup güvenlik tanımlayıcısının (SID) varsayılan olarak ayarlandığını belirler.

```
bool IsGroupDefaulted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısının özgün sağlayıcısı yerine varsayılan bir mekanizma güvenlik tanımlayıcısının grubu SID'yi sağladıysa, doğru döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için [CSecurityDesc::SetGroup](#setgroup) yöntemini kullanın.

## <a name="csecuritydescisownerdefaulted"></a><a name="isownerdefaulted"></a>CSecurityDesc::IsOwnerDefaulted

Güvenlik tanımlayıcısının sahibinin güvenlik tanımlayıcısının (SID) varsayılan olarak ayarlandığını belirler.

```
bool IsOwnerDefaulted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısının özgün sağlayıcısı yerine varsayılan bir mekanizma güvenlik tanımlayıcısının sahibi SID'yi sağladıysa, doğru döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için [CSecurityDesc::SetOwner](#setowner) yöntemini kullanın.

## <a name="csecuritydescissaclautoinherited"></a><a name="issaclautoinherited"></a>CSecurityDesc::IsSaclAutoInherited

Sistem erişim denetim listesinin (SACL) otomatik yayılmayı destekleyecek şekilde yapılandırıp yapılandırılmamasını belirler.

```
bool IsSaclAutoInherited() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı, varolan alt nesnelere devredilebilir erişim denetimi girişlerinin (ACE) otomatik olarak yayılmasını desteklemek üzere ayarlanmış bir SACL içeriyorsa doğru döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Sistem, nesne ve varolan alt nesneleri için otomatik devralma algoritmasını gerçekleştirirken bu biti ayarlar.

## <a name="csecuritydescissacldefaulted"></a><a name="issacldefaulted"></a>CSecurityDesc::IsSaclDefaulted

Güvenlik tanımlayıcısının varsayılan sistem erişim denetim listesi (SACL) ile yapılandırıp yapılandırılmadı sını belirler.

```
bool IsSaclDefaulted() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı varsayılan bir SACL içeriyorsa, aksi takdirde yanlış döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrak, erişim denetimi girişi (ACE) kalıtımı yla ilgili olarak sistemin SACL'yi nasıl ele aldığını etkileyebilir. SE_SACL_PRESENT bayrağı ayarlanmazsa sistem bu bayrağı yoksa.

Bu bayrağı ayarlamak için [CSecurityDesc::SetSacl](#setsacl) yöntemini kullanın.

## <a name="csecuritydescissaclpresent"></a><a name="issaclpresent"></a>CSecurityDesc::IsSaclPresent

Güvenlik tanımlayıcısının bir sistem erişim denetim listesi (SACL) içerip içersizliğini belirleyişini belirler.

```
bool IsSaclPresent() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı bir SACL içeriyorsa, aksi takdirde yanlış döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için [CSecurityDesc::SetSacl](#setsacl) yöntemini kullanın.

## <a name="csecuritydescissaclprotected"></a><a name="issaclprotected"></a>CSecurityDesc::IsSaclProtected

Sistem erişim denetim listesinin (SACL) değişiklikleri önlemek için yapılandırıp yapılandırılmadı sını belirler.

```
bool IsSaclProtected() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısının devredilebilir erişim denetimi girişleri (ACE'ler) tarafından değiştirilmesini önlemek için SACL yapılandırılırsa doğru döndürür. Aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı ayarlamak için [CSecurityDesc::SetSacl](#setsacl) yöntemini kullanın.

Bu yöntem, devredilebilir ACE'lerin otomatik olarak yayılmasını destekler.

## <a name="csecuritydescisselfrelative"></a><a name="isselfrelative"></a>CSecurityDesc::IsSelfRelative

Güvenlik tanımlayıcısının kendi bağıl biçiminde olup olmadığını belirler.

```
bool IsSelfRelative() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenlik tanımlayıcısı bitişik bir bellek bloğundaki tüm güvenlik bilgileriyle birlikte kendi bağıl biçimindeyse doğru döndürür. Güvenlik tanımlayıcısı mutlak biçimdeyse false döndürür. Daha fazla bilgi [için, Mutlak ve Öz-Akraba Güvenlik Tanımlayıcıları'na](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors)bakın.

## <a name="csecuritydescmakeabsolute"></a><a name="makeabsolute"></a>CSecurityDesc::MakeAbsolute

Güvenlik tanımlayıcısını mutlak biçime dönüştürmek için bu yöntemi çağırın.

```
bool MakeAbsolute() throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa doğru döndürür, aksi takdirde yanlış.

### <a name="remarks"></a>Açıklamalar

Mutlak biçimdeki bir güvenlik tanımlayıcısı, bilginin kendisi yerine içerdiği bilgilere işaretçiler içerir. Kendi göreli biçimindeki bir güvenlik tanımlayıcısı, bitişik bir bellek bloğundaki bilgileri içerir. Kendi kendine göreceli güvenlik tanımlayıcısında, `SECURITY_DESCRIPTOR` bir yapı her zaman bilgileri başlatır, ancak güvenlik tanımlayıcısının diğer bileşenleri yapıyı herhangi bir sırada izleyebilir. Bellek adreslerini kullanmak yerine, öz-göreceli güvenlik tanımlayıcısının bileşenleri, güvenlik tanımlayıcısının başlangıcından itibaren uzaklıklarla tanımlanır. Bu biçim, bir güvenlik tanımlayıcısının bir diskte depolanmış olması veya bir iletişim protokolü yoluyla iletilmesi gerektiğinde yararlıdır. Daha fazla bilgi [için, Mutlak ve Öz-Akraba Güvenlik Tanımlayıcıları'na](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors)bakın.

## <a name="csecuritydescmakeselfrelative"></a><a name="makeselfrelative"></a>CSecurityDesc::MakeSelfRelative

Güvenlik tanımlayıcısını kendi bağıl biçimine dönüştürmek için bu yöntemi çağırın.

```
bool MakeSelfRelative() throw(...);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa doğru döndürür, aksi takdirde yanlış.

### <a name="remarks"></a>Açıklamalar

Mutlak biçimdeki bir güvenlik tanımlayıcısı, bilginin kendisini içermek yerine içerdiği bilgilere işaretçiler içerir. Kendi göreli biçimindeki bir güvenlik tanımlayıcısı, bitişik bir bellek bloğundaki bilgileri içerir. Kendi kendine göreceli güvenlik tanımlayıcısında, `SECURITY_DESCRIPTOR` bir yapı her zaman bilgileri başlatır, ancak güvenlik tanımlayıcısının diğer bileşenleri yapıyı herhangi bir sırada izleyebilir. Bellek adreslerini kullanmak yerine, güvenlik tanımlayıcısının bileşenleri, güvenlik tanımlayıcısının başından itibaren uzaklıklarla tanımlanır. Bu biçim, bir güvenlik tanımlayıcısının bir diskte depolanmış olması veya bir iletişim protokolü yoluyla iletilmesi gerektiğinde yararlıdır. Daha fazla bilgi [için, Mutlak ve Öz-Akraba Güvenlik Tanımlayıcıları'na](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors)bakın.

## <a name="csecuritydescoperator-"></a><a name="operator_eq"></a>CSecurityDesc::operatör =

Atama işleci.

```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>Parametreler

*Rhs*<br/>
Nesneye `SECURITY_DESCRIPTOR` `CSecurityDesc` atayacak yapı veya nesne. `CSecurityDesc`

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CSecurityDesc` nesneyi döndürür.

## <a name="csecuritydescoperator-const-security_descriptor-"></a><a name="operator_const_security_descriptor__star"></a>CSecurityDesc::operatör const SECURITY_DESCRIPTOR *

`SECURITY_DESCRIPTOR` Yapıya bir işaretçiiçin bir değer atar.

```
operator const SECURITY_DESCRIPTOR *() const throw();
```

## <a name="csecuritydescsetcontrol"></a><a name="setcontrol"></a>CSecurityDesc::SetControl

Güvenlik tanımlayıcısının denetim bitlerini ayarlar.

```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest,
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```

### <a name="parameters"></a>Parametreler

*ControlBitsOfInterest*<br/>
Ayarlanan denetim bitlerini gösteren SECURITY_DESCRIPTOR_CONTROL maskesi. Ayarlanabilen bayrakların listesi için [SetSecurityDescriptorControl](/windows/win32/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol)bölümüne bakın.

*ControlBitsToSet*<br/>
*ControlBitsOfInterest* maskesi tarafından belirtilen denetim bitlerinin yeni değerlerini gösteren SECURITY_DESCRIPTOR_CONTROL bir maske. Bu *parametre, ControlBitsOfInterest* parametresi için listelenen bayrakların bir birleşimi olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu [yöntem, SetSecurityDescriptorControl](/windows/win32/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol)çağırır.

## <a name="csecuritydescsetdacl"></a><a name="setdacl"></a>CSecurityDesc::SetDacl

Bilgileri isteğe bağlı erişim denetim listesinde (DACL) ayarlar. Güvenlik tanımlayıcısında zaten bir DACL varsa, değiştirilir.

```
inline void SetDacl(
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*Dacl*<br/>
Güvenlik tanımlayıcısı için DACL'yi belirten bir `CDacl` nesneye başvuru. Bu parametre NULL olmamalıdır. Güvenlik tanımlayıcısında NULL DACL ayarlamak için, yöntemin ilk biçimi false olarak ayarlanmış *bPresent* ile kullanılmalıdır.

*bPresent*<br/>
Güvenlik tanımlayıcısında bir DACL varlığını gösteren bir bayrak belirtir. Bu parametre doğruysa, yöntem `SECURITY_DESCRIPTOR_CONTROL` yapıdaki SE_DACL_PRESENT bayrağını ayarlar ve *Dacl* ve *bDefaulted* parametrelerindeki değerleri kullanır. Yanlışsa, yöntem SE_DACL_PRESENT bayrağını temizler ve *bDefaulted* yoksayılır.

*bVarsayılan*<br/>
DACL'nin kaynağını gösteren bir bayrak belirtir. Bu bayrak doğruysa, DACL bazı varsayılan mekanizma tarafından alınmıştır. Yanlışsa, DACL kullanıcı tarafından açıkça belirtilmiştir. Yöntem, bu değeri `SECURITY_DESCRIPTOR_CONTROL` yapının SE_DACL_DEFAULTED bayrağında depolar. Bu parametre belirtilmemişse, SE_DACL_DEFAULTED bayrağı temizlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Boş ve var olmayan bir DACL arasında önemli bir fark vardır. Bir DACL boşsa, erişim denetimi girişleri içermez ve erişim hakları açıkça izin verilmez. Sonuç olarak, nesneye erişim örtülü olarak reddedilir. Bir nesnenin DACL'si yoksa, diğer taraftan, nesneye koruma atanmaz ve herhangi bir erişim isteği verilir.

## <a name="csecuritydescsetgroup"></a><a name="setgroup"></a>CSecurityDesc::SetGroup

Zaten var olan birincil grup bilgilerini değiştirerek, mutlak biçim güvenlik tanımlayıcısının birincil grup bilgilerini ayarlar.

```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*Sid*<br/>
Güvenlik tanımlayıcısının yeni birincil grubu için [csid](../../atl/reference/csid-class.md) nesnesine başvuru. Bu parametre NULL olmamalıdır. Bir güvenlik tanımlayıcısı bir DACL veya SACL sahip değil olarak işaretlenmiş olabilir, ama bir grup ve sahibi olmalıdır, hatta bu NULL SID (özel bir anlamı olan yerleşik bir SID olan).

*bVarsayılan*<br/>
Birincil grup bilgilerinin varsayılan bir mekanizmadan türetilip türetilip türetilenin gösterir. Bu değer doğruysa, varsayılan bilgidir ve yöntem bu değeri `SECURITY_DESCRIPTOR_CONTROL` yapıdaki SE_GROUP_DEFAULTED bayrağı olarak depolar. Bu parametre sıfırsa, SE_GROUP_DEFAULTED bayrağı temizlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

## <a name="csecuritydescsetowner"></a><a name="setowner"></a>CSecurityDesc::SetSahibi

Mutlak biçim güvenlik tanımlayıcısının sahibi bilgilerini ayarlar. Mevcut tüm sahip bilgilerinin yerini alır.

```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*Sid*<br/>
Güvenlik tanımlayıcısının yeni birincil sahibi için [CSid](../../atl/reference/csid-class.md) nesnesi. Bu parametre NULL olmamalıdır.

*bVarsayılan*<br/>
Sahip bilgilerinin varsayılan bir mekanizmadan türetilip türetilmiş olmadığını gösterir. Bu değer doğruysa, varsayılan bilgidir. Yöntem, yapıdaki `SECURITY_DESCRIPTOR_CONTROL` SE_OWNER_DEFAULTED bayrağı olarak bu değeri depolar. Bu parametre sıfırsa, SE_OWNER_DEFAULTED bayrağı temizlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

## <a name="csecuritydescsetsacl"></a><a name="setsacl"></a>CSecurityDesc::SetSacl

Bilgileri sistem erişim denetim listesinde (SACL) ayarlar. Güvenlik tanımlayıcısında zaten bir SACL varsa, değiştirilir.

```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parametreler

*Sacl*<br/>
Güvenlik tanımlayıcısı için SACL belirten bir `CSacl` nesneye işaretçi. Bu parametre NULL olmamalı ve bir CSacl nesnesi olmalıdır. DACL'ların aksine, NULL ile boş bir SACL arasında hiçbir fark yoktur, çünkü SACL nesneleri erişim haklarını belirtmez, yalnızca denetim bilgileri belirtir.

*bVarsayılan*<br/>
SACL'nin kaynağını gösteren bir bayrak belirtir. Bu bayrak doğruysa, SACL bazı varsayılan mekanizma tarafından alınmıştır. Yanlışsa, SACL kullanıcı tarafından açıkça belirtilmiştir. Yöntem, bu değeri `SECURITY_DESCRIPTOR_CONTROL` yapının SE_SACL_DEFAULTED bayrağında depolar. Bu parametre belirtilmemişse, SE_SACL_DEFAULTED bayrağı temizlenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

## <a name="csecuritydesctostring"></a><a name="tostring"></a>CSecurityDesc::ToString

Güvenlik tanımlayıcısını dize biçimine dönüştürür.

```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```

### <a name="parameters"></a>Parametreler

*pstr*<br/>
[Dize biçimi güvenlik tanımlayıcısını](/windows/win32/SecAuthZ/security-descriptor-string-format)alacak bir null-sonlandırılan dize işaretçi.

*Si*<br/>
Çıkış dizesine dahil olacak güvenlik tanımlayıcısının bileşenlerini belirtmek için SECURITY_INFORMATION bit bayraklarının birleşimini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Güvenlik tanımlayıcısı dize biçiminde olduğunda, daha kolay depolanabilir veya iletilebilir. Dizeyi `CSecurityDesc::FromString` bir güvenlik tanımlayıcısına dönüştürmek için yöntemi kullanın.

*SI* parametresi aşağıdaki SECURITY_INFORMATION bayraklarını içerebilir:

|Değer|Anlamı|
|-----------|-------------|
|OWNER_SECURITY_INFORMATION|Sahibini de dahil et.|
|GROUP_SECURITY_INFORMATION|Birincil grubu ekleyin.|
|DACL_SECURITY_INFORMATION|DACL'yi ekleyin.|
|SACL_SECURITY_INFORMATION|SACL'yi ekleyin.|

DACL NULL ise ve SE_DACL_PRESENT denetim biti giriş güvenlik tanımlayıcısında ayarlanırsa, yöntem başarısız olur.

DACL NULL ise ve SE_DACL_PRESENT denetim biti giriş güvenlik tanımlayıcısında ayarlı değilse, ortaya çıkan güvenlik tanımlayıcı dizesi D: bileşeni ne olur. Daha fazla ayrıntı için [Güvenlik Tanımlayıcı String Formatına](/windows/win32/SecAuthZ/security-descriptor-string-format) bakın.

Bu yöntem [ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/win32/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptorw)çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Güvenlik Örneği](../../overview/visual-cpp-samples.md)<br/>
[Securıty_descrıptor](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
