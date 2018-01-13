---
title: IAxWinAmbientDispatch arabirimi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinAmbientDispatch
- ATLIFACE/ATL::IAxWinAmbientDispatch
- ATLIFACE/ATL::get_AllowContextMenu
- ATLIFACE/ATL::get_AllowShowUI
- ATLIFACE/ATL::get_AllowWindowlessActivation
- ATLIFACE/ATL::get_BackColor
- ATLIFACE/ATL::get_DisplayAsDefault
- ATLIFACE/ATL::get_DocHostDoubleClickFlags
- ATLIFACE/ATL::get_DocHostFlags
- ATLIFACE/ATL::get_Font
- ATLIFACE/ATL::get_ForeColor
- ATLIFACE/ATL::get_LocaleID
- ATLIFACE/ATL::get_MessageReflect
- ATLIFACE/ATL::get_OptionKeyPath
- ATLIFACE/ATL::get_ShowGrabHandles
- ATLIFACE/ATL::get_ShowHatching
- ATLIFACE/ATL::get_UserMode
- ATLIFACE/ATL::put_AllowContextMenu
- ATLIFACE/ATL::put_AllowShowUI
- ATLIFACE/ATL::put_AllowWindowlessActivation
- ATLIFACE/ATL::put_BackColor
- ATLIFACE/ATL::put_DisplayAsDefault
- ATLIFACE/ATL::put_DocHostDoubleClickFlags
- ATLIFACE/ATL::put_DocHostFlags
- ATLIFACE/ATL::put_Font
- ATLIFACE/ATL::put_ForeColor
- ATLIFACE/ATL::put_LocaleID
- ATLIFACE/ATL::put_MessageReflect
- ATLIFACE/ATL::put_OptionKeyPath
- ATLIFACE/ATL::put_UserMode
dev_langs: C++
helpviewer_keywords: IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e9d53dc257920e40dbf6a2f360d1289676d121fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="iaxwinambientdispatch-interface"></a>IAxWinAmbientDispatch arabirimi
Bu arabirim barındırılan denetime veya kapsayıcı özelliklerini belirtmek için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
interface IAxWinAmbientDispatch : IDispatch
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[get_AllowContextMenu](#get_allowcontextmenu)|**AllowContextMenu** özelliği, barındırılan denetim kendi bağlam menüsünü görüntülemek için izin verilip verilmediğini belirtir.|  
|[get_AllowShowUI](#get_allowshowui)|**AllowShowUI** özelliği, kendi kullanıcı arabirimini görüntülemek için denetimden izin verilip verilmediğini belirtir.|  
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|**AllowWindowlessActivation** özelliği, kapsayıcı penceresiz etkinleştirme izin verip vermeyeceğini belirtir.|  
|[get_BackColor](#get_backcolor)|`BackColor` Özelliği, kapsayıcı ortam arka plan rengini belirtir.|  
|[get_DisplayAsDefault](#get_displayasdefault)|**DisplayAsDefault** varsayılan denetim olup olmadığını öğrenmek için denetim sağlar ortam bir özelliktir.|  
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|**DocHostDoubleClickFlags** özelliği, yanıt zaman çift tıklatma eylemi olarak gerçekleşeceğini işlemi belirtir.|  
|[get_DocHostFlags](#get_dochostflags)|**DocHostFlags** özelliği, konak nesnesi kullanıcı arabirimi özelliklerini belirtir.|  
|[get_Font](#get_font)|**Yazı tipi** özelliği, kapsayıcının ortam yazı tipini belirtir.|  
|[get_ForeColor](#get_forecolor)|`ForeColor` Özelliği, kapsayıcı ortam ön plan rengini belirtir.|  
|[get_LocaleID](#get_localeid)|**LocaleID** özelliği, kapsayıcı ortam yerel ayar Kimliğini belirtir.|  
|[get_MessageReflect](#get_messagereflect)|**MessageReflect** ortam özelliği, kapsayıcı iletileri barındırılan denetime yansıtılacaktır olup olmadığını belirtir.|  
|[get_OptionKeyPath](#get_optionkeypath)|**OptionKeyPath** özelliği, kullanıcı ayarları için kayıt defteri anahtarının yolunu belirtir.|  
|[get_ShowGrabHandles](#get_showgrabhandles)|**ShowGrabHandles** ortam özelliği, kendisini Al tanıtıcıları ile çizip varsa öğrenmek denetim sağlar.|  
|[get_ShowHatching](#get_showhatching)|**ShowHatching** ortam özelliği, kendisini çizgili çizip varsa öğrenmek denetim sağlar.|  
|[get_UserMode](#get_usermode)|**Kullanıcı modu** özelliği, kapsayıcının ortam kullanıcı modu belirtir.|  
|[put_AllowContextMenu](#put_allowcontextmenu)|**AllowContextMenu** özelliği, barındırılan denetim kendi bağlam menüsünü görüntülemek için izin verilip verilmediğini belirtir.|  
|[put_AllowShowUI](#put_allowshowui)|**AllowShowUI** özelliği, kendi kullanıcı arabirimini görüntülemek için denetimden izin verilip verilmediğini belirtir.|  
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|**AllowWindowlessActivation** özelliği, kapsayıcı penceresiz etkinleştirme izin verip vermeyeceğini belirtir.|  
|[put_BackColor](#put_backcolor)|`BackColor` Özelliği, kapsayıcı ortam arka plan rengini belirtir.|  
|[put_DisplayAsDefault](#put_displayasdefault)|**DisplayAsDefault** varsayılan denetim olup olmadığını öğrenmek için denetim sağlar ortam bir özelliktir.|  
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|**DocHostDoubleClickFlags** özelliği, yanıt zaman çift tıklatma eylemi olarak gerçekleşeceğini işlemi belirtir.|  
|[put_DocHostFlags](#put_dochostflags)|**DocHostFlags** özelliği, konak nesnesi kullanıcı arabirimi özelliklerini belirtir.|  
|[put_Font](#put_font)|**Yazı tipi** özelliği, kapsayıcının ortam yazı tipini belirtir.|  
|[put_ForeColor](#put_forecolor)|`ForeColor` Özelliği, kapsayıcı ortam ön plan rengini belirtir.|  
|[put_LocaleID](#put_localeid)|**LocaleID** özelliği, kapsayıcı ortam yerel ayar Kimliğini belirtir.|  
|[put_MessageReflect](#put_messagereflect)|**MessageReflect** ortam özelliği, kapsayıcı iletileri barındırılan denetime yansıtılacaktır olup olmadığını belirtir.|  
|[put_OptionKeyPath](#put_optionkeypath)|**OptionKeyPath** özelliği, kullanıcı ayarları için kayıt defteri anahtarının yolunu belirtir.|  
|[put_UserMode](#put_usermode)|**Kullanıcı modu** özelliği, kapsayıcının ortam kullanıcı modu belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim nesneleri barındırma ATL'in ActiveX denetimi tarafından sunulur. Yöntemleri kullanılabilir ortam özelliklerine barındırılan denetime ayarlamak veya diğer yönlerini kapsayıcının davranışı belirtmek için bu arabirimde çağırın. Tarafından sağlanan özellikleri desteklemek üzere `IAxWinAmbientDispatch`, kullanın [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md).  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) hakkında türü bilgileri yüklenmeye çalışılacak `IAxWinAmbientDispatch` ve `IAxWinAmbientDispatchEx` kodunu içerir typelib gelen.  
  
 ATL90.dll için bağlıyorsanız **AXHost** türü bilgileri DLL'deki typelib yüklemek.  
  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) daha fazla ayrıntı için.  
  
## <a name="requirements"></a>Gereksinimler  
 Bu arabirim tanımı aşağıdaki tabloda gösterildiği gibi formlar, bir süre içinde kullanılabilir.  
  
|Tanım türü|Dosya|  
|---------------------|----------|  
|IDL|atliface.idl|  
|Tür kitaplığı|ATL.|  
|C++|atliface.h (ATLBase.h içinde de dahil)|  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IAxWinAmbientDispatchEx arabirimi](../../atl/reference/iaxwinambientdispatchex-interface.md)   
 [IAxWinHostWindow arabirimi](../../atl/reference/iaxwinhostwindow-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)









