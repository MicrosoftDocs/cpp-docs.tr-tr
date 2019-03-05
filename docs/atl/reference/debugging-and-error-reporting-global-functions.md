---
title: Hata ayıklama ve hata raporlama genel işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
ms.openlocfilehash: f7483b7473383958089b0c88d0b3c2645ddc2a4f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287576"
---
# <a name="debugging-and-error-reporting-global-functions"></a>Hata ayıklama ve hata raporlama genel işlevleri

Bu işlevler, kullanışlı hata ayıklama ve izleme olanakları sağlayın.

|||
|-|-|
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|Döndürür bir `GetLastError` HRESULT biçiminde hata kodu.|
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Win32 hata kodunu HRESULT biçimine dönüştürür.|
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|Ayarlar `IErrorInfo` istemciye hata ayrıntılarını sağlamak için.|
|[Çeşitlemeleri](debugging-and-error-reporting-global-functions.md#atlthrow)|Oluşturur bir `CAtlException`.|
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Windows işlev sonucuna dayalı olarak hata sinyali vermek için bu işlevi çağırın `GetLastError`.|

##  <a name="atlhresultfromlasterror"></a>  AtlHresultFromLastError

Çağıran iş parçacığının son hata kodu değerini HRESULT biçiminde döndürür.

```
HRESULT AtlHresultFromLastError();
```

### <a name="remarks"></a>Açıklamalar

`AtlHresultFromLastError` çağrıları `GetLastError` son hata elde edilir ve bu hresult_from_wın32 makrosu kullanarak HRESULT dönüştürdükten sonra bir hata döndürür.

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlcomcli.h

##  <a name="atlhresultfromwin32"></a>  AtlHresultFromWin32

Win32 hata kodunu HRESULT biçimine dönüştürür.

```
AtlHresultFromWin32(DWORD error);
```

### <a name="parameters"></a>Parametreler

*Hata*<br/>
Dönüştürülecek hata değeri.

### <a name="remarks"></a>Açıklamalar

Win32 hata kodunu bu hresult_from_wın32 makrosu kullanılarak bir HRESULT biçimine dönüştürür.

> [!NOTE]
>  Yerine `HRESULT_FROM_WIN32(GetLastError())`, işlevini [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror).

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlcomcli.h

##  <a name="atlreporterror"></a>  AtlReportError

Ayarlar `IErrorInfo` hata bilgilerini nesnenin istemcilerine sağlamak için arabirim.

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

*CLSID*<br/>
[in] Hata Raporlama nesne CLSID değeri.

*lpszDesc*<br/>
[in] Hatayı açıklayan bir dize. Unicode sürümlerini belirtmek *lpszDesc* değil LPCOLESTR türü; ANSI sürümü LPCSTR türünü belirtir.

*IID*<br/>
[in] Hata işletim sistemi tarafından tanımlanmış olması durumunda hata veya GUID_NULL tanımlama arabirimi Laboratuvardaki.

*Xact_s_lastresourcemanager*<br/>
[in] İstediğiniz HRESULT arayana döndürülür.

*nID*<br/>
[in] Hata açıklaması dizesi depolandığı kaynak tanımlayıcısı. Bu değer 0x0200 ile 0xFFFF arasında aralığında yer alan. Hata ayıklama yapılarında, bir **ASSERT** neden olur *nID* geçerli bir dize dizinini oluşturmaz. Sürüm yapılarında hata açıklama dizesi "İçin bilinmeyen hata." ayarlanır.

*dwHelpID*<br/>
[in] Hata için Yardım içeriği tanımlayıcı.

*lpszHelpFile*<br/>
[in] Hatayı açıklayan Yardım dosyasının adı ve yolu.

*hInst*<br/>
[in] Kaynağı için tanıtıcı. Varsayılan olarak, bu parametredir `__AtlBaseModuleModule::GetResourceInstance`burada `__AtlBaseModuleModule` genel örneğinin [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) veya ondan türetilmiş bir sınıf.

### <a name="return-value"></a>Dönüş Değeri

Varsa *Xact_s_lastresourcemanager* parametre sıfır olmayan, değerini döndürür *Xact_s_lastresourcemanager*. Varsa *Xact_s_lastresourcemanager* sıfır sonra ilk dört sürümleri `AtlReportError` DISP_E_EXCEPTION döndürür. Son iki sürüm makronun sonucu döndürür **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.

### <a name="remarks"></a>Açıklamalar

Dize *lpszDesc* hatanın metin açıklama kullanılır. İstemci aldığında *Xact_s_lastresourcemanager* gelen dönüş `AtlReportError`, istemcinin erişebildiği `IErrorInfo` yapısı hata hakkındaki ayrıntılar için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]

