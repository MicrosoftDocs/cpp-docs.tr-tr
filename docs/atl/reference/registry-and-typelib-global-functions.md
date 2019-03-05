---
title: Kayıt defteri ve TypeLib genel işlevleri
ms.date: 11/04/2016
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
ms.openlocfilehash: f94dd1770ff194e47e2e38cc3a9b5cf0cbaebe58
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301837"
---
# <a name="registry-and-typelib-global-functions"></a>Kayıt defteri ve TypeLib genel işlevleri

Bu işlevler, yükleme ve bir tür kitaplığı kaydı desteği.

> [!IMPORTANT]
>  Aşağıdaki tablolarda listelenen İşlevler, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

|||
|-|-|
|[AfxRegCreateKey](#afxrefcreatekey)|Belirtilen kayıt defteri anahtarı oluşturur.|
|[AfxRegDeleteKey](#afxrefdeletekey)|Belirtilen kayıt defteri anahtarını siler.|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|Önizleme işleyicisi kaydetmek için yardımcıyı.|
|[AfxUnregisterPreviewHandler](#afxunregisterpreviewhandler)| Bir önizleme işleyici kaydı Yardımcısı. |
|[AtlRegisterTypeLib](#atlregistertypelib)|Tür kitaplığını kaydetmek için bu işlev çağrılır.|
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|Bir tür kitaplığının kaydını silmek için bu işlev çağrılır|
|[AfxRegOpenKey](#afxregopenkey)|Belirtilen kayıt defteri anahtarı'nı açar.|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|Belirtilen kayıt defteri anahtarı'nı açar.|
|[AtlLoadTypeLib](#atlloadtypelib)|Tür kitaplığını yüklemek için bu işlev çağrılır.|
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|Sağlanan kaynaktan kayıt defterini güncelleştirmek için bu işlev çağrılır.|
|[RegistryDataExchange](#registrydataexchange)|Bu işlev, sistem kayıt defterinden okumak veya ona yazmak için kullanılır. Çağıran [kayıt defteri veri değişimi makroları](../../atl/reference/registry-data-exchange-macros.md).|

Bu işlevler, hangi düğümün program bilgileri depolamak için kullandığı kayıt defterinde denetler.

|||
|-|-|
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|Uygulama kayıt defteri erişimini yönlendiren olup olmadığını alır **HKEY_CURRENT_USER** ( **HKCU**) düğüm.|
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|Uygulama kayıt defteri erişimini yönlendiren olup olmadığını ayarlar **HKEY_CURRENT_USER** ( **HKCU**) düğüm.|

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

## <a name="atlgetperuserregistration"></a> AtlGetPerUserRegistration

Uygulama kayıt defteri erişimini yönlendiren olup olmadığını belirlemek için bu işlevi kullanın **HKEY_CURRENT_USER** (**HKCU**) düğüm.

### <a name="syntax"></a>Sözdizimi

```
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);
```

### <a name="parameters"></a>Parametreler

*pEnabled*<br/>
[out] TRUE, kayıt defteri bilgilerini Yönlendirilme biçimini gösterir **HKCU** düğüm; FALSE, uygulama varsayılan düğüme kayıt defteri bilgilerini yazar gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılıysa S_OK, aksi takdirde HRESULT hata kodu bir hata oluşursa.

### <a name="remarks"></a>Açıklamalar

Kayıt defteri yeniden yönlendirme varsayılan olarak etkin değildir. Bu seçeneği etkinleştirirseniz, kayıt defteri erişimini yönlendireceği **HKEY_CURRENT_USER\Software\Classes**.

Yeniden yönlendirme genel değil. Yalnızca MFC ve ATL çerçeveleri, bu kayıt defteri yeniden yönlendirmeyi tarafından etkilenir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

## <a name="afxregcreatekey"></a> AfxRegCreateKey

Belirtilen kayıt defteri anahtarı oluşturur.

### <a name="syntax"></a>Sözdizimi

```
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*hKey*<br/>
Bir kayıt defteri anahtarı için bir tanıtıcı.

*lpSubKey*<br/>
Bu işlev açar veya oluşturur bir anahtarın adı.

*phkResult*<br/>
Açılan veya oluşturulan anahtarı için bir tanıtıcı alan bir değişken için bir işaretçi.

*pTM*<br/>
İşaretçi bir `CAtlTransactionManager` nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürülen değer ERROR_SUCCESS olur. İşlev başarısız olursa, döndürülen değer wınerror içinde tanımlanan bir sıfır olmayan hata kodudur.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxpriv.h

## <a name="afxregdeletekey"></a> AfxRegDeleteKey

Belirtilen kayıt defteri anahtarını siler.

### <a name="syntax"></a>Sözdizimi

```
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*hKey*<br/>
Bir kayıt defteri anahtarı için bir tanıtıcı.

*lpSubKey*<br/>
Silinecek anahtar adı.

*pTM*<br/>
İşaretçi bir `CAtlTransactionManager` nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürülen değer ERROR_SUCCESS olur. İşlev başarısız olursa, döndürülen değer wınerror içinde tanımlanan bir sıfır olmayan hata kodudur.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxpriv.h

## <a name="afxregisterpreviewhandler"></a>

Önizleme işleyicisi kaydetmek için yardımcıyı.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);
```

### <a name="parameters"></a>Parametreler

*lpszCLSID*<br/>
İşleyici CLSID değeri belirtir.

*lpszShortTypeName*<br/>
ProgID işleyicisinin belirtir.

*lpszFilterExt*<br/>
Dosya uzantısı ile bu işleyici kayıtlı belirtir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

##  <a name="atlregistertypelib"></a>  AtlRegisterTypeLib

Tür kitaplığını kaydetmek için bu işlev çağrılır.

```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Parametreler

*hInstTypeLib*<br/>
Modül örneğinin tanıtıcısını.

*lpszIndex*<br/>
Biçim dizesinde "\\\N", burada N tamsayı tür kitaplığı kaynağı dizinidir. Hiçbir dizin gerekiyorsa NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlevi tarafından kullanılan [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) ve [CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib).

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

## <a name="afxregopenkey"></a> AfxRegOpenKey

Belirtilen kayıt defteri anahtarı'nı açar.

### <a name="syntax"></a>Sözdizimi

```
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*hKey*<br/>
Bir kayıt defteri anahtarı için bir tanıtıcı.

*lpSubKey*<br/>
Bu işlev açar veya oluşturur bir anahtarın adı.

*phkResult*<br/>
Oluşturulan anahtarı için bir tanıtıcı alan bir değişken için bir işaretçi.

*pTM*<br/>
İşaretçi bir `CAtlTransactionManager` nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürülen değer ERROR_SUCCESS olur. İşlev başarısız olursa, döndürülen değer wınerror içinde tanımlanan bir sıfır olmayan hata kodudur.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxpriv.h

## <a name="afxregopenkeyex"></a>  AfxRegOpenKeyEx

Belirtilen kayıt defteri anahtarı'nı açar.

### <a name="syntax"></a>Sözdizimi

```
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*hKey*<br/>
Bir kayıt defteri anahtarı için bir tanıtıcı.

*lpSubKey*<br/>
Bu işlev açar veya oluşturur bir anahtarın adı.

*ulOptions*<br/>
Bu parametre ayrılmıştır ve sıfır olmalıdır.

*samDesired*<br/>
İstenen erişim hakları anahtarına belirtir maskesi.

*phkResult*<br/>
Açılan anahtarı için bir tanıtıcı alan bir değişken için bir işaretçi.

*pTM*<br/>
İşaretçi bir `CAtlTransactionManager` nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürülen değer ERROR_SUCCESS olur. İşlev başarısız olursa, döndürülen değer wınerror içinde tanımlanan bir sıfır olmayan hata kodudur.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxpriv.h

## <a name="afxunregisterpreviewhandler"></a> AfxUnregisterPreviewHandler

Bir önizleme işleyici kaydı Yardımcısı.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);
```

### <a name="parameters"></a>Parametreler

*lpszCLSID*<br/>
Sona erdirilecek CLSID işleyicisinin belirtir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="atlsetperuserregistration"></a> AtlSetPerUserRegistration

Uygulama kayıt defteri erişimini yönlendiren olup olmadığını ayarlar **HKEY_CURRENT_USER** (**HKCU**) düğüm.

### <a name="syntax"></a>Sözdizimi

```
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] TRUE, kayıt defteri bilgilerini Yönlendirilme biçimini gösterir **HKCU** düğüm; FALSE, uygulama varsayılan düğüme kayıt defteri bilgilerini yazar gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılıysa S_OK, aksi takdirde HRESULT hata kodu bir hata oluşursa.

### <a name="remarks"></a>Açıklamalar

Kayıt defteri yeniden yönlendirme varsayılan olarak etkin değildir. Bu seçeneği etkinleştirirseniz, kayıt defteri erişimini yönlendireceği **HKEY_CURRENT_USER\Software\Classes**.

Yeniden yönlendirme genel değil. Yalnızca MFC ve ATL çerçeveleri, bu kayıt defteri yeniden yönlendirmeyi tarafından etkilenir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="atlunregistertypelib"></a>  AtlUnRegisterTypeLib

Tür kitaplığının kaydını silmek için bu işlev çağrılır.

### <a name="syntax"></a>Sözdizimi

```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Parametreler

*hInstTypeLib*<br/>
Modül örneğinin tanıtıcısını.

*lpszIndex*<br/>
Biçim dizesinde "\\\N", burada N tamsayı tür kitaplığı kaynağı dizinidir. Hiçbir dizin gerekiyorsa NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlevi tarafından kullanılan [CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) ve [AtlComModuleUnregisterServer](#atlcommoduleunregisterserver).

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="atlloadtypelib"></a>  AtlLoadTypeLib

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
Tür kitaplığı ile ilişkili modülü için işleyin.

*lpszIndex*<br/>
Biçim dizesinde "\\\N", burada N tamsayı tür kitaplığı kaynağı dizinidir. Hiçbir dizin gerekiyorsa NULL olabilir.

*pbstrPath*<br/>
Başarılı getirisini tür kitaplığı ile ilişkili modülü tam yolunu içerir.

*ppTypeLib*<br/>
Başarılı geri yüklenen bir tür kitaplığı için bir işaretçi işaretçisi içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlevi tarafından kullanılan [AtlRegisterTypeLib](#atlregistertypelib) ve [AtlUnRegisterTypeLib](#atlunregistertypelib).

##  <a name="atlupdateregistryfromresourced"></a>  AtlUpdateRegistryFromResourceD

Bu işlev, Visual Studio 2013'te kullanım dışı bırakıldı ve Visual Studio 2015'te kaldırılır.

```
<removed>
```

##  <a name="registrydataexchange"></a>  RegistryDataExchange

Bu işlev, sistem kayıt defterinden okumak veya ona yazmak için kullanılır.

### <a name="syntax"></a>Sözdizimi

```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
Geçerli nesneye bir işaretçi.

*rdxOp*<br/>
İşlev işlemi gösteren bir sabit listesi değeri gerçekleştirmeniz gerekir. İzin verilen değerler için Açıklamalar bölümü içindeki tabloya bakın.

*pItem*<br/>
Okuma veya kayıt defterine, yazılan veri işaretçisi. Verileri ayrıca bir anahtarı kayıt defterinden silinecek temsil edebilir. Varsayılan değer NULL olur.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Makroları [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) ve [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) çağırdığı bir işleve genişletin `RegistryDataExchange`.

İşlev işlemi gerçekleştirmeniz gerekir gösteren olası sabit listesi değerleri aşağıdaki tabloda gösterilmiştir:

|Sabit listesi değeri|Çalışma|
|----------------|---------------|
|eReadFromReg|Kayıt defterinden veri okuma.|
|eWriteToReg|Kayıt defterine veri yazma.|
|eDeleteFromReg|Kayıt anahtarını kayıt defterinden silin.|

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](atl-functions.md)<br/>
[Kayıt Defteri Veri Değişim Makroları](registry-data-exchange-macros.md)
