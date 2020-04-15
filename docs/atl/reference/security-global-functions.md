---
title: Güvenlik Genel İşlevleri
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
ms.openlocfilehash: 682d44aa80f5d6de521223dfd67db2813cb6738c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326029"
---
# <a name="security-global-functions"></a>Güvenlik Genel İşlevleri

Bu işlevler SID ve ACL nesnelerini değiştirmek için destek sağlar.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlevler Windows Runtime'da çalışan uygulamalarda kullanılamaz.

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

**Üstbilgi:** atlsecurity.h

## <a name="atlgetdacl"></a><a name="atlgetdacl"></a>AtlGetDacl

Belirtilen bir nesnenin isteğe bağlı erişim denetimi listesini (DACL) almak için bu işlevi çağırın.

> [!IMPORTANT]
> Bu işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

```
inline bool AtlGetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CDacl* pDacl) throw();
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerini almak için nesneye işitin.

*Nesnetürü*<br/>
*hObject* parametresi tarafından tanımlanan nesne türünü gösteren [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmadan bir değer belirtir.

*pDacl*<br/>
Alınan güvenlik bilgilerini içeren bir DACL nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, *hObject* veya *pDacl* geçersizse bir tasnif hatası oluşur.

## <a name="atlsetdacl"></a><a name="atlsetdacl"></a>AtlSetDacl

Belirtilen bir nesnenin isteğe bağlı erişim denetimi listesini (DACL) ayarlamak için bu işlevi çağırın.

> [!IMPORTANT]
> Bu işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

```
inline bool AtlSetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CDacl& rDacl,
    DWORD dwInheritanceFlowControl = 0) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerini ayarlamak için nesneye işitin.

