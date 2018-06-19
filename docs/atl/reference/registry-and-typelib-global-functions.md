---
title: Kayıt defteri ve TypeLib genel işlevler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb0a89ecf8bb81e515703abe819bb1edfbf80d59
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365513"
---
# <a name="registry-and-typelib-global-functions"></a>Kayıt defteri ve TypeLib genel işlevler
Bu işlevler yükleme ve bir tür kitaplığı kaydı için destek sağlar.  
  
> [!IMPORTANT]
>  Windows çalışma zamanı'nda yürütme uygulamalarda aşağıdaki tablolarda listelenen işlevleri kullanılamaz.  
  
|||  
|-|-|  
|[AfxRegCreateKey](#afxrefcreatekey)|Belirtilen kayıt defteri anahtarı oluşturur.|
|[AfxRegDeleteKey](#afxrefdeletekey)|Belirtilen kayıt defteri anahtarı siler.|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|Önizleme işleyicisi kaydetmek için yardımcıyı.|
|[AfxUnregisterPreviewHandler](#afxunregisterpreviewhandler)| Önizleme işleyicisi kaydı Yardımcısı. |
|[AtlRegisterTypeLib](#atlregistertypelib)|Tür kitaplığını kaydetmek için bu işlev çağrılır.|  
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|Bu işlev bir tür kitaplığı kaydı için çağrılır|  
|[AfxRegOpenKey](#afxregopenkey)|Belirtilen kayıt defteri anahtarı açar.|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|Belirtilen kayıt defteri anahtarı açar.|
|[AtlLoadTypeLib](#atlloadtypelib)|Tür kitaplığını yüklemek için bu işlev çağrılır.|  
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|Sağlanan kaynaktan kayıt defterini güncelleştirmek için bu işlev çağrılır.|  
|[RegistryDataExchange](#registrydataexchange)|Bu işlev, sistem kayıt defterinden okumak veya ona yazmak için kullanılır. Tarafından çağrılır [kayıt defteri veri değişimi makroları](../../atl/reference/registry-data-exchange-macros.md).|  
  
 Bu işlevler program bilgilerini depolamak için kullandığı kayıt defterinde hangi düğümün denetler.  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|Uygulama kayıt erişimi yönlendiren olup olmadığını alır **HKEY_CURRENT_USER** ( **HKCU**) düğüm.|  
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|Uygulama kayıt erişimi yönlendiren olup olmadığını ayarlar **HKEY_CURRENT_USER** ( **HKCU**) düğüm.|  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h

## <a name="atlgetperuserregistration"></a> AtlGetPerUserRegistration
Uygulama kayıt erişimi yönlendiren olup olmadığını belirlemek için bu işlevi kullanın **HKEY_CURRENT_USER** (**HKCU**) düğüm.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] `pEnabled`  
 `TRUE` kayıt defteri bilgileri için yönlendirilir gösterir **HKCU** düğümü; `FALSE` uygulama varsayılan düğüme kayıt defteri bilgilerini yazar gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK` yöntem aksi başarılı olursa `HRESULT` bir hata oluşursa hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt defteri yeniden yönlendirme varsayılan olarak etkin değildir. Bu seçeneği etkinleştirirseniz, kayıt defteri erişimi yönlendireceği **HKEY_CURRENT_USER\Software\Classes**.  
  
 Yeniden yönlendirme genel değil. MFC ve ATL çerçeveleri yalnızca bu kayıt defteri yeniden yönlendirme tarafından etkilenir.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  

 ## <a name="afxregcreatekey"></a> AfxRegCreateKey
 Belirtilen kayıt defteri anahtarı oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>Parametreler  
 `hKey`  
 Bir kayıt defteri anahtarı için bir tanıtıcı.  
  
 `lpSubKey`  
 Bu işlev açar veya oluşturur bir anahtar adı.  
  
 `phkResult`  
 Bir işaretçi bir değişkene açılan ya da oluşturulan anahtarı için bir tanıtıcı alır.  
  
 `pTM`  
 İşaretçi bir `CAtlTransactionManager` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. İşlev başarısız olursa, dönüş değeri Winerror.h'de içinde tanımlanan bir sıfır olmayan hata kodudur.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpriv.h  

## <a name="afxregdeletekey"></a> AfxRegDeleteKey
Belirtilen kayıt defteri anahtarı siler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>Parametreler  
 `hKey`  
 Bir kayıt defteri anahtarı için bir tanıtıcı.  
  
 `lpSubKey`  
 Silinecek anahtarın adı.  
  
 `pTM`  
 İşaretçi bir `CAtlTransactionManager` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. İşlev başarısız olursa, dönüş değeri Winerror.h'de içinde tanımlanan bir sıfır olmayan hata kodudur.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpriv.h  

## <a name="afxregisterpreviewhandler"></a>
Önizleme işleyicisi kaydetmek için yardımcıyı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszCLSID`  
 İşleyici CLSID belirtir.  
  
 `lpszShortTypeName`  
 İşleyici ProgID belirtir.  
  
 `lpszFilterExt`  
 Bu işleyici ile dosya uzantısı kayıtlı belirtir.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h   

##  <a name="atlregistertypelib"></a>  AtlRegisterTypeLib  
 Tür kitaplığını kaydetmek için bu işlev çağrılır.  
  
  
```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `hInstTypeLib`  
 Modül örneğinin tanıtıcısını.  
  
 `lpszIndex`  
 Biçim dizesindeki "\\\N", N tür kitaplığı kaynağı tamsayı dizinini alır. Herhangi bir dizin yoksa NULL olabilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yardımcı işlevi tarafından kullanılan [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) ve [CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib).  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h

 ## <a name="afxregopenkey"></a> AfxRegOpenKey
 Belirtilen kayıt defteri anahtarı açar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>Parametreler  
 `hKey`  
 Bir kayıt defteri anahtarı için bir tanıtıcı.  
  
 `lpSubKey`  
 Bu işlev açar veya oluşturur bir anahtar adı.  
  
 `phkResult`  
 Bir işaretçi bir değişkene oluşturulan anahtarı için bir tanıtıcı alır.  
  
 `pTM`  
 İşaretçi bir `CAtlTransactionManager` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. İşlev başarısız olursa, dönüş değeri Winerror.h'de içinde tanımlanan bir sıfır olmayan hata kodudur.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpriv.h  

## <a name="afxregopenkeyex"></a>  AfxRegOpenKeyEx
Belirtilen kayıt defteri anahtarı açar. 

### <a name="syntax"></a>Sözdizimi  
  
```  
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>Parametreler  
 `hKey`  
 Bir kayıt defteri anahtarı için bir tanıtıcı.  
  
 `lpSubKey`  
 Bu işlev açar veya oluşturur bir anahtar adı.  
  
 `ulOptions`  
 Bu parametre ayrılmıştır ve sıfır olmalıdır.  
  
 `samDesired`  
 Anahtar istenen erişim hakkı belirtir maskesi.  
  
 `phkResult`  
 Bir işaretçi bir değişkene açılan anahtarı için bir tanıtıcı alır.  
  
 `pTM`  
 İşaretçi bir `CAtlTransactionManager` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. İşlev başarısız olursa, dönüş değeri Winerror.h'de içinde tanımlanan bir sıfır olmayan hata kodudur.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpriv.h  

 ## <a name="afxunregisterpreviewhandler"></a> AfxUnregisterPreviewHandler
 Önizleme işleyicisi kaydı Yardımcısı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszCLSID`  
 Sona erdirilecek CLSID işleyicisinin belirtir.  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  

## <a name="atlsetperuserregistration"></a> AtlSetPerUserRegistration
Uygulama kayıt erişimi yönlendiren olup olmadığını ayarlar **HKEY_CURRENT_USER** (**HKCU**) düğüm.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bEnable`  
 `TRUE` kayıt defteri bilgileri için yönlendirilir gösterir **HKCU** düğümü; `FALSE` uygulama varsayılan düğüme kayıt defteri bilgilerini yazar gösterir. Varsayılan düğüm **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK` yöntem aksi başarılı olursa `HRESULT` bir hata oluşursa hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt defteri yeniden yönlendirme varsayılan olarak etkin değildir. Bu seçeneği etkinleştirirseniz, kayıt defteri erişimi yönlendireceği **HKEY_CURRENT_USER\Software\Classes**.  
  
 Yeniden yönlendirme genel değil. MFC ve ATL çerçeveleri yalnızca bu kayıt defteri yeniden yönlendirme tarafından etkilenir.  
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
 `hInstTypeLib`  
 Modül örneğinin tanıtıcısını.  
  
 `lpszIndex`  
 Biçim dizesindeki "\\\N", N tür kitaplığı kaynağı tamsayı dizinini alır. Herhangi bir dizin yoksa NULL olabilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
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
 `hInstTypeLib`  
 Tür kitaplığı ile ilişkili modülü için işleyin.  
  
 `lpszIndex`  
 Biçim dizesindeki "\\\N", N tür kitaplığı kaynağı tamsayı dizinini alır. Herhangi bir dizin yoksa NULL olabilir.  
  
 *pbstrPath*  
 Başarılı getirisi türü Kitaplıkla ilişkilendirilmiş modülü tam yolunu içerir.  
  
 `ppTypeLib`  
 Başarılı getirisi yüklenen tür kitaplığı için bir işaretçi bir işaretçi içeriyor.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yardımcı işlevi tarafından kullanılan [AtlRegisterTypeLib](#atlregistertypelib) ve [AtlUnRegisterTypeLib](#atlunregistertypelib).  
  
##  <a name="atlupdateregistryfromresourced"></a>  AtlUpdateRegistryFromResourceD  
 Bu işlev, Visual Studio 2013'te kullanımdan kaldırılmıştır ve Visual Studio 2015'te kaldırılır.  
  
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
 *PT*  
 Geçerli nesne için bir işaretçi.  
  
 *rdxOp*  
 Hangi işlemi gösteren bir enum değeri işlevi gerçekleştirmeniz gerekir. İzin verilen değerler için açıklamalar bölümündeki tabloya bakın.  
  
 `pItem`  
 İşaretçi okuma veya kayıt defterine, yazılan veriler. Verileri kayıt defterinden silinecek bir anahtar da gösterebilir. Varsayılan değer NULL olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Makrolar [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) ve [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) çağıran bir işlev genişletin `RegistryDataExchange`.  
  
 İşlev işlemi gerçekleştirmesi gereken belirtmek olası enum değerleri aşağıdaki tabloda gösterilmiştir:  
  
|Enum değeri|Çalışma|  
|----------------|---------------|  
|eReadFromReg|Kayıt defterinden veri okuma.|  
|eWriteToReg|Kayıt defterine veri yazma.|  
|eDeleteFromReg|Anahtarı kayıt defterinden silin.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h

## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](atl-functions.md) [kayıt defteri veri değişimi makroları](registry-data-exchange-macros.md)





