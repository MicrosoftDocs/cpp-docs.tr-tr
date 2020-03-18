---
title: Dll 'Leri yönetmeye yönelik makrolar ve Işlevler
ms.date: 03/27/2019
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
ms.openlocfilehash: b27f8763b60dc7ce3ee074cad1365e7e1de3a7e6
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421340"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Dll 'Leri yönetmeye yönelik makrolar ve Işlevler

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|Sınıfları dışarı aktarır.|
|[AFX_MANAGE_STATE](#afx_manage_state)|DLL içindeki bir içe aktarılmış işlevi koruma.|
|[AfxOleInitModule](#afxoleinitmodule)|MFC 'ye dinamik olarak bağlanan normal bir MFC DLL 'den OLE desteği sağlar.|
|[AfxNetInitModule](#afxnetinitmodule)|MFC 'ye dinamik olarak bağlanan normal bir MFC DLL 'den MFC Yuvaları desteği sağlar.|
|[Afxgetambentactctx](#afxgetambientactctx)|Modül başına durum bayrağının geçerli durumunu alır.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|Başlatmadan önce modül durumunu ayarlar ve/veya sildikten sonra önceki modül durumunu geri yüklemek için.|
|[AfxInitExtensionModule](#afxinitextensionmodule)|DLL 'yi başlatır.|
|[Afxsetambentactctx](#afxsetambientactctx)|MFC 'nin WinSxS davranışını etkileyen modül başına durum bayrağını ayarlayın.|
|[AfxTermExtensionModule](#afxtermextensionmodule)|Her işlem DLL 'den ayrıldığında MFC 'nin MFC uzantı DLL 'sini temizlemesini sağlar.|

## <a name="afx_ext_class"></a>AFX_EXT_CLASS

[MFC uzantı dll 'leri](../../build/extension-dlls.md) , sınıfları dışarı aktarmak için AFX_EXT_CLASS makroları kullanır; MFC uzantısı DLL 'sine bağlanan yürütülebilir dosyalar, sınıfları içeri aktarmak için makrosunu kullanır.

### <a name="remarks"></a>Açıklamalar

AFX_EXT_CLASS makroyla, MFC uzantı DLL 'sini oluşturmak için kullanılan üst bilgi dosyaları, DLL 'ye bağlanan yürütülebilir dosyalarla birlikte kullanılabilir.

DLL 'nizin başlık dosyasında, sınıfınızın bildirimine aşağıdaki şekilde AFX_EXT_CLASS anahtar sözcüğünü ekleyin:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Daha fazla bilgi için bkz. [AFX_EXT_CLASS kullanarak dışarı ve Içeri aktarma](../../build/exporting-and-importing-using-afx-ext-class.md).

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxv_dll. h

## <a name="afx_manage_state"></a>AFX_MANAGE_STATE

DLL içindeki bir içe aktarılmış işlevi korumak için bu makroyu çağırın.

### <a name="syntax"></a>Sözdizimi

```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>Parametreler

*pModuleState*<br/>
`AFX_MODULE_STATE` yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu makro çağrıldığında *pModuleState* , en yakın kapsayan kapsamın geri kalanı için etkin modül durumudur. Kapsam ayrıldıktan sonra, önceki etkin modül durumu otomatik olarak geri yüklenir.
`AFX_MODULE_STATE` yapısı, modül için genel verileri, diğer bir deyişle, gönderilen veya atılan modül durumunun bölümünü içerir.

Varsayılan olarak, MFC kaynak şablonunu yüklemek için ana uygulamanın kaynak tanıtıcısını kullanır. Dll 'de bir iletişim kutusu Başlatan gibi bir DLL 'de içe aktarılmış işleviniz varsa, bu şablon aslında DLL modülünde depolanır. Kullanılacak doğru tanıtıcının modül durumunu değiştirmeniz gerekir. Bunu, işlevin başlangıcına aşağıdaki kodu ekleyerek yapabilirsiniz:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Bu, geçerli modülün durumunu geçerli kapsamın sonuna kadar [AfxGetStaticModuleState](#afxgetstaticmodulestate) öğesinden döndürülen durum ile değiştirir.

Modül durumları ve MFC hakkında daha fazla bilgi için [yeni belgeler, pencereler ve görünümler oluşturma](../creating-new-documents-windows-and-views.md) ve [Teknik NOTTA 58](../tn058-mfc-module-state-implementation.md)"MFC modüllerinin durum verilerini yönetme" bölümüne bakın.

> [!NOTE]
>  MFC bir derleme için bir etkinleştirme bağlamı oluşturduğunda, bağlamı oluşturmak için [Afxwininit](application-information-and-management.md#afxwininit) kullanır ve etkinleştirmek ve devre dışı bırakmak için `AFX_MANAGE_STATE`. Ayrıca, MFC kodunun Kullanıcı DLL tarafından seçilen uygun etkinleştirme bağlamında yürütülmesine izin vermek için MFC DLL 'Lerinin yanı sıra, `AFX_MANAGE_STATE` statik MFC kitaplıkları için de etkinleştirilmiş olduğunu unutmayın. Daha fazla bilgi için bkz. [MFC modül durumunda etkinleştirme bağlamları Için destek](../support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxstat_. h

## <a name="a-nameafxoleinitmodulea-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> AfxOleInitModule

MFC 'ye dinamik olarak bağlanan normal bir MFC DLL 'den OLE desteği için MFC OLE DLL 'sini başlatmak üzere normal MFC DLL 'sinin `CWinApp::InitInstance` işlevinde bu işlevi çağırın.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>Açıklamalar

MFC OLE DLL 'i MFC uzantısı DLL 'dir; bir MFC uzantısı DLL 'sinin `CDynLinkLibrary` zincirine kablolu olması için, onu kullanacak her modülün bağlamında bir `CDynLinkLibrary` nesnesi oluşturması gerekir. `AfxOleInitModule`, normal MFC DLL 'inin `CDynLinkLibrary` nesne zincirine kablolu olması için normal MFC DLL bağlamındaki `CDynLinkLibrary` nesnesini oluşturur.

OLE denetimi oluşturuyorsanız ve `COleControlModule`kullanıyorsanız, `COleControlModule` çağrılarının `InitInstance` üye işlevi `AfxOleInitModule`için `AfxOleInitModule` çağırmamalıdır.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: \<afxdll_. h >

## <a name="afxnetinitmodule"></a>AfxNetInitModule

MFC 'ye dinamik olarak bağlanan normal bir MFC DLL 'den MFC Yuvaları desteği için, MFC Yuvaları DLL 'sini başlatmak üzere normal MFC DLL 'sinin `CWinApp::InitInstance` işlevinde bu işleve bir çağrı ekleyin.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>Açıklamalar

MFC Yuvaları DLL 'i bir MFC uzantısı DLL 'si; bir MFC uzantısı DLL 'sinin `CDynLinkLibrary` zincirine kablolu olması için, onu kullanacak her modülün bağlamında bir `CDynLinkLibrary` nesnesi oluşturması gerekir. `AfxNetInitModule`, normal MFC DLL 'inin `CDynLinkLibrary` nesne zincirine kablolu olması için normal MFC DLL bağlamındaki `CDynLinkLibrary` nesnesini oluşturur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<afxdll_. h >

## <a name="afxgetambientactctx"></a>Afxgetambentactctx

Bu işlevi, MFC 'nin WinSxS davranışını etkileyen modül başına durum bayrağının geçerli durumunu almak için kullanın.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>Dönüş Değeri

Modül durumu bayrağı geçerli değeri.

### <a name="remarks"></a>Açıklamalar

Bayrak ayarlandığında (varsayılan olarak) ve bir iş parçacığı bir MFC modülüne girdiğinde (bkz. [AFX_MANAGE_STATE](#afx_manage_state)), modülün bağlamı etkinleştirilir.

Bayrak ayarlanmamışsa, modülün bağlamı girişte etkinleştirilmez.

Modülün bağlamı, genellikle modül kaynaklarına gömülü olan bildiriminden belirlenir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcomctl32. h

## <a name="afxgetstaticmodulestate"></a>AfxGetStaticModuleState

Başlatmadan önce modül durumunu ayarlamak ve/veya sildikten sonra önceki modül durumunu geri yüklemek için bu işlevi çağırın.

### <a name="syntax"></a>Sözdizimi

```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>Dönüş Değeri

`AFX_MODULE_STATE` yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`AFX_MODULE_STATE` yapısı, modül için genel verileri, diğer bir deyişle, gönderilen veya atılan modül durumunun bölümünü içerir.

Varsayılan olarak, MFC kaynak şablonunu yüklemek için ana uygulamanın kaynak tanıtıcısını kullanır. Dll 'de bir iletişim kutusu Başlatan gibi bir DLL 'de içe aktarılmış işleviniz varsa, bu şablon aslında DLL modülünde depolanır. Kullanılacak doğru tanıtıcının modül durumunu değiştirmeniz gerekir. Bunu, işlevin başlangıcına aşağıdaki kodu ekleyerek yapabilirsiniz:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Bu, geçerli modül durumunu geçerli kapsamın sonuna kadar `AfxGetStaticModuleState` döndürülen durum ile değiştirir.

Modül durumları ve MFC hakkında daha fazla bilgi için [yeni belgeler, pencereler ve görünümler oluşturma](../creating-new-documents-windows-and-views.md) ve [Teknik NOTTA 58](../tn058-mfc-module-state-implementation.md)"MFC modüllerinin durum verilerini yönetme" bölümüne bakın.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxstat_. h

## <a name="afxinitextensionmodule"></a>AfxInitExtensionModule

DLL 'yi başlatmak için bu işlevi bir MFC uzantı DLL 'sinin `DllMain` çağırın.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>Parametreler

*durumunda*<br/>
Başlangıçtan sonra MFC uzantısı DLL modülünün durumunu içerecek [AFX_EXTENSION_MODULE yapısı](afx-extension-module-structure.md) yapısına yönelik bir başvuru. Durum, `DllMain` girilmeden önce yürütülen normal statik nesne oluşturma bir parçası olarak MFC uzantı DLL tarafından başlatılan çalışma zamanı sınıfı nesnelerinin bir kopyasını içerir.

*hModule*<br/>
MFC uzantı DLL modülünün tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

MFC uzantı DLL 'SI başarıyla başlatılmışsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Örneğin:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;
...
```

`AfxInitExtensionModule`, DLL 'nin HMODULE kopyasını oluşturur ve DLL 'nin çalışma zamanı sınıflarını (`CRuntimeClass` yapılarını) ve nesne fabrikalarını (`COleObjectFactory` nesneleri), daha sonra `CDynLinkLibrary` nesnesi oluşturulduğunda kullanmak üzere yakalar.
MFC uzantı dll 'Lerinin `DllMain` işlevinde iki şey yapması gerekir:

- [AfxInitExtensionModule 'ü](#afxinitextensionmodule) çağırın ve dönüş değerini denetleyin.

- DLL [CRuntimeClass yapı](cruntimeclass-structure.md) nesnelerini dışarı aktaracaktır veya kendi özel kaynaklarına sahip olursa `CDynLinkLibrary` nesnesi oluşturun.

Her işlem MFC uzantısı DLL 'sinden ayrıldığında (işlem çıktığında veya bir `AfxFreeLibrary` çağrısının sonucu olarak DLL kaldırıldığında gerçekleşir) MFC uzantı DLL 'sini temizlemek için `AfxTermExtensionModule` çağırabilirsiniz.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxdll_. h

## <a name="afxsetambientactctx"></a>Afxsetambentactctx

Bu işlevi, MFC 'nin WinSxS davranışını etkileyen modül başına durum bayrağını ayarlamak için kullanın.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI AfxSetAmbientActCtx(BOOL bSet);
```

### <a name="parameters"></a>Parametreler

*bSet*<br/>
Modül durumu bayrağının yeni değeri.

### <a name="remarks"></a>Açıklamalar

Bayrak ayarlandığında (varsayılan olarak) ve bir iş parçacığı bir MFC modülüne girdiğinde (bkz. [AFX_MANAGE_STATE](#afx_manage_state)), modülün bağlamı etkinleştirilir.
Bayrak ayarlanmamışsa, modülün bağlamı girişte etkinleştirilmez.
Modülün bağlamı, genellikle modül kaynaklarına gömülü olan bildiriminden belirlenir.

### <a name="example"></a>Örnek

```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
}
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcomctl32. h

## <a name="afxtermextensionmodule"></a>AfxTermExtensionModule

Bu işlevi, MFC 'nin her bir işlem DLL 'den ayrıldığında (işlem çıktığında veya `AfxFreeLibrary` çağrısının bir sonucu olarak kaldırıldığında gerçekleşir) MFC uzantı DLL 'sini temizlemesini sağlamak için çağırın.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );
```

### <a name="parameters"></a>Parametreler

*durumunda*<br/>
MFC uzantı DLL modülünün durumunu içeren [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) yapısına yönelik bir başvuru.

*Topu*<br/>
TRUE ise, tüm MFC uzantı DLL modüllerini temizleyin. Aksi takdirde, yalnızca geçerli DLL modülünü temizleyin.

### <a name="remarks"></a>Açıklamalar

`AfxTermExtensionModule`, modüle eklenen tüm yerel depolamayı silecek ve ileti eşleme önbelleğindeki tüm girdileri kaldıracak. Örneğin:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;

        new CMyDynLinkLibrary(NVC_MFC_DLLDLL);

    }
    else if (dwReason == DLL_PROCESS_DETACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Terminating!\n");

        // Terminate the library before destructors are called
        AfxTermExtensionModule(NVC_MFC_DLLDLL);
    }
    return 1;   // ok
}
```

Uygulamanız MFC uzantı dll 'Lerini dinamik olarak yükler ve serbest bırakır, `AfxTermExtensionModule`çağırdığınızdan emin olun. Çoğu MFC uzantı dll 'Leri dinamik olarak yüklenmediğinden (genellikle içeri aktarma kitaplıkları aracılığıyla bağlantılarlarsa) `AfxTermExtensionModule` çağrısı genellikle gerekli değildir.

MFC uzantı dll 'Lerinin `DllMain`[AfxInitExtensionModule](#afxinitextensionmodule) çağrısı gerekir. DLL, [CRuntimeClass](cruntimeclass-structure.md) nesnelerini dışarı aktaracaktır veya kendi özel kaynaklarına sahip olursa, `DllMain`bir `CDynLinkLibrary` nesnesi oluşturmanız da gerekir.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxdll_. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[MFC Modüllerinin Durum Verisini Yönetme](../managing-the-state-data-of-mfc-modules.md)<br/>
