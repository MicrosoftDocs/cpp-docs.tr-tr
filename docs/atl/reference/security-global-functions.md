---
title: Güvenlik genel işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- SIDs [C++], modifying SID objects
- ACL object global functions
- security IDs [C++]
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bbac8dc499c08d96abd33d49f5adec08095ca420
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067299"
---
# <a name="security-global-functions"></a>Güvenlik genel işlevleri

Bu işlevler, SID ve ACL nesneleri değiştirmek için destek sağlar.

> [!IMPORTANT]
>  Aşağıdaki tabloda listelenen İşlevler, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlGetDacl](#atlgetdacl)|Belirtilen bir nesnenin isteğe bağlı erişim denetimi listesini (DACL) almak için bu işlevi çağırın.|
|[AtlSetDacl](#atlsetdacl)|Belirtilen bir nesnenin isteğe bağlı erişim denetimi listesini (DACL) ayarlamak için bu işlevi çağırın.|
|[AtlGetGroupSid](#atlgetgroupsid)|Bir nesnenin grup güvenlik tanımlayıcısını (SID) almak için bu işlevi çağırın.|
|[AtlSetGroupSid](#atlsetgroupsid)|Bir nesnenin grup güvenlik tanımlayıcısını (SID) ayarlamak için bu işlevi çağırın.|
|[AtlGetOwnerSid](#atlgetownersid)|Bir nesnenin sahip güvenlik tanımlayıcısını (SID) almak için bu işlevi çağırın.|
|[AtlSetOwnerSid](#atlsetownersid)|Bir nesnenin sahip güvenlik tanımlayıcısını (SID) ayarlamak için bu işlevi çağırın.|
|[AtlGetSacl](#atlgetsacl)|Belirtilen bir nesnenin sistem erişim denetimi listesini (SACL) almak için bu işlevi çağırın.|
|[AtlSetSacl](#atlsetsacl)|Belirtilen bir nesnenin sistem erişim denetimi listesini (SACL) ayarlamak için bu işlevi çağırın.|
|[AtlGetSecurityDescriptor](#atlgetsecuritydescriptor)|Verilen bir nesnenin güvenlik tanımlayıcısını almak için bu işlevi çağırın.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="atlgetdacl"></a>  AtlGetDacl

Belirtilen bir nesnenin isteğe bağlı erişim denetimi listesini (DACL) almak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlGetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CDacl* pDacl) throw();
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerini almak istediğiniz nesneye işleyin.

*ObjectType*<br/>
Bir değer belirtir [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) tarafından tanımlanan nesne türünü gösteren sabit listesi *hObject* parametresi.

*pDacl*<br/>
Alınan güvenlik bilgilerini içeren bir DACL nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama derlemelerinde, ya da bir onaylama işlemi hatası meydana gelir *hObject* veya *pDacl* geçersiz.

##  <a name="atlsetdacl"></a>  AtlSetDacl

Belirtilen bir nesnenin isteğe bağlı erişim denetimi listesini (DACL) ayarlamak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlSetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CDacl& rDacl,
    DWORD dwInheritanceFlowControl = 0) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerini ayarlamak istediğiniz nesneye işleyin.

*ObjectType*<br/>
Bir değer belirtir [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) tarafından tanımlanan nesne türünü gösteren sabit listesi *hObject* parametresi.

*rDacl*<br/>
Yeni güvenlik bilgilerini içeren DACL.

*dwInheritanceFlowControl*<br/>
Devralma akış denetimi. Bu değer, 0 (varsayılan), PROTECTED_DACL_SECURITY_INFORMATION veya UNPROTECTED_DACL_SECURITY_INFORMATION olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *hObject* geçersiz veya *dwInheritanceFlowControl* üç izin verilen değerlerden biri değil.
### <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="atlgetgroupsid"></a>  AtlGetGroupSid

Bir nesnenin grup güvenlik tanımlayıcısını (SID) almak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlGetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgileri alınacağı nesneye işleyin.

*ObjectType*<br/>
Bir değer belirtir [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) tarafından tanımlanan nesne türünü gösteren sabit listesi *hObject* parametresi.

*Psıd*<br/>
İşaretçi bir `CSid` yeni güvenlik bilgilerini içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="atlsetgroupsid"></a>  AtlSetGroupSid

Bir nesnenin grup güvenlik tanımlayıcısını (SID) ayarlamak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlSetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerini ayarlamak istediğiniz nesneye işleyin.

*ObjectType*<br/>
Bir değer belirtir [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) tarafından tanımlanan nesne türünü gösteren sabit listesi *hObject* parametresi.

*rSid*<br/>
`CSid` Yeni güvenlik bilgilerini içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="atlgetownersid"></a>  AtlGetOwnerSid

Bir nesnenin sahip güvenlik tanımlayıcısını (SID) almak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlGetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgileri alınacağı nesneye işleyin.

*ObjectType*<br/>
Bir değer belirtir [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) tarafından tanımlanan nesne türünü gösteren sabit listesi *hObject* parametresi.

*Psıd*<br/>
İşaretçi bir `CSid` yeni güvenlik bilgilerini içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="atlsetownersid"></a>  AtlSetOwnerSid

Bir nesnenin sahip güvenlik tanımlayıcısını (SID) ayarlamak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlSetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerini ayarlamak istediğiniz nesneye işleyin.

*ObjectType*<br/>
Bir değer belirtir [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) tarafından tanımlanan nesne türünü gösteren sabit listesi *hObject* parametresi.

*rSid*<br/>
`CSid` Yeni güvenlik bilgilerini içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="atlgetsacl"></a>  AtlGetSacl

Belirtilen bir nesnenin sistem erişim denetimi listesini (SACL) almak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

```
inline bool AtlGetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSacl* pSacl,
    bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerini alınacağı nesneye işleyin.

*ObjectType*<br/>
Bir değer belirtir [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) tarafından tanımlanan nesne türünü gösteren sabit listesi *hObject* parametresi.

*pSacl*<br/>
Alınan güvenlik bilgilerini içeren bir SACL nesne işaretçisi.

*bRequestNeededPrivileges*<br/>
TRUE ise, işlev SE_SECURITY_NAME ayrıcalık etkinleştirmek ve tamamlanma geri dener.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Varsa `AtlGetSacl` birçok farklı nesneler üzerinde birden çok kez çağrılması için bir kez işlevi ile çağırmadan önce SE_SECURITY_NAME ayrıcalık etkinleştirmek için daha verimli olacaktır *bRequestNeededPrivileges* false olarak ayarlayın.

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="atlsetsacl"></a>  AtlSetSacl

Belirtilen bir nesnenin sistem erişim denetimi listesini (SACL) ayarlamak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

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
Güvenlik bilgilerini ayarlamak istediğiniz nesneye işleyin.

*ObjectType*<br/>
Bir değer belirtir [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) tarafından tanımlanan nesne türünü gösteren sabit listesi *hObject* parametresi.

*rSacl*<br/>
Yeni güvenlik bilgilerini içeren SACL.

*dwInheritanceFlowControl*<br/>
Devralma akış denetimi. Bu değer, 0 (varsayılan), PROTECTED_SACL_SECURITY_INFORMATION veya UNPROTECTED_SACL_SECURITY_INFORMATION olabilir.

*bRequestNeededPrivileges*<br/>
TRUE ise, işlev SE_SECURITY_NAME ayrıcalık etkinleştirmek ve tamamlanma geri dener.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *hObject* geçersiz veya *dwInheritanceFlowControl* üç izin verilen değerlerden biri değil.

Varsa `AtlSetSacl` birçok farklı nesneler üzerinde birden çok kez çağrılması için bir kez işlevi ile çağırmadan önce SE_SECURITY_NAME ayrıcalık etkinleştirmek için daha verimli olacaktır *bRequestNeededPrivileges* false olarak ayarlayın.

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="atlgetsecuritydescriptor"></a>  AtlGetSecurityDescriptor

Verilen bir nesnenin güvenlik tanımlayıcısını almak için bu işlevi çağırın.

> [!IMPORTANT]
>  Bu işlev, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

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
Güvenlik bilgileri alınacağı nesnesinin adını belirtir. null ile sonlandırılmış bir dize işaretçisi.

*ObjectType*<br/>
Bir değer belirtir [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) tarafından tanımlanan nesne türünü gösteren sabit listesi *pszObjectName* parametresi.

*pSecurityDescriptor*<br/>
İstenen güvenlik tanımlayıcısı alan nesne.

*requestedInfo*<br/>
Bir dizi [SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information) bit almak için güvenlik bilgi türünü belirten bayraklar. Bu parametre aşağıdaki değerleri birleşimi olabilir.

*bRequestNeededPrivileges*<br/>
TRUE ise, işlev SE_SECURITY_NAME ayrıcalık etkinleştirmek ve tamamlanma geri dener.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Varsa `AtlGetSecurityDescriptor` birçok farklı nesneler üzerinde birden çok kez çağrılması için bir kez işlevi ile çağırmadan önce SE_SECURITY_NAME ayrıcalık etkinleştirmek için daha verimli olacaktır *bRequestNeededPrivileges* false olarak ayarlayın.

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../../atl/reference/atl-functions.md)
