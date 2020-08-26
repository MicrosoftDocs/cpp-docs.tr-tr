---
title: Dll 'Leri yönetmeye yönelik makrolar ve Işlevler
ms.date: 03/27/2019
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
ms.openlocfilehash: e4170ba95775fd3380837673a76a8adafc8ad011
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837195"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Dll 'Leri yönetmeye yönelik makrolar ve Işlevler

|Ad|Açıklama|
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

## <a name="afx_ext_class"></a><a name="afx_ext_class"></a> AFX_EXT_CLASS

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

## <a name="afx_manage_state"></a><a name="afx_manage_state"></a> AFX_MANAGE_STATE

DLL içindeki bir içe aktarılmış işlevi korumak için bu makroyu çağırın.

### <a name="syntax"></a>Söz dizimi

```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>Parametreler

*pModuleState*<br/>
Bir yapıya yönelik işaretçi `AFX_MODULE_STATE` .

### <a name="remarks"></a>Açıklamalar

Bu makro çağrıldığında *pModuleState* , en yakın kapsayan kapsamın geri kalanı için etkin modül durumudur. Kapsam ayrıldıktan sonra, önceki etkin modül durumu otomatik olarak geri yüklenir.
`AFX_MODULE_STATE`Yapı, modül için genel verileri, diğer bir deyişle, gönderilen veya polalanan modül durumunun bölümünü içerir.

Varsayılan olarak, MFC kaynak şablonunu yüklemek için ana uygulamanın kaynak tanıtıcısını kullanır. Dll 'de bir iletişim kutusu Başlatan gibi bir DLL 'de içe aktarılmış işleviniz varsa, bu şablon aslında DLL modülünde depolanır. Kullanılacak doğru tanıtıcının modül durumunu değiştirmeniz gerekir. Bunu, işlevin başlangıcına aşağıdaki kodu ekleyerek yapabilirsiniz:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Bu, geçerli modülün durumunu geçerli kapsamın sonuna kadar [AfxGetStaticModuleState](#afxgetstaticmodulestate) öğesinden döndürülen durum ile değiştirir.

Modül durumları ve MFC hakkında daha fazla bilgi için [yeni belgeler, pencereler ve görünümler oluşturma](../creating-new-documents-windows-and-views.md) ve [Teknik NOTTA 58](../tn058-mfc-module-state-implementation.md)"MFC modüllerinin durum verilerini yönetme" bölümüne bakın.

> [!NOTE]
> MFC bir derleme için bir etkinleştirme bağlamı oluşturduğunda, bağlamı oluşturmak ve etkinleştirmek ve devre dışı bırakmak için [Afxwininit](application-information-and-management.md#afxwininit) kullanır `AFX_MANAGE_STATE` . Ayrıca, MFC `AFX_MANAGE_STATE` kodunun Kullanıcı dll tarafından seçilen uygun etkinleştirme bağlamında yürütülmesine izin vermek IÇIN MFC DLL 'lerinin yanı sıra STATIK MFC kitaplıkları için de etkinleştirilmiş olduğunu unutmayın. Daha fazla bilgi için bkz. [MFC modül durumunda etkinleştirme bağlamları Için destek](../support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxstat_. h

## <a name="a-nameafxoleinitmodule-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> AfxOleInitModule

MFC 'ye dinamik olarak bağlanan normal bir MFC DLL 'den OLE desteği için `CWinApp::InitInstance` MFC OLE dll 'sini başlatmak üzere normal MFC DLL 'nin işlevindeki bu işlevi çağırın.

### <a name="syntax"></a>Syntax

```cpp
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>Açıklamalar

MFC OLE DLL 'i MFC uzantısı DLL 'dir; bir MFC uzantısı DLL 'inin bir zincirine kablolu olması için, onu `CDynLinkLibrary` `CDynLinkLibrary` kullanacak her modülün bağlamında bir nesne oluşturması gerekir. `AfxOleInitModule` normal mfc dll `CDynLinkLibrary` `CDynLinkLibrary` 'inin nesne zincirine kablolu olması için NESNEYI normal MFC DLL içeriğinde oluşturur.

