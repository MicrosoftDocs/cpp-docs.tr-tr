---
title: Güvenlik Genel Işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlsecurity/ATL::AtlGetDacl
- atlsecurity/ATL::AtlSetDacl
- atlsecurity/ATL::AtlGetGroupSid
- atlsecurity/ATL::AtlSetGroupSid
- atlsecurity/ATL::AtlGetOwnerSid
- atlsecurity/ATL::AtlSetOwnerSid
- atlsecurity/ATL::AtlGetSacl
- atlsecurity/ATL::AtlSetSacl
- atlsecurity/ATL::AtlGetSecurityDescriptor
helpviewer_keywords:
- SIDs [C++], modifying SID objects
- ACL object global functions
- security IDs [C++]
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
ms.openlocfilehash: 5f3c0464b239f4500d416b80ae4fdf06c2dc386f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495170"
---
# <a name="security-global-functions"></a>Güvenlik Genel Işlevleri

Bu işlevler, SID ve ACL nesnelerini değiştirmek için destek sağlar.

> [!IMPORTANT]
>  Aşağıdaki tabloda listelenen işlevler, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlGetDacl](#atlgetdacl)|Belirtilen bir nesnenin isteğe bağlı erişim denetimi listesini (DACL) almak için bu işlevi çağırın.|
|[AtlSetDacl](#atlsetdacl)|Belirtilen bir nesnenin isteğe bağlı erişim denetimi listesini (DACL) ayarlamak için bu işlevi çağırın.|
|[AtlGetGroupSid](#atlgetgroupsid)|Bir nesnenin grup güvenlik tanımlayıcısını (SID) almak için bu işlevi çağırın.|
|[Atlsetgroupsıd](#atlsetgroupsid)|Bir nesnenin grup güvenlik tanımlayıcısını (SID) ayarlamak için bu işlevi çağırın.|
|[AtlGetOwnerSid](#atlgetownersid)|Bir nesnenin sahip güvenlik tanımlayıcısını (SID) almak için bu işlevi çağırın.|
|[Atlsetownersıd](#atlsetownersid)|Bir nesnenin sahip güvenlik tanımlayıcısını (SID) ayarlamak için bu işlevi çağırın.|
|[AtlGetSacl](#atlgetsacl)|Belirtilen bir nesnenin sistem erişim denetimi listesini (SACL) almak için bu işlevi çağırın.|
|[AtlSetSacl](#atlsetsacl)|Belirtilen bir nesnenin sistem erişim denetimi listesini (SACL) ayarlamak için bu işlevi çağırın.|
|[AtlGetSecurityDescriptor](#atlgetsecuritydescriptor)|Verilen bir nesnenin güvenlik tanımlayıcısını almak için bu işlevi çağırın.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="atlgetdacl"></a>AtlGetDacl

Belirtilen bir nesnenin isteğe bağlı erişim denetimi listesini (DACL) almak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlGetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CDacl* pDacl) throw();
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerinin alınacağı nesnenin tanıtıcısı.

*Nesne*<br/>
[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmasından, *hObject* parametresi tarafından tanımlanan nesne türünü gösteren bir değer belirtir.

*pDacl*<br/>
Alınan güvenlik bilgilerini içeren bir DACL nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, *hObject* veya *pDacl* geçersizse bir onaylama hatası oluşur.

##  <a name="atlsetdacl"></a>AtlSetDacl

Belirtilen bir nesnenin isteğe bağlı erişim denetimi listesini (DACL) ayarlamak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlSetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CDacl& rDacl,
    DWORD dwInheritanceFlowControl = 0) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerinin ayarlanacağı nesneye yönelik işleyici.

*Nesne*<br/>
[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmasından, *hObject* parametresi tarafından tanımlanan nesne türünü gösteren bir değer belirtir.

*rDacl*<br/>
Yeni güvenlik bilgilerini içeren DACL.

*dwInheritanceFlowControl*<br/>
Devralma akışı denetimi. Bu değer 0 (varsayılan), PROTECTED_DACL_SECURITY_INFORMATION veya UNPROTECTED_DACL_SECURITY_INFORMATION olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, *hObject* geçersizse veya *Dwinheritanceflowcontrol* izin verilen üç değerden biri değilse bir onaylama hatası oluşur.
### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="atlgetgroupsid"></a>AtlGetGroupSid

Bir nesnenin grup güvenlik tanımlayıcısını (SID) almak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlGetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerinin alınacağı nesnenin tanıtıcısı.

*Nesne*<br/>
[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmasından, *hObject* parametresi tarafından tanımlanan nesne türünü gösteren bir değer belirtir.

*PSID*<br/>
Yeni güvenlik bilgilerini `CSid` içeren bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="atlsetgroupsid"></a>Atlsetgroupsıd

Bir nesnenin grup güvenlik tanımlayıcısını (SID) ayarlamak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlSetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerinin ayarlanacağı nesneye yönelik işleyici.

*Nesne*<br/>
[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmasından, *hObject* parametresi tarafından tanımlanan nesne türünü gösteren bir değer belirtir.

*Rsıd*<br/>
Yeni güvenlik bilgilerini içeren nesne.`CSid`

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="atlgetownersid"></a>AtlGetOwnerSid

Bir nesnenin sahip güvenlik tanımlayıcısını (SID) almak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlGetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerinin alınacağı nesnenin tanıtıcısı.

*Nesne*<br/>
[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmasından, *hObject* parametresi tarafından tanımlanan nesne türünü gösteren bir değer belirtir.

*PSID*<br/>
Yeni güvenlik bilgilerini `CSid` içeren bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="atlsetownersid"></a>Atlsetownersıd

Bir nesnenin sahip güvenlik tanımlayıcısını (SID) ayarlamak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlSetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerinin ayarlanacağı nesneye yönelik işleyici.

*Nesne*<br/>
[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmasından, *hObject* parametresi tarafından tanımlanan nesne türünü gösteren bir değer belirtir.

*Rsıd*<br/>
Yeni güvenlik bilgilerini içeren nesne.`CSid`

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="atlgetsacl"></a>AtlGetSacl

Belirtilen bir nesnenin sistem erişim denetimi listesini (SACL) almak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlGetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSacl* pSacl,
    bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerinin alınacağı nesnenin tanıtıcısı.

*Nesne*<br/>
[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmasından, *hObject* parametresi tarafından tanımlanan nesne türünü gösteren bir değer belirtir.

*pSacl*<br/>
Alınan güvenlik bilgilerini içeren bir SACL nesnesi işaretçisi.

*bRequestNeededPrivileges*<br/>
True ise, işlev SE_SECURITY_NAME ayrıcalığını etkinleştirmeye çalışır ve tamamlandığında geri yükler.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Birçok farklı nesnede çok sayıda çağrılacaksa, işlev çağrılmadan önce SE_SECURITY_NAME ayrıcalığının bir kez etkinleştirilmesi daha verimli olacaktır, *bRequestNeededPrivileges* yanlış olarak ayarlanır. `AtlGetSacl`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="atlsetsacl"></a>AtlSetSacl

Belirtilen bir nesnenin sistem erişim denetimi listesini (SACL) ayarlamak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlSetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSacl& rSacl,
    DWORD dwInheritanceFlowControl = 0,
    bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerinin ayarlanacağı nesneye yönelik işleyici.

*Nesne*<br/>
[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmasından, *hObject* parametresi tarafından tanımlanan nesne türünü gösteren bir değer belirtir.

*rSacl*<br/>
Yeni güvenlik bilgilerini içeren SACL.

*dwInheritanceFlowControl*<br/>
Devralma akışı denetimi. Bu değer 0 (varsayılan), PROTECTED_SACL_SECURITY_INFORMATION veya UNPROTECTED_SACL_SECURITY_INFORMATION olabilir.

*bRequestNeededPrivileges*<br/>
True ise, işlev SE_SECURITY_NAME ayrıcalığını etkinleştirmeye çalışır ve tamamlandığında geri yükler.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, *hObject* geçersizse veya *Dwinheritanceflowcontrol* izin verilen üç değerden biri değilse bir onaylama hatası oluşur.

Birçok farklı nesnede çok sayıda çağrılacaksa, işlev çağrılmadan önce SE_SECURITY_NAME ayrıcalığının bir kez etkinleştirilmesi daha verimli olacaktır, *bRequestNeededPrivileges* yanlış olarak ayarlanır. `AtlSetSacl`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

##  <a name="atlgetsecuritydescriptor"></a>AtlGetSecurityDescriptor

Verilen bir nesnenin güvenlik tanımlayıcısını almak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlGetSecurityDescriptor(
    LPCTSTR pszObjectName,
    SE_OBJECT_TYPE ObjectType,
    CSecurityDesc* pSecurityDescriptor,
    SECURITY_INFORMATION requestedInfo = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION,
bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*pszObjectName*<br/>
Güvenlik bilgilerinin alınacağı nesnenin adını belirten, null ile sonlandırılmış bir dize işaretçisi.

*Nesne*<br/>
[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmasından *pszObjectName* parametresi tarafından tanımlanan nesne türünü gösteren bir değer belirtir.

*pSecurityDescriptor*<br/>
İstenen güvenlik tanımlayıcısını alan nesne.

*Requesteınfo*<br/>
Alınacak güvenlik bilgilerinin türünü gösteren bir [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) bit bayrakları kümesi. Bu parametre aşağıdaki değerlerin bir birleşimi olabilir.

*bRequestNeededPrivileges*<br/>
True ise, işlev SE_SECURITY_NAME ayrıcalığını etkinleştirmeye çalışır ve tamamlandığında geri yükler.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Birçok farklı nesnede çok sayıda çağrılacaksa, işlev çağrılmadan önce SE_SECURITY_NAME ayrıcalığının bir kez etkinleştirilmesi daha verimli olacaktır, *bRequestNeededPrivileges* yanlış olarak ayarlanır. `AtlGetSecurityDescriptor`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
