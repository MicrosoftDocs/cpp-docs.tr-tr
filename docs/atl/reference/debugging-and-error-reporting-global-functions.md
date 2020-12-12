---
description: 'Hakkında daha fazla bilgi edinin: hata ayıklama ve hata raporlama genel Işlevleri'
title: Hata ayıklama ve hata raporlama genel Işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
ms.openlocfilehash: 3c729a7d8e870ce7b104ca53cd83bf8c41112dea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139990"
---
# <a name="debugging-and-error-reporting-global-functions"></a>Hata ayıklama ve hata raporlama genel Işlevleri

Bu işlevler, yararlı hata ayıklama ve izleme olanakları sağlar.

|Ad|Açıklama|
|-|-|
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|`GetLastError`HRESULT biçiminde bir hata kodu döndürür.|
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Win32 hata kodunu HRESULT biçimine dönüştürür.|
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|`IErrorInfo`Bir istemciye hata ayrıntılarını sağlamak için ayarlar.|
|[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)|Bir oluşturur `CAtlException` .|
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Windows işlevinin sonucuna bağlı olarak bir hatayı bildirmek için bu işlevi çağırın `GetLastError` .|

## <a name="atlhresultfromlasterror"></a><a name="atlhresultfromlasterror"></a> AtlHresultFromLastError

Çağıran iş parçacığının son hata kodu değerini HRESULT biçiminde döndürür.

```
HRESULT AtlHresultFromLastError();
```

### <a name="remarks"></a>Açıklamalar

`AtlHresultFromLastError``GetLastError`son hatayı elde etmek için çağırır ve HRESULT_FROM_WIN32 makrosunu kullanarak BIR HRESULT 'e dönüştürdükten sonra hatayı döndürür.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomclı. h

## <a name="atlhresultfromwin32"></a><a name="atlhresultfromwin32"></a> AtlHresultFromWin32

Win32 hata kodunu HRESULT biçimine dönüştürür.

```
AtlHresultFromWin32(DWORD error);
```

### <a name="parameters"></a>Parametreler

*hatayla*<br/>
Dönüştürülecek hata değeri.

### <a name="remarks"></a>Açıklamalar

HRESULT_FROM_WIN32 makro kullanarak bir Win32 hata kodunu HRESULT 'ye dönüştürür.

> [!NOTE]
> Kullanmak yerine `HRESULT_FROM_WIN32(GetLastError())` , [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)işlevini kullanın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomclı. h

## <a name="atlreporterror"></a><a name="atlreporterror"></a> AtlReportError

`IErrorInfo`Nesnesinin istemcilerine hata bilgileri sağlamak için arabirimi ayarlar.

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

*in*<br/>
'ndaki Hatayı raporlayan nesnenin CLSID 'SI.

*lpszDesc*<br/>
'ndaki Hatayı açıklayan dize. Unicode sürümleri, *lpszDesc* 'ın LPCOTASTR; türünde olduğunu belirtir ANSI sürümü bir LPCSTR türü belirtir.

*'si*<br/>
'ndaki Hatayı tanımlayan arabirimin IID 'si veya hata işletim sistemi tarafından tanımlanmışsa GUID_NULL.

*hRes*<br/>
'ndaki Çağırana geri dönmek istediğiniz HRESULT.

*NID*<br/>
'ndaki Hata açıklaması dizesinin depolandığı kaynak tanımlayıcısı. Bu değer, ikisi de dahil olmak üzere 0x0200 ile 0xFFFF arasında olmalıdır. Hata ayıklama yapılarında, *NID* geçerli bir dizeye Dizin oluşturmadığı takdirde bir **onaylama** sonucu olur. Yayın derlemeleri ' nde hata açıklaması dizesi "Bilinmeyen hata" olarak ayarlanır.

*dwHelpID*<br/>
'ndaki Hatanın yardım bağlamı tanımlayıcısı.

*lpszHelpFile*<br/>
'ndaki Hatayı açıklayan Yardım dosyasının yolu ve adı.

*hInst*<br/>
'ndaki Kaynağın tanıtıcısı. Varsayılan olarak, bu parametre `__AtlBaseModuleModule::GetResourceInstance` ' dir; burada, `__AtlBaseModuleModule` [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) 'un genel örneği veya ondan türetilmiş bir sınıf vardır.