> [!CAUTION]
>  Kullanmayın `AtlReportError` c++'ta catch işleyicileri. Sırayla kullandığınız dahili olarak, bu işlevlerin bazı geçersiz kılmaları ATL dize dönüşüm makroları kullanın `_alloca` dahili olarak işlev. Kullanarak `AtlReportError` bir C++ catch işleyicisi özel durumları C++ catch işleyicileri neden olabilir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="atlthrow"></a>  Çeşitlemeleri

Bir HRESULT durum koduna göre hata sinyali vermek için bu işlevi çağırın.

```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```

### <a name="parameters"></a>Parametreler

*İK*<br/>
Standart HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir hata koşulu olması durumunda, ATL ve MFC kodu tarafından kullanılır. Ayrıca kendi koddan çağrılabilir. Bu işlev varsayılan uygulamasını sembol _ATL_NO_EXCEPTIONS tanımını ve MFC veya ATL projesi türünü bağlıdır.

Her durumda, bu işlev hata ayıklayıcı HRESULT izler.

Visual Studio 2015 güncelleştirme 3 ve sonraki sürümlerinde, bu işlev öznitelikli __declspec(noreturn) alacaklardır SAL uyarılarının önlemek için kullanılır.

Bir MFC projesinde _ATL_NO_EXCEPTIONS tanımlı değil, bu işlev oluşturur. bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md) HRESULT değerini temel alarak.

Bir ATL projesinde _ATL_NO_EXCEPTIONS tanımlı değil, işlev oluşturur. bir [CAtlException](../../atl/reference/catlexception-class.md).

_ATL_NO_EXCEPTIONS tanımlanmazsa, işlev bir özel durum oluşturmaktansa bir onaylama işlemi hatasına neden olur.

ATL projeleri için bu işlev bir hata olması durumunda ATL tarafından kullanılmak üzere kendi uygulamasını sağlamak mümkündür. Bunu yapmak için kendi işlevi aynı imzaya sahip tanımlama `AtlThrow` ve #define `AtlThrow` işlev uygulamanızın adı olacak. Bu, (yani herhangi bir ATL üstbilgilerine atlbase.h atlexcept.h içerdiğinden dahil önce yapılmalıdır) atlexcept.h eklemeden önce yapılmalıdır. İşlevinizi özniteliği `__declspec(noreturn)` alacaklardır SAL uyarılarının önlemek için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldef.h

##  <a name="atlthrowlastwin32"></a>  AtlThrowLastWin32

Windows işlev sonucuna dayalı olarak hata sinyali vermek için bu işlevi çağırın `GetLastError`.

```
inline void AtlThrowLastWin32();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev sonucu izler `GetLastError` hata ayıklayıcı.

Bir MFC projesinde _ATL_NO_EXCEPTIONS tanımlı değil, bu işlev oluşturur. bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md) tarafından döndürülen değere göre `GetLastError`.

Bir ATL projesinde _ATL_NO_EXCEPTIONS tanımlı değil, işlev oluşturur. bir [CAtlException](../../atl/reference/catlexception-class.md).

_ATL_NO_EXCEPTIONS tanımlanmazsa, işlev bir özel durum oluşturmaktansa bir onaylama işlemi hatasına neden olur.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldef.h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)<br/>
[Hata Ayıklama ve Hata Raporlama Makroları](../../atl/reference/debugging-and-error-reporting-macros.md)
