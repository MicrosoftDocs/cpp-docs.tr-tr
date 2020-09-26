---
title: IAxWinAmbientDispatch arabirimi
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
ms.openlocfilehash: dbd682451ca5499aef4b16b3b51feba8411bdd12
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352966"
---
# <a name="iaxwinambientdispatch-interface"></a>IAxWinAmbientDispatch arabirimi

Bu arabirim barındırılan denetimin veya kapsayıcının özelliklerini belirtmek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
interface IAxWinAmbientDispatch : IDispatch
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|-|-|
|[get_AllowContextMenu](#get_allowcontextmenu)|`AllowContextMenu`Özelliği barındırılan denetimin kendi bağlam menüsünü görüntülemesine izin verilip verilmeyeceğini belirtir.|
|[get_AllowShowUI](#get_allowshowui)|`AllowShowUI`Özelliği barındırılan denetimin kendi Kullanıcı arabirimini görüntülemesine izin verilip verilmeyeceğini belirtir.|
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|`AllowWindowlessActivation`Özelliği, kapsayıcının penceresiz etkinleştirmeye izin verip vermeyeceğini belirtir.|
|[get_BackColor](#get_backcolor)|`BackColor`Özelliği, kapsayıcının çevresel arka plan rengini belirtir.|
|[get_DisplayAsDefault](#get_displayasdefault)|`DisplayAsDefault` , denetimin varsayılan denetim olup olmadığını bulmasına izin veren bir çevresel özelliktir.|
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|`DocHostDoubleClickFlags`Özelliği, Çift tıklamayla yanıt olarak gerçekleşmesi gereken işlemi belirtir.|
|[get_DocHostFlags](#get_dochostflags)|`DocHostFlags`Özelliği, ana bilgisayar nesnesinin kullanıcı arabirimi yeteneklerini belirtir.|
|[get_Font](#get_font)|`Font`Özelliği, kapsayıcının çevresel yazı tipini belirtir.|
|[get_ForeColor](#get_forecolor)|`ForeColor`Özelliği, kapsayıcının çevresel ön plan rengini belirtir.|
|[get_LocaleID](#get_localeid)|`LocaleID`Özelliği, kapsayıcının çevresel yerel kimliğini belirtir.|
|[get_MessageReflect](#get_messagereflect)|`MessageReflect`Ambient özelliği, kapsayıcının iletileri barındırılan denetime yansıtmayacağını belirtir.|
|[get_OptionKeyPath](#get_optionkeypath)|`OptionKeyPath`Özelliği, Kullanıcı ayarlarının kayıt defteri anahtarı yolunu belirtir.|
|[get_ShowGrabHandles](#get_showgrabhandles)|`ShowGrabHandles`Ambient özelliği, denetimin kendisini alma tutamaçlarla çizmesi gerekip gerekmediğini bulmasına olanak tanır.|
|[get_ShowHatching](#get_showhatching)|`ShowHatching`Ambient özelliği, denetimin kendisini taralı olarak çizmesi gerekip gerekmediğini bulmasına olanak tanır.|
|[get_UserMode](#get_usermode)|`UserMode`Özelliği, kapsayıcının çevresel Kullanıcı modunu belirtir.|
|[put_AllowContextMenu](#put_allowcontextmenu)|`AllowContextMenu`Özelliği barındırılan denetimin kendi bağlam menüsünü görüntülemesine izin verilip verilmeyeceğini belirtir.|
|[put_AllowShowUI](#put_allowshowui)|`AllowShowUI`Özelliği barındırılan denetimin kendi Kullanıcı arabirimini görüntülemesine izin verilip verilmeyeceğini belirtir.|
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|`AllowWindowlessActivation`Özelliği, kapsayıcının penceresiz etkinleştirmeye izin verip vermeyeceğini belirtir.|
|[put_BackColor](#put_backcolor)|`BackColor`Özelliği, kapsayıcının çevresel arka plan rengini belirtir.|
|[put_DisplayAsDefault](#put_displayasdefault)|`DisplayAsDefault` , denetimin varsayılan denetim olup olmadığını bulmasına izin veren bir çevresel özelliktir.|
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|`DocHostDoubleClickFlags`Özelliği, Çift tıklamayla yanıt olarak gerçekleşmesi gereken işlemi belirtir.|
|[put_DocHostFlags](#put_dochostflags)|`DocHostFlags`Özelliği, ana bilgisayar nesnesinin kullanıcı arabirimi yeteneklerini belirtir.|
|[put_Font](#put_font)|`Font`Özelliği, kapsayıcının çevresel yazı tipini belirtir.|
|[put_ForeColor](#put_forecolor)|`ForeColor`Özelliği, kapsayıcının çevresel ön plan rengini belirtir.|
|[put_LocaleID](#put_localeid)|`LocaleID`Özelliği, kapsayıcının çevresel yerel kimliğini belirtir.|
|[put_MessageReflect](#put_messagereflect)|`MessageReflect`Ambient özelliği, kapsayıcının iletileri barındırılan denetime yansıtmayacağını belirtir.|
|[put_OptionKeyPath](#put_optionkeypath)|`OptionKeyPath`Özelliği, Kullanıcı ayarlarının kayıt defteri anahtarı yolunu belirtir.|
|[put_UserMode](#put_usermode)|`UserMode`Özelliği, kapsayıcının çevresel Kullanıcı modunu belirtir.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, ATL 'nin ActiveX denetimi barındırma nesneleri tarafından sunulur. Barındırılan denetim için kullanılabilir çevresel özellikleri ayarlamak ya da kapsayıcının davranışının diğer yönlerini belirtmek için bu arabirimdeki yöntemleri çağırın. Tarafından sunulan özellikleri tamamlamak için `IAxWinAmbientDispatch` , [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)kullanın.

<xref:System.Windows.Forms.AxHost>`IAxWinAmbientDispatch` `IAxWinAmbientDispatchEx` kodu içeren tür kitaplığı üzerinden ve ile ilgili tür bilgilerini yüklemeye çalışır.

ATL90.dll bağlıyorsanız, **AxHost** tür bilgilerini dll 'deki TypeLib 'den yükler.

Daha fazla ayrıntı için bkz. [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) .

## <a name="requirements"></a>Gereksinimler

Bu arabirimin tanımı, aşağıdaki tabloda gösterildiği gibi çeşitli formlarda kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|IDL|atlıyüz. IDL|
|Tür kitaplığı|ATL.dll|
|C++|atlıyüz. h (ATLBase. h 'ye de dahildir)|

## <a name="iaxwinambientdispatchget_allowcontextmenu"></a><a name="get_allowcontextmenu"></a> IAxWinAmbientDispatch:: get_AllowContextMenu

`AllowContextMenu`Özelliği barındırılan denetimin kendi bağlam menüsünü görüntülemesine izin verilip verilmeyeceğini belirtir.

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>Parametreler

*pbAllowContextMenu*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchget_allowshowui"></a><a name="get_allowshowui"></a> IAxWinAmbientDispatch:: get_AllowShowUI

`AllowShowUI`Özelliği barındırılan denetimin kendi Kullanıcı arabirimini görüntülemesine izin verilip verilmeyeceğini belirtir.

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>Parametreler

*Pballowshowuı*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak VARIANT_FALSE kullanır.

## <a name="iaxwinambientdispatchget_allowwindowlessactivation"></a><a name="get_allowwindowlessactivation"></a> IAxWinAmbientDispatch:: get_AllowWindowlessActivation

`AllowWindowlessActivation`Özelliği, kapsayıcının penceresiz etkinleştirmeye izin verip vermeyeceğini belirtir.

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>Parametreler

*Pballowpenceresiz*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchget_backcolor"></a><a name="get_backcolor"></a> IAxWinAmbientDispatch:: get_BackColor

`BackColor`Özelliği, kapsayıcının çevresel arka plan rengini belirtir.

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>Parametreler

*pclrBackground*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL konak nesne uygulama, bu özelliğin varsayılan değeri olarak COLOR_BTNFACE veya COLOR_WINDOW kullanır (konak penceresinin üst öğesinin bir iletişim kutusu olup olmadığına bağlı olarak).

## <a name="iaxwinambientdispatchget_displayasdefault"></a><a name="get_displayasdefault"></a> IAxWinAmbientDispatch:: get_DisplayAsDefault

`DisplayAsDefault` , denetimin varsayılan denetim olup olmadığını bulmasına izin veren bir çevresel özelliktir.

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>Parametreler

*pbDisplayAsDefault*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak VARIANT_FALSE kullanır.

## <a name="iaxwinambientdispatchget_dochostdoubleclickflags"></a><a name="get_dochostdoubleclickflags"></a> IAxWinAmbientDispatch:: get_DocHostDoubleClickFlags

`DocHostDoubleClickFlags`Özelliği, Çift tıklamayla yanıt olarak gerçekleşmesi gereken işlemi belirtir.

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Parametreler

*pdwDocHostDoubleClickFlags*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak DOCHOSTUIDBLCLK_DEFAULT kullanır.

## <a name="iaxwinambientdispatchget_dochostflags"></a><a name="get_dochostflags"></a> IAxWinAmbientDispatch:: get_DocHostFlags

`DocHostFlags`Özelliği, ana bilgisayar nesnesinin kullanıcı arabirimi yeteneklerini belirtir.

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>Parametreler

*pdwDocHostFlags*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak DOCHOSTUIFLAG_NO3DBORDER kullanır.

## <a name="iaxwinambientdispatchget_font"></a><a name="get_font"></a> IAxWinAmbientDispatch:: get_Font

`Font`Özelliği, kapsayıcının çevresel yazı tipini belirtir.

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
dışı `IFontDisp` Bu özelliğin geçerli değerini almak için kullanılan bir arabirim işaretçisinin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının varsayılan GUI yazı tipini veya sistem yazı tipini bu özelliğin varsayılan değeri olarak kullanır.

## <a name="iaxwinambientdispatchget_forecolor"></a><a name="get_forecolor"></a> IAxWinAmbientDispatch:: get_ForeColor

`ForeColor`Özelliği, kapsayıcının çevresel ön plan rengini belirtir.

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>Parametreler

*Pclrönalanı*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulama, bu özelliğin varsayılan değeri olarak sistem pencere metin rengini kullanır.

## <a name="iaxwinambientdispatchget_localeid"></a><a name="get_localeid"></a> IAxWinAmbientDispatch:: get_LocaleID

`LocaleID`Özelliği, kapsayıcının çevresel yerel kimliğini belirtir.

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>Parametreler

*Plcidlocaleıd*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama, kullanıcının varsayılan yerel ayarını bu özelliğin varsayılan değeri olarak kullanır.

Bu yöntemle, Ambient LocalId ' yi, diğer bir deyişle, denetiminizin kullanıldığı programın LocaleID 'sini bulabilirsiniz. LocaleID 'yi öğrendikten sonra, yerel ayara özgü açıklamalı alt yazıları, hata iletisi metnini ve benzerlerini bir kaynak dosyasından veya uydu DLL 'sinden yüklemek için kodu çağırabilirsiniz.

## <a name="iaxwinambientdispatchget_messagereflect"></a><a name="get_messagereflect"></a> IAxWinAmbientDispatch:: get_MessageReflect

`MessageReflect`Ambient özelliği, kapsayıcının iletileri barındırılan denetime yansıtmayacağını belirtir.

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>Parametreler

*Pbmessagerefseç*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchget_optionkeypath"></a><a name="get_optionkeypath"></a> IAxWinAmbientDispatch:: get_OptionKeyPath

`OptionKeyPath`Özelliği, Kullanıcı ayarlarının kayıt defteri anahtarı yolunu belirtir.

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>Parametreler

*pbstrOptionKeyPath*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="iaxwinambientdispatchget_showgrabhandles"></a><a name="get_showgrabhandles"></a> IAxWinAmbientDispatch:: get_ShowGrabHandles

`ShowGrabHandles`Ambient özelliği, denetimin kendisini alma tutamaçlarla çizmesi gerekip gerekmediğini bulmasına olanak tanır.

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>Parametreler

*pbShowGrabHandles*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulama, her zaman bu özelliğin değeri olarak VARIANT_FALSE döndürür.

## <a name="iaxwinambientdispatchget_showhatching"></a><a name="get_showhatching"></a> IAxWinAmbientDispatch:: get_ShowHatching

`ShowHatching`Ambient özelliği, denetimin kendisini taralı olarak çizmesi gerekip gerekmediğini bulmasına olanak tanır.

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>Parametreler

*Pbshowhadikiş*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulama, her zaman bu özelliğin değeri olarak VARIANT_FALSE döndürür.

## <a name="iaxwinambientdispatchget_usermode"></a><a name="get_usermode"></a> IAxWinAmbientDispatch:: get_UserMode

`UserMode`Özelliği, kapsayıcının çevresel Kullanıcı modunu belirtir.

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>Parametreler

*pbUserMode*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchput_allowcontextmenu"></a><a name="put_allowcontextmenu"></a> IAxWinAmbientDispatch::p ut_AllowContextMenu

`AllowContextMenu`Özelliği barındırılan denetimin kendi bağlam menüsünü görüntülemesine izin verilip verilmeyeceğini belirtir.

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>Parametreler

*bAllowContextMenu*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchput_allowshowui"></a><a name="put_allowshowui"></a> IAxWinAmbientDispatch::p ut_AllowShowUI

`AllowShowUI`Özelliği barındırılan denetimin kendi Kullanıcı arabirimini görüntülemesine izin verilip verilmeyeceğini belirtir.

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>Parametreler

*Ballowshowuı*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak VARIANT_FALSE kullanır.

## <a name="iaxwinambientdispatchput_allowwindowlessactivation"></a><a name="put_allowwindowlessactivation"></a> IAxWinAmbientDispatch::p ut_AllowWindowlessActivation

`AllowWindowlessActivation`Özelliği, kapsayıcının penceresiz etkinleştirmeye izin verip vermeyeceğini belirtir.

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>Parametreler

*Ballowpenceresiz*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchput_backcolor"></a><a name="put_backcolor"></a> IAxWinAmbientDispatch::p ut_BackColor

`BackColor`Özelliği, kapsayıcının çevresel arka plan rengini belirtir.

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>Parametreler

*clrBackground*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL konak nesne uygulama, bu özelliğin varsayılan değeri olarak COLOR_BTNFACE veya COLOR_WINDOW kullanır (konak penceresinin üst öğesinin bir iletişim kutusu olup olmadığına bağlı olarak).

## <a name="iaxwinambientdispatchput_displayasdefault"></a><a name="put_displayasdefault"></a> IAxWinAmbientDispatch::p ut_DisplayAsDefault

`DisplayAsDefault` , denetimin varsayılan denetim olup olmadığını bulmasına izin veren bir çevresel özelliktir.

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>Parametreler

*bDisplayAsDefault*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak VARIANT_FALSE kullanır.

## <a name="iaxwinambientdispatchput_dochostdoubleclickflags"></a><a name="put_dochostdoubleclickflags"></a> IAxWinAmbientDispatch::p ut_DocHostDoubleClickFlags

`DocHostDoubleClickFlags`Özelliği, Çift tıklamayla yanıt olarak gerçekleşmesi gereken işlemi belirtir.

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Parametreler

*dwDocHostDoubleClickFlags*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak DOCHOSTUIDBLCLK_DEFAULT kullanır.

## <a name="iaxwinambientdispatchput_dochostflags"></a><a name="put_dochostflags"></a> IAxWinAmbientDispatch::p ut_DocHostFlags

`DocHostFlags`Özelliği, ana bilgisayar nesnesinin kullanıcı arabirimi yeteneklerini belirtir.

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>Parametreler

*dwDocHostFlags*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak DOCHOSTUIFLAG_NO3DBORDER kullanır.

## <a name="iaxwinambientdispatchput_font"></a><a name="put_font"></a> IAxWinAmbientDispatch::p ut_Font

`Font`Özelliği, kapsayıcının çevresel yazı tipini belirtir.

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının varsayılan GUI yazı tipini veya sistem yazı tipini bu özelliğin varsayılan değeri olarak kullanır.

## <a name="iaxwinambientdispatchput_forecolor"></a><a name="put_forecolor"></a> IAxWinAmbientDispatch::p ut_ForeColor

`ForeColor`Özelliği, kapsayıcının çevresel ön plan rengini belirtir.

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>Parametreler

*Clrönalanı*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesnesi uygulama, bu özelliğin varsayılan değeri olarak sistem pencere metin rengini kullanır.

## <a name="iaxwinambientdispatchput_localeid"></a><a name="put_localeid"></a> IAxWinAmbientDispatch::p ut_LocaleID

`LocaleID`Özelliği, kapsayıcının çevresel yerel kimliğini belirtir.

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>Parametreler

*LCID kimliği*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama, kullanıcının varsayılan yerel ayarını bu özelliğin varsayılan değeri olarak kullanır.

## <a name="iaxwinambientdispatchput_messagereflect"></a><a name="put_messagereflect"></a> IAxWinAmbientDispatch::p ut_MessageReflect

`MessageReflect`Ambient özelliği, kapsayıcının iletileri barındırılan denetime yansıtmayacağını belirtir.

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>Parametreler

*Bmessagerefseç*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="iaxwinambientdispatchput_optionkeypath"></a><a name="put_optionkeypath"></a> IAxWinAmbientDispatch::p ut_OptionKeyPath

`OptionKeyPath`Özelliği, Kullanıcı ayarlarının kayıt defteri anahtarı yolunu belirtir.

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>Parametreler

*bstrOptionKeyPath*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="iaxwinambientdispatchput_usermode"></a><a name="put_usermode"></a> IAxWinAmbientDispatch::p ut_UserMode

`UserMode`Özelliği, kapsayıcının çevresel Kullanıcı modunu belirtir.

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>Parametreler

*bUserMode*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının bu özelliğin varsayılan değeri olarak VARIANT_TRUE kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[IAxWinAmbientDispatchEx arabirimi](../../atl/reference/iaxwinambientdispatchex-interface.md)<br/>
[IAxWinHostWindow arabirimi](../../atl/reference/iaxwinhostwindow-interface.md)<br/>
[CAxWindow:: QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
