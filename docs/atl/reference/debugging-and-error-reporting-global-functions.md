---
title: Hata ayıklama ve hata genel işlevler raporlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
dev_langs:
- C++
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb3257b5205587b27a83671ed8e610aad5373eef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="debugging-and-error-reporting-global-functions"></a>Hata ayıklama ve hata raporlama genel işlevler
Bu işlevler yararlı hata ayıklama ve izleme olanakları sağlar.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|Döndürür bir `GetLastError` biçiminde bir HRESULT hata kodu.|  
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Win32 hata kodunu HRESULT biçimine dönüştürür.|  
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|Ayarlayan **IErrorInfo** istemciye hata ayrıntılarını sağlamak için.|  
|[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)|Atan bir `CAtlException`.|  
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Windows işlev sonucuna hata göstermek için bu işlevi çağırmak `GetLastError`.|  
  
##  <a name="atlhresultfromlasterror"></a>  AtlHresultFromLastError  
 Çağıran iş parçacığının son hata kodu değerini HRESULT biçiminde döndürür.  
  
```
HRESULT AtlHresultFromLastError();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `AtlHresultFromLastError` çağrıları `GetLastError` son hata elde edilir ve kullanarak bir HRESULT dönüştürdükten sonra hata döndürür **HRESULT_FROM_WIN32** makrosu.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcomcli.h  

##  <a name="atlhresultfromwin32"></a>  AtlHresultFromWin32  
 Win32 hata kodunu HRESULT biçimine dönüştürür.  
  
```
AtlHresultFromWin32(DWORD error);
```  
  
### <a name="parameters"></a>Parametreler  
 *Hata*  
 Dönüştürülecek hata değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Win32 hata kodu makrosu kullanarak bir HRESULT dönüştürür **HRESULT_FROM_WIN32**.  
  
> [!NOTE]
>  Yerine **HRESULT_FROM_WIN32(GetLastError())**, işlevini [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror).  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcomcli.h  

##  <a name="atlreporterror"></a>  AtlReportError  
 Ayarlayan `IErrorInfo` nesne istemcilere hata bilgileri sağlamak için arabirim.  
  
```
HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```  
  
### <a name="parameters"></a>Parametreler  
 `clsid`  
 [in] Hata Raporlama nesnesinin CLSID.  
  
 `lpszDesc`  
 [in] Hatayı açıklayan dize. Unicode sürümleri belirtin `lpszDesc` türü **LPCOLESTR**; ANSI sürümü türünü `LPCSTR`.  
  
 `iid`  
 [in] Hata tanımlayan arabirim IID veya `GUID_NULL` hata işletim sistemi tarafından tanımlanmış olması durumunda.  
  
 `hRes`  
 [in] `HRESULT` İstediğiniz çağırana döndürülen.  
  
 `nID`  
 [in] Hata açıklama dizesi depolandığı kaynak tanımlayıcısı. Bu değer 0x0200 arasında 0xFFFF, ikisi de dahil olmak kalan. Hata ayıklama derlemelerinde, bir **ASSERT** neden olur `nID` geçerli bir dize dizin kullanılamıyor. Yayın derlemelerde "İçin bilinmeyen hata." hatası açıklama dizesi ayarlanacak  
  
 `dwHelpID`  
 [in] Hata için Yardım içeriği tanımlayıcı.  
  
 `lpszHelpFile`  
 [in] Hatayı açıklayan Yardım dosyasının adını ve yolunu.  
  
 `hInst`  
 [in] Kaynağı için tanıtıcı. Varsayılan olarak, bu parametredir **__AtlBaseModuleModule::GetResourceInstance**, burada **__AtlBaseModuleModule** genel örneğinin [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) ya da bir sınıf ondan türetilmiş.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa `hRes` parametre sıfır olmayan, değerini döndürür `hRes`. Varsa `hRes` sıfır sonra ilk dört sürümleri olan `AtlReportError` iade `DISP_E_EXCEPTION`. Son iki sürüm makrosu sonuç **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.  
  
### <a name="remarks"></a>Açıklamalar  
 Dize *lpszDesc* hata metin açıklaması olarak kullanılır. İstemci zaman alır `hRes` , döndürmek `AtlReportError`, istemcinin erişebildiği **IErrorInfo** hata hakkındaki ayrıntılar için yapısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]  
  
> [!CAUTION]
>  Kullanmayın `AtlReportError` c++'ta catch işleyicileri. Bu işlevlerin bazı geçersiz kılmaları sırayla kullandığınız ATL dize dönüşüm makroları dahili olarak kullanın. `_alloca` dahili olarak işlev. Kullanarak `AtlReportError` bir C++ catch işleyicisi C++ catch işleyicileri özel durumlara neden olabilir.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
    
##  <a name="atlthrow"></a>  AtlThrow  
 Temel bir hata göstermek için bu işlevi çağırmak bir `HRESULT` durum kodu.  
  
```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```  
  
### <a name="parameters"></a>Parametreler  
 `hr`  
 Standart HRESULT değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, bir hata koşulu durumunda ATL ve MFC kodu tarafından kullanılır. Ayrıca kendi koddan çağrılabilir. Bu işlev varsayılan uygulaması simgenin tanımını bağlıdır **_ATL_NO_EXCEPTIONS** ve proje, MFC ya da ATL türü  
  
 Her durumda, bu işlev HRESULT hata ayıklayıcı izler.  
  
 Visual Studio 2015 güncelleştirme 3 ve sonraki sürümlerinde, bu işlev öznitelikli __declspec(noreturn) alacaklardır SAL uyarılarını önlemek amacıyla kullanılır.  
  
 Varsa **_ATL_NO_EXCEPTIONS** tanımlı değil Bu işlev bir MFC projesine oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md) HRESULT değere göre.  
  
 Varsa **_ATL_NO_EXCEPTIONS** ATL projesinde, işlevi atar tanımlanmamış bir [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Varsa **_ATL_NO_EXCEPTIONS** olan tanımlanan işlevi bir özel durum atma yerine bir onaylama işlemi hatasına neden olur.  
  
 ATL projeleri için bu işlevin ATL tarafından bir arıza olması durumunda kullanılmak üzere kendi uygulama sunmak amacıyla mümkündür. Bunu yapmak için kendi işlev aynı imzayla tanımlayın `AtlThrow` ve #define `AtlThrow` , işlevin adı olmalıdır. Bu, (yani atlbase.h atlexcept.h içeren bu yana tüm ATL üstbilgileri dahil olmak üzere önce yapılmalıdır) atlexcept.h eklemeden önce yapılmalıdır. İşlevinizi özniteliği `__declspec(noreturn)` alacaklardır SAL uyarılarını önlemek amacıyla.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldef.h  

##  <a name="atlthrowlastwin32"></a>  AtlThrowLastWin32  
 Windows işlev sonucuna hata göstermek için bu işlevi çağırmak `GetLastError`.  
  
```
inline void AtlThrowLastWin32();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevin sonucu izler `GetLastError` hata ayıklayıcı için.  
  
 Varsa **_ATL_NO_EXCEPTIONS** tanımlı değil Bu işlev bir MFC projesine oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md) tarafındandöndürülendeğergöre`GetLastError`.  
  
 Varsa **_ATL_NO_EXCEPTIONS** ATL projesinde, işlevi atar tanımlanmamış bir [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Varsa **_ATL_NO_EXCEPTIONS** olan tanımlanan işlevi bir özel durum atma yerine bir onaylama işlemi hatasına neden olur.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldef.h  
   
     
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)   
 [Hata Ayıklama ve Hata Raporlama Makroları](../../atl/reference/debugging-and-error-reporting-macros.md)









