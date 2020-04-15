---
title: Hata Ayıklama ve Hata Raporlama Genel İşlevleri
ms.date: 11/04/2016
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
ms.openlocfilehash: f7636b1f4e13340b223edd8c63c39bbeb21c8bd0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330202"
---
# <a name="debugging-and-error-reporting-global-functions"></a>Hata Ayıklama ve Hata Raporlama Genel İşlevleri

Bu işlevler yararlı hata ayıklama ve izleme tesisleri sağlar.

|||
|-|-|
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|HRESULT `GetLastError` şeklinde bir hata kodu verir.|
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Win32 hata kodunu HRESULT biçimine dönüştürür.|
|[AtlReportHatası](debugging-and-error-reporting-global-functions.md#atlreporterror)|İstemciye hata ayrıntıları sağlamak için ayarlar. `IErrorInfo`|
|[Atlthrow](debugging-and-error-reporting-global-functions.md#atlthrow)|Atar bir `CAtlException`.|
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Windows işlevinin `GetLastError`sonucuna dayalı bir hata sinyali vermek için bu işlevi arayın.|

## <a name="atlhresultfromlasterror"></a><a name="atlhresultfromlasterror"></a>AtlHresultFromLastError

Çağıran iş parçacığının son hata kodu değerini HRESULT biçiminde döndürür.

```
HRESULT AtlHresultFromLastError();
```

### <a name="remarks"></a>Açıklamalar

`AtlHresultFromLastError`son `GetLastError` hatayı almak için çağırır ve HRESULT_FROM_WIN32 makroyu kullanarak bir HRESULT'a dönüştürdükten sonra hatayı döndürür.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomcli.h

## <a name="atlhresultfromwin32"></a><a name="atlhresultfromwin32"></a>AtlHresultFromWin32

Win32 hata kodunu HRESULT biçimine dönüştürür.

```
AtlHresultFromWin32(DWORD error);
```

### <a name="parameters"></a>Parametreler

*error*<br/>
Dönüştürülecek hata değeri.

### <a name="remarks"></a>Açıklamalar

Makro HRESULT_FROM_WIN32 kullanarak Win32 hata kodunu HRESULT'a dönüştürür.

> [!NOTE]
> Kullanmak yerine `HRESULT_FROM_WIN32(GetLastError())` [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)işlevini kullanın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomcli.h

## <a name="atlreporterror"></a><a name="atlreporterror"></a>AtlReportHatası

Nesnenin `IErrorInfo` istemcilerine hata bilgileri sağlamak için arabirimi ayarlar.

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

*Clsıd*<br/>
[içinde] Hatayı bildiren nesnenin CLSID'si.

*lpszDesc*<br/>
[içinde] Hatayı açıklayan dize. Unicode sürümleri *lpszDesc* tip LPCOLESTR olduğunu belirtin; ANSI sürümü bir LPCSTR türünü belirtir.

*ııd*<br/>
[içinde] Hata işletim sistemi tarafından tanımlanırsa hatayı tanımlayan arabirimin IID'si veya GUID_NULL.

*hRes*<br/>
[içinde] Arayana döndürülmek istediğiniz HRESULT.

*Nıd*<br/>
[içinde] Hata açıklaması dizesinin depolandığı kaynak tanımlayıcısı. Bu değer 0x0200 ile 0xFFFF arasında olmalıdır. Hata ayıklama yapılarında, *nID* geçerli bir dize ekizin vermezse bir **Assert** ortaya çıkacaktır. Sürüm yapılarında, hata açıklaması dizesi "Bilinmeyen Hata" olarak ayarlanır.

*dwHelpID*<br/>
[içinde] Hata için yardım bağlamı tanımlayıcısı.

*lpszHelpFile*<br/>
[içinde] Hatayı açıklayan yardım dosyasının yolu ve adı.

*hInst*<br/>
[içinde] Kaynağa tanıtıcı. Varsayılan olarak, bu `__AtlBaseModuleModule::GetResourceInstance`parametre `__AtlBaseModuleModule` , [CAtlBaseModule'in](../../atl/reference/catlbasemodule-class.md) genel örneği veya ondan türetilen bir sınıftır.

### <a name="return-value"></a>Dönüş Değeri

*hRes* parametresi sıfır değilse, *hRes*değerini döndürür. *HRes* sıfır ise, `AtlReportError` daha sonra DISP_E_EXCEPTION dönmek ilk dört sürümü. Son iki sürüm makro MAKE_HRESULT **(1, FACILITY_ITF,** `nID` **)** sonucunu döndürer.

### <a name="remarks"></a>Açıklamalar

String *lpszDesc* hatanın metin açıklaması olarak kullanılır. İstemci geri döndüğünüz *hRes* `AtlReportError`aldığında, istemci `IErrorInfo` hata hakkında ayrıntılar için yapıya erişebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]

> [!CAUTION]
> C++ `AtlReportError` catch işleyicilerinde kullanmayın. Bu işlevlerin bazı geçersiz kılmaları, atl dize dönüştürme makrolarını dahili olarak kullanır ve bu makrolar da `_alloca` işlevi dahili olarak kullanır. C++ catch işleyicisi kullanmak, `AtlReportError` C++ catch işleyicilerinde özel durumlara neden olabilir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="atlthrow"></a><a name="atlthrow"></a>Atlthrow

HRESULT durum kodunu temel alan bir hata sinyali vermek için bu işlevi çağırın.

```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```

### <a name="parameters"></a>Parametreler

*Hr*<br/>
Standart HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir hata koşulu durumunda ATL ve MFC kodu tarafından kullanılır. Kendi kodunuzdan da çağrılabilir. Bu işlevin varsayılan uygulaması, _ATL_NO_EXCEPTIONS sembolünün tanımına ve proje, MFC veya ATL türüne bağlıdır.

Her durumda, bu işlev Hata ayıklama için HRESULT izler.

Visual Studio 2015 Update 3 ve sonraki durumlarda, bu işlev sahte SAL uyarılarını önlemek için __declspec (geri dönüş) atfedilir.

_ATL_NO_EXCEPTIONS bir MFC projesinde tanımlanmamışsa, bu işlev HRESULT'In değerini temel alan bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md) atar.

_ATL_NO_EXCEPTIONS bir ATL projesinde tanımlanmamışsa, işlev bir [CAtlException](../../atl/reference/catlexception-class.md)atar.

_ATL_NO_EXCEPTIONS tanımlanırsa, işlev özel durum atmak yerine bir sedama hatasına neden olur.

ATL projeleri için, bir hata durumunda ATL tarafından kullanılacak bu işlevin kendi uygulama sağlamak mümkündür. Bunu yapmak için, işlevinizin adı `AtlThrow` olarak `AtlThrow` aynı imza ve #define ile kendi işlevinizi tanımlayın. Bu atlexcept.h dahil edilmeden önce yapılmalıdır (bu da atlbase.h atlexcept.h içerdiğinden, atlbase.h dahil edilmeden önce yapılması gerektiği anlamına gelir). Sahte SAL `__declspec(noreturn)` uyarılarından kaçınmak için işlevinizi atfedin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldef.h

## <a name="atlthrowlastwin32"></a><a name="atlthrowlastwin32"></a>AtlThrowLastWin32

Windows işlevinin `GetLastError`sonucuna dayalı bir hata sinyali vermek için bu işlevi arayın.

```
inline void AtlThrowLastWin32();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev hata ayıklama nın `GetLastError` sonucunu izler.

_ATL_NO_EXCEPTIONS bir MFC projesinde tanımlanmamışsa, bu işlev tarafından `GetLastError`döndürülen değere göre bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md) atar.

_ATL_NO_EXCEPTIONS bir ATL projesinde tanımlanmamışsa, işlev bir [CAtlException](../../atl/reference/catlexception-class.md)atar.

_ATL_NO_EXCEPTIONS tanımlanırsa, işlev özel durum atmak yerine bir sedama hatasına neden olur.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldef.h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)<br/>
[Hata Ayıklama ve Hata Raporlama Makroları](../../atl/reference/debugging-and-error-reporting-macros.md)
