---
title: Kayıt Defteri ve TypeLib Global Fonksiyonlar
ms.date: 03/27/2019
f1_keywords:
- atlbase/ATL::AtlGetPerUserRegistration
- afxpriv/ATL::AfxRegCreateKey
- afxpriv/ATL::AfxRegDeleteKey
- atlbase/ATL::AtlRegisterTypeLib
- afxpriv/ATL::AfxRegOpenKey
- afxpriv/ATL::AfxRegOpenKeyEx
- afxdisp/ATL::AfxUnregisterPreviewHandler
- atlbase/ATL::AtlSetPerUserRegistration
- atlbase/ATL::AtlUnRegisterTypeLib
- atlbase/ATL::AtlLoadTypeLib
- atlbase/ATL::AtlUpdateRegistryFromResourceD
- atlbase/ATL::RegistryDataExchange
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
ms.openlocfilehash: 69df927ddd04c19d10703854aa8c8948894309d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326085"
---
# <a name="registry-and-typelib-global-functions"></a>Kayıt Defteri ve TypeLib Global Fonksiyonlar

Bu işlevler, bir tür kitaplığını yüklemek ve kaydetmek için destek sağlar.

> [!IMPORTANT]
> Aşağıdaki tablolarda listelenen işlevler Windows Runtime'da çalışan uygulamalarda kullanılamaz.