OLE denetimi oluşturuyorsanız ve kullanıyorsanız `COleControlModule` , `AfxOleInitModule` `InitInstance` çağrılar için üye işlevi olduğundan çağırmamalıdır `COleControlModule` `AfxOleInitModule` .

### <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<afxdll_.h>

## <a name="afxnetinitmodule"></a><a name="afxnetinitmodule"></a> AfxNetInitModule

MFC 'ye dinamik olarak bağlanan normal bir MFC DLL 'den MFC Yuvaları desteği için, `CWinApp::InitInstance` MFC YUVALARı dll 'sini başlatmak üzere normal MFC DLL 'nin işlevinde bu işleve bir çağrı ekleyin.

### <a name="syntax"></a>Syntax

```cpp
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>Açıklamalar

MFC Yuvaları DLL 'i bir MFC uzantısı DLL 'si; bir MFC uzantısı DLL 'inin bir zincirine kablolu olması için, onu `CDynLinkLibrary` `CDynLinkLibrary` kullanacak her modülün bağlamında bir nesne oluşturması gerekir. `AfxNetInitModule` normal mfc dll `CDynLinkLibrary` `CDynLinkLibrary` 'inin nesne zincirine kablolu olması için NESNEYI normal MFC DLL içeriğinde oluşturur.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<afxdll_.h>

## <a name="afxgetambientactctx"></a><a name="afxgetambientactctx"></a> Afxgetambentactctx

Bu işlevi, MFC 'nin WinSxS davranışını etkileyen modül başına durum bayrağının geçerli durumunu almak için kullanın.

### <a name="syntax"></a>Syntax

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

## <a name="afxgetstaticmodulestate"></a><a name="afxgetstaticmodulestate"></a> AfxGetStaticModuleState

Başlatmadan önce modül durumunu ayarlamak ve/veya sildikten sonra önceki modül durumunu geri yüklemek için bu işlevi çağırın.

### <a name="syntax"></a>Syntax

```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>Dönüş Değeri

Bir yapıya yönelik işaretçi `AFX_MODULE_STATE` .

### <a name="remarks"></a>Açıklamalar

`AFX_MODULE_STATE`Yapı, modül için genel verileri, diğer bir deyişle, gönderilen veya polalanan modül durumunun bölümünü içerir.

Varsayılan olarak, MFC kaynak şablonunu yüklemek için ana uygulamanın kaynak tanıtıcısını kullanır. Dll 'de bir iletişim kutusu Başlatan gibi bir DLL 'de içe aktarılmış işleviniz varsa, bu şablon aslında DLL modülünde depolanır. Kullanılacak doğru tanıtıcının modül durumunu değiştirmeniz gerekir. Bunu, işlevin başlangıcına aşağıdaki kodu ekleyerek yapabilirsiniz:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Bu, geçerli modül durumunu `AfxGetStaticModuleState` geçerli kapsamın sonuna kadar döndürülen durum ile değiştirir.

Modül durumları ve MFC hakkında daha fazla bilgi için [yeni belgeler, pencereler ve görünümler oluşturma](../creating-new-documents-windows-and-views.md) ve [Teknik NOTTA 58](../tn058-mfc-module-state-implementation.md)"MFC modüllerinin durum verilerini yönetme" bölümüne bakın.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxstat_. h

## <a name="afxinitextensionmodule"></a>AfxInitExtensionModule

DLL 'yi başlatmak için bu işlevi bir MFC uzantı DLL dosyasında çağırın `DllMain` .

### <a name="syntax"></a>Söz dizimi

