---
title: "CSecurityDesc sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
helpviewer_keywords: CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b199565221173d7664600f2869e079c2f1c95aae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csecuritydesc-class"></a>CSecurityDesc sınıfı
Bu sınıf için sarmalayıcı, **SECURITY_DESCRIPTOR** yapısı.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CSecurityDesc
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSecurityDesc::CSecurityDesc](#csecuritydesc)|Oluşturucu.|  
|[CSecurityDesc:: ~ CSecurityDesc](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSecurityDesc::FromString](#fromstring)|Dize biçimi güvenlik tanımlayıcısı geçerli, işlev güvenlik tanımlayıcısı dönüştürür.|  
|[CSecurityDesc::GetControl](#getcontrol)|Alır, bilgileri güvenlik tanımlayıcısı denetler.|  
|[CSecurityDesc::GetDacl](#getdacl)|İsteğe bağlı erişim denetimi listesi (DACL) bilgileri güvenlik tanımlayıcısından alır.|  
|[CSecurityDesc::GetGroup](#getgroup)|Birincil grup bilgileri güvenlik tanımlayıcısından alır.|  
|[CSecurityDesc::GetOwner](#getowner)|Güvenlik tanımlayıcısı sahibi bilgilerini alır.|  
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|Bir işaretçi döndürür **SECURITY_DESCRIPTOR** yapısı.|  
|[CSecurityDesc::GetSacl](#getsacl)|Güvenlik tanımlayıcısından sistem erişim denetimi listesi (SACL) bilgilerini alır.|  
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|DACL otomatik yayma desteklemek üzere yapılandırılmış olup olmadığını belirler.|  
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|Güvenlik tanımlayıcısı varsayılan DACL ile yapılandırılmış olup olmadığını belirler.|  
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|Güvenlik tanımlayıcısı DACL içerip içermediğini belirler.|  
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|DACL değişiklikleri önlemek için yapılandırılmış olup olmadığını belirler.|  
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|Güvenlik tanımlayıcı grubun güvenlik tanımlayıcısı (SID) varsayılan olarak ayarlanmış olmadığını belirler.|  
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|Güvenlik tanımlayıcı sahibi SID'si varsayılan olarak ayarlanmış olmadığını belirler.|  
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|SACL otomatik yayma desteklemek üzere yapılandırılmış olup olmadığını belirler.|  
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|Güvenlik tanımlayıcısı varsayılan SACL ile yapılandırılmış olup olmadığını belirler.|  
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|Güvenlik tanımlayıcısı SACL içerip içermediğini belirler.|  
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|SACL değişiklikleri önlemek için yapılandırılmış olup olmadığını belirler.|  
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|Güvenlik tanımlayıcısı kendine bağlı biçimde olup olmadığını belirler.|  
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|Güvenlik tanımlayıcısı mutlak biçimine dönüştürmek için bu yöntemi çağırın.|  
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|Güvenlik tanımlayıcısı kendine bağlı biçime dönüştürmek için bu yöntemi çağırın.|  
|[CSecurityDesc::SetControl](#setcontrol)|Güvenlik tanımlayıcısının denetim bitlerini ayarlar.|  
|[CSecurityDesc::SetDacl](#setdacl)|Bilgiler bir DACL ayarlar. Güvenlik tanımlayıcısı DACL zaten varsa, değiştirilir.|  
|[CSecurityDesc::SetGroup](#setgroup)|Zaten mevcut herhangi bir birincil grup bilgi değiştirerek bir mutlak biçimde güvenlik tanımlayıcısı birincil grup bilgilerini ayarlar.|  
|[CSecurityDesc::SetOwner](#setowner)|Zaten mevcut herhangi bir sahibi bilgi değiştirerek bir mutlak biçimde güvenlik tanımlayıcısı sahibi bilgilerini ayarlar.|  
|[CSecurityDesc::SetSacl](#setsacl)|Bir SACL bilgilerini ayarlar. Güvenlik tanımlayıcısı SACL zaten varsa, değiştirilir.|  
|[CSecurityDesc::ToString](#tostring)|Güvenlik tanımlayıcısı dizesi biçimine dönüştürür.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSecurityDesc::operator const SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|Bir işaretçi döndürür **SECURITY_DESCRIPTOR** yapısı.|  
|[CSecurityDesc::operator =](#operator_eq)|Atama işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 **SECURITY_DESCRIPTOR** yapısı bir nesneyle ilişkilendirilmiş güvenlik bilgilerini içerir. Uygulama bu yapı ayarlayın ve bir nesnenin güvenlik durumunu sorgulamak için kullanır. Ayrıca bkz. [AtlGetSecurityDescriptor](security-global-functions.md#atlgetsecuritydescriptor).  
  
 Uygulamaları değişiklik **SECURITY_DESCRIPTOR** yapısı doğrudan ve bunun yerine kullanması gereken sağlanan sınıfı yöntemleri.  
  
 Erişim denetimi modeli Windows giriş için bkz: [erişim denetimi](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows SDK'sındaki.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h  
  
##  <a name="csecuritydesc"></a>CSecurityDesc::CSecurityDesc  
 Oluşturucu.  
  
```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );  
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 `CSecurityDesc` Nesne veya **SECURITY_DESCRIPTOR** yeni sunucuya atanacak yapı `CSecurityDesc` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CSecurityDesc` Nesne isteğe bağlı olarak kullanılarak oluşturulabilir bir **SECURITY_DESCRIPTOR** yapısı veya önceden tanımlanmış `CSecurityDesc` nesnesi.  
  
##  <a name="dtor"></a>CSecurityDesc:: ~ CSecurityDesc  
 Yok Edicisi.  
  
```
virtual ~CSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="fromstring"></a>CSecurityDesc::FromString  
 Dize biçimi güvenlik tanımlayıcısı geçerli, işlev güvenlik tanımlayıcısı dönüştürür.  
  
```
bool FromString(LPCTSTR pstr) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pstr`  
 İşaretçi içeren null ile sonlandırılmış bir dizeye [dize biçimi güvenlik tanımlayıcısı](http://msdn.microsoft.com/library/windows/desktop/aa379570) dönüştürülecek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı true döndürür. Bir özel durum hatası oluşturur.  
  
### <a name="remarks"></a>Açıklamalar  
 Dize kullanarak oluşturulabilir [CSecurityDesc::ToString](#tostring). Güvenlik tanımlayıcısı bir dizeye dönüştürme depolamak ve iletmek kolaylaştırır.  
  
 Çağırır çünkü bu yöntem yalnızca Windows 2000 ve daha sonra kullanılabilir [ConvertStringSecurityDescriptorToSecurityDescriptor](http://msdn.microsoft.com/library/windows/desktop/aa376401).  
  
##  <a name="getcontrol"></a>CSecurityDesc::GetControl  
 Alır, bilgileri güvenlik tanımlayıcısı denetler.  
  
```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *psdc*  
 İşaretçi bir **SECURITY_DESCRIPTOR_CONTROL** yapısı güvenlik tanımlayıcı denetim bilgilerini alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, false başarısız olursa true döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırır gibi bu yöntem yalnızca Windows 2000 kullanırken anlamlı ya da üstü [GetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa446647).  
  
##  <a name="getdacl"></a>CSecurityDesc::GetDacl  
 İsteğe bağlı erişim denetimi listesi (DACL) bilgileri güvenlik tanımlayıcısından alır.  
  
```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDacl`  
 İşaretçi bir `CDacl` güvenlik tanımlayıcı DACL kopyasını depolanacağı yapısı. Bir isteğe bağlı ise **ACL** yoksa, yöntem kümeleri `pDacl` güvenlik adresine tanımlayıcısı isteğe bağlı **ACL**. Bir isteğe bağlı ise **ACL** yok, hiçbir değer depolanır.  
  
 `pbPresent`  
 Bir isteğe bağlı durumunu gösteren bir değer işaretçi **ACL** içinde belirtilen güvenlik tanımlayıcısı. Güvenlik tanımlayıcısı bir isteğe bağlı içeriyorsa **ACL**, bu parametreyi ayarlayın true. Güvenlik tanımlayıcısı bir isteğe bağlı içermiyorsa **ACL**, bu parametre false olarak ayarlanır.  
  
 `pbDefaulted`  
 Bir bayrak için işaretçisi ayarlanmaya SE_DACL_DEFAULTED bayrağı değerine **SECURITY_DESCRIPTOR_CONTROL** bir isteğe bağlı, yapı **ACL** için güvenlik tanımlayıcısı yok. Bu bayrak true ise isteğe bağlı **ACL** tarafından varsayılan bir mekanizma; false ise, alınan isteğe bağlı **ACL** bir kullanıcı tarafından açıkça belirtildi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, false başarısız olursa true döndürür.  
  
##  <a name="getgroup"></a>CSecurityDesc::GetGroup  
 Birincil grup bilgileri güvenlik tanımlayıcısından alır.  
  
```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSid`  
 İşaretçi bir [CSID](../../atl/reference/csid-class.md) (güvenlik tanımlayıcısı) CDacl depolanan Grup bir kopyasını alır.  
  
 `pbDefaulted`  
 Bir bayrak için işaretçisi ayarlanmaya SE_GROUP_DEFAULTED bayrağı değerine **SECURITY_DESCRIPTOR_CONTROL** yöntem döndüğünde yapılandırın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, false başarısız olursa true döndürür.  
  
##  <a name="getowner"></a>CSecurityDesc::GetOwner  
 Güvenlik tanımlayıcısı sahibi bilgilerini alır.  
  
```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSid`  
 İşaretçi bir [CSID](../../atl/reference/csid-class.md) (güvenlik tanımlayıcısı) CDacl depolanan Grup bir kopyasını alır.  
  
 `pbDefaulted`  
 Bir bayrak için işaretçisi ayarlanmaya SE_OWNER_DEFAULTED bayrağı değerine **SECURITY_DESCRIPTOR_CONTROL** yöntem döndüğünde yapılandırın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, false başarısız olursa true döndürür.  
  
##  <a name="getpsecurity_descriptor"></a>CSecurityDesc::GetPSECURITY_DESCRIPTOR  
 Bir işaretçi döndürür **SECURITY_DESCRIPTOR** yapısı.  
  
```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561) yapısı.  
  
##  <a name="getsacl"></a>CSecurityDesc::GetSacl  
 Güvenlik tanımlayıcısından sistem erişim denetimi listesi (SACL) bilgilerini alır.  
  
```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSacl`  
 İşaretçi bir `CSacl` güvenlik tanımlayıcı SACL kopyasını depolanacağı yapısı. Bir sistem durumunda **ACL** yoksa, yöntem kümeleri `pSacl` güvenlik tanımlayıcı sistem adresine **ACL**. Bir sistem durumunda **ACL** yok, hiçbir değer depolanır.  
  
 `pbPresent`  
 Yöntemini ayarlar bir sistem varlığını göstermek için bir bayrak işaretçi **ACL** içinde belirtilen güvenlik tanımlayıcısı. Bir sistem güvenlik tanımlayıcısı içeriyorsa, **ACL**, bu parametreyi ayarlayın true. Güvenlik tanımlayıcısı bir sistem içermiyorsa **ACL**, bu parametre false olarak ayarlanır.  
  
 `pbDefaulted`  
 Bir bayrak için işaretçisi ayarlanmaya SE_SACL_DEFAULTED bayrağı değerine **SECURITY_DESCRIPTOR_CONTROL** bir sistemi yapısı **ACL** için güvenlik tanımlayıcısı yok.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, false başarısız olursa true döndürür.  
  
##  <a name="isdaclautoinherited"></a>CSecurityDesc::IsDaclAutoInherited  
 İsteğe bağlı erişim denetimi listesi (DACL) otomatik yayma desteklemek üzere yapılandırılmış olup olmadığını belirler.  
  
```
bool IsDaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güvenlik tanımlayıcısı devralınabilir erişim denetimi girişlerinin (ACE'ler) mevcut alt nesneleri için otomatik yayılmasını desteklemek üzere ayarlanan bir DACL içeriyorsa true döndürür. Aksi takdirde false döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne ve varolan alt nesneleri için otomatik devralma algoritması gerçekleştirdiğinde, sistem bu bit ayarlar.  
  
##  <a name="isdacldefaulted"></a>CSecurityDesc::IsDaclDefaulted  
 Güvenlik tanımlayıcısı varsayılan isteğe bağlı erişim denetimi listesi (DACL) ile yapılandırılmış olup olmadığını belirler.  
  
```
bool IsDaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güvenlik tanımlayıcısı DACL, varsayılan false aksi içeriyorsa true değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bayrak, sistem erişim denetim girdisi (ACE) devralma göre DACL nasıl işler etkileyebilir. Örneğin, bir nesnenin oluşturan bir DACL belirtmiyorsa nesne DACL varsayılan oluşturanın erişim belirtecinden alır. SE_DACL_PRESENT bayrağı ayarlanmamışsa sistem bu bayrak yoksayar.  
  
 Bu bayrak, nesne üzerinde son DACL nasıl hesaplanması belirlemek için kullanılır ve fiziksel olarak güvenli kılınabilir nesne güvenlik tanımlayıcısı denetiminde depolanmaz.  
  
 Bu bayrak ayarlamak için kullanın [CSecurityDesc::SetDacl](#setdacl) yöntemi.  
  
##  <a name="isdaclpresent"></a>CSecurityDesc::IsDaclPresent  
 Güvenlik tanımlayıcısı isteğe bağlı erişim denetimi listesi (DACL) içerip içermediğini belirler.  
  
```
bool IsDaclPresent() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güvenlik tanımlayıcısı bir DACL yanlış aksi içeriyorsa true döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bayrak ayarlanmazsa ya da bu bayrağı ayarlanmış olduğundan ve DACL NULL ise, güvenlik tanımlayıcısı herkese tam erişim sağlar.  
  
 Bu bayrak, güvenlik tanımlayıcısı güvenliği sağlanabilir nesne ile ilişkili olduğu kadar çağıran tarafından belirtilen güvenlik bilgilerini tutmak için kullanılır. Güvenlik tanımlayıcısı güvenliği sağlanabilir nesne ile ilişkili olduğunda SE_DACL_PRESENT bayrağını her zaman güvenlik tanımlayıcısı denetiminde ayarlanır.  
  
 Bu bayrak ayarlamak için kullanın [CSecurityDesc::SetDacl](#setdacl) yöntemi.  
  
##  <a name="isdaclprotected"></a>CSecurityDesc::IsDaclProtected  
 İsteğe bağlı erişim denetimi listesi (DACL) değişiklikleri önlemek için yapılandırılmış olup olmadığını belirler.  
  
```
bool IsDaclProtected() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 DACL devralınabilir erişim denetimi girişlerinin (ACE'ler) tarafından değiştirilen güvenlik tanımlayıcısı önlemek için yapılandırılmışsa, true döndürür. Aksi takdirde false döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bayrak ayarlamak için kullanın [CSecurityDesc::SetDacl](#setdacl) yöntemi.  
  
 Yalnızca Windows 2000 Devralınabilir ACE otomatik yayılmasını desteklediği bu yöntem yalnızca Windows 2000 veya sonraki sürümlerde, anlamlıdır.  
  
##  <a name="isgroupdefaulted"></a>CSecurityDesc::IsGroupDefaulted  
 Güvenlik tanımlayıcı grubun güvenlik tanımlayıcısı (SID) varsayılan olarak ayarlanmış olmadığını belirler.  
  
```
bool IsGroupDefaulted() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 True değerini döndürür güvenlik tanımlayıcısı özgün sağlayıcısı yerine varsayılan bir mekanizma güvenlik tanımlayıcı sağlanırsa, SID grup. Aksi takdirde false döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bayrak ayarlamak için kullanın [CSecurityDesc::SetGroup](#setgroup) yöntemi.  
  
##  <a name="isownerdefaulted"></a>CSecurityDesc::IsOwnerDefaulted  
 Güvenlik tanımlayıcı sahibi güvenlik tanımlayıcısı (SID) varsayılan olarak ayarlanmış olmadığını belirler.  
  
```
bool IsOwnerDefaulted() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güvenlik tanımlayıcısı özgün sağlayıcısı yerine varsayılan bir mekanizma güvenlik tanımlayıcı sahibi SID'si sağlanan varsa true değerini döndürür. Aksi takdirde false döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bayrak ayarlamak için kullanın [CSecurityDesc::SetOwner](#setowner) yöntemi.  
  
##  <a name="issaclautoinherited"></a>CSecurityDesc::IsSaclAutoInherited  
 Sistem erişim denetimi listesi (SACL) otomatik yayma desteklemek üzere yapılandırılmış olup olmadığını belirler.  
  
```
bool IsSaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güvenlik tanımlayıcısı devralınabilir erişim denetimi girişlerinin (ACE'ler) mevcut alt nesneleri için otomatik yayılmasını desteklemek için ayarlanan SACL içeriyorsa true döndürür. Aksi takdirde false döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne ve varolan alt nesneleri için otomatik devralma algoritması gerçekleştirdiğinde, sistem bu bit ayarlar.  
  
##  <a name="issacldefaulted"></a>CSecurityDesc::IsSaclDefaulted  
 Güvenlik tanımlayıcısı varsayılan sistem erişim denetimi listesi (SACL) ile yapılandırılmış olup olmadığını belirler.  
  
```
bool IsSaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güvenlik tanımlayıcısı SACL, varsayılan false aksi içeriyorsa true değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bayrak, sistem erişim denetim girdisi (ACE) devralma göre SACL nasıl işler etkileyebilir. SE_SACL_PRESENT bayrağı ayarlanmamışsa sistem bu bayrak yoksayar.  
  
 Bu bayrak ayarlamak için kullanın [CSecurityDesc::SetSacl](#setsacl) yöntemi.  
  
##  <a name="issaclpresent"></a>CSecurityDesc::IsSaclPresent  
 Güvenlik tanımlayıcısı sistem erişim denetimi listesi (SACL) içerip içermediğini belirler.  
  
```
bool IsSaclPresent() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güvenlik tanımlayıcısı bir SACL yanlış aksi içeriyorsa true döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bayrak ayarlamak için kullanın [CSecurityDesc::SetSacl](#setsacl) yöntemi.  
  
##  <a name="issaclprotected"></a>CSecurityDesc::IsSaclProtected  
 Sistem erişim denetimi listesi (SACL) değişiklikleri önlemek için yapılandırılmış olup olmadığını belirler.  
  
```
bool IsSaclProtected() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 SACL devralınabilir erişim denetimi girişlerinin (ACE'ler) tarafından değiştirilen güvenlik tanımlayıcısı önlemek için yapılandırılmışsa, true döndürür. Aksi takdirde false döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bayrak ayarlamak için kullanın [CSecurityDesc::SetSacl](#setsacl) yöntemi.  
  
 Yalnızca Windows 2000 Devralınabilir ACE otomatik yayılmasını desteklediği bu yöntem yalnızca Windows 2000 veya sonraki sürümlerde, anlamlıdır.  
  
##  <a name="isselfrelative"></a>CSecurityDesc::IsSelfRelative  
 Güvenlik tanımlayıcısı kendine bağlı biçimde olup olmadığını belirler.  
  
```
bool IsSelfRelative() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güvenlik tanımlayıcısı kendine bağlı biçimde bitişik bir bellek bloğu tüm güvenlik bilgileri ile true değerini döndürür. Mutlak biçimde güvenlik tanımlayıcısı ise, yanlış değerini döndürür. Daha fazla bilgi için bkz: [mutlak ve Self-Relative güvenlik tanımlayıcıları](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="makeabsolute"></a>CSecurityDesc::MakeAbsolute  
 Güvenlik tanımlayıcısı mutlak biçimine dönüştürmek için bu yöntemi çağırın.  
  
```
bool MakeAbsolute() throw(...);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, false Aksi takdirde true değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Mutlak biçimde güvenlik tanımlayıcısı, bilgi yerine içerdiği bilgilere işaretçiler içerir. Güvenlik tanımlayıcısı kendine bağlı biçimde bitişik bir bellek bloğu bilgileri içerir. Kendine bağlı güvenlik tanımlayıcısı'nda bir **SECURITY_DESCRIPTOR** yapısı bilgileri her zaman başlatır, ancak diğer güvenlik tanımlayıcısı kullanıcının bileşenleri herhangi bir sırada yapısı izleyin. Bellek adreslerini kullanmak yerine, kendine bağlı güvenlik tanımlayıcısı bileşenlerinin güvenlik tanımlayıcısı başından uzaklık tarafından tanımlanır. Bu biçim bir güvenlik açıklayıcısı bir diskte depolanan veya bir iletişim protokolü aracılığıyla aktarılan faydalıdır. Daha fazla bilgi için bkz: [mutlak ve Self-Relative güvenlik tanımlayıcıları](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="makeselfrelative"></a>CSecurityDesc::MakeSelfRelative  
 Güvenlik tanımlayıcısı kendine bağlı biçime dönüştürmek için bu yöntemi çağırın.  
  
```
bool MakeSelfRelative() throw(...);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, false Aksi takdirde true değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Mutlak biçimde güvenlik tanımlayıcısı bilgilerini içeren yerine, içerdiği bilgilere işaretçiler içerir. Güvenlik tanımlayıcısı kendine bağlı biçimde bitişik bir bellek bloğu bilgileri içerir. Kendine bağlı güvenlik tanımlayıcısı'nda bir **SECURITY_DESCRIPTOR** yapısı bilgileri her zaman başlatır, ancak diğer güvenlik tanımlayıcısı kullanıcının bileşenleri herhangi bir sırada yapısı izleyin. Bellek adreslerini kullanmak yerine, güvenlik tanımlayıcısı bileşenlerinin güvenlik tanımlayıcısı başından uzaklık tarafından tanımlanır. Bu biçim bir güvenlik açıklayıcısı bir diskte depolanan veya bir iletişim protokolü aracılığıyla aktarılan faydalıdır. Daha fazla bilgi için bkz: [mutlak ve Self-Relative güvenlik tanımlayıcıları](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="operator_eq"></a>CSecurityDesc::operator =  
 Atama işleci.  
  
```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);  
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 **SECURITY_DESCRIPTOR** yapısı veya `CSecurityDesc` atamak için nesne `CSecurityDesc` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CSecurityDesc` nesnesi.  
  
##  <a name="operator_const_security_descriptor__star"></a>CSecurityDesc::operator const SECURITY_DESCRIPTOR *  
 Bir işaretçi bir değere bıraktığı **SECURITY_DESCRIPTOR** yapısı.  
  
```  
operator const SECURITY_DESCRIPTOR *() const throw();
```  
  
##  <a name="setcontrol"></a>CSecurityDesc::SetControl  
 Güvenlik tanımlayıcısının denetim bitlerini ayarlar.  
  
```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest, 
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ControlBitsOfInterest`  
 A **SECURITY_DESCRIPTOR_CONTROL** ayarlamak için Denetim bitleri belirten maske. Ayarlanabilir bayrakları listesi için bkz: [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).  
  
 `ControlBitsToSet`  
 A `SECURITY_DESCRIPTOR_CONTROL` tarafından belirtilen denetim BITS için yeni değerleri gösteren maskesi `ControlBitsOfInterest` maske. Bu parametre için listelenen bayrakları bir bileşimi olabilir `ControlBitsOfInterest` parametresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırır gibi bu yöntem yalnızca Windows 2000 ve daha sonra kullanılabilir [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).  
  
##  <a name="setdacl"></a>CSecurityDesc::SetDacl  
 Bir isteğe bağlı erişim denetimi listesi (DACL) bilgilerini ayarlar. Güvenlik tanımlayıcısı DACL zaten varsa, değiştirilir.  
  
```
inline void SetDacl(  
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(  
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *DACL*  
 Başvuru bir `CDacl` nesne için güvenlik tanımlayıcısı DACL belirtme. Bu parametre NULL olmamalıdır. Güvenlik tanımlayıcısı NULL DACL ayarlamak için yönteminin ilk form ile kullanılması gereken `bPresent` false olarak ayarlayın.  
  
 `bPresent`  
 Güvenlik Tanımlayıcısı'nda bir DACL varlığını gösteren bir bayrak belirtir. Bu parametre true ise, yöntem SE_DACL_PRESENT bayrağını ayarlar **SECURITY_DESCRIPTOR_CONTROL** yapısı ve değerleri kullanır *Dacl* ve `bDefaulted` parametreleri. False ise, yöntem SE_DACL_PRESENT bayrağını temizler ve `bDefaulted` göz ardı edilir.  
  
 `bDefaulted`  
 DACL kaynağını belirten bir bayrak belirtir. Bu bayrak true ise, DACL bazı varsayılan mekanizması tarafından alınmış. Yanlışsa, bir kullanıcı tarafından DACL açıkça belirtilmiş. Yöntemi bu değer SE_DACL_DEFAULTED bayrağını depolar **SECURITY_DESCRIPTOR_CONTROL** yapısı. Bu parametre belirtilmezse, SE_DACL_DEFAULTED bayrağı temizlenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Boş bir ve varolmayan bir DACL arasında önemli bir fark yoktur. DACL boş olduğunda, hiçbir erişim denetimi girdileri içerir ve hiçbir erişim haklarını açıkça verildi. Sonuç olarak, nesne erişimi örtük olarak reddedildi. Bir nesne DACL yok olduğunda, diğer yandan koruma nesnesine atanmış ve herhangi bir erişim istek verilir.  
  
##  <a name="setgroup"></a>CSecurityDesc::SetGroup  
 Zaten mevcut herhangi bir birincil grup bilgi değiştirerek bir mutlak biçimde güvenlik tanımlayıcısı birincil grup bilgilerini ayarlar.  
  
```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `Sid`  
 Başvuru bir [CSID](../../atl/reference/csid-class.md) güvenlik tanımlayıcı yeni birincil grubu için nesne. Bu parametre NULL olmamalıdır. Bir güvenlik açıklayıcısı DACL veya SACL olmamasından olarak işaretlenebilir, ancak bunlar bile bir grubu ve bir sahip olması gerekir (Bu, yerleşik bir SID ile özel bir anlamı olan) NULL SID şunlardır.  
  
 `bDefaulted`  
 Birincil grup bilgileri varsayılan bir mekanizma türetilen olup olmadığını gösterir. Bu değer true ise, varsayılan bilgileri olan ve SE_GROUP_DEFAULTED bayrağı olarak bu değer yöntemi depolar **SECURITY_DESCRIPTOR_CONTROL** yapısı. Bu parametre sıfırsa SE_GROUP_DEFAULTED bayrağı temizlenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="setowner"></a>CSecurityDesc::SetOwner  
 Mutlak biçimde güvenlik tanımlayıcısı sahibi bilgilerini ayarlar. Zaten mevcut herhangi bir sahiplik bilgilerini değiştirir.  
  
```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `Sid`  
 [CSID](../../atl/reference/csid-class.md) nesne için güvenlik tanımlayıcı yeni birincil sahibi. Bu parametre NULL olmamalıdır.  
  
 `bDefaulted`  
 Sahibi bilgileri varsayılan bir mekanizma türetilmiş olup olmadığını gösterir. Bu değeri true ise, varsayılan bilgileri olur. SE_OWNER_DEFAULTED bayrağı olarak bu değer yöntemi depolar **SECURITY_DESCRIPTOR_CONTROL** yapısı. Bu parametre sıfırsa SE_OWNER_DEFAULTED bayrağı temizlenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="setsacl"></a>CSecurityDesc::SetSacl  
 Bilgileri bir sistem erişim denetimi listesi (SACL) ayarlar. Güvenlik tanımlayıcısı SACL zaten varsa, değiştirilir.  
  
```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *SACL*  
 İşaretçi bir `CSacl` nesne için güvenlik tanımlayıcısı SACL belirtme. Bu parametre NULL olmamalı ve bir CSacl nesnesi olmalıdır. DACL farklı olarak, hiçbir arasında fark yoktur NULL ve boş bir SACL SACL nesneleri yalnızca bilgi Denetim erişim hakkı belirtmeyin gibi.  
  
 `bDefaulted`  
 SACL kaynağını belirten bir bayrak belirtir. Bu bayrak true ise, SACL bazı varsayılan mekanizması tarafından alınmış. Yanlışsa, bir kullanıcı tarafından SACL açıkça belirtilmiş. Yöntemi bu değer SE_SACL_DEFAULTED bayrağını depolar **SECURITY_DESCRIPTOR_CONTROL** yapısı. Bu parametre belirtilmezse, SE_SACL_DEFAULTED bayrağı temizlenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
##  <a name="tostring"></a>CSecurityDesc::ToString  
 Güvenlik tanımlayıcısı dizesi biçimine dönüştürür.  
  
```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pstr`  
 İşaretçi alacak null ile sonlandırılmış bir dizeye [dize biçimi güvenlik tanımlayıcısı](http://msdn.microsoft.com/library/windows/desktop/aa379570).  
  
 `si`  
 Çıkış dizesi eklemek için güvenlik tanımlayıcısı bileşenlerini göstermek için SECURITY_INFORMATION bit bayrakları bileşimini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Güvenlik tanımlayıcısı dize biçiminde eklendiğinde, yeniden daha kolay depolanan aktarılan veya bırakılabilir. Kullanım `CSecurityDesc::FromString` dize bir güvenlik açıklayıcısı dönüştürmek için yöntem.  
  
 `si` Parametresi, aşağıdaki SECURITY_INFORMATION bayraklar içerebilir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|OWNER_SECURITY_INFORMATION|Sahibi içerir.|  
|GROUP_SECURITY_INFORMATION|Birincil grup içerir.|  
|DACL_SECURITY_INFORMATION|DACL içerir.|  
|SACL_SECURITY_INFORMATION|SACL içerir.|  
  
 DACL NULL ve giriş güvenlik tanımlayıcısı SE_DACL_PRESENT denetim biti ayarlanmış yöntemi başarısız olur.  
  
 DACL NULL ise ve SE_DACL_PRESENT denetim bit giriş güvenlik tanımlayıcısı ayarlı değil, sonuçta ortaya çıkan güvenlik açıklayıcı dizesinin D: bileşen yok. Bkz: [güvenlik tanımlayıcısı dizesi biçimi](http://msdn.microsoft.com/library/windows/desktop/aa379570) daha fazla ayrıntı için.  
  
 Çağırır gibi bu yöntem yalnızca Windows 2000 ve daha sonra kullanılabilir [ConvertStringSecurityDescriptorToSecurityDescriptor](http://msdn.microsoft.com/library/windows/desktop/aa376401).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenliği örneği](../../visual-cpp-samples.md)   
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
