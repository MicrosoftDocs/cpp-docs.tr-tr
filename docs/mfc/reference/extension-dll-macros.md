---
title: "Makrolar ve İşlevler DLL'leri yönetme | Microsoft Docs"
ms.custom: 
ms.date: 04/03/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 535045d715651d6393227457068a86f240c27dce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="macros-and-functions-for-managing-dlls"></a>Makrolar ve İşlevler DLL'leri yönetmek için

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|Sınıfları dışarı aktarır.|
|[AFX_MANAGE_STATE](#afx_manage_state)|DLL'den dışarı aktarılan bir işlevinde koruyun.|
|[AfxOleInitModule](#afxoleinitmodule)|Dinamik olarak MFC'ye bağlı normal bir MFC DLL OLE desteği sağlar.|
|[AfxNetInitModule](#afxnetinitmodule)|Dinamik olarak MFC'ye bağlı normal bir MFC DLL gelen MFC yuva desteği sağlar.|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|Modül başına durumu bayrağı geçerli durumunu alır.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|Modül durumu başlatmadan önce ve/veya önceki Modül durumu temizleme sonrasında geri yüklemek için ayarlar.|
|[AfxInitExtensionModule]()#afxinitextensionmodule|DLL başlatır.|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|MFC WinSxS davranışını etkiler modül başına durumu bayrağını ayarlayın.|
|[AfxTermExtensionModule]()#afxtermextensionmodule)|MFC DLL her işlem ayırır olduğunda Temizleme için MFC uzantı DLL'si izin verir.|


## <a name="afx_ext_class"></a>AFX_EXT_CLASS
[MFC uzantı DLL'leri](../../build/extension-dlls.md) makrosu kullanma **AFX_EXT_CLASS** dışarı aktarmak için sınıfları; sınıflarını içeri aktarmak için makro MFC uzantı DLL'si bağlantı yürütülebilir dosyaları kullanın.  
   
### <a name="remarks"></a>Açıklamalar  
 İle **AFX_EXT_CLASS** makrosu, aynı üstbilgi MFC uzantı DLL'si oluşturmak için kullanılan dosyalar için DLL'e yürütülebilir dosyaları ile kullanılabilir.  
  
 DLL üstbilgi dosyasına ekleyin **AFX_EXT_CLASS** sınıfınız bildirimi aşağıdaki gibi anahtar:  
  
```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
``` 
  
 Daha fazla bilgi için bkz: [dışarı ve içeri aktarma AFX_EXT_CLASS kullanarak](../../build/exporting-and-importing-using-afx-ext-class.md).  
   
### <a name="requirements"></a>Gereksinimler  
 Başlık: **afxv_**dll.h  
   
## <a name="afx_manage_state"></a>AFX_MANAGE_STATE
DLL'den dışarı aktarılan bir işlevinde korumak için bu makrosu çağırın.  
   
### <a name="syntax"></a>Sözdizimi    
```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )  
```
### <a name="parameters"></a>Parametreler  
 `pModuleState`  
 Bir işaretçi bir `AFX_MODULE_STATE` yapısı.  
   
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu çağrıldığında, `pModuleState` etkili Modül durumu geri kalanı hemen kapsam içeren. Kapsam bırakarak bağlı önceki etkili Modül durumu otomatik olarak geri yüklenir.    
 `AFX_MODULE_STATE` Yapısı modülü, başka bir deyişle, gönderilen veya Sil'i Modül durumu kısmı için genel verileri içerir.    
 Varsayılan olarak, MFC kaynak şablonu yüklemek için ana uygulama kaynak tanıtıcısı kullanır. DLL iletişim kutusunda başlatan bir gibi DLL'den dışarı aktarılan bir işlevin varsa bu şablon DLL modülünde gerçekte depolanır. Kullanılacak doğru tanıtıcı Modül durumu geçmeniz gerekir. Aşağıdaki kod işlevi başlangıcına ekleyerek bunu yapabilirsiniz:    
```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```
 Bu döndürülen durumuyla geçerli modül durumunu değiştirir [AfxGetStaticModuleState](#afxgetstaticmodulestate) geçerli kapsam sonuna kadar.    
 Modül durumları ve MFC hakkında daha fazla bilgi için bkz: "Yönetme durumu verileri, MFC modülleri" [oluşturma yeni belgeler, pencereler ve görünümler](../creating-new-documents-windows-and-views.md) ve [Teknik Not 58](../tn058-mfc-module-state-implementation.md).    
> [!NOTE]
>  MFC için derlemeyi etkinleştirme bağlamı oluşturduğunda, kullanan [Afxwinınit](#afxwininit) bağlam oluşturmak için ve `AFX_MANAGE_STATE` etkinleştirme ve devre dışı. Ayrıca `AFX_MANAGE_STATE` statik MFC kitaplıkları, yanı sıra MFC DLL'leri kullanıcı DLL tarafından seçilen uygun etkinleştirme bağlamda yürütmek MFC kodu izin vermek üzere etkinleştirilir. Daha fazla bilgi için bkz: [MFC modül durumunda etkinleştirme bağlamları desteği](../support-for-activation-contexts-in-the-mfc-module-state.md).     
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxstat_.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [AfxGetStaticModuleState](#afxgetstaticmodulestate)

## <a name="a-nameafxoleinitmodulea-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/>AfxOleInitModule
Dinamik olarak MFC'ye bağlı normal bir MFC DLL gelen OLE desteği için bu işlev, Normal MFC DLL içinde çağrı `CWinApp::InitInstance` işlevi MFC OLE DLL başlatılamadı.  
   
### <a name="syntax"></a>Sözdizimi    
```
void AFXAPI AfxOleInitModule( );  
```  
   
### <a name="remarks"></a>Açıklamalar  
 MFC OLE MFC uzantı DLL'si DLL'dir; MFC uzantı DLL'si sipariş içine kablolu için de bir **CDynLinkLibrary** zinciri, onu oluşturmanız gerekir bir **CDynLinkLibrary** kullanarak her bir modüle bağlamda nesnesi. `AfxOleInitModule`oluşturur **CDynLinkLibrary** içine kablolu böylece Normal MFC DLL bağlamda nesne **CDynLinkLibrary** nesne Normal MFC DLL zinciri.  
  
 OLE denetim oluşturma ve kullanıyorsanız `COleControlModule`, değil çağırmalıdır **AfxOleInitModule** çünkü `InitInstance` üye işlevi için `COleControlModule` çağrıları `AfxOleInitModule`.  
   
### <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: < afxdll_.h >  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxnetinitmodule"></a>AfxNetInitModule
Dinamik olarak MFC'ye bağlı normal bir MFC DLL gelen MFC yuva desteklemek için bu işlevi çağrısı, Normal MFC DLL içinde eklemek **CWinApp::InitInstance** işlevi MFC yuva DLL başlatılamadı.  
   
### <a name="syntax"></a>Sözdizimi    
```
void AFXAPI AfxNetInitModule( );  
```  
   
### <a name="remarks"></a>Açıklamalar  
 MFC yuva MFC uzantı DLL'si DLL'dir; MFC uzantı DLL'si sipariş içine kablolu için de bir **CDynLinkLibrary** zinciri, onu oluşturmanız gerekir bir **CDynLinkLibrary** kullanarak her bir modüle bağlamda nesnesi. `AfxNetInitModule`oluşturur **CDynLinkLibrary** içine kablolu böylece Normal MFC DLL bağlamda nesne **CDynLinkLibrary** nesne Normal MFC DLL zinciri.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** < afxdll_.h >  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxgetambientactctx"></a>AfxGetAmbientActCtx
MFC WinSxS davranışını etkileyen modül başına durumu bayrağı geçerli durumunu almak için bu işlevi kullanın.  
   
### <a name="syntax"></a>Sözdizimi    
```  
BOOL AFXAPI AfxGetAmbientActCtx();   
```  
   
### <a name="return-value"></a>Dönüş Değeri  
 Modül durumu bayrağı geçerli değeri.  
   
### <a name="remarks"></a>Açıklamalar  
 Ne zaman bayrağını (varsayılan değer olan) ayarlayın ve bir iş parçacığı bir MFC modül girer (bkz [AFX_MANAGE_STATE](#afx_manage_state)), modül bağlamında etkinleştirilir.  
  
 Bayrağı ayarlanmamış olduğundan, modül bağlamında girişinde etkinleştirilmedi.  
  
 Bir modül bağlamında modülü kaynaklarında genellikle katıştırılmış kendi bildirimindeki belirlenir.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcomctl32.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [AFX_MANAGE_STATE](#afx_manage_state)   
 [MFC modüllerinin durum verisini yönetme](../managing-the-state-data-of-mfc-modules.md)   
 [AfxSetAmbientActCtx](#setambientactctx)
 
## <a name="afxgetstaticmodulestate"></a>AfxGetStaticModuleState
Modül durumu başlatmadan önce ayarlamak için ve/veya önceki Modül durumu temizleme sonrasında geri yüklemek için bu işlevini çağırın.  
   
### <a name="syntax"></a>Sözdizimi    
```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );  
```  
   
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `AFX_MODULE_STATE` yapısı.  
   
### <a name="remarks"></a>Açıklamalar  
 `AFX_MODULE_STATE` Yapısı modülü, başka bir deyişle, gönderilen veya Sil'i Modül durumu kısmı için genel verileri içerir.  
  
 Varsayılan olarak, MFC kaynak şablonu yüklemek için ana uygulama kaynak tanıtıcısı kullanır. DLL iletişim kutusunda başlatan bir gibi DLL'den dışarı aktarılan bir işlevin varsa bu şablon DLL modülünde gerçekte depolanır. Kullanılacak doğru tanıtıcı Modül durumu geçmeniz gerekir. Aşağıdaki kod işlevi başlangıcına ekleyerek bunu yapabilirsiniz:  
  
```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```
  
 Bu döndürülen durumuyla geçerli modül durumunu değiştirir `AfxGetStaticModuleState` geçerli kapsam sonuna kadar.  
  
 Modül durumları ve MFC hakkında daha fazla bilgi için bkz: "Yönetme durumu verileri, MFC modülleri" [oluşturma yeni belgeler, pencereler ve görünümler](../creating-new-documents-windows-and-views.md) ve [Teknik Not 58](../tn058-mfc-module-state-implementation.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxstat_.h  
   

## <a name="afxinitextensionmodule"></a>AfxInitExtensionModule
Bir MFC uzantı DLL'in bu işlevi çağırmak `DllMain` DLL başlatılamadı.  
   
### <a name="syntax"></a>Sözdizimi    
```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );  
```
### <a name="parameters"></a>Parametreler  
 `state`  
 Bir başvuru [AFX_EXTENSION_MODULE yapısı](afx-extension-module-structure.md) MFC uzantı DLL modülü durumunu başlattıktan içerecek yapısı. Durumu normal statik nesne oluşturması önce yürütülen bir parçası olarak MFC uzantı DLL'si başlatılmadı çalışma zamanı sınıf nesnelerin bir kopyasını içeren `DllMain` girilir.  
  
 `hModule`  
 MFC uzantı DLL modülü tanıtıcısı.  
   
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** MFC uzantı DLL'si başarıyla başlatılmış; Aksi takdirde ise **FALSE**.  
   
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

```
  
 `AfxInitExtensionModule`DLL'in bir kopyasını oluşturur **hModule'ü** ve DLL'nin çalışma zamanı-sınıfları yakalar (`CRuntimeClass` yapıları) yanı sıra kendi nesne oluşturucuları (`COleObjectFactory` nesneleri) kullanmak için sonraki olduğunda **CDynLinkLibrary**nesnesi oluşturulur.    
 MFC uzantı DLL'leri iki şeyler gerek kendi `DllMain` işlevi:    
-   Çağrı [AfxInitExtensionModule](#_mfc_afxinitextensionmodule) ve dönüş değerini denetleyin.   
-   Oluşturma bir **CDynLinkLibrary** DLL verme durumunda nesne [CRuntimeClass yapısı](cruntimeclass-structure.md) nesneleri veya kendi özel kaynaklar içeriyor.    
 Çağırabilirsiniz `AfxTermExtensionModule` her işlem MFC uzantı DLL'si ayrıldığında MFC uzantı DLL temizlemesini (işlem çıktığında ya da DLL sonucu olarak kaldırıldığında gerçekleşir bir `AfxFreeLibrary` çağrısı).     

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdll_.h     

### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [AfxTermExtensionModule](#afxtermextensionmodule)

 ## <a name="afxsetambientactctx"></a>AfxSetAmbientActCtx
MFC WinSxS davranışını etkileyen modül başına durumu bayrağı ayarlamak için bu işlevi kullanın.  
   
### <a name="syntax"></a>Sözdizimi  
  ```
   void AFXAPI AfxSetAmbientActCtx( BOOL bSet  
);  
```
### <a name="parameters"></a>Parametreler  
 `bSet`  
 Modül durumu bayrağı yeni değeri.  
   
### <a name="remarks"></a>Açıklamalar  
 Ne zaman bayrağını (varsayılan değer olan) ayarlayın ve bir iş parçacığı bir MFC modül girer (bkz [AFX_MANAGE_STATE](#afx_manage_state)), modül bağlamında etkinleştirilir.    
 Bayrağı ayarlanmamış olduğundan, modül bağlamında girişinde etkinleştirilmedi.    
 Bir modül bağlamında modülü kaynaklarında genellikle katıştırılmış kendi bildirimindeki belirlenir.  
   
### <a name="example"></a>Örnek  
 ```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
```
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcomctl32.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [AfxGetAmbientActCtx](#afxgetambientactctx)   
 [AFX_MANAGE_STATE](#afx_manage_state)   
 [MFC Modüllerinin Durum Verisini Yönetme](../managing-the-state-data-of-mfc-modules.md) 

## <a name="afxtermextensionmodule"></a>AfxTermExtensionModule

Her işlem DLL'den ayırır olduğunda MFC Temizleme için MFC uzantı DLL'si izin verir. Bu işlev çağrısı (işlem çıktığında ya da DLL sonucu olarak kaldırıldığında gerçekleşir bir `AfxFreeLibrary` çağrısı).  
   
### <a name="syntax"></a>Sözdizimi  
  ```
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );  
```
### <a name="parameters"></a>Parametreler  
 `state`  
 Bir başvuru [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) MFC uzantı DLL modülü durumunu içeren yapısı.  
  
 *Top*  
 Varsa **doğru**, Temizle tüm MFC uzantı DLL modülleri. Aksi takdirde temizleme yalnızca geçerli DLL modülü.  
   
### <a name="remarks"></a>Açıklamalar  
 `AfxTermExtensionModule`işlem modülü bağlı herhangi bir yerel depolama silecek ve herhangi bir giriş ileti eşlemesi önbelleğinden kaldırın. Örneğin:  
  
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
  
 Uygulamanızı yükler ve MFC uzantı DLL'leri dinamik olarak boşaltır, çağırdığınızdan emin olun `AfxTermExtensionModule`. Çoğu MFC uzantı DLL'leri dinamik olarak yüklenmez bu yana (genellikle, bunlar, içeri aktarma kitaplıkları bağlı), çağrısı `AfxTermExtensionModule` genellikle gerekli değildir.  
  
 MFC uzantı DLL'leri gereksinim çağırmak [AfxInitExtensionModule](#afxinitextensionmodule) içinde kendi `DllMain`. DLL dışa aktarılıyorsa [CRuntimeClass](cruntimeclass-structure.md) nesneleri veya kendi özel kaynaklara sahip, oluşturmak için gereken bir **CDynLinkLibrary** nesnesinde `DllMain`.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdll_.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [AfxInitExtensionModule](#afxinitextensionmodule)
 