*Nesnetürü*<br/>
*hObject* parametresi tarafından tanımlanan nesne türünü gösteren [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmadan bir değer belirtir.

*rDacl*<br/>
Yeni güvenlik bilgilerini içeren DACL.

*dwInheritanceFlowControl*<br/>
Kalıtım akışı kontrolü. Bu değer 0 (varsayılan), PROTECTED_DACL_SECURITY_INFORMATION veya UNPROTECTED_DACL_SECURITY_INFORMATION olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, *hObject* geçersizse veya *dwInheritanceFlowControl* izin verilen üç değerden biri değilse bir tasnif hatası oluşur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="atlgetgroupsid"></a><a name="atlgetgroupsid"></a>AtlGetGroupSid

Bir nesnenin grup güvenlik tanımlayıcısını (SID) almak için bu işlevi çağırın.

> [!IMPORTANT]
> Bu işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

```
inline bool AtlGetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerini almak için nesneye işle.

*Nesnetürü*<br/>
*hObject* parametresi tarafından tanımlanan nesne türünü gösteren [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmadan bir değer belirtir.

*pSid*<br/>
Yeni güvenlik `CSid` bilgilerini içeren bir nesneyi işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="atlsetgroupsid"></a><a name="atlsetgroupsid"></a>AtlSetGroupSid

Bir nesnenin grup güvenlik tanımlayıcısını (SID) ayarlamak için bu işlevi çağırın.

> [!IMPORTANT]
> Bu işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

```
inline bool AtlSetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerini ayarlamak için nesneye işitin.

*Nesnetürü*<br/>
*hObject* parametresi tarafından tanımlanan nesne türünü gösteren [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmadan bir değer belirtir.

*rSid*<br/>
Yeni `CSid` güvenlik bilgilerini içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="atlgetownersid"></a><a name="atlgetownersid"></a>AtlGetOwnerSid

Bir nesnenin sahip güvenlik tanımlayıcısını (SID) almak için bu işlevi çağırın.

> [!IMPORTANT]
> Bu işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

```
inline bool AtlGetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerini almak için nesneye işle.

*Nesnetürü*<br/>
*hObject* parametresi tarafından tanımlanan nesne türünü gösteren [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmadan bir değer belirtir.

*pSid*<br/>
Yeni güvenlik `CSid` bilgilerini içeren bir nesneyi işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="atlsetownersid"></a><a name="atlsetownersid"></a>AtlSetOwnerSid

Bir nesnenin sahip güvenlik tanımlayıcısını (SID) ayarlamak için bu işlevi çağırın.

> [!IMPORTANT]
> Bu işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

```
inline bool AtlSetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerini ayarlamak için nesneye işitin.

*Nesnetürü*<br/>
*hObject* parametresi tarafından tanımlanan nesne türünü gösteren [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmadan bir değer belirtir.

*rSid*<br/>
Yeni `CSid` güvenlik bilgilerini içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="atlgetsacl"></a><a name="atlgetsacl"></a>AtlGetSacl

Belirtilen bir nesnenin sistem erişim denetimi listesini (SACL) almak için bu işlevi çağırın.

> [!IMPORTANT]
> Bu işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

```
inline bool AtlGetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSacl* pSacl,
    bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>Parametreler

*hObject*<br/>
Güvenlik bilgilerini almak için nesneye işitin.

*Nesnetürü*<br/>
*hObject* parametresi tarafından tanımlanan nesne türünü gösteren [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmadan bir değer belirtir.

*pSacl*<br/>
Alınan güvenlik bilgilerini içeren bir SACL nesnesine işaretçi.

*bRequestNeededAyrıcalıklar*<br/>
Doğruysa, işlev SE_SECURITY_NAME ayrıcalığını etkinleştirmeye ve tamamlandığında geri yüklemeye çalışır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

`AtlGetSacl` Birçok farklı nesne üzerinde birçok kez çağrılacaksa, *bRequestNeededPrivileges* yanlış olarak ayarlanmış olan işlevi aramadan önce SE_SECURITY_NAME ayrıcalığını bir kez etkinleştirmek daha verimli olacaktır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="atlsetsacl"></a><a name="atlsetsacl"></a>AtlSetSacl

Belirtilen bir nesnenin sistem erişim denetimi listesini (SACL) ayarlamak için bu işlevi çağırın.

> [!IMPORTANT]
> Bu işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

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
Güvenlik bilgilerini ayarlamak için nesneye işitin.

*Nesnetürü*<br/>
*hObject* parametresi tarafından tanımlanan nesne türünü gösteren [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmadan bir değer belirtir.

*rSacl*<br/>
Yeni güvenlik bilgilerini içeren SACL.

*dwInheritanceFlowControl*<br/>
Kalıtım akışı kontrolü. Bu değer 0 (varsayılan), PROTECTED_SACL_SECURITY_INFORMATION veya UNPROTECTED_SACL_SECURITY_INFORMATION olabilir.

*bRequestNeededAyrıcalıklar*<br/>
Doğruysa, işlev SE_SECURITY_NAME ayrıcalığını etkinleştirmeye ve tamamlandığında geri yüklemeye çalışır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, *hObject* geçersizse veya *dwInheritanceFlowControl* izin verilen üç değerden biri değilse bir tasnif hatası oluşur.

`AtlSetSacl` Birçok farklı nesne üzerinde birçok kez çağrılacaksa, *bRequestNeededPrivileges* yanlış olarak ayarlanmış olan işlevi aramadan önce SE_SECURITY_NAME ayrıcalığını bir kez etkinleştirmek daha verimli olacaktır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="atlgetsecuritydescriptor"></a><a name="atlgetsecuritydescriptor"></a>AtlGetSecurityDescriptor

Verilen bir nesnenin güvenlik tanımlayıcısını almak için bu işlevi çağırın.

> [!IMPORTANT]
> Bu işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

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
Güvenlik bilgilerini almak için nesnenin adını belirten geçersiz sonlandırılmış bir dize işaretçi.

*Nesnetürü*<br/>
*pszObjectName* parametresi tarafından tanımlanan nesnetürünü gösteren [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) numaralandırmadan bir değer belirtir.

*pSecurityDescriptor*<br/>
İstenen güvenlik tanımlayıcısını alan nesne.

*istenenInfo*<br/>
Alınacak güvenlik bilgisi türünü gösteren [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) bit bayrakları kümesi. Bu parametre aşağıdaki değerlerin bir leşimi olabilir.

*bRequestNeededAyrıcalıklar*<br/>
Doğruysa, işlev SE_SECURITY_NAME ayrıcalığını etkinleştirmeye ve tamamlandığında geri yüklemeye çalışır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olma durumunda true, aksi durumda false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

`AtlGetSecurityDescriptor` Birçok farklı nesne üzerinde birçok kez çağrılacaksa, *bRequestNeededPrivileges* yanlış olarak ayarlanmış olan işlevi aramadan önce SE_SECURITY_NAME ayrıcalığını bir kez etkinleştirmek daha verimli olacaktır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
