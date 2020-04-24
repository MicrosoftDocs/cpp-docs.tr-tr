---
title: DL'leri Yönetmek için Makrolar ve Fonksiyonlar
ms.date: 03/27/2019
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
ms.openlocfilehash: 42a08ff2e806acae6713c9df3fe170f7e89f05af
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751593"
---
# <a name="macros-and-functions-for-managing-dlls"></a>DL'leri Yönetmek için Makrolar ve Fonksiyonlar

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|Sınıfları dışa dışa aktarma.|
|[AFX_MANAGE_STATE](#afx_manage_state)|Dışa aktarılan bir işlevi Bir DLL'de koruyun.|
|[AfxOleInitModülü](#afxoleinitmodule)|Dinamik olarak MFC'ye bağlı normal bir MFC DLL'den OLE desteği sağlar.|
|[AfxNetInitModülü](#afxnetinitmodule)|MFC Soketleri, dinamik olarak MFC'ye bağlı normal bir MFC DLL'den destek sağlar.|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|Modül başına durum bayrağının geçerli durumunu alır.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|Başlatmadan önce modül durumunu ve/veya temizlemeden sonra önceki modül durumunu geri yüklemeyi ayarlar.|
|[AfxInitExtensionModule](#afxinitextensionmodule)|DLL'yi başharfe iter.|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|MFC'nin WinSxS davranışını etkileyen modül başına durum bayrağını ayarlayın.|
|[AfxTermExtensionModülü](#afxtermextensionmodule)|Her işlem DLL'den ayrıldığunda MFC uzantısı DLL'yi temizlemesine olanak tanır.|

## <a name="afx_ext_class"></a><a name="afx_ext_class"></a>Afx_ext_class

[MFC uzantılı DL'ler](../../build/extension-dlls.md) sınıfları dışa aktarmak için makro AFX_EXT_CLASS kullanır; MFC uzantısı DLL'ye bağlanan yürütülebilir uygulamalar, sınıfları almak için makroyu kullanır.

### <a name="remarks"></a>Açıklamalar

makroAFX_EXT_CLASS ile, MFC uzantısı DLL oluşturmak için kullanılan aynı üstbilgi dosyası(lar) DLL bağlantı yürütülebilir ile kullanılabilir.

DLL'nizin üstbilgi dosyasına, AFX_EXT_CLASS anahtar sözcüğü sınıfınızın bildirimine aşağıdaki gibi ekleyin:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Daha fazla bilgi için bkz [AFX_EXT_CLASS.](../../build/exporting-and-importing-using-afx-ext-class.md)

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxv_dll.h

## <a name="afx_manage_state"></a><a name="afx_manage_state"></a>AFX_MANAGE_STATE

DLL'de dışa aktarılan bir işlevi korumak için bu makroyu çağırın.

### <a name="syntax"></a>Sözdizimi

```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>Parametreler

*pModuleState*<br/>
Bir yapıiçin `AFX_MODULE_STATE` bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu makro çağrıldığı zaman, *pModuleState* hemen içeren kapsamın geri kalanı için etkili modül durumudur. Kapsam ayrıldıktan sonra, önceki etkin modül durumu otomatik olarak geri yüklenir.
Yapı, `AFX_MODULE_STATE` modül için genel verileri, yani modül durumunun itilen veya patlatılan kısmını içerir.

Varsayılan olarak, MFC kaynak şablonu yüklemek için ana uygulamanın kaynak tutamacını kullanır. DLL'de bir iletişim kutusu başlatan bir işlev gibi bir DLL'de dışa aktarılan bir işleviniz varsa, bu şablon aslında DLL modülünde depolanır. Doğru tutamacın kullanılabileceğini bilmek için modül durumunu değiştirmeniz gerekir. Bunu, işlevin başına aşağıdaki kodu ekleyerek yapabilirsiniz:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Bu, geçerli modül durumunu [AfxGetStaticModuleState'den](#afxgetstaticmodulestate) dönen durumla, geçerli kapsamın sonuna kadar değiştirir.

Modül durumları ve MFC hakkında daha fazla bilgi için, [Yeni Belgeler, Windows ve Görünümler ve](../creating-new-documents-windows-and-views.md) Teknik [Not 58](../tn058-mfc-module-state-implementation.md)Oluşturma'da "MFC Modüllerinin Durum Verilerini Yönetme" bölümüne bakın.

> [!NOTE]
> MFC bir derleme için etkinleştirme bağlamı oluşturduğunda, bağlamı oluşturmak `AFX_MANAGE_STATE` ve etkinleştirmek ve devre dışı bırakmak için [AfxWinInit](application-information-and-management.md#afxwininit) kullanır. MFC `AFX_MANAGE_STATE` kodunun Kullanıcı DLL tarafından seçilen uygun etkinleştirme bağlamında yürütülmesine izin vermek için statik MFC kitaplıklarının yanı sıra MFC DL'leri için de etkinleştirildiğini unutmayın. Daha fazla bilgi [için, MFC Modülü Durumunda etkinleştirme bağlamları için Destek'e](../support-for-activation-contexts-in-the-mfc-module-state.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxstat_.h

## <a name="a-nameafxoleinitmodule-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/>AfxOleInitModülü

Dinamik olarak MFC'ye bağlı normal bir MFC DLL'den OLE desteği için, MFC OLE DLL'yi başlatmak için bu işlevi normal MFC DLL `CWinApp::InitInstance` işlevinde arayın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>Açıklamalar

MFC OLE DLL bir MFC uzantısı DLL olduğunu; Bir MFC uzantısı DLL'nin bir `CDynLinkLibrary` zincire bağlanabilmesi `CDynLinkLibrary` için, onu kullanacak her modül bağlamında bir nesne oluşturması gerekir. `AfxOleInitModule`normal MFC DLL'nizin `CDynLinkLibrary` `CDynLinkLibrary` nesne zincirine bağlanıyor diye normal MFC DLL bağlamında nesne oluşturur.

Bir OLE denetimi oluşturuyorsanız ve `COleControlModule`kullanıyorsanız, `AfxOleInitModule` aramalar `AfxOleInitModule` `InitInstance` için `COleControlModule` üye işlev nedeniyle aramamalısınız.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi** \<: afxdll_.h>

## <a name="afxnetinitmodule"></a><a name="afxnetinitmodule"></a>AfxNetInitModülü

MFC Soketleri, Dinamik olarak MFC'ye bağlı normal bir MFC DLL desteği için, MFC `CWinApp::InitInstance` Soketleri DLL'yi başlatmayı sağlamak için normal MFC DLL işlevinizde bu işleve bir çağrı ekleyin.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>Açıklamalar

MFC Soketleri DLL bir MFC uzantısı DLL olduğunu; Bir MFC uzantısı DLL'nin bir `CDynLinkLibrary` zincire bağlanabilmesi `CDynLinkLibrary` için, onu kullanacak her modül bağlamında bir nesne oluşturması gerekir. `AfxNetInitModule`normal MFC DLL'nizin `CDynLinkLibrary` `CDynLinkLibrary` nesne zincirine bağlanıyor diye normal MFC DLL bağlamında nesne oluşturur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<afxdll_.h>

## <a name="afxgetambientactctx"></a><a name="afxgetambientactctx"></a>AfxGetAmbientActCtx

MFC'nin WinSxS davranışını etkileyen modül başına durum bayrağının geçerli durumunu almak için bu işlevi kullanın.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>Dönüş Değeri

Modül durum bayrağı geçerli değeri.

### <a name="remarks"></a>Açıklamalar

Bayrak ayarlandığında (varsayılan olan) ve bir iş parçacığı bir MFC modülüne girdiğinde [(AFX_MANAGE_STATE](#afx_manage_state)bakınız), modülün bağlamı etkinleştirilir.

Bayrak ayarlanmazsa, modülün bağlamı girişte etkinleştirilmez.

Bir modülün bağlamı, genellikle modül kaynaklarına gömülü olan manifestosundan belirlenir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcomctl32.h

## <a name="afxgetstaticmodulestate"></a><a name="afxgetstaticmodulestate"></a>AfxGetStaticModuleState

Başlatmadan önce modül durumunu ayarlamak ve/veya temizlemeden sonra önceki modül durumunu geri yüklemek için bu işlevi arayın.

### <a name="syntax"></a>Sözdizimi

```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>Dönüş Değeri

Bir yapıiçin `AFX_MODULE_STATE` bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Yapı, `AFX_MODULE_STATE` modül için genel verileri, yani modül durumunun itilen veya patlatılan kısmını içerir.

Varsayılan olarak, MFC kaynak şablonu yüklemek için ana uygulamanın kaynak tutamacını kullanır. DLL'de bir iletişim kutusu başlatan bir işlev gibi bir DLL'de dışa aktarılan bir işleviniz varsa, bu şablon aslında DLL modülünde depolanır. Doğru tutamacın kullanılabileceğini bilmek için modül durumunu değiştirmeniz gerekir. Bunu, işlevin başına aşağıdaki kodu ekleyerek yapabilirsiniz:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Bu, geçerli modül durumunu geçerli kapsamın `AfxGetStaticModuleState` sonuna kadar döndürülen durumla değiştirir.

Modül durumları ve MFC hakkında daha fazla bilgi için, [Yeni Belgeler, Windows ve Görünümler ve](../creating-new-documents-windows-and-views.md) Teknik [Not 58](../tn058-mfc-module-state-implementation.md)Oluşturma'da "MFC Modüllerinin Durum Verilerini Yönetme" bölümüne bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxstat_.h

## <a name="afxinitextensionmodule"></a>AfxInitExtensionModule

DLL'yi başlatması için bu `DllMain` işlevi Bir MFC uzantısı DLL's'de arayın.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>Parametreler

*durum*<br/>
Başlatmadan sonra MFC uzantısı DLL modülünün durumunu içerecek [AFX_EXTENSION_MODULE Yapısı](afx-extension-module-structure.md) yapısına bir başvuru. Durum, girilmeden önce `DllMain` yürütülen normal statik nesne yapısının bir parçası olarak MFC uzantısı DLL tarafından başharfe çevrilmiş çalışma zamanı sınıfı nesnelerinin bir kopyasını içerir.

*hModülü*<br/>
MFC uzatma DLL modülübir kolu.

### <a name="return-value"></a>Dönüş Değeri

MFC uzantısı DLL başarıyla başharfe çevriliyse DOĞRU; aksi takdirde, YANLIŞ.

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

`AfxInitExtensionModule`DLL'nin HMODULE'sinin bir kopyasını yapar ve`CRuntimeClass` `COleObjectFactory` `CDynLinkLibrary` dll'nin çalışma zamanı sınıflarını (yapıları) ve nesne fabrikalarının (nesneleri) daha sonra nesne oluşturulduğunda kullanılmak üzere yakalar.
MFC uzantılı DL'lerin `DllMain` işlevlerinde iki şey yapmaları gerekir:

- [AfxInitExtensionModule'i](#afxinitextensionmodule) arayın ve iade değerini kontrol edin.

- DLL `CDynLinkLibrary` [CRuntimeClass Yapısı](cruntimeclass-structure.md) nesneleri dışa aktarıyor olacaksa veya kendi özel kaynakları varsa bir nesne oluşturun.

Her işlem `AfxTermExtensionModule` MFC uzantısı DLL'den ayrıldıklarında (işlem çıktığında veya `AfxFreeLibrary` bir arama sonucunda DLL boşaltıldığında olur) MFC uzantısı DLL'yi temizlemek için arayabilirsiniz.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdll_.h

## <a name="afxsetambientactctx"></a><a name="afxsetambientactctx"></a>AfxSetAmbientActCtx

MFC'nin WinSxS davranışını etkileyen modül başına durum bayrağını ayarlamak için bu işlevi kullanın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI AfxSetAmbientActCtx(BOOL bSet);
```

### <a name="parameters"></a>Parametreler

*bSet*<br/>
Modül durum bayrağının yeni değeri.

### <a name="remarks"></a>Açıklamalar

Bayrak ayarlandığında (varsayılan olan) ve bir iş parçacığı bir MFC modülüne girdiğinde [(AFX_MANAGE_STATE](#afx_manage_state)bakınız), modülün bağlamı etkinleştirilir.
Bayrak ayarlanmazsa, modülün bağlamı girişte etkinleştirilmez.
Bir modülün bağlamı, genellikle modül kaynaklarına gömülü olan manifestosundan belirlenir.

### <a name="example"></a>Örnek

```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
}
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcomctl32.h

## <a name="afxtermextensionmodule"></a><a name="afxtermextensionmodule"></a>AfxTermExtensionModülü

Her işlem DLL'den ayrıldıklarında (işlem çıktığında veya `AfxFreeLibrary` arama sonucunda DLL boşaltıldığında meydana gelen) MFC uzantısı DLL'yi temizlemesine izin vermek için bu işlevi arayın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );
```

### <a name="parameters"></a>Parametreler

*durum*<br/>
MFC uzantısı DLL modülü durumunu içeren [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) yapıya bir başvuru.

*Topu*<br/>
DOĞRUYSA, tüm MFC uzatma DLL modüllerini temizleyin. Aksi takdirde, yalnızca geçerli DLL modüllerini temizleyin.

### <a name="remarks"></a>Açıklamalar

`AfxTermExtensionModule`modüle iliştirilen herhangi bir yerel depolama alanını siler ve ileti eşleği önbelleğinden girişleri kaldırır. Örneğin:

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

Uygulamanız MFC uzantısı DL'leri dinamik olarak yükler ve `AfxTermExtensionModule`serbest hale alırsa, 'yi mutlaka arayın. Çoğu MFC uzantılı DL dinamik olarak yüklenmediğinden (genellikle, alma kitaplıkları üzerinden bağlanır), çağrı `AfxTermExtensionModule` genellikle gerekli değildir.

MFC uzantılı DL'lerin [AfxInitExtensionModule'i](#afxinitextensionmodule) aramaları gerekmektedir. `DllMain` DLL [CRuntimeClass](cruntimeclass-structure.md) nesneleri dışa aktarıyor olacak veya kendi özel kaynakları varsa, aynı zamanda bir `CDynLinkLibrary` nesne oluşturmanız `DllMain`gerekir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdll_.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](mfc-macros-and-globals.md)<br/>
[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[MFC Modüllerinin Durum Verilerinin Yönetimi](../managing-the-state-data-of-mfc-modules.md)<br/>
