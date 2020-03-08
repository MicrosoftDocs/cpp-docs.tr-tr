---
title: Hata ayıklama ve hata raporlama genel Işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
ms.openlocfilehash: f7483b7473383958089b0c88d0b3c2645ddc2a4f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864897"
---
# <a name="debugging-and-error-reporting-global-functions"></a>Hata ayıklama ve hata raporlama genel Işlevleri

Bu işlevler, yararlı hata ayıklama ve izleme olanakları sağlar.

|||
|-|-|
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|HRESULT biçiminde bir `GetLastError` hata kodu döndürür.|
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Win32 hata kodunu HRESULT biçimine dönüştürür.|
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|İstemciye hata ayrıntılarını sağlamak için `IErrorInfo` ayarlar.|
|[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)|Bir `CAtlException`oluşturur.|
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Windows işlevinin `GetLastError`sonucuna bağlı olarak bir hata bildirmek için bu işlevi çağırın.|

##  <a name="atlhresultfromlasterror"></a>AtlHresultFromLastError

Çağıran iş parçacığının son hata kodu değerini HRESULT biçiminde döndürür.

```
HRESULT AtlHresultFromLastError();
```

### <a name="remarks"></a>Açıklamalar

`AtlHresultFromLastError`, son hatayı almak için `GetLastError` çağırır ve HRESULT_FROM_WIN32 makrosunu kullanarak bir HRESULT 'e dönüştürdükten sonra hatayı döndürür.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomclı. h

##  <a name="atlhresultfromwin32"></a>AtlHresultFromWin32

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
>  `HRESULT_FROM_WIN32(GetLastError())`kullanmak yerine [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)işlevini kullanın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomclı. h

##  <a name="atlreporterror"></a>AtlReportError

Nesnesinin istemcilerine hata bilgilerini sağlamak için `IErrorInfo` arabirimini ayarlar.

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
'ndaki Kaynağın tanıtıcısı. Varsayılan olarak, bu parametre `__AtlBaseModuleModule::GetResourceInstance`, burada `__AtlBaseModuleModule`, [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) 'un genel örneğidir veya ondan türetilmiş bir sınıftır.

### <a name="return-value"></a>Dönüş Değeri

*HRes* parametresi sıfır değilse, *hRes*'nin değerini döndürür. *HRes* sıfırsa, `AtlReportError` ilk dört sürümü DISP_E_EXCEPTION döndürür. Son iki sürüm MAKE_HRESULT makro sonucunu döndürür **(1, FACILITY_ITF,** `nID` **)** .

### <a name="remarks"></a>Açıklamalar

*LpszDesc* dizesi, hatanın metin açıklaması olarak kullanılır. İstemci, `AtlReportError`geri döndürülen *hRes* 'leri aldığında, hata hakkındaki ayrıntılar için istemci `IErrorInfo` yapısına erişebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]

> [!CAUTION]
>  C++ Catch işleyicilerde `AtlReportError` kullanmayın. Bu işlevlerin bazı geçersiz kılmaları, ATL dize dönüştürme makrolarını dahili olarak kullanır, bu da dahili olarak `_alloca` işlevini kullanır. Bir C++ catch işleyicisinde `AtlReportError` kullanmak, C++ catch işleyicilerinde özel durumlara neden olabilir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="atlthrow"></a>AtlThrow

HRESULT durum koduna dayalı bir hatayı bildirmek için bu işlevi çağırın.

```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```

### <a name="parameters"></a>Parametreler

*HR*<br/>
Standart HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ATL ve MFC kodu tarafından bir hata koşulu durumunda kullanılır. Bu, kendi kodınızdan da çağrılabilir. Bu işlevin varsayılan uygulanması, sembol _ATL_NO_EXCEPTIONS ve proje, MFC veya ATL türü tanımına bağlıdır.

Her durumda, bu işlev HRESULT 'yi hata ayıklayıcıya izler.

Visual Studio 2015 güncelleştirme 3 ve sonraki sürümlerde, bu işleve __declspec (noreturn), bu işlev, sursal SAL uyarılarını önlemek için öznitelikli.

_ATL_NO_EXCEPTIONS bir MFC projesinde tanımlanmamışsa, bu işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya HRESULT değerine göre bir [copaexception](../../mfc/reference/coleexception-class.md) oluşturur.

Bir ATL projesinde _ATL_NO_EXCEPTIONS tanımlanmamışsa, işlev bir [CAtlException](../../atl/reference/catlexception-class.md)oluşturur.

_ATL_NO_EXCEPTIONS tanımlanmışsa, işlev özel durum oluşturmak yerine bir onaylama hatasına neden olur.

ATL projeleri için, bir hata durumunda ATL tarafından kullanılmak üzere bu işlevin kendi uygulamanızı sağlamak mümkündür. Bunu yapmak için, `AtlThrow` imzayla aynı imzaya sahip kendi işlevinizi tanımlayın ve işlevinizin adı olarak `AtlThrow` #define. Bu, atlexcept. h dahil etmeden önce yapılmalıdır (atlbase. h, atlexcept. h dosyasını içerdiğinden tüm ATL üstbilgileri dahil etmeden önce yapılması gerekir). İşlevinizin `__declspec(noreturn)` özniteliği, suremsal uyarılarını önlemek için kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldef. h

##  <a name="atlthrowlastwin32"></a>AtlThrowLastWin32

Windows işlevinin `GetLastError`sonucuna bağlı olarak bir hata bildirmek için bu işlevi çağırın.

```
inline void AtlThrowLastWin32();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, hata ayıklayıcıya `GetLastError` sonucunu izler.

_ATL_NO_EXCEPTIONS bir MFC projesinde tanımlanmamışsa, bu işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya `GetLastError`tarafından döndürülen değere göre bir [copaexception](../../mfc/reference/coleexception-class.md) oluşturur.

Bir ATL projesinde _ATL_NO_EXCEPTIONS tanımlanmamışsa, işlev bir [CAtlException](../../atl/reference/catlexception-class.md)oluşturur.

_ATL_NO_EXCEPTIONS tanımlanmışsa, işlev özel durum oluşturmak yerine bir onaylama hatasına neden olur.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldef. h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)<br/>
[Hata Ayıklama ve Hata Raporlama Makroları](../../atl/reference/debugging-and-error-reporting-macros.md)
