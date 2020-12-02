---
title: Dll 'Leri yönetmeye yönelik makrolar ve işlevler
description: MFC makroları ve DLL 'Leri yönetmeye yönelik işlevler için başvuru kılavuzu.
ms.date: 11/30/2020
helpviewer_keywords:
- module macros in MFC
ms.openlocfilehash: b70c4506d49f656e1570f2500cfaa39c28053291
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440327"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Dll 'Leri yönetmeye yönelik makrolar ve işlevler

| Ad | Açıklama |
|--|--|
| [`AFX_EXT_CLASS`](#afx_ext_class)] | Sınıfları dışarı aktarır. |
| [`AFX_MANAGE_STATE`](#afx_manage_state) | DLL içindeki bir içe aktarılmış işlevi koruma. |
| [`AfxOleInitModule`](#afxoleinitmodule) | MFC 'ye dinamik olarak bağlanan normal bir MFC DLL 'den OLE desteği sağlar. |
| [`AfxNetInitModule`](#afxnetinitmodule) | MFC 'ye dinamik olarak bağlanan normal bir MFC DLL 'den MFC Yuvaları desteği sağlar. |
| [`AfxGetAmbientActCtx`](#afxgetambientactctx) | Modül başına durum bayrağının geçerli durumunu alır. |
| [`AfxGetStaticModuleState`](#afxgetstaticmodulestate) | Başlatmadan önce modül durumunu ayarlar ve temizleme sonrasında önceki modül durumunu geri yükler. |
| [`AfxInitExtensionModule`](#afxinitextensionmodule) | DLL 'yi başlatır. |
| [`AfxSetAmbientActCtx`](#afxsetambientactctx) | MFC 'nin WinSxS davranışını etkileyen modül başına durum bayrağını ayarlayın. |
| [`AfxTermExtensionModule`](#afxtermextensionmodule) | Her işlem DLL 'den ayrıldığında MFC 'nin MFC uzantı DLL 'sini temizlemesini sağlar. |

## <a name="afx_ext_class"></a><a name="afx_ext_class"></a> `AFX_EXT_CLASS`

[MFC uzantı dll 'leri](../../build/extension-dlls.md) `AFX_EXT_CLASS` sınıfları dışarı aktarmak için MAKROYU kullanır; mfc uzantısı DLL 'sine bağlanan yürütülebilir dosyalar, sınıfları içeri aktarmak için makroyu kullanır.

### <a name="remarks"></a>Açıklamalar

Makro ile `AFX_EXT_CLASS` , MFC UZANTı dll 'sini oluşturmak için kullanılan üst bilgi dosyaları, dll 'ye bağlanan yürütülebilir dosyalarla birlikte kullanılabilir.

DLL 'nizin başlık dosyasında, `AFX_EXT_CLASS` anahtar sözcüğünü aşağıdaki şekilde sınıfınızın bildirimine ekleyin:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Daha fazla bilgi için bkz. öğesini [kullanarak `AFX_EXT_CLASS` dışarı ve içeri aktarma ](../../build/exporting-and-importing-using-afx-ext-class.md).

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<afxv_dll.h>

## <a name="afx_manage_state"></a><a name="afx_manage_state"></a> `AFX_MANAGE_STATE`

DLL içindeki bir içe aktarılmış işlevi korumak için bu makroyu çağırın.

### <a name="syntax"></a>Sözdizimi

```cpp
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>Parametreler

*`pModuleState`*<br/>
Bir yapıya yönelik işaretçi `AFX_MODULE_STATE` .

### <a name="remarks"></a>Açıklamalar

Bu makro çağrıldığında, *`pModuleState`* en yakın kapsayan kapsamın geri kalanı için etkin modül durumudur. Kapsam ayrıldıktan sonra, önceki etkin modül durumu otomatik olarak geri yüklenir.

`AFX_MODULE_STATE`Yapı, modül için genel verileri, diğer bir deyişle, gönderilen veya polalanan modül durumunun bölümünü içerir.

Varsayılan olarak, MFC kaynak şablonunu yüklemek için ana uygulamanın kaynak tanıtıcısını kullanır. Dll 'de bir iletişim kutusu Başlatan gibi bir DLL 'de içe aktarılmış işleviniz varsa, kaynak şablonu DLL modülünde depolanır. Kullanılacak doğru tanıtıcının modül durumunu değiştirdiğinizden emin olun. İşlevin başlangıcına aşağıdaki kodu ekleyerek durumu değiştirebilirsiniz:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Bu makro geçerli modül durumunu [`AfxGetStaticModuleState`](#afxgetstaticmodulestate) geçerli kapsamın sonuna kadar döndürülen durum ile değiştirir.

Modül durumları ve MFC hakkında daha fazla bilgi için bkz. [MFC modüllerinin durum verilerini yönetme](../managing-the-state-data-of-mfc-modules.md) ve [Teknik not58](../tn058-mfc-module-state-implementation.md).

> [!NOTE]
> MFC bir derleme için bir etkinleştirme bağlamı oluşturduğunda, [`AfxWinInit`](application-information-and-management.md#afxwininit) bağlamını oluşturmak ve `AFX_MANAGE_STATE` bunu etkinleştirmek ve devre dışı bırakmak için kullanılır. Ayrıca, MFC `AFX_MANAGE_STATE` kodunun Kullanıcı dll tarafından seçilen uygun etkinleştirme bağlamında yürütülmesine izin vermek IÇIN MFC DLL 'lerinin yanı sıra STATIK MFC kitaplıkları için de etkinleştirilmiş olduğunu unutmayın. Daha fazla bilgi için bkz. [MFC modül durumunda etkinleştirme bağlamları Için destek](../support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<afxstat_.h>

## <a name="a-nameafxoleinitmodule-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> `AfxOleInitModule`

MFC 'ye dinamik olarak bağlanan normal bir MFC DLL 'den OLE desteği için `CWinApp::InitInstance` MFC OLE dll 'sini başlatmak üzere normal MFC DLL 'nin işlevindeki bu işlevi çağırın.

### <a name="syntax"></a>Syntax

```cpp
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>Açıklamalar

MFC OLE DLL 'i MFC uzantısı DLL 'dir; bir MFC uzantısı DLL 'inin bir zincirine kablolu olması için, onu `CDynLinkLibrary` `CDynLinkLibrary` kullanacak her modülün bağlamında bir nesne oluşturması gerekir. `AfxOleInitModule` normal mfc dll `CDynLinkLibrary` `CDynLinkLibrary` 'inin nesne zincirine kablolu olması için NESNEYI normal MFC DLL içeriğinde oluşturur.

OLE denetimi oluşturuyorsanız ve kullanıyorsanız `COleControlModule` , `AfxOleInitModule` `InitInstance` çağrılar için üye işlevi olduğundan çağrılırsınız `COleControlModule` `AfxOleInitModule` .

### <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<afxdll_.h>

## <a name="afxnetinitmodule"></a><a name="afxnetinitmodule"></a> `AfxNetInitModule`

MFC 'ye dinamik olarak bağlanan normal bir MFC DLL 'den MFC Yuvaları desteği için, `CWinApp::InitInstance` MFC YUVALARı dll 'sini başlatmak üzere normal MFC DLL 'nin işlevinde bu işleve bir çağrı ekleyin.

### <a name="syntax"></a>Syntax

```cpp
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>Açıklamalar

MFC Yuvaları DLL 'i bir MFC uzantısı DLL 'si; bir MFC uzantısı DLL 'inin bir zincirine kablolu olması için, onu `CDynLinkLibrary` `CDynLinkLibrary` kullanacak her modülün bağlamında bir nesne oluşturması gerekir. `AfxNetInitModule` normal mfc dll `CDynLinkLibrary` `CDynLinkLibrary` 'inin nesne zincirine kablolu olması için NESNEYI normal MFC DLL içeriğinde oluşturur.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<afxdll_.h>

## <a name="afxgetambientactctx"></a><a name="afxgetambientactctx"></a> `AfxGetAmbientActCtx`

Bu işlevi, MFC 'nin WinSxS davranışını etkileyen modül başına durum bayrağının geçerli durumunu almak için kullanın.

### <a name="syntax"></a>Syntax

```cpp
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>Dönüş Değeri

Modül durumu bayrağı geçerli değeri.

### <a name="remarks"></a>Açıklamalar

Bayrak ayarlandığında (varsayılan olarak) ve bir iş parçacığı bir MFC modülüne (bkz [`AFX_MANAGE_STATE`](#afx_manage_state) .) girdiğinde, modülün bağlamı etkinleştirilir.

Bayrak ayarlanmamışsa, modülün bağlamı girişte etkinleştirilmez.

Modülün bağlamı, genellikle modül kaynaklarına gömülü olan bildiriminden belirlenir.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<afxcomctl32.h>

## <a name="afxgetstaticmodulestate"></a><a name="afxgetstaticmodulestate"></a> `AfxGetStaticModuleState`

Başlatmadan önce modül durumunu ayarlamak ve temizleme sonrasında önceki modül durumunu geri yüklemek için bu işlevi çağırın.

### <a name="syntax"></a>Syntax

```cpp
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>Dönüş Değeri

Bir yapıya yönelik işaretçi `AFX_MODULE_STATE` .

### <a name="remarks"></a>Açıklamalar

`AFX_MODULE_STATE`Yapı, modül için genel verileri, diğer bir deyişle, gönderilen veya polalanan modül durumunun bölümünü içerir.

Varsayılan olarak, MFC kaynak şablonunu yüklemek için ana uygulamanın kaynak tanıtıcısını kullanır. Dll 'de bir iletişim kutusu Başlatan gibi bir DLL 'de içe aktarılmış işleviniz varsa, kaynak şablonu DLL modülünde depolanır. Kullanılacak doğru tanıtıcının modül durumunu değiştirdiğinizden emin olun. İşlevin başlangıcına aşağıdaki kodu ekleyerek durumu değiştirebilirsiniz:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Bu makro geçerli modül durumunu `AfxGetStaticModuleState` geçerli kapsamın sonuna kadar döndürülen durum ile değiştirir.

Modül durumları ve MFC hakkında daha fazla bilgi için bkz. [MFC modüllerinin durum verilerini yönetme](../managing-the-state-data-of-mfc-modules.md) ve [Teknik not58](../tn058-mfc-module-state-implementation.md).

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<afxstat_.h>

## <a name="afxinitextensionmodule"></a><a name="afxinitextensionmodule"></a> `AfxInitExtensionModule`

DLL 'yi başlatmak için bu işlevi bir MFC uzantı DLL dosyasında çağırın `DllMain` .

### <a name="syntax"></a>Sözdizimi

```cpp
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>Parametreler

*`state`*<br/>
Başlatma işleminden sonra MFC uzantı DLL modülünün durumunu içerecek [ `AFX_EXTENSION_MODULE` Yapı](afx-extension-module-structure.md) yapısına başvuru. Durum, daha önce yürütülen normal statik nesne oluşturma bir parçası olarak MFC uzantı DLL tarafından başlatılan çalışma zamanı sınıfı nesnelerinin bir kopyasını içerir `DllMain` .

*`hModule`*<br/>
MFC uzantı DLL modülünün tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

`TRUE` MFC uzantı DLL 'SI başarıyla başlatılmışsa; Aksi takdirde, `FALSE` .

### <a name="remarks"></a>Açıklamalar

Örnek:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL;
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

`AfxInitExtensionModule` DLL 'nin HMODULE kopyasını oluşturur ve DLL 'nin çalışma zamanı sınıflarını ( `CRuntimeClass` yapıları) ve ayrıca `COleObjectFactory` nesne oluşturulduğunda kullanmak üzere nesne fabrikalarını (nesneleri) yakalar `CDynLinkLibrary` .
MFC uzantı dll 'Lerinin kendi işlevleriyle iki şey yapması gerekir `DllMain` :

- [`AfxInitExtensionModule`](#afxinitextensionmodule)Döndürülen değeri çağırın ve denetleyin.

- `CDynLinkLibrary`DLL, [ `CRuntimeClass` Yapı](cruntimeclass-structure.md) nesnelerini dışarı aktaracaktır veya kendi özel kaynaklarına sahipse bir nesne oluşturun.

`AfxTermExtensionModule`Her bir Işlem MFC UZANTı dll 'sinden ayrıldığında (işlem çıktığında veya dll bir çağrı tarafından kaldırıldığında gerçekleşir) MFC UZANTı dll 'sini temizlemeyi çağırabilirsiniz `AfxFreeLibrary` .

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<afxdll_.h>

## <a name="afxsetambientactctx"></a><a name="afxsetambientactctx"></a> `AfxSetAmbientActCtx`

Bu işlevi, MFC 'nin WinSxS davranışını etkileyen modül başına durum bayrağını ayarlamak için kullanın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI AfxSetAmbientActCtx(BOOL bSet);
```

### <a name="parameters"></a>Parametreler

*`bSet`*<br/>
Modül durumu bayrağının yeni değeri.

### <a name="remarks"></a>Açıklamalar

Bayrak ayarlandığında (varsayılan olarak) ve bir iş parçacığı bir MFC modülüne (bkz [`AFX_MANAGE_STATE`](#afx_manage_state) .) girdiğinde, modülün bağlamı etkinleştirilir.
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

**Üst bilgi:**\<afxcomctl32.h>

## <a name="afxtermextensionmodule"></a><a name="afxtermextensionmodule"></a> `AfxTermExtensionModule`

MFC 'nin her bir işlem DLL 'den ayrıldığında (işlem çıktığında veya DLL bir çağrı tarafından kaldırıldığında gerçekleşir) MFC uzantı DLL 'sini temizlemesini sağlamak için bu işlevi çağırın `AfxFreeLibrary` .

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI AfxTermExtensionModule( AFX_EXTENSION_MODULE& state, BOOL bAll = FALSE );
```

### <a name="parameters"></a>Parametreler

*`state`*<br/>
[`AFX_EXTENSION_MODULE`](afx-extension-module-structure.md)MFC UZANTı dll modülünün durumunu içeren yapıya başvuru.

*`bAll`*<br/>
TRUE ise, tüm MFC uzantı DLL modüllerini temizleyin. Aksi takdirde, yalnızca geçerli DLL modülünü temizleyin.

### <a name="remarks"></a>Açıklamalar

`AfxTermExtensionModule` , modüle bağlı tüm yerel depolamayı siler ve ileti eşleme önbelleğinden gelen girdileri kaldırır. Örnek:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL;
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

Uygulamanız MFC uzantı dll 'Lerini dinamik olarak yüklerse ve serbest bıraktığında, ' i çağırmayı unutmayın `AfxTermExtensionModule` . Çoğu MFC uzantı dll 'Leri dinamik olarak yüklenmediğinden (normalde içeri aktarma kitaplıkları aracılığıyla bağlantılarlarsa), bu çağrı `AfxTermExtensionModule` genellikle gerekli değildir.

MFC uzantı dll 'Lerinin [`AfxInitExtensionModule`](#afxinitextensionmodule) ' de çağırması gerekir `DllMain` . DLL, nesneleri dışa aktarır [`CRuntimeClass`](cruntimeclass-structure.md) veya kendi özel kaynaklarına sahipse, içinde bir nesnesi de oluşturmanız gerekir `CDynLinkLibrary` `DllMain` .

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<afxdll_.h>

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
[`AfxMessageBox`](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[MFC modüllerinin durum verisini yönetme](../managing-the-state-data-of-mfc-modules.md)<br/>
