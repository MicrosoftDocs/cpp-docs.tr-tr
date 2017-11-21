---
title: "IAtlMemMgr sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAtlMemMgr
- ATLMEM/ATL::IAtlMemMgr
- ATLMEM/ATL::Allocate
- ATLMEM/ATL::Free
- ATLMEM/ATL::GetSize
- ATLMEM/ATL::Reallocate
dev_langs: C++
helpviewer_keywords:
- IAtlMemMgr class
- memory, managing
- memory, memory manager
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2f8bda6ab864c01227d76efafcc8db7bdfec1327
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="iatlmemmgr-class"></a>IAtlMemMgr sınıfı
Bu sınıf, bir bellek yöneticisi arabirimi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Ayırma](#allocate)|Bir bellek bloğu ayırmak için bu yöntemi çağırın.|  
|[Boş](#free)|Bir bellek bloğu boşaltmak için bu yöntemi çağırın.|  
|[GetSize](#getsize)|Ayrılmış bellek bloğu boyutu almak için bu yöntemi çağırın.|  
|[Yeniden ayırma](#reallocate)|Bir bellek bloğu yeniden ayırmak üzere bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim tarafından uygulanan [CComHeap](../../atl/reference/ccomheap-class.md), [CCRTHeap](../../atl/reference/ccrtheap-class.md), [CLocalHeap](../../atl/reference/clocalheap-class.md), [CGlobalHeap](../../atl/reference/cglobalheap-class.md), veya [CWin32Heap](../../atl/reference/cwin32heap-class.md).  
  
> [!NOTE]
>  Yerel ve genel heap işlevleri diğer bellek yönetimi işlevleri yavaş çalışır ve gibi birçok özellik sağlamaz. Bu nedenle, yeni uygulamalar kullanmalıdır [yığın işlevleri](http://msdn.microsoft.com/library/windows/desktop/aa366711). Bunlar kullanılabilir olan [CWin32Heap](../../atl/reference/cwin32heap-class.md) sınıfı.  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlmem.h  
  
##  <a name="allocate"></a>IAtlMemMgr::Allocate  
 Bir bellek bloğu ayırmak için bu yöntemi çağırın.  
  
```
void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nBytes`  
 İstenen yeni bellek bloğu içindeki bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi yeni ayrılan bellek bloğu başlangıcını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [IAtlMemMgr::Free](#free) veya [IAtlMemMgr::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
### <a name="example"></a>Örnek  
 Bir örnek için bkz: [IAtlMemMgr genel bakış](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="free"></a>IAtlMemMgr::Free  
 Bir bellek bloğu boşaltmak için bu yöntemi çağırın.  
  
```
void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Bu bellek yöneticisi tarafından önceden ayrılmış bellek işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından alınan belleği boşaltmak için bu yöntemi kullanın [IAtlMemMgr::Allocate](#allocate) veya [IAtlMemMgr::Reallocate](#reallocate).  
  
### <a name="example"></a>Örnek  
 Bir örnek için bkz: [IAtlMemMgr genel bakış](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="getsize"></a>IAtlMemMgr::GetSize  
 Ayrılmış bellek bloğu boyutu almak için bu yöntemi çağırın.  
  
```
size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Bu bellek yöneticisi tarafından önceden ayrılmış bellek işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek blok boyutunu bayt cinsinden döndürür.  
  
### <a name="example"></a>Örnek  
 Bir örnek için bkz: [IAtlMemMgr genel bakış](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="reallocate"></a>IAtlMemMgr::Reallocate  
 Bu bellek yöneticisi tarafından ayrılan belleği yeniden tahsis etmek için bu yöntemi çağırın.  
  
```
void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Bu bellek yöneticisi tarafından önceden ayrılmış bellek işaretçisi.  
  
 `nBytes`  
 İstenen yeni bellek bloğu içindeki bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi yeni ayrılan bellek bloğu başlangıcını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [IAtlMemMgr::Free](#free) veya [IAtlMemMgr::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
 Kavramsal olarak bu yöntem, varolan belleği serbest bırakır ve yeni bir bellek bloğu ayırır. Gerçekte, mevcut bellek olabilir genişletilmiş veya aksi halde yeniden.  
  
### <a name="example"></a>Örnek  
 Bir örnek için bkz: [IAtlMemMgr genel bakış](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="get_allowcontextmenu"></a>IAxWinAmbientDispatch::get_AllowContextMenu  
 **AllowContextMenu** özelliği, barındırılan denetim kendi bağlam menüsünü görüntülemek için izin verilip verilmediğini belirtir.  
  
```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 *pbAllowContextMenu*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan `VARIANT_TRUE` bu özelliğin varsayılan değeri olarak.  
  
##  <a name="get_allowshowui"></a>IAxWinAmbientDispatch::get_AllowShowUI  
 **AllowShowUI** özelliği, kendi kullanıcı arabirimini görüntülemek için denetimden izin verilip verilmediğini belirtir.  
  
```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```  
  
### <a name="parameters"></a>Parametreler  
 *pbAllowShowUI*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan **VARIANT_FALSE** bu özelliğin varsayılan değeri olarak.  
  
##  <a name="get_allowwindowlessactivation"></a>IAxWinAmbientDispatch::get_AllowWindowlessActivation  
 **AllowWindowlessActivation** özelliği, kapsayıcı penceresiz etkinleştirme izin verip vermeyeceğini belirtir.  
  
```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```  
  
### <a name="parameters"></a>Parametreler  
 *pbAllowWindowless*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan `VARIANT_TRUE` bu özelliğin varsayılan değeri olarak.  
  
##  <a name="get_backcolor"></a>IAxWinAmbientDispatch::get_BackColor  
 `BackColor` Özelliği, kapsayıcı ortam arka plan rengini belirtir.  
  
```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```  
  
### <a name="parameters"></a>Parametreler  
 *pclrBackground*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan **COLOR_BTNFACE** veya **COLOR_WINDOW** (ana penceresinin üst bir iletişim kutusu veya olup olmamasına bağlı olarak) bu özelliğin varsayılan değeri olarak.  
  
##  <a name="get_displayasdefault"></a>IAxWinAmbientDispatch::get_DisplayAsDefault  
 **DisplayAsDefault** varsayılan denetim olup olmadığını öğrenmek için denetim sağlar ortam bir özelliktir.  
  
```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```  
  
### <a name="parameters"></a>Parametreler  
 *pbDisplayAsDefault*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan **VARIANT_FALSE** bu özelliğin varsayılan değeri olarak.  
  
##  <a name="get_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::get_DocHostDoubleClickFlags  
 **DocHostDoubleClickFlags** özelliği, yanıt zaman çift tıklatma eylemi olarak gerçekleşeceğini işlemi belirtir.  
  
```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 *pdwDocHostDoubleClickFlags*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan **DOCHOSTUIDBLCLK_DEFAULT** bu özelliğin varsayılan değeri olarak.  
  
##  <a name="get_dochostflags"></a>IAxWinAmbientDispatch::get_DocHostFlags  
 **DocHostFlags** özelliği, konak nesnesi kullanıcı arabirimi özelliklerini belirtir.  
  
```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 *pdwDocHostFlags*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan **DOCHOSTUIFLAG_NO3DBORDER** bu özelliğin varsayılan değeri olarak.  
  
##  <a name="get_font"></a>IAxWinAmbientDispatch::get_Font  
 **Yazı tipi** özelliği, kapsayıcının ortam yazı tipini belirtir.  
  
```
STDMETHOD(get_Font)(IFontDisp** pFont);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFont`  
 [out] Adresini bir **IFontDisp** bu özelliğin geçerli değeri almak için kullanılan arabirim işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması, bu özellik varsayılan değer olarak varsayılan GUI yazı tipi veya sistem yazı tipi kullanır.  
  
##  <a name="get_forecolor"></a>IAxWinAmbientDispatch::get_ForeColor  
 `ForeColor` Özelliği, kapsayıcı ortam ön plan rengini belirtir.  
  
```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```  
  
### <a name="parameters"></a>Parametreler  
 *pclrForeground*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması sistem pencere metin rengi bu özelliğin varsayılan değeri kullanır.  
  
##  <a name="get_localeid"></a>IAxWinAmbientDispatch::get_LocaleID  
 **LocaleID** özelliği, kapsayıcı ortam yerel ayar Kimliğini belirtir.  
  
```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```  
  
### <a name="parameters"></a>Parametreler  
 *plcidLocaleID*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanıcının varsayılan yerel ayar, bu özelliğin varsayılan değeri kullanır.  
  
 Bu yöntemle ortam localId bulabilir, diğer bir deyişle, program LocaleID denetiminizi olarak kullanılıyor. LocaleID öğrendikten sonra yerel ayarlara özgü başlıklar, yüklemek için kod hata ileti metni, vb. bir kaynak dosya veya uydu DLL çağırabilirsiniz.  
  
##  <a name="get_messagereflect"></a>IAxWinAmbientDispatch::get_MessageReflect  
 **MessageReflect** ortam özelliği, kapsayıcı iletileri barındırılan denetime yansıtılacaktır olup olmadığını belirtir.  
  
```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```  
  
### <a name="parameters"></a>Parametreler  
 *pbMessageReflect*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan `VARIANT_TRUE` bu özelliğin varsayılan değeri olarak.  
  
##  <a name="get_optionkeypath"></a>IAxWinAmbientDispatch::get_OptionKeyPath  
 **OptionKeyPath** özelliği, kullanıcı ayarları için kayıt defteri anahtarının yolunu belirtir.  
  
```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```  
  
### <a name="parameters"></a>Parametreler  
 *pbstrOptionKeyPath*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="get_showgrabhandles"></a>IAxWinAmbientDispatch::get_ShowGrabHandles  
 **ShowGrabHandles** ortam özelliği, kendisini Al tanıtıcıları ile çizip varsa öğrenmek denetim sağlar.  
  
```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```  
  
### <a name="parameters"></a>Parametreler  
 *pbShowGrabHandles*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması her zaman döndürür **VARIANT_FALSE** bu özelliğin değeri olarak.  
  
##  <a name="get_showhatching"></a>IAxWinAmbientDispatch::get_ShowHatching  
 **ShowHatching** ortam özelliği, kendisini çizgili çizip varsa öğrenmek denetim sağlar.  
  
```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```  
  
### <a name="parameters"></a>Parametreler  
 *pbShowHatching*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması her zaman döndürür **VARIANT_FALSE** bu özelliğin değeri olarak.  
  
##  <a name="get_usermode"></a>IAxWinAmbientDispatch::get_UserMode  
 **Kullanıcı modu** özelliği, kapsayıcının ortam kullanıcı modu belirtir.  
  
```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```  
  
### <a name="parameters"></a>Parametreler  
 *pbUserMode*  
 [out] Bu özelliğin geçerli değeri almak için bir değişken adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan `VARIANT_TRUE` bu özelliğin varsayılan değeri olarak.  
  
##  <a name="put_allowcontextmenu"></a>IAxWinAmbientDispatch::put_AllowContextMenu  
 **AllowContextMenu** özelliği, barındırılan denetim kendi bağlam menüsünü görüntülemek için izin verilip verilmediğini belirtir.  
  
```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 *bAllowContextMenu*  
 [in] Bu özelliğin yeni değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan `VARIANT_TRUE` bu özelliğin varsayılan değeri olarak.  
  
##  <a name="put_allowshowui"></a>IAxWinAmbientDispatch::put_AllowShowUI  
 **AllowShowUI** özelliği, kendi kullanıcı arabirimini görüntülemek için denetimden izin verilip verilmediğini belirtir.  
  
```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```  
  
### <a name="parameters"></a>Parametreler  
 *bAllowShowUI*  
 [in] Bu özelliğin yeni değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan **VARIANT_FALSE** bu özelliğin varsayılan değeri olarak.  
  
##  <a name="put_allowwindowlessactivation"></a>IAxWinAmbientDispatch::put_AllowWindowlessActivation  
 **AllowWindowlessActivation** özelliği, kapsayıcı penceresiz etkinleştirme izin verip vermeyeceğini belirtir.  
  
```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```  
  
### <a name="parameters"></a>Parametreler  
 *bAllowWindowless*  
 [in] Bu özelliğin yeni değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan `VARIANT_TRUE` bu özelliğin varsayılan değeri olarak.  
  
##  <a name="put_backcolor"></a>IAxWinAmbientDispatch::put_BackColor  
 `BackColor` Özelliği, kapsayıcı ortam arka plan rengini belirtir.  
  
```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```  
  
### <a name="parameters"></a>Parametreler  
 *clrBackground*  
 [in] Bu özelliğin yeni değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan **COLOR_BTNFACE** veya **COLOR_WINDOW** (ana penceresinin üst bir iletişim kutusu veya olup olmamasına bağlı olarak) bu özelliğin varsayılan değeri olarak.  
  
##  <a name="put_displayasdefault"></a>IAxWinAmbientDispatch::put_DisplayAsDefault  
 **DisplayAsDefault** varsayılan denetim olup olmadığını öğrenmek için denetim sağlar ortam bir özelliktir.  
  
```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```  
  
### <a name="parameters"></a>Parametreler  
 `bDisplayAsDefault`  
 [in] Bu özelliğin yeni değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan **VARIANT_FALSE** bu özelliğin varsayılan değeri olarak.  
  
##  <a name="put_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::put_DocHostDoubleClickFlags  
 **DocHostDoubleClickFlags** özelliği, yanıt zaman çift tıklatma eylemi olarak gerçekleşeceğini işlemi belirtir.  
  
```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwDocHostDoubleClickFlags*  
 [in] Bu özelliğin yeni değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan **DOCHOSTUIDBLCLK_DEFAULT** bu özelliğin varsayılan değeri olarak.  
  
##  <a name="put_dochostflags"></a>IAxWinAmbientDispatch::put_DocHostFlags  
 **DocHostFlags** özelliği, konak nesnesi kullanıcı arabirimi özelliklerini belirtir.  
  
```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwDocHostFlags*  
 [in] Bu özelliğin yeni değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan **DOCHOSTUIFLAG_NO3DBORDER** bu özelliğin varsayılan değeri olarak.  
  
##  <a name="put_font"></a>IAxWinAmbientDispatch::put_Font  
 **Yazı tipi** özelliği, kapsayıcının ortam yazı tipini belirtir.  
  
```
STDMETHOD(put_Font)(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFont`  
 [in] Bu özelliğin yeni değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması, bu özellik varsayılan değer olarak varsayılan GUI yazı tipi veya sistem yazı tipi kullanır.  
  
##  <a name="put_forecolor"></a>IAxWinAmbientDispatch::put_ForeColor  
 `ForeColor` Özelliği, kapsayıcı ortam ön plan rengini belirtir.  
  
```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```  
  
### <a name="parameters"></a>Parametreler  
 *clrForeground*  
 [in] Bu özelliğin yeni değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması sistem pencere metin rengi bu özelliğin varsayılan değeri kullanır.  
  
##  <a name="put_localeid"></a>IAxWinAmbientDispatch::put_LocaleID  
 **LocaleID** özelliği, kapsayıcı ortam yerel ayar Kimliğini belirtir.  
  
```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```  
  
### <a name="parameters"></a>Parametreler  
 *lcidLocaleID*  
 [in] Bu özelliğin yeni değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanıcının varsayılan yerel ayar, bu özelliğin varsayılan değeri kullanır.  
  
##  <a name="put_messagereflect"></a>IAxWinAmbientDispatch::put_MessageReflect  
 **MessageReflect** ortam özelliği, kapsayıcı iletileri barındırılan denetime yansıtılacaktır olup olmadığını belirtir.  
  
```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```  
  
### <a name="parameters"></a>Parametreler  
 `bMessageReflect`  
 [in] Bu özelliğin yeni değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan `VARIANT_TRUE` bu özelliğin varsayılan değeri olarak.  
  
##  <a name="put_optionkeypath"></a>IAxWinAmbientDispatch::put_OptionKeyPath  
 **OptionKeyPath** özelliği, kullanıcı ayarları için kayıt defteri anahtarının yolunu belirtir.  
  
```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```  
  
### <a name="parameters"></a>Parametreler  
 *bstrOptionKeyPath*  
 [in] Bu özelliğin yeni değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="put_usermode"></a>IAxWinAmbientDispatch::put_UserMode  
 **Kullanıcı modu** özelliği, kapsayıcının ortam kullanıcı modu belirtir.  
  
```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```  
  
### <a name="parameters"></a>Parametreler  
 `bUserMode`  
 [in] Bu özelliğin yeni değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL konak nesne uygulaması kullanan `VARIANT_TRUE` bu özelliğin varsayılan değeri olarak.  
  
##  <a name="setambientdispatch"></a>IAxWinAmbientDispatchEx::SetAmbientDispatch  
 Bu yöntem, kullanıcı tanımlı bir arabirimi varsayılan ortam özelliği arabirimiyle desteklemek üzere çağrılır.  
  
```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 *pDispatch*  
 Yeni arabirimi işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `SetAmbientDispatch` çağrılır herhangi bir özellik veya için barındırılan denetim tarafından sorulan yöntemleri çağırmak için bu yeni arabirim kullanılacak yeni bir arabirimi için bir işaretçi ile — bu özellikleri zaten tarafından sağlanmamışsa [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).  
  
##  <a name="attachcontrol"></a>IAxWinHostWindow::AttachControl  
 Var olan (ve daha önce başlatılmış) denetim tarafından tanımlanan penceresini kullanarak ana bilgisayar nesneye ekler `hWnd`.  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnkControl*  
 [in] Bir işaretçi **IUnknown** ana bilgisayar nesnesine eklenecek denetiminin arabirimi.  
  
 `hWnd`  
 [in] Barındırma için kullanılacak penceresi için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="createcontrol"></a>IAxWinHostWindow::CreateControl  
 Bir denetimi oluşturur, bunu başlatır ve tarafından tanımlanan penceresinde barındıran `hWnd`.  
  
```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpTricsData`  
 [in] Oluşturulacak denetimin tanımlayan bir dize. (Köşeli parantez içermelidir) CLSID, ProgID, URL veya ham HTML olabilir (önüne **MSHTML:**).  
  
 `hWnd`  
 [in] Barındırma için kullanılacak penceresi için bir tanıtıcı.  
  
 `pStream`  
 [in] Arabirim işaretçisi denetimi için başlatma verilerini içeren bir akış için. Olabilir **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu pencere iletileri denetime yansıtılması ve diğer kapsayıcı özellikleri çalışır bu arabirimi gösterme ana bilgisayar nesnesi tarafından sınıflandırma.  
  
 Bu yöntemin çağrılması için arama eşdeğer [IAxWinHostWindow::CreateControlEx](#createcontrolex).  
  
 Lisanslı bir ActiveX denetimi oluşturmak için bkz: [IAxWinHostWindowLic::CreateControlLic](#createcontrollicex).  
  
##  <a name="createcontrolex"></a>IAxWinHostWindow::CreateControlEx  
 ActiveX denetimi oluşturur, bunu başlatır ve benzer belirtilen penceresinde barındıran [IAxWinHostWindow::CreateControl](#createcontrol).  
  
```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpTricsData`  
 [in] Oluşturulacak denetimin tanımlayan bir dize. (Köşeli parantez içermelidir) CLSID, ProgID, URL veya ham HTML olabilir (önekine sahip **MSHTML:**).  
  
 `hWnd`  
 [in] Barındırma için kullanılacak penceresi için bir tanıtıcı.  
  
 `pStream`  
 [in] Arabirim işaretçisi denetimi için başlatma verilerini içeren bir akış için. Olabilir **NULL**.  
  
 `ppUnk`  
 [out] Alacak bir işaretçi adresini **IUnknown** oluşturulan denetiminin arabirimi. Olabilir **NULL**.  
  
 *riidAdvise*  
 [in] Kapsanan nesne giden bir arabirimde arabirimi tanımlayıcısı. Olabilir **IID_NULL**.  
  
 *punkAdvise*  
 [in] Bir işaretçi **IUnknown** arabirimi tarafından belirtilen kapsanan nesne bağlantı noktasında bağlanması için havuz nesnesinin `iidSink`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Farklı `CreateControl` yöntemi, `CreateControlEx` ayrıca yeni oluşturulan denetlemek için bir arabirim işaretçisi almak ve denetim tarafından tetiklenen olayları almak için bir olay iç havuz ayarlamanıza olanak sağlar.  
  
 Lisanslı bir ActiveX denetimi oluşturmak için bkz: [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex).  
  
##  <a name="querycontrol"></a>IAxWinHostWindow::QueryControl  
 Barındırılan denetim tarafından sağlanan belirtilen arabirim işaretçisi döndürür.  
  
```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `riid`  
 [in] İstenen denetim arabirime kimliği.  
  
 `ppvObject`  
 [out] Belirtilen arabirim oluşturulan denetiminin alacak bir işaretçi adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="setexternaldispatch"></a>IAxWinHostWindow::SetExternalDispatch  
 Kapsanan denetimlerine kullanılabilir olan dış görüntüleme arabirimi, ayarlar [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) yöntemi.  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDisp`  
 [in] Bir işaretçi bir `IDispatch` arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="setexternaluihandler"></a>IAxWinHostWindow::SetExternalUIHandler  
 Dış ayarlamak için bu işlevi çağırmak [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) için arabirim `CAxWindow` nesnesi.  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDisp`  
 [in] Bir işaretçi bir **IDocHostUIHandlerDispatch** arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev ana bilgisayarın site için sorgu denetimleri (örneğin, Web tarayıcısı denetimi) tarafından kullanılan `IDocHostUIHandlerDispatch` arabirimi.  
  
##  <a name="createcontrollic"></a>IAxWinHostWindowLic::CreateControlLic  
 Lisanslı denetim oluşturur, bunu başlatır ve tarafından tanımlanan penceresinde barındıran `hWnd`.  
  
```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>Parametreler  
 `bstrLic`  
 [in] Denetim için lisans anahtarı içeren BSTR.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IAxWinHostWindow::CreateControl](#createcontrol) kalan parametreler ve dönüş değeri açıklaması.  
  
 Bu yöntemin çağrılması için arama eşdeğer [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)  
  
### <a name="example"></a>Örnek  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `IAxWinHostWindowLic::CreateControlLic`.  
  
##  <a name="createcontrollicex"></a>IAxWinHostWindowLic::CreateControlLicEx  
 Lisanslı bir ActiveX denetimi oluşturur, bunu başlatır ve benzer belirtilen penceresinde barındıran [IAxWinHostWindow::CreateControl](#createcontrol).  
  
```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>Parametreler  
 `bstrLic`  
 [in] Denetim için lisans anahtarı içeren BSTR.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IAxWinHostWindow::CreateControlEx](#createcontrolex) kalan parametreler ve dönüş değeri açıklaması.  
  
### <a name="example"></a>Örnek  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `IAxWinHostWindowLic::CreateControlLicEx`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
