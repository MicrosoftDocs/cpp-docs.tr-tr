---
title: Iaxwinambientdispatch arabirimi
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
ms.openlocfilehash: 9b9557a76d133d81a07320f1a64482d17c955ef2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301603"
---
# <a name="iaxwinambientdispatch-interface"></a>Iaxwinambientdispatch arabirimi

Bu arabirim, barındırılan denetim veya kapsayıcı özelliklerini belirtmek için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
interface IAxWinAmbientDispatch : IDispatch
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[get_AllowContextMenu](#get_allowcontextmenu)|`AllowContextMenu` Özelliği, bağlam menüsünü görüntülemek için denetimden izin verilip verilmeyeceğini belirtir.|
|[get_AllowShowUI](#get_allowshowui)|`AllowShowUI` Özelliği, kendi kullanıcı arabirimini görüntülemek için denetimden izin verilip verilmeyeceğini belirtir.|
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|`AllowWindowlessActivation` Özelliği, kapsayıcı penceresiz etkinleştirme izin verip vermeyeceğini belirtir.|
|[get_BackColor](#get_backcolor)|`BackColor` Özelliği, kapsayıcının ortam arka plan rengini belirtir.|
|[get_DisplayAsDefault](#get_displayasdefault)|`DisplayAsDefault` Varsayılan Denetim olup olmadığını öğrenmek için bir denetim sağlayan bir ortam özelliğidir.|
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|`DocHostDoubleClickFlags` Özelliği, yanıt bir çift olarak gerçekleşmesi gereken işlemi belirler.|
|[get_DocHostFlags](#get_dochostflags)|`DocHostFlags` Özellik konak nesnesi kullanıcı arabirimi özelliklerini belirtir.|
|[get_Font](#get_font)|`Font` Özelliği, kapsayıcının ortam yazı tipini belirtir.|
|[get_ForeColor](#get_forecolor)|`ForeColor` Özelliği, kapsayıcının ortam ön plan rengini belirtir.|
|[get_LocaleID](#get_localeid)|`LocaleID` Özelliği, kapsayıcının ortam yerel ayar Kimliğini belirtir.|
|[get_MessageReflect](#get_messagereflect)|`MessageReflect` Ortam özelliği, kapsayıcıda barındırılan denetim iletileri yansıtmadığını belirtir.|
|[get_OptionKeyPath](#get_optionkeypath)|`OptionKeyPath` Özelliği, kullanıcı ayarları için kayıt defteri anahtarının yolunu belirtir.|
|[get_ShowGrabHandles](#get_showgrabhandles)|`ShowGrabHandles` Ortam özelliği, kendisini tutamaçların ile çizip varsa öğrenmek denetim sağlar.|
|[get_ShowHatching](#get_showhatching)|`ShowHatching` Ortam özelliği, kendisini çizgili çizip varsa öğrenmek denetim sağlar.|
|[get_UserMode](#get_usermode)|`UserMode` Özelliği, kapsayıcının ortam kullanıcı modunu belirtir.|
|[put_AllowContextMenu](#put_allowcontextmenu)|`AllowContextMenu` Özelliği, bağlam menüsünü görüntülemek için denetimden izin verilip verilmeyeceğini belirtir.|
|[put_AllowShowUI](#put_allowshowui)|`AllowShowUI` Özelliği, kendi kullanıcı arabirimini görüntülemek için denetimden izin verilip verilmeyeceğini belirtir.|
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|`AllowWindowlessActivation` Özelliği, kapsayıcı penceresiz etkinleştirme izin verip vermeyeceğini belirtir.|
|[put_BackColor](#put_backcolor)|`BackColor` Özelliği, kapsayıcının ortam arka plan rengini belirtir.|
|[put_DisplayAsDefault](#put_displayasdefault)|`DisplayAsDefault` Varsayılan Denetim olup olmadığını öğrenmek için bir denetim sağlayan bir ortam özelliğidir.|
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|`DocHostDoubleClickFlags` Özelliği, yanıt bir çift olarak gerçekleşmesi gereken işlemi belirler.|
|[put_DocHostFlags](#put_dochostflags)|`DocHostFlags` Özellik konak nesnesi kullanıcı arabirimi özelliklerini belirtir.|
|[put_Font](#put_font)|`Font` Özelliği, kapsayıcının ortam yazı tipini belirtir.|
|[put_ForeColor](#put_forecolor)|`ForeColor` Özelliği, kapsayıcının ortam ön plan rengini belirtir.|
|[put_LocaleID](#put_localeid)|`LocaleID` Özelliği, kapsayıcının ortam yerel ayar Kimliğini belirtir.|
|[put_MessageReflect](#put_messagereflect)|`MessageReflect` Ortam özelliği, kapsayıcıda barındırılan denetim iletileri yansıtmadığını belirtir.|
|[put_OptionKeyPath](#put_optionkeypath)|`OptionKeyPath` Özelliği, kullanıcı ayarları için kayıt defteri anahtarının yolunu belirtir.|
|[put_UserMode](#put_usermode)|`UserMode` Özelliği, kapsayıcının ortam kullanıcı modunu belirtir.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, nesneler barındırma ATL'nin ActiveX denetimi tarafından kullanıma sunulur. Barındırılan denetim için kullanılabilir ortam özelliklerini ayarlamak için veya diğer yönleri kapsayıcının davranışını belirtmek için bu arabirimdeki yöntemleri çağırın. Tarafından sağlanan özellikleri desteklemek üzere `IAxWinAmbientDispatch`, kullanın [Iaxwinambientdispatchex](../../atl/reference/iaxwinambientdispatchex-interface.md).

[AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) hakkında tür bilgisi yüklenmeye çalışılacak `IAxWinAmbientDispatch` ve `IAxWinAmbientDispatchEx` typelib'den kodunu içerir.

ATL90.dll için bağlıyorsanız **AXHost** dll typelib'den tür bilgilerini yükler.

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) daha fazla ayrıntı için.

## <a name="requirements"></a>Gereksinimler

Bu arabirim tanımı aşağıdaki tabloda gösterildiği gibi formlar, bir süre içinde kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|IDL|atliface.idl|
|Tür kitaplığı|ATL.dll|
|C++|atliface.h (ATLBase.h içinde de dahil)|

##  <a name="get_allowcontextmenu"></a>  IAxWinAmbientDispatch::get_AllowContextMenu

`AllowContextMenu` Özelliği, bağlam menüsünü görüntülemek için denetimden izin verilip verilmeyeceğini belirtir.

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>Parametreler

*pbAllowContextMenu*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama VARIANT_TRUE bu özelliğin varsayılan değeri kullanır.

##  <a name="get_allowshowui"></a>  IAxWinAmbientDispatch::get_AllowShowUI

`AllowShowUI` Özelliği, kendi kullanıcı arabirimini görüntülemek için denetimden izin verilip verilmeyeceğini belirtir.

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>Parametreler

*pbAllowShowUI*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama özelliği, bu özelliğin varsayılan değeri kullanır.

##  <a name="get_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::get_AllowWindowlessActivation

`AllowWindowlessActivation` Özelliği, kapsayıcı penceresiz etkinleştirme izin verip vermeyeceğini belirtir.

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>Parametreler

*pbAllowWindowless*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama VARIANT_TRUE bu özelliğin varsayılan değeri kullanır.

##  <a name="get_backcolor"></a>  IAxWinAmbientDispatch::get_BackColor

`BackColor` Özelliği, kapsayıcının ortam arka plan rengini belirtir.

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>Parametreler

*pclrBackground*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama COLOR_BTNFACE veya COLOR_WINDOW (ana penceresinin üst bir iletişim kutusu veya olup olmamasına bağlı olarak), bu özelliğin varsayılan değeri kullanır.

##  <a name="get_displayasdefault"></a>  IAxWinAmbientDispatch::get_DisplayAsDefault

`DisplayAsDefault` Varsayılan Denetim olup olmadığını öğrenmek için bir denetim sağlayan bir ortam özelliğidir.

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>Parametreler

*pbDisplayAsDefault*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama özelliği, bu özelliğin varsayılan değeri kullanır.

##  <a name="get_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::get_DocHostDoubleClickFlags

`DocHostDoubleClickFlags` Özelliği, yanıt bir çift olarak gerçekleşmesi gereken işlemi belirler.

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Parametreler

*pdwDocHostDoubleClickFlags*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama DOCHOSTUIDBLCLK_DEFAULT bu özelliğin varsayılan değeri kullanır.

##  <a name="get_dochostflags"></a>  IAxWinAmbientDispatch::get_DocHostFlags

`DocHostFlags` Özellik konak nesnesi kullanıcı arabirimi özelliklerini belirtir.

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>Parametreler

*pdwDocHostFlags*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama DOCHOSTUIFLAG_NO3DBORDER bu özelliğin varsayılan değeri kullanır.

##  <a name="get_font"></a>  IAxWinAmbientDispatch::get_Font

`Font` Özelliği, kapsayıcının ortam yazı tipini belirtir.

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
[out] Adresini bir `IFontDisp` bu özelliğin geçerli değerini almak için kullanılan arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesne uygulamasını varsayılan GUI yazı tipi veya sistem yazı tipi, bu özelliğin varsayılan değeri kullanır.

##  <a name="get_forecolor"></a>  IAxWinAmbientDispatch::get_ForeColor

`ForeColor` Özelliği, kapsayıcının ortam ön plan rengini belirtir.

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>Parametreler

*pclrForeground*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama, bu özelliğin varsayılan değeri sistem penceresi metin rengi kullanır.

##  <a name="get_localeid"></a>  IAxWinAmbientDispatch::get_LocaleID

`LocaleID` Özelliği, kapsayıcının ortam yerel ayar Kimliğini belirtir.

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>Parametreler

*plcidLocaleID*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama kullanıcının varsayılan yerel ayar, bu özelliğin varsayılan değeri kullanır.

Bu yöntemle ortam localId bulabilir, diğer bir deyişle, programın LocaleID denetiminizin içinde kullanılıyor. LocaleID öğrendikten sonra yerel ayara özgü açıklamalı alt yazılar yükleyecek kodu hata iletisi metni, vb. bir kaynak dosyası veya uydu DLL çağırabilirsiniz.

##  <a name="get_messagereflect"></a>  IAxWinAmbientDispatch::get_MessageReflect

`MessageReflect` Ortam özelliği, kapsayıcıda barındırılan denetim iletileri yansıtmadığını belirtir.

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>Parametreler

*pbMessageReflect*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama VARIANT_TRUE bu özelliğin varsayılan değeri kullanır.

##  <a name="get_optionkeypath"></a>  IAxWinAmbientDispatch::get_OptionKeyPath

`OptionKeyPath` Özelliği, kullanıcı ayarları için kayıt defteri anahtarının yolunu belirtir.

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>Parametreler

*pbstrOptionKeyPath*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="get_showgrabhandles"></a>  IAxWinAmbientDispatch::get_ShowGrabHandles

`ShowGrabHandles` Ortam özelliği, kendisini tutamaçların ile çizip varsa öğrenmek denetim sağlar.

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>Parametreler

*pbShowGrabHandles*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama her zaman VARIANT_FALSE bu özelliğin değeri döndürür.

##  <a name="get_showhatching"></a>  IAxWinAmbientDispatch::get_ShowHatching

`ShowHatching` Ortam özelliği, kendisini çizgili çizip varsa öğrenmek denetim sağlar.

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>Parametreler

*pbShowHatching*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama her zaman VARIANT_FALSE bu özelliğin değeri döndürür.

##  <a name="get_usermode"></a>  IAxWinAmbientDispatch::get_UserMode

`UserMode` Özelliği, kapsayıcının ortam kullanıcı modunu belirtir.

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>Parametreler

*pbUserMode*<br/>
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama VARIANT_TRUE bu özelliğin varsayılan değeri kullanır.

##  <a name="put_allowcontextmenu"></a>  IAxWinAmbientDispatch::put_AllowContextMenu

`AllowContextMenu` Özelliği, bağlam menüsünü görüntülemek için denetimden izin verilip verilmeyeceğini belirtir.

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>Parametreler

*bAllowContextMenu*<br/>
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama VARIANT_TRUE bu özelliğin varsayılan değeri kullanır.

##  <a name="put_allowshowui"></a>  IAxWinAmbientDispatch::put_AllowShowUI

`AllowShowUI` Özelliği, kendi kullanıcı arabirimini görüntülemek için denetimden izin verilip verilmeyeceğini belirtir.

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>Parametreler

*bAllowShowUI*<br/>
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama özelliği, bu özelliğin varsayılan değeri kullanır.

##  <a name="put_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::put_AllowWindowlessActivation

`AllowWindowlessActivation` Özelliği, kapsayıcı penceresiz etkinleştirme izin verip vermeyeceğini belirtir.

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>Parametreler

*bAllowWindowless*<br/>
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama VARIANT_TRUE bu özelliğin varsayılan değeri kullanır.

##  <a name="put_backcolor"></a>  IAxWinAmbientDispatch::put_BackColor

`BackColor` Özelliği, kapsayıcının ortam arka plan rengini belirtir.

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>Parametreler

*clrBackground*<br/>
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama COLOR_BTNFACE veya COLOR_WINDOW (ana penceresinin üst bir iletişim kutusu veya olup olmamasına bağlı olarak), bu özelliğin varsayılan değeri kullanır.

##  <a name="put_displayasdefault"></a>  IAxWinAmbientDispatch::put_DisplayAsDefault

`DisplayAsDefault` Varsayılan Denetim olup olmadığını öğrenmek için bir denetim sağlayan bir ortam özelliğidir.

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>Parametreler

*bDisplayAsDefault*<br/>
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama özelliği, bu özelliğin varsayılan değeri kullanır.

##  <a name="put_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::put_DocHostDoubleClickFlags

`DocHostDoubleClickFlags` Özelliği, yanıt bir çift olarak gerçekleşmesi gereken işlemi belirler.

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Parametreler

*dwDocHostDoubleClickFlags*<br/>
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama DOCHOSTUIDBLCLK_DEFAULT bu özelliğin varsayılan değeri kullanır.

##  <a name="put_dochostflags"></a>  IAxWinAmbientDispatch::put_DocHostFlags

`DocHostFlags` Özellik konak nesnesi kullanıcı arabirimi özelliklerini belirtir.

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>Parametreler

*dwDocHostFlags*<br/>
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama DOCHOSTUIFLAG_NO3DBORDER bu özelliğin varsayılan değeri kullanır.

##  <a name="put_font"></a>  IAxWinAmbientDispatch::put_Font

`Font` Özelliği, kapsayıcının ortam yazı tipini belirtir.

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesne uygulamasını varsayılan GUI yazı tipi veya sistem yazı tipi, bu özelliğin varsayılan değeri kullanır.

##  <a name="put_forecolor"></a>  IAxWinAmbientDispatch::put_ForeColor

`ForeColor` Özelliği, kapsayıcının ortam ön plan rengini belirtir.

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>Parametreler

*clrForeground*<br/>
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama, bu özelliğin varsayılan değeri sistem penceresi metin rengi kullanır.

##  <a name="put_localeid"></a>  IAxWinAmbientDispatch::put_LocaleID

`LocaleID` Özelliği, kapsayıcının ortam yerel ayar Kimliğini belirtir.

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>Parametreler

*lcidLocaleID*<br/>
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama kullanıcının varsayılan yerel ayar, bu özelliğin varsayılan değeri kullanır.

##  <a name="put_messagereflect"></a>  IAxWinAmbientDispatch::put_MessageReflect

`MessageReflect` Ortam özelliği, kapsayıcıda barındırılan denetim iletileri yansıtmadığını belirtir.

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>Parametreler

*bMessageReflect*<br/>
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama VARIANT_TRUE bu özelliğin varsayılan değeri kullanır.

##  <a name="put_optionkeypath"></a>  IAxWinAmbientDispatch::put_OptionKeyPath

`OptionKeyPath` Özelliği, kullanıcı ayarları için kayıt defteri anahtarının yolunu belirtir.

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>Parametreler

*bstrOptionKeyPath*<br/>
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="put_usermode"></a>  IAxWinAmbientDispatch::put_UserMode

`UserMode` Özelliği, kapsayıcının ortam kullanıcı modunu belirtir.

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>Parametreler

*bUserMode*<br/>
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama VARIANT_TRUE bu özelliğin varsayılan değeri kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[IAxWinAmbientDispatchEx Arabirimi](../../atl/reference/iaxwinambientdispatchex-interface.md)<br/>
[IAxWinHostWindow Arabirimi](../../atl/reference/iaxwinhostwindow-interface.md)<br/>
[CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
