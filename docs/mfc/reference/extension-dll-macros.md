---
title: Makrolar ve İşlevler DLL'leri yönetmek için
ms.date: 03/27/2019
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
ms.openlocfilehash: b27f8763b60dc7ce3ee074cad1365e7e1de3a7e6
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565431"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Makrolar ve İşlevler DLL'leri yönetmek için

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|Sınıfları dışarı aktarır.|
|[AFX_MANAGE_STATE](#afx_manage_state)|DLL'de dışa aktarılan bir işlevin koruyun.|
|[AfxOleInitModule](#afxoleinitmodule)|Dinamik olarak MFC'ye bağlı normal MFC DLL'SİNİN OLE desteği sağlar.|
|[AfxNetInitModule](#afxnetinitmodule)|Dinamik olarak MFC'ye bağlı normal MFC DLL'SİNİN gelen MFC yuva desteği sağlar.|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|Modül başına durum bayrağı geçerli durumunu alır.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|Başlatmadan önce ve/veya temizleme sonra önceki modül durumunu geri yüklemek için modül durumunu ayarlar.|
|[AfxInitExtensionModule](#afxinitextensionmodule)|DLL başlatır.|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|MFC WinSxS davranışını etkileyen modül başına durum bayrağını ayarlayın.|
|[AfxTermExtensionModule](#afxtermextensionmodule)|Her işlem DLL'den ayırdığında MFC uzantısı DLL temizlemek MFC sağlar.|

## <a name="afx_ext_class"></a>  AFX_EXT_CLASS

[MFC uzantı DLL'leri](../../build/extension-dlls.md) AFX_EXT_CLASS makrosu sınıflarını dışarı aktarmak için kullanın; sınıflarını içeri aktarmak için makro MFC uzantısı DLL için bağlama yürütülebilir dosyaları kullanın.

### <a name="remarks"></a>Açıklamalar

AFX_EXT_CLASS makrosu ile MFC uzantısı DLL oluşturmak için kullanılan aynı üst bilgi dosyaları için DLL'e yürütülebilir dosyaları ile kullanılabilir.

DLL dosyanız için üstbilgi dosyasında AFX_EXT_CLASS anahtar sözcüğü, sınıf bildirimi için aşağıdaki gibi ekleyin:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Daha fazla bilgi için [dışarı ve içeri aktarma AFX_EXT_CLASS kullanarak](../../build/exporting-and-importing-using-afx-ext-class.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxv_dll.h

## <a name="afx_manage_state"></a>  AFX_MANAGE_STATE

DLL'de dışa aktarılan bir işlevin korumak için bu makroyu çağırın.

### <a name="syntax"></a>Sözdizimi

```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>Parametreler

*pModuleState*<br/>
Bir işaretçi bir `AFX_MODULE_STATE` yapısı.

### <a name="remarks"></a>Açıklamalar

Bu makro çağrıldığında *pModuleState* etkili modül durumunu geri kalanı için hemen kapsam içeren. Kapsam ayrıldıktan sonra önceki etkili Modül durumu otomatik olarak kurulacaktır.
`AFX_MODULE_STATE` Modülü, diğer bir deyişle, gönderilen veya POP Modül durumu kısmı için genel veri yapısı içerir.

Varsayılan olarak, kaynak şablonu yüklemek için ana uygulama kaynak tanıtıcısı MFC kullanır. Bir iletişim kutusu, DLL başlatan bir gibi bir DLL'de dışa aktarılan bir işlevin varsa bu şablon aslında DLL modülü içinde depolanır. Geçiş için kullanılacak doğru tanıtıcı Modül durumu gerekir. Bu işlevin başlangıcına aşağıdaki kodu ekleyerek yapabilirsiniz:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Bu geçerli bir modül durumunu döndürüldüğü durumu ile değiştirir [AfxGetStaticModuleState](#afxgetstaticmodulestate) geçerli kapsamdaki sonuna kadar.

Modül durumları ve MFC ile ilgili daha fazla bilgi için bkz: "Yönetme durumu verileri, MFC modülleri" [yeni belgeler oluşturma, Windows ve görünümler](../creating-new-documents-windows-and-views.md) ve [Teknik Not 58](../tn058-mfc-module-state-implementation.md).

> [!NOTE]
>  MFC etkinleştirme bağlamı için bir derleme oluşturur, bunu kullanan [Afxwinınit](application-information-and-management.md#afxwininit) bağlamı oluşturur ve `AFX_MANAGE_STATE` etkinleştirmesine ve devre dışı. Ayrıca `AFX_MANAGE_STATE` statik MFC kitaplıkları, yanı sıra MFC DLL'leri kullanıcı DLL tarafından seçilen uygun etkinleştirme bağlamı yürütmek için MFC kodu izin vermek üzere etkinleştirilir. Daha fazla bilgi için [MFC modül durumunda etkinleştirme bağlamları desteği](../support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxstat_.h

## <a name="a-nameafxoleinitmodulea-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> AfxOleInitModule

Dinamik olarak MFC'ye bağlı normal MFC DLL'SİNİN OLE destek için Normal MFC DLL içinde bu işlevi çağırın `CWinApp::InitInstance` MFC OLE DLL işlevi.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>Açıklamalar

MFC OLE DLL bir MFC uzantılı DLL dosyasıdır; bir MFC uzantılı DLL içine kablolu için sırada bir `CDynLinkLibrary` zinciri gerekir oluşturma bir `CDynLinkLibrary` onu kullanan her bir modüle bağlamında nesne. `AfxOleInitModule` oluşturur `CDynLinkLibrary` içine kablolu, böylece Normal MFC DLL bağlamda nesne `CDynLinkLibrary` nesnesi Normal MFC DLL'SİNİN zinciri.

Bir OLE denetim oluşturma ve kullanıyorsanız `COleControlModule`, değil, çağırmalıdır `AfxOleInitModule` çünkü `InitInstance` üye işlevi için `COleControlModule` çağrıları `AfxOleInitModule`.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<afxdll_.h >

## <a name="afxnetinitmodule"></a>  AfxNetInitModule

Dinamik olarak MFC'ye bağlı normal MFC DLL'SİNİN gelen MFC yuva desteği sağlamak için bu işlev çağrısı, Normal MFC DLL içinde ekleyin `CWinApp::InitInstance` yuva MFC DLL işlevi.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>Açıklamalar

MFC yuva DLL bir MFC uzantılı DLL dosyasıdır; bir MFC uzantılı DLL içine kablolu için sırada bir `CDynLinkLibrary` zinciri gerekir oluşturma bir `CDynLinkLibrary` onu kullanan her bir modüle bağlamında nesne. `AfxNetInitModule` oluşturur `CDynLinkLibrary` içine kablolu, böylece Normal MFC DLL bağlamda nesne `CDynLinkLibrary` nesnesi Normal MFC DLL'SİNİN zinciri.

### <a name="requirements"></a>Gereksinimler

**Başlık:** \<afxdll_.h >

## <a name="afxgetambientactctx"></a> AfxGetAmbientActCtx

MFC WinSxS davranışını etkileyen modül başına durum bayrağı geçerli durumunu almak için bu işlevi kullanın.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>Dönüş Değeri

Modül durum bayrağı geçerli değeri.

### <a name="remarks"></a>Açıklamalar

Ne zaman bayrağını (varsayılan değer olan) olarak ayarlanır ve bir iş parçacığına MFC modül girer (bkz [AFX_MANAGE_STATE](#afx_manage_state)), modül bağlamında etkinleştirilir.

Bayrak ayarlanmazsa, modül bağlamında girişinde etkinleştirilmedi.

Bir modül bağlamında, bildirimindeki modülü kaynaklar genellikle katıştırılmış belirlenir.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxcomctl32.h

## <a name="afxgetstaticmodulestate"></a> AfxGetStaticModuleState

Başlatmadan önce Modül durumu ayarlamak için ve/veya temizleme sonra önceki modül durumunu geri yüklemek için bu işlevi çağırın.

### <a name="syntax"></a>Sözdizimi

```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `AFX_MODULE_STATE` yapısı.

### <a name="remarks"></a>Açıklamalar

`AFX_MODULE_STATE` Modülü, diğer bir deyişle, gönderilen veya POP Modül durumu kısmı için genel veri yapısı içerir.

Varsayılan olarak, kaynak şablonu yüklemek için ana uygulama kaynak tanıtıcısı MFC kullanır. Bir iletişim kutusu, DLL başlatan bir gibi bir DLL'de dışa aktarılan bir işlevin varsa bu şablon aslında DLL modülü içinde depolanır. Geçiş için kullanılacak doğru tanıtıcı Modül durumu gerekir. Bu işlevin başlangıcına aşağıdaki kodu ekleyerek yapabilirsiniz:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Bu geçerli bir modül durumunu döndürüldüğü durumu ile değiştirir `AfxGetStaticModuleState` geçerli kapsamdaki sonuna kadar.

Modül durumları ve MFC ile ilgili daha fazla bilgi için bkz: "Yönetme durumu verileri, MFC modülleri" [yeni belgeler oluşturma, Windows ve görünümler](../creating-new-documents-windows-and-views.md) ve [Teknik Not 58](../tn058-mfc-module-state-implementation.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxstat_.h

## <a name="afxinitextensionmodule"></a>AfxInitExtensionModule

Bir MFC uzantı DLL'in bu işlevi çağırın `DllMain` DLL başlatılamadı.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>Parametreler

*durumu*<br/>
Bir başvuru [AFX_EXTENSION_MODULE yapısı](afx-extension-module-structure.md) başlatmadan sonra MFC uzantısı DLL modülü durumunu içerecek yapı. Durum normal durağan nesnenin yapımı önce yürütülen bir parçası olarak MFC uzantısı DLL tarafından başlatılmamış. çalışma zamanı sınıf nesnelerin bir kopyasını içeren `DllMain` girilir.

*hModule'ü*<br/>
MFC uzantısı DLL modül tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

MFC uzantı DLL'sini başarıyla başlatılırsa, TRUE; Aksi takdirde FALSE.

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

`AfxInitExtensionModule` DLL'nin hModule'ü bir kopyasını oluşturur ve DLL'nin çalışma zamanı sınıflar yakalar (`CRuntimeClass` yapıları), nesne fabrikaları yanı sıra (`COleObjectFactory` nesneleri) kullanmak için sonraki olduğunda `CDynLinkLibrary` nesnesi oluşturulur.
MFC uzantısı DLL'leri iki şeyler gerek kendi `DllMain` işlevi:

- Çağrı [AfxInitExtensionModule](#afxinitextensionmodule) ve dönüş değeri denetleyin.

- Oluşturma bir `CDynLinkLibrary` DLL dışa, nesne [CRuntimeClass yapısı](cruntimeclass-structure.md) nesneleri veya kendi özel kaynaklara sahip.

Çağırabilirsiniz `AfxTermExtensionModule` her işlem MFC uzantısı DLL ayırdığında MFC uzantısı DLL temizlemek için (işlem çıktığında veya DLL sonucu olarak kaldırıldığında gerçekleşir bir `AfxFreeLibrary` arayın).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdll_.h

## <a name="afxsetambientactctx"></a>  AfxSetAmbientActCtx

MFC WinSxS davranışını etkileyen modül başına durumunu bayrağını ayarlamak için bu işlevi kullanın.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI AfxSetAmbientActCtx(BOOL bSet);
```

### <a name="parameters"></a>Parametreler

*bInternet*<br/>
Yeni Modül durumu bayrak değeri.

### <a name="remarks"></a>Açıklamalar

Ne zaman bayrağını (varsayılan değer olan) olarak ayarlanır ve bir iş parçacığına MFC modül girer (bkz [AFX_MANAGE_STATE](#afx_manage_state)), modül bağlamında etkinleştirilir.
Bayrak ayarlanmazsa, modül bağlamında girişinde etkinleştirilmedi.
Bir modül bağlamında, bildirimindeki modülü kaynaklar genellikle katıştırılmış belirlenir.

### <a name="example"></a>Örnek

```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
}
```

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxcomctl32.h

## <a name="afxtermextensionmodule"></a>  AfxTermExtensionModule

MFC her işlem DLL'den ayırdığında MFC uzantısı DLL temizlemeye izin vermek için bu işlevi çağırın (işlem çıktığında veya DLL sonucu olarak kaldırıldığında gerçekleşir bir `AfxFreeLibrary` arayın).

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );
```

### <a name="parameters"></a>Parametreler

*durumu*<br/>
Bir başvuru [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) MFC uzantısı DLL modülü durumunu içeren yapısı.

*Top*<br/>
TRUE ise tüm MFC uzantısı DLL modülleri temizleyin. Aksi takdirde, yalnızca geçerli DLL modülü temizleyin.

### <a name="remarks"></a>Açıklamalar

`AfxTermExtensionModule` Modülü bağlı herhangi bir yerel depolama silme ve tüm girdileri ileti eşlemesi önbellekten kaldırma başlar. Örneğin:

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

Uygulamanızı yükler ve MFC uzantısı DLL'leri dinamik olarak boşaltır, çağırdığınızdan emin olun `AfxTermExtensionModule`. Çoğu MFC uzantısı DLL'leri dinamik olarak yüklenmediği beri (genellikle kullanıcılar, içeri aktarma kitaplıkları bağlı), çağrı `AfxTermExtensionModule` genellikle gerekli değildir.

MFC uzantısı DLL'leri çağırmak için gereken [AfxInitExtensionModule](#afxinitextensionmodule) içinde kendi `DllMain`. DLL dışa aktarılıyorsa [CRuntimeClass](cruntimeclass-structure.md) nesneleri veya kendi özel kaynaklara sahip oluşturmanız gerekir bir `CDynLinkLibrary` nesnesine `DllMain`.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdll_.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](mfc-macros-and-globals.md)<br/>
[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[MFC Modüllerinin Durum Verisini Yönetme](../managing-the-state-data-of-mfc-modules.md)<br/>
