---
title: IAxWinAmbientDispatch Arabirimi
ms.date: 11/04/2016
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
helpviewer_keywords:
- IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
ms.openlocfilehash: 6a4f5322d957b1e978bd123db3b4796be6b300da
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330005"
---
# <a name="iaxwinambientdispatch-interface"></a>IAxWinAmbientDispatch Arabirimi

Bu arabirim, barındırılan denetimin veya kapsayıcının özelliklerini belirtmek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
interface IAxWinAmbientDispatch : IDispatch
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[get_AllowContextMenu](#get_allowcontextmenu)|Özellik, `AllowContextMenu` barındırılan denetimin kendi bağlam menüsünü görüntülemesine izin verilip verilmediğini belirtir.|
|[get_AllowShowUI](#get_allowshowui)|Özellik, `AllowShowUI` barındırılan denetimin kendi kullanıcı arabirimini görüntülemesine izin verilip verilmediğini belirtir.|
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|Özellik, `AllowWindowlessActivation` kapsayıcının penceresiz etkinleştirmeye izin verip vermeyeceği belirtilir.|
|[get_BackColor](#get_backcolor)|Özellik, `BackColor` kapsayıcının ortam arka plan rengini belirtir.|
|[get_DisplayAsDefault](#get_displayasdefault)|`DisplayAsDefault`denetimin varsayılan denetim olup olmadığını öğrenmesini sağlayan bir ortam özelliğidir.|
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|Özellik, `DocHostDoubleClickFlags` çift tıklatmaya yanıt olarak gerçekleşmesi gereken işlemi belirtir.|
|[get_DocHostFlags](#get_dochostflags)|Özellik, `DocHostFlags` ana bilgisayar nesnesinin kullanıcı arabirimi özelliklerini belirtir.|
|[get_Font](#get_font)|Özellik, `Font` kapsayıcının ortam yazı tipini belirtir.|
|[get_ForeColor](#get_forecolor)|Özellik, `ForeColor` konteynerin ortam ön plan rengini belirtir.|
|[get_LocaleID](#get_localeid)|Özellik, `LocaleID` kapsayıcının ortam yerel kimliğini belirtir.|
|[get_MessageReflect](#get_messagereflect)|Ortam `MessageReflect` özelliği, kapsayıcının iletileri barındırılan denetime yansıtıp yansıtmayacağını belirtir.|
|[get_OptionKeyPath](#get_optionkeypath)|Özellik, `OptionKeyPath` kullanıcı ayarlarına giden kayıt defteri anahtar yolunu belirtir.|
|[get_ShowGrabHandles](#get_showgrabhandles)|Ortam `ShowGrabHandles` özelliği, kontrolün kendisini tutamak kollarıyla çizip çizmemesi gerektiğini öğrenmesini sağlar.|
|[get_ShowHatching](#get_showhatching)|Ortam `ShowHatching` özelliği, kontrolün kendisini yumurtadan çıkarıp çıkarmaması gerektiğini öğrenmesini sağlar.|
|[get_UserMode](#get_usermode)|Özellik, `UserMode` kapsayıcının ortam kullanıcı modunu belirtir.|
|[put_AllowContextMenu](#put_allowcontextmenu)|Özellik, `AllowContextMenu` barındırılan denetimin kendi bağlam menüsünü görüntülemesine izin verilip verilmediğini belirtir.|
|[put_AllowShowUI](#put_allowshowui)|Özellik, `AllowShowUI` barındırılan denetimin kendi kullanıcı arabirimini görüntülemesine izin verilip verilmediğini belirtir.|
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|Özellik, `AllowWindowlessActivation` kapsayıcının penceresiz etkinleştirmeye izin verip vermeyeceği belirtilir.|
|[put_BackColor](#put_backcolor)|Özellik, `BackColor` kapsayıcının ortam arka plan rengini belirtir.|
|[put_DisplayAsDefault](#put_displayasdefault)|`DisplayAsDefault`denetimin varsayılan denetim olup olmadığını öğrenmesini sağlayan bir ortam özelliğidir.|
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|Özellik, `DocHostDoubleClickFlags` çift tıklatmaya yanıt olarak gerçekleşmesi gereken işlemi belirtir.|
|[put_DocHostFlags](#put_dochostflags)|Özellik, `DocHostFlags` ana bilgisayar nesnesinin kullanıcı arabirimi özelliklerini belirtir.|
|[put_Font](#put_font)|Özellik, `Font` kapsayıcının ortam yazı tipini belirtir.|
|[put_ForeColor](#put_forecolor)|Özellik, `ForeColor` konteynerin ortam ön plan rengini belirtir.|
|[put_LocaleID](#put_localeid)|Özellik, `LocaleID` kapsayıcının ortam yerel kimliğini belirtir.|
|[put_MessageReflect](#put_messagereflect)|Ortam `MessageReflect` özelliği, kapsayıcının iletileri barındırılan denetime yansıtıp yansıtmayacağını belirtir.|
|[put_OptionKeyPath](#put_optionkeypath)|Özellik, `OptionKeyPath` kullanıcı ayarlarına giden kayıt defteri anahtar yolunu belirtir.|
|[put_UserMode](#put_usermode)|Özellik, `UserMode` kapsayıcının ortam kullanıcı modunu belirtir.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, ATL'nin ActiveX denetim barındırma nesneleri tarafından ortaya çıkarır. Barındırılan denetimin kullanılabilir ortam özelliklerini ayarlamak veya kapsayıcının davranışının diğer yönlerini belirtmek için bu arabirimdeki yöntemleri çağırın. Tarafından sağlanan özellikleri `IAxWinAmbientDispatch`tamamlamak için , [iAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)kullanın.

<xref:System.Windows.Forms.AxHost>kodu içeren typelib `IAxWinAmbientDispatch` hakkında `IAxWinAmbientDispatchEx` ve gelen tür bilgilerini yüklemeye çalışacaktır.

ATL90.dll'ye bağlayacaksanız, **AXHost** dll'deki typelib'den tür bilgilerini yükler.

Daha fazla bilgi için [ATL AXHost kullanarak ActiveX Denetimleri Barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bakın.

## <a name="requirements"></a>Gereksinimler

Bu arabirimin tanımı, aşağıdaki tabloda gösterildiği gibi, çeşitli formlarda kullanılabilir.

|Tanım Türü|Dosya|
|---------------------|----------|
|ıdl|atliface.idl|
|Tür Kitaplığı|ATL.dll|
|C++|atliface.h (Ayrıca ATLBase.h dahil)|

## <a name="iaxwinambientdispatchget_allowcontextmenu"></a><a name="get_allowcontextmenu"></a>IAxWinAmbientDispatch::get_AllowContextMenu

Özellik, `AllowContextMenu` barındırılan denetimin kendi bağlam menüsünü görüntülemesine izin verilip verilmediğini belirtir.

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>Parametreler

*pbAllowContextMenu*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchget_allowshowui"></a><a name="get_allowshowui"></a>IAxWinAmbientDispatch::get_AllowShowUI

Özellik, `AllowShowUI` barındırılan denetimin kendi kullanıcı arabirimini görüntülemesine izin verilip verilmediğini belirtir.

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>Parametreler

*pbAllowShowUI*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak VARIANT_FALSE kullanır.

## <a name="iaxwinambientdispatchget_allowwindowlessactivation"></a><a name="get_allowwindowlessactivation"></a>IAxWinAmbientDispatch::get_AllowWindowlessActivation

Özellik, `AllowWindowlessActivation` kapsayıcının penceresiz etkinleştirmeye izin verip vermeyeceği belirtilir.

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>Parametreler

*pbAllowWindowless*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchget_backcolor"></a><a name="get_backcolor"></a>IAxWinAmbientDispatch::get_BackColor

Özellik, `BackColor` kapsayıcının ortam arka plan rengini belirtir.

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>Parametreler

*pclrArka*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak COLOR_BTNFACE veya COLOR_WINDOW kullanır (ana bilgisayar penceresinin üst öğesinin iletişim kutusu olup olmamasına bağlı olarak).

## <a name="iaxwinambientdispatchget_displayasdefault"></a><a name="get_displayasdefault"></a>IAxWinAmbientDispatch::get_DisplayAsDefault

`DisplayAsDefault`denetimin varsayılan denetim olup olmadığını öğrenmesini sağlayan bir ortam özelliğidir.

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>Parametreler

*pbDisplayAsVarsayılan*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak VARIANT_FALSE kullanır.

## <a name="iaxwinambientdispatchget_dochostdoubleclickflags"></a><a name="get_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::get_DocHostDoubleClickFlags

Özellik, `DocHostDoubleClickFlags` çift tıklatmaya yanıt olarak gerçekleşmesi gereken işlemi belirtir.

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Parametreler

*pdwDocHostDoubleClickClickFlags*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak DOCHOSTUIDBLCLK_DEFAULT kullanır.

## <a name="iaxwinambientdispatchget_dochostflags"></a><a name="get_dochostflags"></a>IAxWinAmbientDispatch::get_DocHostFlags

Özellik, `DocHostFlags` ana bilgisayar nesnesinin kullanıcı arabirimi özelliklerini belirtir.

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>Parametreler

*pdwDocHostFlags*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak DOCHOSTUIFLAG_NO3DBORDER kullanır.

## <a name="iaxwinambientdispatchget_font"></a><a name="get_font"></a>IAxWinAmbientDispatch::get_Font

Özellik, `Font` kapsayıcının ortam yazı tipini belirtir.

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
[çıkış] Bu özelliğin `IFontDisp` geçerli değerini almak için kullanılan bir arabirim işaretçisinin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak varsayılan GUI yazı tipini veya sistem yazı tipini kullanır.

## <a name="iaxwinambientdispatchget_forecolor"></a><a name="get_forecolor"></a>IAxWinAmbientDispatch::get_ForeColor

Özellik, `ForeColor` konteynerin ortam ön plan rengini belirtir.

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>Parametreler

*pclrForeground*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak sistem penceresi metin rengini kullanır.

## <a name="iaxwinambientdispatchget_localeid"></a><a name="get_localeid"></a>IAxWinAmbientDispatch::get_LocaleID

Özellik, `LocaleID` kapsayıcının ortam yerel kimliğini belirtir.

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>Parametreler

*plcidLocaleID*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak kullanıcının varsayılan yerel sini kullanır.

Bu yöntemle Ortam LocalID'ini, yani denetiminizin kullanıldığı programın LocaleID'ini keşfedebilirsiniz. LocaleID'yi anladıktan sonra, yerel e-özel altyazıları, hata iletisi metnini ve benzeri özellikleri bir kaynak dosyasından veya uydu DLL'den yüklemek için kodu arayabilirsiniz.

## <a name="iaxwinambientdispatchget_messagereflect"></a><a name="get_messagereflect"></a>IAxWinAmbientDispatch::get_MessageReflect

Ortam `MessageReflect` özelliği, kapsayıcının iletileri barındırılan denetime yansıtıp yansıtmayacağını belirtir.

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>Parametreler

*pbMessageReflect*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchget_optionkeypath"></a><a name="get_optionkeypath"></a>IAxWinAmbientDispatch::get_OptionKeyPath

Özellik, `OptionKeyPath` kullanıcı ayarlarına giden kayıt defteri anahtar yolunu belirtir.

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>Parametreler

*pbstrOptionKeyPath*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="iaxwinambientdispatchget_showgrabhandles"></a><a name="get_showgrabhandles"></a>IAxWinAmbientDispatch::get_ShowGrabHandles

Ortam `ShowGrabHandles` özelliği, kontrolün kendisini tutamak kollarıyla çizip çizmemesi gerektiğini öğrenmesini sağlar.

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>Parametreler

*pbShowGrabHandles*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması her zaman bu özelliğin değeri olarak VARIANT_FALSE döndürür.

## <a name="iaxwinambientdispatchget_showhatching"></a><a name="get_showhatching"></a>IAxWinAmbientDispatch::get_ShowHatching

Ortam `ShowHatching` özelliği, kontrolün kendisini yumurtadan çıkarıp çıkarmaması gerektiğini öğrenmesini sağlar.

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>Parametreler

*pbShowHatching*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması her zaman bu özelliğin değeri olarak VARIANT_FALSE döndürür.

## <a name="iaxwinambientdispatchget_usermode"></a><a name="get_usermode"></a>IAxWinAmbientDispatch::get_UserMode

Özellik, `UserMode` kapsayıcının ortam kullanıcı modunu belirtir.

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>Parametreler

*pbUserMode*<br/>
[çıkış] Bu özelliğin geçerli değerini almak için bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchput_allowcontextmenu"></a><a name="put_allowcontextmenu"></a>IAxWinAmbientDispatch::put_AllowContextMenu

Özellik, `AllowContextMenu` barındırılan denetimin kendi bağlam menüsünü görüntülemesine izin verilip verilmediğini belirtir.

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>Parametreler

*bAllowContextMenu*<br/>
[içinde] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchput_allowshowui"></a><a name="put_allowshowui"></a>IAxWinAmbientDispatch::put_AllowShowUI

Özellik, `AllowShowUI` barındırılan denetimin kendi kullanıcı arabirimini görüntülemesine izin verilip verilmediğini belirtir.

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>Parametreler

*bAllowShowUI*<br/>
[içinde] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak VARIANT_FALSE kullanır.

## <a name="iaxwinambientdispatchput_allowwindowlessactivation"></a><a name="put_allowwindowlessactivation"></a>IAxWinAmbientDispatch::put_AllowWindowlessActivation

Özellik, `AllowWindowlessActivation` kapsayıcının penceresiz etkinleştirmeye izin verip vermeyeceği belirtilir.

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>Parametreler

*bAllowWindowless*<br/>
[içinde] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchput_backcolor"></a><a name="put_backcolor"></a>IAxWinAmbientDispatch::put_BackColor

Özellik, `BackColor` kapsayıcının ortam arka plan rengini belirtir.

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>Parametreler

*clrArka*<br/>
[içinde] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak COLOR_BTNFACE veya COLOR_WINDOW kullanır (ana bilgisayar penceresinin üst öğesinin iletişim kutusu olup olmamasına bağlı olarak).

## <a name="iaxwinambientdispatchput_displayasdefault"></a><a name="put_displayasdefault"></a>IAxWinAmbientDispatch::put_DisplayAsDefault

`DisplayAsDefault`denetimin varsayılan denetim olup olmadığını öğrenmesini sağlayan bir ortam özelliğidir.

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>Parametreler

*bDisplayAsDefault*<br/>
[içinde] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak VARIANT_FALSE kullanır.

## <a name="iaxwinambientdispatchput_dochostdoubleclickflags"></a><a name="put_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::put_DocHostDoubleClickFlags

Özellik, `DocHostDoubleClickFlags` çift tıklatmaya yanıt olarak gerçekleşmesi gereken işlemi belirtir.

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Parametreler

*dwDocHostDoubleClickFlags*<br/>
[içinde] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak DOCHOSTUIDBLCLK_DEFAULT kullanır.

## <a name="iaxwinambientdispatchput_dochostflags"></a><a name="put_dochostflags"></a>IAxWinAmbientDispatch::put_DocHostFlags

Özellik, `DocHostFlags` ana bilgisayar nesnesinin kullanıcı arabirimi özelliklerini belirtir.

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>Parametreler

*dwDocHostFlags*<br/>
[içinde] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak DOCHOSTUIFLAG_NO3DBORDER kullanır.

## <a name="iaxwinambientdispatchput_font"></a><a name="put_font"></a>IAxWinAmbientDispatch::put_Font

Özellik, `Font` kapsayıcının ortam yazı tipini belirtir.

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
[içinde] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak varsayılan GUI yazı tipini veya sistem yazı tipini kullanır.

## <a name="iaxwinambientdispatchput_forecolor"></a><a name="put_forecolor"></a>IAxWinAmbientDispatch::put_ForeColor

Özellik, `ForeColor` konteynerin ortam ön plan rengini belirtir.

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>Parametreler

*clrForeground*<br/>
[içinde] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak sistem penceresi metin rengini kullanır.

## <a name="iaxwinambientdispatchput_localeid"></a><a name="put_localeid"></a>IAxWinAmbientDispatch::put_LocaleID

Özellik, `LocaleID` kapsayıcının ortam yerel kimliğini belirtir.

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>Parametreler

*lcidLocaleID*<br/>
[içinde] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak kullanıcının varsayılan yerel sini kullanır.

## <a name="iaxwinambientdispatchput_messagereflect"></a><a name="put_messagereflect"></a>IAxWinAmbientDispatch::put_MessageReflect

Ortam `MessageReflect` özelliği, kapsayıcının iletileri barındırılan denetime yansıtıp yansıtmayacağını belirtir.

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>Parametreler

*bMessageReflect*<br/>
[içinde] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchput_optionkeypath"></a><a name="put_optionkeypath"></a>IAxWinAmbientDispatch::put_OptionKeyPath

Özellik, `OptionKeyPath` kullanıcı ayarlarına giden kayıt defteri anahtar yolunu belirtir.

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>Parametreler

*bstrOptionKeyPath*<br/>
[içinde] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="iaxwinambientdispatchput_usermode"></a><a name="put_usermode"></a>IAxWinAmbientDispatch::put_UserMode

Özellik, `UserMode` kapsayıcının ortam kullanıcı modunu belirtir.

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>Parametreler

*bUserMode*<br/>
[içinde] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulaması, bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[IAxWinAmbientDispatchEx Arabirimi](../../atl/reference/iaxwinambientdispatchex-interface.md)<br/>
[IAxWinHostWindow Arabirimi](../../atl/reference/iaxwinhostwindow-interface.md)<br/>
[CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