```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>Parametreler

*durumunda*<br/>
Başlangıçtan sonra MFC uzantısı DLL modülünün durumunu içerecek [AFX_EXTENSION_MODULE yapısı](afx-extension-module-structure.md) yapısına yönelik bir başvuru. Durum, daha önce yürütülen normal statik nesne oluşturma bir parçası olarak MFC uzantı DLL tarafından başlatılan çalışma zamanı sınıfı nesnelerinin bir kopyasını içerir `DllMain` .

*hModule*<br/>
MFC uzantı DLL modülünün tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

MFC uzantı DLL 'SI başarıyla başlatılmışsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Örnek:

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

`AfxInitExtensionModule` DLL 'nin HMODULE kopyasını oluşturur ve DLL 'nin çalışma zamanı sınıfları ( `CRuntimeClass` yapıları) ile nesne fabrikaları ( `COleObjectFactory` nesneler), daha sonra `CDynLinkLibrary` nesne oluşturulduğunda kullanılmak üzere.
MFC uzantı dll 'Lerinin kendi işlevleriyle iki şey yapması gerekir `DllMain` :

- [AfxInitExtensionModule 'ü](#afxinitextensionmodule) çağırın ve dönüş değerini denetleyin.

- `CDynLinkLibrary`Dll [CRuntimeClass yapı](cruntimeclass-structure.md) nesnelerini dışarı aktaracaktır veya kendi özel kaynaklarına sahipse bir nesne oluşturun.

`AfxTermExtensionModule`Her bir Işlem MFC UZANTı dll 'sinden ayrıldığında (işlem çıktığında ya da dll bir çağrının sonucu olarak kaldırıldığında gerçekleşir) MFC UZANTı dll 'sini temizlemeyi çağırabilirsiniz `AfxFreeLibrary` .

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxdll_. h

## <a name="afxsetambientactctx"></a><a name="afxsetambientactctx"></a> Afxsetambentactctx

Bu işlevi, MFC 'nin WinSxS davranışını etkileyen modül başına durum bayrağını ayarlamak için kullanın.

### <a name="syntax"></a>Söz dizimi

```cpp
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

## <a name="afxtermextensionmodule"></a><a name="afxtermextensionmodule"></a> AfxTermExtensionModule

MFC 'nin her bir işlem DLL 'den ayrıldığında (işlem çıktığında veya DLL bir çağrının sonucu olarak kaldırıldığında gerçekleşir) MFC uzantı DLL 'sini temizlemesini sağlamak için bu işlevi çağırın `AfxFreeLibrary` .

### <a name="syntax"></a>Söz dizimi

```cpp
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );
```

### <a name="parameters"></a>Parametreler

*durumunda*<br/>
MFC uzantı DLL modülünün durumunu içeren [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) yapısına yönelik bir başvuru.

*Topu*<br/>
TRUE ise, tüm MFC uzantı DLL modüllerini temizleyin. Aksi takdirde, yalnızca geçerli DLL modülünü temizleyin.

### <a name="remarks"></a>Açıklamalar

`AfxTermExtensionModule` , modüle bağlı tüm yerel depolamayı siler ve ileti eşleme önbelleğinden gelen girdileri kaldırır. Örnek:

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

Uygulamanız MFC uzantı dll 'Lerini dinamik olarak yüklerse ve serbest bıraktığında, ' i çağırmayı unutmayın `AfxTermExtensionModule` . Çoğu MFC uzantı dll 'Leri dinamik olarak yüklenmediğinden (genellikle içeri aktarma kitaplıkları aracılığıyla bağlantılarlarsa), çağrısı `AfxTermExtensionModule` genellikle gerekli değildir.

MFC uzantı dll 'Lerinin, içinde [AfxInitExtensionModule](#afxinitextensionmodule) çağrısı yapması gerekir `DllMain` . DLL [CRuntimeClass](cruntimeclass-structure.md) nesnelerini dışarı aktaracaktır veya kendi özel kaynaklarına sahipse, içinde bir nesnesi de oluşturmanız gerekir `CDynLinkLibrary` `DllMain` .

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxdll_. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[MFC modüllerinin durum verilerini yönetme](../managing-the-state-data-of-mfc-modules.md)<br/>
