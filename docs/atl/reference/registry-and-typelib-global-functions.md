---
title: Kayıt defteri ve TypeLib genel Işlevleri
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
ms.openlocfilehash: 0f29f8cac62a7452781e8fde697cdf992db00b8c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834624"
---
# <a name="registry-and-typelib-global-functions"></a>Kayıt defteri ve TypeLib genel Işlevleri

Bu işlevler, bir tür kitaplığının yüklenmesi ve kaydedilmesi için destek sağlar.

> [!IMPORTANT]
> Aşağıdaki tablolarda listelenen işlevler, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

|Ad|Açıklama|
|-|-|
|[AfxRegCreateKey](#afxregcreatekey)|Belirtilen kayıt defteri anahtarını oluşturur.|
|[AfxRegDeleteKey](#afxregdeletekey)|Belirtilen kayıt defteri anahtarını siler.|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|Önizleme işleyicisini kaydetme Yardımcısı.|
|[AfxUnregisterPreviewHandler](#afxunregisterpreviewhandler)| Önizleme işleyicisinin kaydını silme Yardımcısı. |
|[AtlRegisterTypeLib](#atlregistertypelib)|Tür kitaplığını kaydetmek için bu işlev çağrılır.|
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|Bu işlev, bir tür kitaplığının kaydını silmek için çağırılır|
|[AfxRegOpenKey](#afxregopenkey)|Belirtilen kayıt defteri anahtarını açar.|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|Belirtilen kayıt defteri anahtarını açar.|
|[AtlLoadTypeLib](#atlloadtypelib)|Tür kitaplığını yüklemek için bu işlev çağrılır.|
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|Sağlanan kaynaktan kayıt defterini güncelleştirmek için bu işlev çağrılır.|
|[RegistryDataExchange](#registrydataexchange)|Bu işlev, sistem kayıt defterinden okumak veya ona yazmak için kullanılır. [Kayıt defteri verileri Exchange makroları](../../atl/reference/registry-data-exchange-macros.md)tarafından çağırılır.|

Bu işlevler, programın bilgileri depolamak için kullandığı kayıt defterindeki hangi düğümde olduğunu denetler.

|Ad|Açıklama|
|-|-|
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** ( **HKCU**) düğümüne yeniden yönlendirip yönlendirmeyeceğini alır.|
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** ( **HKCU**) düğümüne yeniden yönlendirip yönlendirmeyeceğini ayarlar.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="atlgetperuserregistration"></a><a name="atlgetperuserregistration"></a> AtlGetPerUserRegistration

Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** (**HKCU**) düğümüne yeniden yönlendirip yönlendirmediğini öğrenmek için bu işlevi kullanın.

### <a name="syntax"></a>Söz dizimi

```
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);
```

### <a name="parameters"></a>Parametreler

*pEnabled*<br/>
dışı DOĞRU, kayıt defteri bilgilerinin **HKCU** düğümüne yönlendirildiğini gösterir; FALSE, uygulamanın kayıt defteri bilgilerini varsayılan düğüme yazdığını gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK, aksi takdirde HRESULT hata kodu bir hata oluşur.

### <a name="remarks"></a>Açıklamalar

Kayıt defteri yönlendirmesi varsayılan olarak etkin değildir. Bu seçeneği etkinleştirirseniz, kayıt defteri erişimi **HKEY_CURRENT_USER \Software\Classes**'a yönlendirilir.

Yeniden yönlendirme genel değildir. Yalnızca MFC ve ATL çerçeveleri bu kayıt defteri yeniden yönlendirmesinin etkilenmiştir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="afxregcreatekey"></a><a name="afxregcreatekey"></a> AfxRegCreateKey

Belirtilen kayıt defteri anahtarını oluşturur.

### <a name="syntax"></a>Söz dizimi

```
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*hKey*<br/>
Açık bir kayıt defteri anahtarına yönelik bir tanıtıcı.

*Lpaltanahtar*<br/>
Bu işlevin açtığı veya oluşturduğu bir anahtarın adı.

*phkResult*<br/>
Açık veya oluşturulmuş anahtara bir tanıtıcı alan bir değişkene yönelik işaretçi.

*pTM*<br/>
Bir nesne işaretçisi `CAtlTransactionManager` .

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS. İşlev başarısız olursa, dönüş değeri, Winerror. h içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** AFXPRIV. h

## <a name="afxregdeletekey"></a><a name="afxregdeletekey"></a> AfxRegDeleteKey

Belirtilen kayıt defteri anahtarını siler.

### <a name="syntax"></a>Söz dizimi

```
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*hKey*<br/>
Açık bir kayıt defteri anahtarına yönelik bir tanıtıcı.

*Lpaltanahtar*<br/>
Silinecek anahtarın adı.

*pTM*<br/>
Bir nesne işaretçisi `CAtlTransactionManager` .

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS. İşlev başarısız olursa, dönüş değeri, Winerror. h içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** AFXPRIV. h

## <a name="afxregisterpreviewhandler"></a>

Önizleme işleyicisini kaydetme Yardımcısı.

### <a name="syntax"></a>Söz dizimi

```
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);
```

### <a name="parameters"></a>Parametreler

*lpszCLSID*<br/>
İşleyicinin CLSID değerini belirtir.

*lpszShortTypeName*<br/>
İşleyicinin ProgID 'sini belirtir.

*lpszFilterExt*<br/>
Bu işleyicide kayıtlı dosya uzantısını belirtir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="atlregistertypelib"></a><a name="atlregistertypelib"></a> AtlRegisterTypeLib

Tür kitaplığını kaydetmek için bu işlev çağrılır.

```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Parametreler

*Hınsttypelib*<br/>
Modül örneği için tanıtıcı.

*lpszIndex*<br/>
"\N" biçiminde dize \\ , burada N, tür kitaplığı kaynağının tamsayı dizinidir. Dizin gerekmiyorsa NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlev [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) ve [CAtlComModule:: RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib)tarafından kullanılır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="afxregopenkey"></a><a name="afxregopenkey"></a> AfxRegOpenKey

Belirtilen kayıt defteri anahtarını açar.

### <a name="syntax"></a>Söz dizimi

```
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*hKey*<br/>
Açık bir kayıt defteri anahtarına yönelik bir tanıtıcı.

*Lpaltanahtar*<br/>
Bu işlevin açtığı veya oluşturduğu bir anahtarın adı.

*phkResult*<br/>
Oluşturulan anahtara bir tanıtıcı alan bir değişken işaretçisi.

*pTM*<br/>
Bir nesne işaretçisi `CAtlTransactionManager` .

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS. İşlev başarısız olursa, dönüş değeri, Winerror. h içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** AFXPRIV. h

## <a name="afxregopenkeyex"></a><a name="afxregopenkeyex"></a> AfxRegOpenKeyEx

Belirtilen kayıt defteri anahtarını açar.

### <a name="syntax"></a>Söz dizimi

```
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*hKey*<br/>
Açık bir kayıt defteri anahtarına yönelik bir tanıtıcı.

*Lpaltanahtar*<br/>
Bu işlevin açtığı veya oluşturduğu bir anahtarın adı.

*ulOptions*<br/>
Bu parametre ayrılmıştır ve sıfır olmalıdır.

*samDesired*<br/>
Anahtara istenen erişim haklarını belirten bir maske.

*phkResult*<br/>
Açık anahtara bir tanıtıcı alan bir değişken işaretçisi.

*pTM*<br/>
Bir nesne işaretçisi `CAtlTransactionManager` .

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS. İşlev başarısız olursa, dönüş değeri, Winerror. h içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** AFXPRIV. h

## <a name="afxunregisterpreviewhandler"></a><a name="afxunregisterpreviewhandler"></a> AfxUnregisterPreviewHandler

Önizleme işleyicisinin kaydını silme Yardımcısı.

### <a name="syntax"></a>Söz dizimi

```
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);
```

### <a name="parameters"></a>Parametreler

*lpszCLSID*<br/>
Kaydı Kaldırılacak işleyicinin CLSID değerini belirtir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="atlsetperuserregistration"></a><a name="atlsetperuserregistration"></a> AtlSetPerUserRegistration

Uygulamanın kayıt defteri erişimini **HKEY_CURRENT_USER** (**HKCU**) düğümüne yeniden yönlendirip yönlendirmeyeceğini ayarlar.

### <a name="syntax"></a>Söz dizimi

```
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki DOĞRU, kayıt defteri bilgilerinin **HKCU** düğümüne yönlendirildiğini gösterir; FALSE, uygulamanın kayıt defteri bilgilerini varsayılan düğüme yazdığını gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** (**HKCR**).

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK, aksi takdirde HRESULT hata kodu bir hata oluşur.

### <a name="remarks"></a>Açıklamalar

Kayıt defteri yönlendirmesi varsayılan olarak etkin değildir. Bu seçeneği etkinleştirirseniz, kayıt defteri erişimi **HKEY_CURRENT_USER \Software\Classes**'a yönlendirilir.

Yeniden yönlendirme genel değildir. Yalnızca MFC ve ATL çerçeveleri bu kayıt defteri yeniden yönlendirmesinin etkilenmiştir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="atlunregistertypelib"></a><a name="atlunregistertypelib"></a> AtlUnRegisterTypeLib

Tür kitaplığının kaydını silmek için bu işlev çağrılır.

### <a name="syntax"></a>Söz dizimi

```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>Parametreler

*Hınsttypelib*<br/>
Modül örneği için tanıtıcı.

*lpszIndex*<br/>
"\N" biçiminde dize \\ , burada N, tür kitaplığı kaynağının tamsayı dizinidir. Dizin gerekmiyorsa NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlevi [CAtlComModule:: UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) ve [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver)tarafından kullanılır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="atlloadtypelib"></a><a name="atlloadtypelib"></a> AtlLoadTypeLib

Tür kitaplığını yüklemek için bu işlev çağrılır.

### <a name="syntax"></a>Söz dizimi

```
ATLINLINE ATLAPI AtlLoadTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex,
    BSTR* pbstrPath,
    ITypeLib** ppTypeLib);
```

### <a name="parameters"></a>Parametreler

*Hınsttypelib*<br/>
Tür kitaplığıyla ilişkili modülün tanıtıcısı.

*lpszIndex*<br/>
"\N" biçiminde dize \\ , burada N, tür kitaplığı kaynağının tamsayı dizinidir. Dizin gerekmiyorsa NULL olabilir.

*pbstrPath*<br/>
Başarılı bir dönüşte, tür kitaplığıyla ilişkili modülün tam yolunu içerir.

*ppTypeLib*<br/>
Başarılı dönüşte, yüklenen tür kitaplığının işaretçisi için bir işaretçi içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yardımcı işlevi, [AtlRegisterTypeLib](#atlregistertypelib) ve [AtlUnRegisterTypeLib](#atlunregistertypelib)tarafından kullanılır.

## <a name="atlupdateregistryfromresourced"></a><a name="atlupdateregistryfromresourced"></a> AtlUpdateRegistryFromResourceD

Bu işlev Visual Studio 2013 kullanımdan kaldırılmıştır ve Visual Studio 2015 ' de kaldırılır.

```
<removed>
```

## <a name="registrydataexchange"></a><a name="registrydataexchange"></a> RegistryDataExchange

Bu işlev, sistem kayıt defterinden okumak veya ona yazmak için kullanılır.

### <a name="syntax"></a>Söz dizimi

```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```

### <a name="parameters"></a>Parametreler

*Yönergelerinin*<br/>
Geçerli nesneye yönelik bir işaretçi.

*rdxOp*<br/>
İşlevin hangi işlemi gerçekleştireceğini belirten Enum değeri. İzin verilen değerler için açıklamalar bölümündeki tabloya bakın.

*pItem*<br/>
Kayıt defterinden okunacak veya üzerine yazılacak verilere yönelik işaretçi. Veriler, kayıt defterinden silinecek bir anahtarı da temsil edebilir. Varsayılan değer NULL.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Makrolar [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) ve [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) çağıran bir işleve genişletilir `RegistryDataExchange` .

İşlevin gerçekleştirmesi gereken işlemi belirten olası Enum değerleri aşağıdaki tabloda gösterilmiştir:

|Sabit listesi değeri|İşlem|
|----------------|---------------|
|eReadFromReg|Kayıt defterinden verileri okuyun.|
|eWriteToReg|Kayıt defterine veri yazma.|
|eDeleteFromReg|Anahtarı kayıt defterinden silin.|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](atl-functions.md)<br/>
[Kayıt defteri verileri Exchange makroları](registry-data-exchange-macros.md)