|||
|-|-|
|[AfxRegCreateKey](#afxregcreatekey)|Belirtilen kayıt defteri anahtarını oluşturur.|
|[AfxRegDeleteKey](#afxregdeletekey)|Belirtilen kayıt defteri anahtarını siler.|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|Önizleme işleyicisini kaydetmek için bir yardımcı.|
|[AfxUnregisterPreviewHandler](#afxunregisterpreviewhandler)| Önizleme işleyicisi kaydını çıkarmak için bir yardımcı. |
|[AtlRegisterTypeLib](#atlregistertypelib)|Tür kitaplığını kaydetmek için bu işlev çağrılır.|
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|Bu işlev, bir tür kitaplığı kaydını çıkarmak için çağrılır|
|[AfxRegOpenKey](#afxregopenkey)|Belirtilen kayıt defteri anahtarını açar.|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|Belirtilen kayıt defteri anahtarını açar.|
|[AtlLoadTypeLib](#atlloadtypelib)|Tür kitaplığını yüklemek için bu işlev çağrılır.|
|[AtlUpdateRegistryKaynakKaynak](#atlupdateregistryfromresourced)|Sağlanan kaynaktan kayıt defterini güncelleştirmek için bu işlev çağrılır.|
|[Kayıt DefteriDataExchange](#registrydataexchange)|Bu işlev, sistem kayıt defterinden okumak veya ona yazmak için kullanılır. [Kayıt Defteri Veri Alışverişi Makroları](../../atl/reference/registry-data-exchange-macros.md)tarafından çağrılır.|

Bu işlevler, programın bilgileri depolamak için kullandığı kayıt defterinde hangi düğümü denetler.

|||
|-|-|
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** **(HKCU)** düğümüne yönlendirip yönlendirmediğini alır.|
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** **(HKCU)** düğümüne yönlendirip yönlendirmediğini ayarlar.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="atlgetperuserregistration"></a><a name="atlgetperuserregistration"></a>AtlGetPerUserRegistration

Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** **(HKCU)** düğümüne yönlendirip yönlendirmediğini belirlemek için bu işlevi kullanın.

### <a name="syntax"></a>Sözdizimi

```
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);
```

### <a name="parameters"></a>Parametreler

*pEtkin*<br/>
[çıkış] TRUE, kayıt defteri bilgilerinin **HKCU** düğümüne yönlendirilmiş olduğunu gösterir; FALSE, uygulamanın kayıt defteri bilgilerini varsayılan düğüme yazdığını gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** **(HKCR)** idi.

### <a name="return-value"></a>Dönüş Değeri

S_OK yöntem başarılı olursa, aksi takdirde bir hata oluşursa HRESULT hata kodu.

### <a name="remarks"></a>Açıklamalar

Kayıt defteri yeniden yönlendirmesi varsayılan olarak etkinleştirilir. Bu seçeneği etkinleştiriseniz, kayıt defteri erişimi **HKEY_CURRENT_USER\Software\Classes'a**yönlendirilir.

Yeniden yönlendirme genel değildir. Bu kayıt defteri yeniden yönlendirmesi yalnızca MFC ve ATL çerçeveleri etkilenir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="afxregcreatekey"></a><a name="afxregcreatekey"></a>AfxRegCreateKey

Belirtilen kayıt defteri anahtarını oluşturur.

### <a name="syntax"></a>Sözdizimi

```
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*Hkey*<br/>
Açık bir kayıt defteri anahtarının tutamacı.

*lpSubKey*<br/>
Bu işlevin açtığı veya oluşturduğu anahtarın adı.

*phkResult*<br/>
Açılan veya oluşturulan anahtara tutamacı alan bir değişkenin işaretçisi.

*pTM*<br/>
Bir `CAtlTransactionManager` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, iade değeri ERROR_SUCCESS. İşlev başarısız olursa, iade değeri Winerror.h'de tanımlanan sıfır olmayan bir hata kodudur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpriv.h

## <a name="afxregdeletekey"></a><a name="afxregdeletekey"></a>AfxRegDeleteKey

Belirtilen kayıt defteri anahtarını siler.

### <a name="syntax"></a>Sözdizimi

```
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*Hkey*<br/>
Açık bir kayıt defteri anahtarının tutamacı.

*lpSubKey*<br/>
Silinecek anahtarın adı.

*pTM*<br/>
Bir `CAtlTransactionManager` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, iade değeri ERROR_SUCCESS. İşlev başarısız olursa, iade değeri Winerror.h'de tanımlanan sıfır olmayan bir hata kodudur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpriv.h

## <a name="afxregisterpreviewhandler"></a>

Önizleme işleyicisini kaydetmek için bir yardımcı.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);
```

### <a name="parameters"></a>Parametreler

*lpszCLSID*<br/>
Işleyicinin CLSID'sini belirtir.

*lpszShortTypeName*<br/>
Işleyicinin ProgID'ini belirtir.

*lpszFilterExt*<br/>
Bu işleyiciye kayıtlı dosya uzantısını belirtir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="atlregistertypelib"></a><a name="atlregistertypelib"></a>AtlRegisterTypeLib

Tür kitaplığını kaydetmek için bu işlev çağrılır.

```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Parametreler

*hInstTypeLib*<br/>
Modül örneğinin tutamacı.

*lpszIndex*<br/>
N türü kitaplık kaynağının insadin dizin olduğu\\"\N" biçiminde dize. Dizin gerekmiyorsa NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlevi [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) ve [CAtlComModule tarafından kullanılmaktadır::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="afxregopenkey"></a><a name="afxregopenkey"></a>AfxRegOpenKey

Belirtilen kayıt defteri anahtarını açar.

### <a name="syntax"></a>Sözdizimi

```
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*Hkey*<br/>
Açık bir kayıt defteri anahtarının tutamacı.

*lpSubKey*<br/>
Bu işlevin açtığı veya oluşturduğu anahtarın adı.

*phkResult*<br/>
Oluşturulan anahtara tutamacı alan bir değişkenin işaretçisi.

*pTM*<br/>
Bir `CAtlTransactionManager` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, iade değeri ERROR_SUCCESS. İşlev başarısız olursa, iade değeri Winerror.h'de tanımlanan sıfır olmayan bir hata kodudur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpriv.h

## <a name="afxregopenkeyex"></a><a name="afxregopenkeyex"></a>AfxRegOpenKeyEx

Belirtilen kayıt defteri anahtarını açar.

### <a name="syntax"></a>Sözdizimi

```
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*Hkey*<br/>
Açık bir kayıt defteri anahtarının tutamacı.

*lpSubKey*<br/>
Bu işlevin açtığı veya oluşturduğu anahtarın adı.

*ulOptions*<br/>
Bu parametre ayrılmıştır ve sıfır olmalıdır.

*samDesired*<br/>
Anahtarın istenen erişim haklarını belirten bir maske.

*phkResult*<br/>
Açılan anahtara tutamacı alan bir değişkenin işaretçisi.

*pTM*<br/>
Bir `CAtlTransactionManager` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, iade değeri ERROR_SUCCESS. İşlev başarısız olursa, iade değeri Winerror.h'de tanımlanan sıfır olmayan bir hata kodudur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpriv.h

## <a name="afxunregisterpreviewhandler"></a><a name="afxunregisterpreviewhandler"></a>AfxUnregisterPreviewHandler

Önizleme işleyicisi kaydını çıkarmak için bir yardımcı.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);
```

### <a name="parameters"></a>Parametreler

*lpszCLSID*<br/>
Işleyicinin CLSID'sinin kayıt dışı olmasını belirtir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="atlsetperuserregistration"></a><a name="atlsetperuserregistration"></a>AtlSetPerUserRegistration

Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** **(HKCU)** düğümüne yönlendirip yönlendirmediğini ayarlar.

### <a name="syntax"></a>Sözdizimi

```
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] TRUE, kayıt defteri bilgilerinin **HKCU** düğümüne yönlendirilmiş olduğunu gösterir; FALSE, uygulamanın kayıt defteri bilgilerini varsayılan düğüme yazdığını gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** **(HKCR)** idi.

### <a name="return-value"></a>Dönüş Değeri

S_OK yöntem başarılı olursa, aksi takdirde bir hata oluşursa HRESULT hata kodu.

### <a name="remarks"></a>Açıklamalar

Kayıt defteri yeniden yönlendirmesi varsayılan olarak etkinleştirilir. Bu seçeneği etkinleştiriseniz, kayıt defteri erişimi **HKEY_CURRENT_USER\Software\Classes'a**yönlendirilir.

Yeniden yönlendirme genel değildir. Bu kayıt defteri yeniden yönlendirmesi yalnızca MFC ve ATL çerçeveleri etkilenir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="atlunregistertypelib"></a><a name="atlunregistertypelib"></a>AtlUnRegisterTypeLib

Tür kitaplığının kaydını silmek için bu işlev çağrılır.

### <a name="syntax"></a>Sözdizimi

```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Parametreler

*hInstTypeLib*<br/>
Modül örneğinin tutamacı.

*lpszIndex*<br/>
N türü kitaplık kaynağının insadin dizin olduğu\\"\N" biçiminde dize. Dizin gerekmiyorsa NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlevi [CAtlComModule tarafından kullanılmaktadır::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) ve [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="atlloadtypelib"></a><a name="atlloadtypelib"></a>AtlLoadTypeLib

Tür kitaplığını yüklemek için bu işlev çağrılır.

### <a name="syntax"></a>Sözdizimi

```
ATLINLINE ATLAPI AtlLoadTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex,
    BSTR* pbstrPath,
    ITypeLib** ppTypeLib);
```

### <a name="parameters"></a>Parametreler

*hInstTypeLib*<br/>
Tür kitaplığıyla ilişkili modüle işle.

*lpszIndex*<br/>
N türü kitaplık kaynağının insadin dizin olduğu\\"\N" biçiminde dize. Dizin gerekmiyorsa NULL olabilir.

*pbstrPath*<br/>
Başarılı dönüşte, tür kitaplığıyla ilişkili modülün tam yolunu içerir.

*ppTypeLib*<br/>
Başarılı dönüşte, yüklenen tür kitaplığı için bir işaretçi içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlevi [AtlRegisterTypeLib](#atlregistertypelib) ve [AtlUnRegisterTypeLib](#atlunregistertypelib)tarafından kullanılmaktadır.

## <a name="atlupdateregistryfromresourced"></a><a name="atlupdateregistryfromresourced"></a>AtlUpdateRegistryKaynakKaynak

Bu işlev Visual Studio 2013'te iptal edildi ve Visual Studio 2015'te kaldırıldı.

```
<removed>
```

## <a name="registrydataexchange"></a><a name="registrydataexchange"></a>Kayıt DefteriDataExchange

Bu işlev, sistem kayıt defterinden okumak veya ona yazmak için kullanılır.

### <a name="syntax"></a>Sözdizimi

```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
Geçerli nesneye işaretçi.

*rdxOp*<br/>
İşlevin hangi işlemi gerçekleştirmesi gerektiğini gösteren bir enum değeri. İzin verilen değerler için Açıklamalar bölümündeki tabloya bakın.

*pItem*<br/>
Kayıt defterinden okunacak veya yazılacak verileri işaretle. Veriler, kayıt defterinden silinecek bir anahtarı da temsil edebilir. Varsayılan değer NULL'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Makrolar [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) ve [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) çağıran `RegistryDataExchange`bir işleve genişletin.

İşlevin gerçekleştirmesi gereken işlemi gösteren olası enum değerleri aşağıdaki tabloda gösterilmiştir:

|Enum değeri|İşlem|
|----------------|---------------|
|eReadFromReg|Kayıt defterindeki verileri okuyun.|
|eWriteToReg|Verileri kayıt defterine yazın.|
|eDeleteFromReg|Anahtarı kayıt defterinden silin.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](atl-functions.md)<br/>
[Kayıt Defteri Veri Değişim Makroları](registry-data-exchange-macros.md)