### <a name="return-value"></a>Dönüş Değeri

*HRes* parametresi sıfır değilse, *hRes*'nin değerini döndürür. *HRes* sıfırsa, ' ın ilk dört sürümü `AtlReportError` DISP_E_EXCEPTION döndürür. Son iki sürüm MAKE_HRESULT makro sonucunu döndürür **(1, FACILITY_ITF,** `nID` **)**.

### <a name="remarks"></a>Açıklamalar

*LpszDesc* dizesi, hatanın metin açıklaması olarak kullanılır. İstemci üzerinden döndürülen *hRes* 'leri aldığında `AtlReportError` , `IErrorInfo` hata hakkındaki ayrıntılar için istemci yapıya erişebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]

> [!CAUTION]
> `AtlReportError`C++ catch işleyicilerinde kullanmayın. Bu işlevlerin bazı geçersiz kılmaları, ATL dize dönüştürme makrolarını dahili olarak kullanır ve bu da `_alloca` işlevi dahili olarak kullanır. `AtlReportError`C++ catch işleyicide kullanılması, c++ catch işleyicilerinde özel durumlara neden olabilir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="atlthrow"></a><a name="atlthrow"></a> AtlThrow

HRESULT durum koduna dayalı bir hatayı bildirmek için bu işlevi çağırın.

```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```

### <a name="parameters"></a>Parametreler

*sa*<br/>
Standart HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ATL ve MFC kodu tarafından bir hata koşulu durumunda kullanılır. Bu, kendi kodınızdan da çağrılabilir. Bu işlevin varsayılan uygulanması, sembol _ATL_NO_EXCEPTIONS ve proje, MFC veya ATL türü tanımına bağlıdır.

Her durumda, bu işlev HRESULT 'yi hata ayıklayıcıya izler.

Visual Studio 2015 güncelleştirme 3 ve sonraki sürümlerde, bu işleve __declspec (noreturn), bu işlev, sursal SAL uyarılarını önlemek için öznitelikli.

_ATL_NO_EXCEPTIONS bir MFC projesinde tanımlanmamışsa, bu işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya HRESULT değerine göre bir [copaexception](../../mfc/reference/coleexception-class.md) oluşturur.

Bir ATL projesinde _ATL_NO_EXCEPTIONS tanımlanmamışsa, işlev bir [CAtlException](../../atl/reference/catlexception-class.md)oluşturur.

_ATL_NO_EXCEPTIONS tanımlanmışsa, işlev özel durum oluşturmak yerine bir onaylama hatasına neden olur.

ATL projeleri için, bir hata durumunda ATL tarafından kullanılmak üzere bu işlevin kendi uygulamanızı sağlamak mümkündür. Bunu yapmak için, aynı imzayla aynı imzaya sahip kendi işlevinizi tanımlayın `AtlThrow` ve `AtlThrow` işlevinizin adı olacak #define. Bu, atlexcept. h dahil etmeden önce yapılmalıdır (atlbase. h, atlexcept. h dosyasını içerdiğinden tüm ATL üstbilgileri dahil etmeden önce yapılması gerekir). İşlevinizi, `__declspec(noreturn)` suremsal uyarılarını önlemek için kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldef. h

## <a name="atlthrowlastwin32"></a><a name="atlthrowlastwin32"></a> AtlThrowLastWin32

Windows işlevinin sonucuna bağlı olarak bir hatayı bildirmek için bu işlevi çağırın `GetLastError` .

```
inline void AtlThrowLastWin32();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, `GetLastError` hata ayıklayıcıya sonucunu izler.

_ATL_NO_EXCEPTIONS bir MFC projesinde tanımlanmamışsa, bu işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya tarafından döndürülen değere göre bir [copaexception](../../mfc/reference/coleexception-class.md) oluşturur `GetLastError` .

Bir ATL projesinde _ATL_NO_EXCEPTIONS tanımlanmamışsa, işlev bir [CAtlException](../../atl/reference/catlexception-class.md)oluşturur.

_ATL_NO_EXCEPTIONS tanımlanmışsa, işlev özel durum oluşturmak yerine bir onaylama hatasına neden olur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldef. h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)<br/>
[Hata ayıklama ve hata raporlama makroları](../../atl/reference/debugging-and-error-reporting-macros.md)
