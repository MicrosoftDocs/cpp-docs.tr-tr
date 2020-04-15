---
title: CStockPropImpl Sınıfı
ms.date: 05/06/2019
f1_keywords:
- CStockPropImpl
- ATLCTL/ATL::CStockPropImpl
- ATLCTL/ATL::get_Appearance
- ATLCTL/ATL::get_AutoSize
- ATLCTL/ATL::get_BackColor
- ATLCTL/ATL::get_BackStyle
- ATLCTL/ATL::get_BorderColor
- ATLCTL/ATL::get_BorderStyle
- ATLCTL/ATL::get_BorderVisible
- ATLCTL/ATL::get_BorderWidth
- ATLCTL/ATL::get_Caption
- ATLCTL/ATL::get_DrawMode
- ATLCTL/ATL::get_DrawStyle
- ATLCTL/ATL::get_DrawWidth
- ATLCTL/ATL::get_Enabled
- ATLCTL/ATL::get_FillColor
- ATLCTL/ATL::get_FillStyle
- ATLCTL/ATL::get_Font
- ATLCTL/ATL::get_ForeColor
- ATLCTL/ATL::get_HWND
- ATLCTL/ATL::get_MouseIcon
- ATLCTL/ATL::get_MousePointer
- ATLCTL/ATL::get_Picture
- ATLCTL/ATL::get_ReadyState
- ATLCTL/ATL::get_TabStop
- ATLCTL/ATL::get_Text
- ATLCTL/ATL::getvalid
- ATLCTL/ATL::get_Window
- ATLCTL/ATL::put_Appearance
- ATLCTL/ATL::put_AutoSize
- ATLCTL/ATL::put_BackColor
- ATLCTL/ATL::put_BackStyle
- ATLCTL/ATL::put_BorderColor
- ATLCTL/ATL::put_BorderStyle
- ATLCTL/ATL::put_BorderVisible
- ATLCTL/ATL::put_BorderWidth
- ATLCTL/ATL::put_Caption
- ATLCTL/ATL::put_DrawMode
- ATLCTL/ATL::put_DrawStyle
- ATLCTL/ATL::put_DrawWidth
- ATLCTL/ATL::put_Enabled
- ATLCTL/ATL::put_FillColor
- ATLCTL/ATL::put_FillStyle
- ATLCTL/ATL::put_Font
- ATLCTL/ATL::put_ForeColor
- ATLCTL/ATL::put_HWND
- ATLCTL/ATL::put_MouseIcon
- ATLCTL/ATL::put_MousePointer
- ATLCTL/ATL::put_Picture
- ATLCTL/ATL::put_ReadyState
- ATLCTL/ATL::put_TabStop
- ATLCTL/ATL::put_Text
- ATLCTL/ATL::putvalid
- ATLCTL/ATL::put_Window
- ATLCTL/ATL::putref_Font
- ATLCTL/ATL::putref_MouseIcon
- ATLCTL/ATL::putref_Picture
helpviewer_keywords:
- CStockPropImpl class
- controls [ATL], stock properties
- stock properties, ATL controls
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
ms.openlocfilehash: 0aaeb1b6de0febfd5fc0d41cbcc7bad41c607af4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330667"
---
# <a name="cstockpropimpl-class"></a>CStockPropImpl Sınıfı

Bu sınıf, stok özellik değerlerini desteklemek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <
    class T,
    class InterfaceName,
    const IID* piid = &_ATL_IIDOF(InterfaceName),
    const GUID* plibid = &CComModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0,
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE CStockPropImpl :
    public IDispatchImpl<InterfaceName, piid, plibid, wMajor, wMinor, tihclass>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Denetimi uygulayan ve 'den `CStockPropImpl`kaynaklanan sınıf.

*Arabirimadı*<br/>
Stok özelliklerini ortaya çıkaran çift arabirim.

*piid*<br/>
IID için bir `InterfaceName`işaretçi .

*plibid*<br/>
'nin tanımını içeren tür kitaplığı LIBID için `InterfaceName`bir işaretçi

*wMajor*<br/>
Tür kitaplığın ana sürümü. Varsayılan değer 1’dir.

*wMinor*<br/>
Tür kitaplığın küçük sürümü. Varsayılan değer 0’dır.

*tihclass*<br/>
*T.* için tür bilgilerini yönetmek için kullanılan sınıf. Varsayılan `CComTypeInfoHolder`değer.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|[get_Appearance](#get_appearance)|Denetim tarafından kullanılan boya stilini almak için bu yöntemi arayın, örneğin, düz veya 3D.|
|[get_AutoSize](#get_autosize)|Denetimbaşka bir boyut olup olmadığını belirten bayrağın durumunu almak için bu yöntemi arayın.|
|[get_BackColor](#get_backcolor)|Denetimin arka plan rengini almak için bu yöntemi arayın.|
|[get_BackStyle](#get_backstyle)|Denetimin arka plan stilini almak için saydam veya opak bu yöntemi arayın.|
|[get_BorderColor](#get_bordercolor)|Denetimin kenarlık rengini almak için bu yöntemi arayın.|
|[get_BorderStyle](#get_borderstyle)|Denetimin kenarlık stilini almak için bu yöntemi arayın.|
|[get_BorderVisible](#get_bordervisible)|Denetimin kenarlığı görünür olup olmadığını gösteren bayrağın durumunu almak için bu yöntemi arayın.|
|[get_BorderWidth](#get_borderwidth)|Denetimin kenarlığı genişliğini (piksel olarak) almak için bu yöntemi arayın.|
|[get_Caption](#get_caption)|Nesnenin başlığında belirtilen metni almak için bu yöntemi arayın.|
|[get_DrawMode](#get_drawmode)|Denetimin çizim moduna almak için bu yöntemi arayın, örneğin, XOR Kalem veya Renkleri Tersine Çevir.|
|[get_DrawStyle](#get_drawstyle)|Denetimin çizim stilini almak için bu yöntemi çağırın, örneğin katı, kesikli veya noktalı.|
|[get_DrawWidth](#get_drawwidth)|Denetimin çizim yöntemleri tarafından kullanılan çizim genişliğini (piksel olarak) almak için bu yöntemi arayın.|
|[get_Enabled](#get_enabled)|Denetimin etkin olup olmadığını belirten bayrağın durumunu almak için bu yöntemi arayın.|
|[get_FillColor](#get_fillcolor)|Denetimin dolgu rengini almak için bu yöntemi arayın.|
|[get_FillStyle](#get_fillstyle)|Örneğin, katı, saydam veya çapraz kapaklı olarak denetimin dolgu stilini almak için bu yöntemi arayın.|
|[get_Font](#get_font)|Denetimin yazı tipi özelliklerine işaretçi almak için bu yöntemi arayın.|
|[get_ForeColor](#get_forecolor)|Denetimin ön plan rengini almak için bu yöntemi arayın.|
|[get_HWND](#get_hwnd)|Denetimle ilişkili pencere tutamacını almak için bu yöntemi arayın.|
|[get_MouseIcon](#get_mouseicon)|Fare denetim üzerindeyken grafiğin (simge, biteşveya metadosya) resim özelliklerini niçin görüntülenmesini sağlamak için bu yöntemi arayın.|
|[get_MousePointer](#get_mousepointer)|Fare denetim üzerindeyken görüntülenmeyi sağlamak için bu yöntemi çağırın, örneğin ok, çapraz veya kum saati.|
|[get_Picture](#get_picture)|Görüntülenecek bir grafiğin (simge, biteşveya metadosya) resim özelliklerine işaretçi almak için bu yöntemi arayın.|
|[get_ReadyState](#get_readystate)|Denetimin hazır durumunu almak için bu yöntemi çağırın, örneğin, yükleme veya yükleme.|
|[get_TabStop](#get_tabstop)|Denetimin sekme durağı olup olmadığını belirten bayrağı almak için bu yöntemi arayın.|
|[get_Text](#get_text)|Denetimle görüntülenen metni almak için bu yöntemi arayın.|
|[getvalid](#get_valid)|Denetimin geçerli olup olmadığını belirten bayrağın durumunu almak için bu yöntemi arayın.|
|[get_Window](#get_window)|Denetimle ilişkili pencere tutamacını almak için bu yöntemi arayın. [CStockPropImpl ile aynı::get_HWND](#get_hwnd).|
|[put_Appearance](#put_appearance)|Denetim tarafından kullanılan boya stilini ayarlamak için bu yöntemi çağırın, örneğin, düz veya 3D.|
|[put_AutoSize](#put_autosize)|Denetimbaşka bir boyut olup olmadığını gösteren bayrağın değerini ayarlamak için bu yöntemi çağırın.|
|[put_BackColor](#put_backcolor)|Denetimin arka plan rengini ayarlamak için bu yöntemi arayın.|
|[put_BackStyle](#put_backstyle)|Denetimin arka plan stilini ayarlamak için bu yöntemi arayın.|
|[put_BorderColor](#put_bordercolor)|Denetimin kenarlık rengini ayarlamak için bu yöntemi arayın.|
|[put_BorderStyle](#put_borderstyle)|Denetimin kenarlık stilini ayarlamak için bu yöntemi arayın.|
|[put_BorderVisible](#put_bordervisible)|Denetimin kenarlığı görünür olup olmadığını gösteren bayrağın değerini ayarlamak için bu yöntemi çağırın.|
|[put_BorderWidth](#put_borderwidth)|Denetimin kenarlığı genişliğini ayarlamak için bu yöntemi arayın.|
|[put_Caption](#put_caption)|Denetimi ile görüntülenecek metni ayarlamak için bu yöntemi arayın.|
|[put_DrawMode](#put_drawmode)|Denetimin çizim modunu ayarlamak için bu yöntemi çağırın, örneğin XOR Kalem veya Renkleri Tersine Çevir.|
|[put_DrawStyle](#put_drawstyle)|Denetimin çizim stilini ayarlamak için bu yöntemi çağırın, örneğin katı, kesikli veya noktalı.|
|[put_DrawWidth](#put_drawwidth)|Denetimin çizim yöntemleri tarafından kullanılan genişliği (piksel olarak) ayarlamak için bu yöntemi arayın.|
|[put_Enabled](#put_enabled)|Denetimin etkin olup olmadığını belirten bayrağı ayarlamak için bu yöntemi çağırın.|
|[put_FillColor](#put_fillcolor)|Denetimin dolgu rengini ayarlamak için bu yöntemi arayın.|
|[put_FillStyle](#put_fillstyle)|Denetimin dolgu stilini ayarlamak için bu yöntemi çağırın, örneğin katı, saydam veya çapraz kapaklı.|
|[put_Font](#put_font)|Denetimin yazı tipi özelliklerini ayarlamak için bu yöntemi çağırın.|
|[put_ForeColor](#put_forecolor)|Denetimin ön plan rengini ayarlamak için bu yöntemi arayın.|
|[put_HWND](#put_hwnd)|Bu yöntem E_FAIL döndürür.|
|[put_MouseIcon](#put_mouseicon)|Fare denetim üzerindeyken grafiğin (simge, biteşveya metadosya) resim özelliklerini görüntülenecek şekilde ayarlamak için bu yöntemi arayın.|
|[put_MousePointer](#put_mousepointer)|Fare denetim üzerindeyken görüntülenen fare işaretçisi türünü ayarlamak için bu yöntemi çağırın, örneğin ok, çapraz veya kum saati.|
|[put_Picture](#put_picture)|Görüntülenecek bir grafiğin (simge, biteşveya metadosya) resim özelliklerini ayarlamak için bu yöntemi çağırın.|
|[put_ReadyState](#put_readystate)|Denetimin hazır durumunu ayarlamak için bu yöntemi çağırın, örneğin, yükleme veya yükleme.|
|[put_TabStop](#put_tabstop)|Denetimin sekme durağı olup olmadığını belirten bayrağın değerini ayarlamak için bu yöntemi çağırın.|
|[put_Text](#put_text)|Denetimle birlikte görüntülenen metni ayarlamak için bu yöntemi çağırın.|
|[putvalid](#put_valid)|Denetimin geçerli olup olmadığını belirten bayrağı ayarlamak için bu yöntemi çağırın.|
|[put_Window](#put_window)|Bu yöntem [CStockPropImpl::put_HWND](#put_hwnd)çağırır, E_FAIL döndürür.|
|[putref_Font](#putref_font)|Denetimin yazı tipi özelliklerini başvuru sayısıyla ayarlamak için bu yöntemi çağırın.|
|[putref_MouseIcon](#putref_mouseicon)|Fare denetim üzerindeyken, bir başvuru sayısıyla görüntülenecek grafiğin (simge, biteşveya metadosya) resim özelliklerini ayarlamak için bu yöntemi çağırın.|
|[putref_Picture](#putref_picture)|Bir grafiğin (simge, bitmap veya metadosya) resim özelliklerini referans sayısıyla birlikte görüntülenecek şekilde ayarlamak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CStockPropImpl`her stok özelliği için **koymak** ve **almak** yöntemleri sağlar. Bu yöntemler, her özellik ile ilişkili veri üyesini ayarlamak veya almak ve herhangi bir özellik değiştiğinde kapsayıcıyı bildirmek ve eşitlemek için gerekli kodu sağlar.

Visual Studio, sihirbazları aracılığıyla stok özellikleri için destek sağlar. Denetime stok özellikleri ekleme hakkında daha fazla bilgi için [ATL Tutorial'a](../../atl/active-template-library-atl-tutorial.md)bakın.

Geriye dönük uyumluluk `CStockPropImpl` için, `get_Window` `put_Window` aynı zamanda `get_HWND` ortaya `put_HWND`çıkarır ve sadece arama yöntemleri ve , sırasıyla. HWND salt `put_HWND` okunur bir özellik olmalıdır beri E_FAIL döner varsayılan uygulama.

Aşağıdaki özellikleri de bir **putref** uygulaması var:

- Yazı tipi

- MouseIcon

- Resim

Aynı üç stok özelliği, ilgili veri üyesinin atama işleci aracılığı ile doğru arabirim referans sayımı sağlayan tür `CComPtr` veya başka bir sınıfta olmasını gerektirir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

[ıdispatchımpl](../../atl/reference/idispatchimpl-class.md)

`CStockPropImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="cstockpropimplget_appearance"></a><a name="get_appearance"></a>CStockPropImpl::get_Appearance

Denetim tarafından kullanılan boya stilini almak için bu yöntemi arayın, örneğin, düz veya 3D.

```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```

### <a name="parameters"></a>Parametreler

*pnAppearance*<br/>
Denetimin boya stilini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_autosize"></a><a name="get_autosize"></a>CStockPropImpl::get_AutoSize

Denetimbaşka bir boyut olup olmadığını belirten bayrağın durumunu almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```

### <a name="parameters"></a>Parametreler

*pbOtomatik Boyut*<br/>
Bayrak durumunu alan değişken. TRUE, denetimin başka bir boyut olamayacağını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_backcolor"></a><a name="get_backcolor"></a>CStockPropImpl::get_BackColor

Denetimin arka plan rengini almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```

### <a name="parameters"></a>Parametreler

*pclrBackColor*<br/>
Denetimin arka plan rengini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_backstyle"></a><a name="get_backstyle"></a>CStockPropImpl::get_BackStyle

Denetimin arka plan stilini almak için saydam veya opak bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```

### <a name="parameters"></a>Parametreler

*pnBackStyle*<br/>
Denetimin arka plan stilini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_bordercolor"></a><a name="get_bordercolor"></a>CStockPropImpl::get_BorderColor

Denetimin kenarlık rengini almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```

### <a name="parameters"></a>Parametreler

*pclrBorderColor*<br/>
Denetimin kenarlık rengini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_borderstyle"></a><a name="get_borderstyle"></a>CStockPropImpl::get_BorderStyle

Denetimin kenarlık stilini almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```

### <a name="parameters"></a>Parametreler

*pnBorderStyle*<br/>
Denetimin kenarlık stilini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_bordervisible"></a><a name="get_bordervisible"></a>CStockPropImpl::get_BorderVisible

Denetimin kenarlığı görünür olup olmadığını gösteren bayrağın durumunu almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```

### <a name="parameters"></a>Parametreler

*pbBorderVisible*<br/>
Bayrak durumunu alan değişken. TRUE, denetimin kenarlığı görünür olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_borderwidth"></a><a name="get_borderwidth"></a>CStockPropImpl::get_BorderWidth

Denetimin kenarlığı genişliğini elde etmek için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```

### <a name="parameters"></a>Parametreler

*pnBorderWidth*<br/>
Denetimin kenarlık genişliğini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_caption"></a><a name="get_caption"></a>CStockPropImpl::get_Caption

Nesnenin başlığında belirtilen metni almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```

### <a name="parameters"></a>Parametreler

*pbstrCaption*<br/>
Denetimle birlikte görüntülenecek metin.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_drawmode"></a><a name="get_drawmode"></a>CStockPropImpl::get_DrawMode

Denetimin çizim moduna almak için bu yöntemi arayın, örneğin, XOR Kalem veya Renkleri Tersine Çevir.

```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```

### <a name="parameters"></a>Parametreler

*pnDrawMode*<br/>
Denetimin çizim modunu alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_drawstyle"></a><a name="get_drawstyle"></a>CStockPropImpl::get_DrawStyle

Denetimin çizim stilini almak için bu yöntemi çağırın, örneğin katı, kesikli veya noktalı.

```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```

### <a name="parameters"></a>Parametreler

*pnDrawStyle*<br/>
Denetimin çizim stilini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_drawwidth"></a><a name="get_drawwidth"></a>CStockPropImpl::get_DrawWidth

Denetimin çizim yöntemleri tarafından kullanılan çizim genişliğini (piksel olarak) almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```

### <a name="parameters"></a>Parametreler

*pnDrawWidth*<br/>
Denetimin genişlik değerini piksel olarak alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_enabled"></a><a name="get_enabled"></a>CStockPropImpl::get_Enabled

Denetimin etkin olup olmadığını belirten bayrağın durumunu almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```

### <a name="parameters"></a>Parametreler

*pbEtkin*<br/>
Bayrak durumunu alan değişken. TRUE, denetimin etkin olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_fillcolor"></a><a name="get_fillcolor"></a>CStockPropImpl::get_FillColor

Denetimin dolgu rengini almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```

### <a name="parameters"></a>Parametreler

*pclrFillColor*<br/>
Denetimin dolgu rengini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_fillstyle"></a><a name="get_fillstyle"></a>CStockPropImpl::get_FillStyle

Denetimin dolgu stilini almak için bu yöntemi çağırın, örneğin katı, saydam veya çapraz hatched.

```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```

### <a name="parameters"></a>Parametreler

*pnFillStyle*<br/>
Denetimin dolgu stilini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_font"></a><a name="get_font"></a>CStockPropImpl::get_Font

Denetimin yazı tipi özelliklerine işaretçi almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```

### <a name="parameters"></a>Parametreler

*ppFont*<br/>
Denetimin yazı tipi özelliklerine işaretçi alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_forecolor"></a><a name="get_forecolor"></a>CStockPropImpl::get_ForeColor

Denetimin ön plan rengini almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```

### <a name="parameters"></a>Parametreler

*pclrForeColor*<br/>
Denetimleri ön plan rengini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_hwnd"></a><a name="get_hwnd"></a>CStockPropImpl::get_HWND

Denetimle ilişkili pencere tutamacını almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Parametreler

*phWnd*<br/>
Denetimle ilişkili pencere tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_mouseicon"></a><a name="get_mouseicon"></a>CStockPropImpl::get_MouseIcon

Fare denetim üzerindeyken grafiğin (simge, biteşveya metadosya) resim özelliklerini niçin görüntülenmesini sağlamak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Parametreler

*ppResim*<br/>
Grafiğin resim özelliklerine işaretçi alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_mousepointer"></a><a name="get_mousepointer"></a>CStockPropImpl::get_MousePointer

Fare denetim üzerindeyken görüntülenmeyi sağlamak için bu yöntemi çağırın, örneğin ok, çapraz veya kum saati.

```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```

### <a name="parameters"></a>Parametreler

*pnMousePointer*<br/>
Fare işaretçisi türünü alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_picture"></a><a name="get_picture"></a>CStockPropImpl::get_Picture

Görüntülenecek bir grafiğin (simge, biteşveya metadosya) resim özelliklerine işaretçi almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Parametreler

*ppResim*<br/>
Resmin özelliklerine işaretçi alan değişken. Daha fazla bilgi için [IPictureDisp'e](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_readystate"></a><a name="get_readystate"></a>CStockPropImpl::get_ReadyState

Denetimin hazır durumunu almak için bu yöntemi çağırın, örneğin, yükleme veya yükleme.

```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```

### <a name="parameters"></a>Parametreler

*pnReadyState*<br/>
Denetimin hazır durumunu alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_tabstop"></a><a name="get_tabstop"></a>CStockPropImpl::get_TabStop

Denetimin sekme durağı olup olmadığını belirten bayrağın durumunu almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```

### <a name="parameters"></a>Parametreler

*pbTabStop*<br/>
Bayrak durumunu alan değişken. TRUE, denetimin bir sekme durağı olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_text"></a><a name="get_text"></a>CStockPropImpl::get_Text

Denetimle görüntülenen metni almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```

### <a name="parameters"></a>Parametreler

*pbstrText*<br/>
Denetimle birlikte görüntülenen metin.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplgetvalid"></a><a name="get_valid"></a>CStockPropImpl::getvalid

Denetimin geçerli olup olmadığını belirten bayrağın durumunu almak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```

### <a name="parameters"></a>Parametreler

*pbGeçerli*<br/>
Bayrak durumunu alan değişken. TRUE denetimin geçerli olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplget_window"></a><a name="get_window"></a>CStockPropImpl::get_Window

Denetimle ilişkili pencere tutamacını almak için bu yöntemi arayın. [CStockPropImpl ile aynı::get_HWND](#get_hwnd).

```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Parametreler

*phWnd*<br/>
Denetimle ilişkili pencere tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_appearance"></a><a name="put_appearance"></a>CStockPropImpl::put_Görünüm

Denetim tarafından kullanılan boya stilini ayarlamak için bu yöntemi çağırın, örneğin, düz veya 3D.

```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```

### <a name="parameters"></a>Parametreler

*nGörünüm*<br/>
Yeni boya stili kontrol tarafından kullanılacak.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_autosize"></a><a name="put_autosize"></a>CStockPropImpl::put_AutoSize

Denetimbaşka bir boyut olup olmadığını gösteren bayrak değerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```

### <a name="parameters"></a>Parametreler

*bOtomatik Boyut*<br/>
Denetim başka bir boyut olamazsa DOĞRU.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_backcolor"></a><a name="put_backcolor"></a>CStockPropImpl::put_BackColor

Denetimin arka plan rengini ayarlamak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```

### <a name="parameters"></a>Parametreler

*clrBackColor*<br/>
Yeni denetim arka plan rengi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_backstyle"></a><a name="put_backstyle"></a>CStockPropImpl::put_BackStyle

Denetimin arka plan stilini ayarlamak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```

### <a name="parameters"></a>Parametreler

*nBackStyle*<br/>
Yeni denetim arka plan stili.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_bordercolor"></a><a name="put_bordercolor"></a>CStockPropImpl::put_BorderColor

Denetimin kenarlık rengini ayarlamak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```

### <a name="parameters"></a>Parametreler

*clrBorderColor*<br/>
Yeni kenarlık rengi. OLE_COLOR veri türü dahili olarak 32 bit uzunluğunda bir tamsayı olarak temsil edilir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_borderstyle"></a><a name="put_borderstyle"></a>CStockPropImpl::put_BorderStyle

Denetimin kenarlık stilini ayarlamak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```

### <a name="parameters"></a>Parametreler

*nBorderStyle*<br/>
Yeni kenarlık stili.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_bordervisible"></a><a name="put_bordervisible"></a>CStockPropImpl::put_BorderVisible

Denetimin kenarlığı görünür olup olmadığını gösteren bayrağın değerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```

### <a name="parameters"></a>Parametreler

*bBorderVisible*<br/>
Kenarlık görünür olacaksa DOĞRU.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_borderwidth"></a><a name="put_borderwidth"></a>CStockPropImpl::put_BorderWidth

Denetimin kenarlığı genişliğini ayarlamak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```

### <a name="parameters"></a>Parametreler

*nBorderWidth*<br/>
Denetim sınırının yeni genişliği.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_caption"></a><a name="put_caption"></a>CStockPropImpl::put_Caption

Denetimi ile görüntülenecek metni ayarlamak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```

### <a name="parameters"></a>Parametreler

*bstrCaption*<br/>
Denetimle birlikte görüntülenecek metin.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_drawmode"></a><a name="put_drawmode"></a>CStockPropImpl::put_DrawMode

Denetimin çizim modunu ayarlamak için bu yöntemi çağırın, örneğin XOR Kalem veya Renkleri Tersine Çevir.

```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```

### <a name="parameters"></a>Parametreler

*nDrawMode*<br/>
Denetim için yeni çizim modu.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_drawstyle"></a><a name="put_drawstyle"></a>CStockPropImpl::put_DrawStyle

Denetimin çizim stilini ayarlamak için bu yöntemi çağırın, örneğin katı, kesikli veya noktalı.

```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```

### <a name="parameters"></a>Parametreler

*nDrawStyle*<br/>
Denetim için yeni çizim stili.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_drawwidth"></a><a name="put_drawwidth"></a>CStockPropImpl::put_DrawWidth

Denetimin çizim yöntemleri tarafından kullanılan genişliği (piksel olarak) ayarlamak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```

### <a name="parameters"></a>Parametreler

*nDrawWidth*<br/>
Denetimin çizim yöntemleri tarafından kullanılacak yeni genişlik.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_enabled"></a><a name="put_enabled"></a>CStockPropImpl::put_Etkin

Denetimin etkin olup olmadığını gösteren bayrağın değerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```

### <a name="parameters"></a>Parametreler

*bEtkin*<br/>
Denetim etkinse TRUE.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_fillcolor"></a><a name="put_fillcolor"></a>CStockPropImpl::put_FillColor

Denetimin dolgu rengini ayarlamak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```

### <a name="parameters"></a>Parametreler

*clrFillColor*<br/>
Denetim için yeni dolgu rengi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_fillstyle"></a><a name="put_fillstyle"></a>CStockPropImpl::put_FillStyle

Denetimin dolgu stilini ayarlamak için bu yöntemi çağırın, örneğin katı, saydam veya çapraz kapaklı.

```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```

### <a name="parameters"></a>Parametreler

*nFillStyle*<br/>
Denetim için yeni dolgu stili.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_font"></a><a name="put_font"></a>CStockPropImpl::put_Font

Denetimin yazı tipi özelliklerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
Denetimin yazı tipi özelliklerine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_forecolor"></a><a name="put_forecolor"></a>CStockPropImpl::put_ForeColor

Denetimin ön plan rengini ayarlamak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```

### <a name="parameters"></a>Parametreler

*clrForeColor*<br/>
Kontrolün yeni ön plan rengi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_hwnd"></a><a name="put_hwnd"></a>CStockPropImpl::put_HWND

Bu yöntem E_FAIL döndürür.

```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

E_FAIL döndürür.

### <a name="remarks"></a>Açıklamalar

Pencere tutamacı salt okunur değerdir.

## <a name="cstockpropimplput_mouseicon"></a><a name="put_mouseicon"></a>CStockPropImpl::put_MouseIcon

Fare denetim üzerindeyken grafiğin (simge, biteşveya metadosya) resim özelliklerini görüntülenecek şekilde ayarlamak için bu yöntemi arayın.

```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parametreler

*pResim*<br/>
Grafiğin resim özelliklerine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_mousepointer"></a><a name="put_mousepointer"></a>CStockPropImpl::put_MousePointer

Fare denetim üzerindeyken görüntülenen fare işaretçisi türünü ayarlamak için bu yöntemi çağırın, örneğin ok, çapraz veya kum saati.

```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```

### <a name="parameters"></a>Parametreler

*nMousePointer*<br/>
Fare işaretçisi türü.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_picture"></a><a name="put_picture"></a>CStockPropImpl::put_Resim

Görüntülenecek bir grafiğin (simge, biteşveya metadosya) resim özelliklerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parametreler

*pResim*<br/>
Resmin özelliklerine işaretçi. Daha fazla bilgi için [IPictureDisp'e](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_readystate"></a><a name="put_readystate"></a>CStockPropImpl::put_ReadyState

Denetimin hazır durumunu ayarlamak için bu yöntemi çağırın, örneğin, yükleme veya yükleme.

```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```

### <a name="parameters"></a>Parametreler

*nReadyState*<br/>
Kontrol hazır durumda.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_tabstop"></a><a name="put_tabstop"></a>CStockPropImpl::put_TabStop

Denetimin sekme durağı olup olmadığını gösteren bayrağı ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```

### <a name="parameters"></a>Parametreler

*bTabStop*<br/>
Denetim bir sekme durağı ise DOĞRU.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_text"></a><a name="put_text"></a>CStockPropImpl::put_Text

Denetimle birlikte görüntülenen metni ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```

### <a name="parameters"></a>Parametreler

*bstrText*<br/>
Denetimle birlikte görüntülenen metin.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplputvalid"></a><a name="put_valid"></a>CStockPropImpl::putvalid

Denetimin geçerli olup olmadığını belirten bayrağı ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```

### <a name="parameters"></a>Parametreler

*bGeçerli*<br/>
Denetim geçerliyse DOĞRU.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="cstockpropimplput_window"></a><a name="put_window"></a>CStockPropImpl::put_Pencere

Bu yöntem [CStockPropImpl::put_HWND](#put_hwnd)çağırır, E_FAIL döndürür.

```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
Pencere kolu.

### <a name="return-value"></a>Dönüş Değeri

E_FAIL döndürür.

### <a name="remarks"></a>Açıklamalar

Pencere tutamacı salt okunur değerdir.

## <a name="cstockpropimplputref_font"></a><a name="putref_font"></a>CStockPropImpl::putref_Font

Denetimin yazı tipi özelliklerini başvuru sayısıyla ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
Denetimin yazı tipi özelliklerine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

[CStockPropImpl::put_Font](#put_font)ile aynı, ancak bir referans sayısı ile.

## <a name="cstockpropimplputref_mouseicon"></a><a name="putref_mouseicon"></a>CStockPropImpl::putref_MouseIcon

Fare denetim üzerindeyken, bir başvuru sayısıyla görüntülenecek grafiğin (simge, biteşveya metadosya) resim özelliklerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parametreler

*pResim*<br/>
Grafiğin resim özelliklerine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

[CStockPropImpl: :put_MouseIcon](#put_mouseicon)ile aynı, ancak bir referans sayısı ile.

## <a name="cstockpropimplputref_picture"></a><a name="putref_picture"></a>CStockPropImpl::putref_Resim

Bir grafiğin (simge, bitmap veya metadosya) resim özelliklerini referans sayısıyla birlikte görüntülenecek şekilde ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parametreler

*pResim*<br/>
Resmin özelliklerine işaretçi. Daha fazla bilgi için [IPictureDisp'e](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

[CStockPropImpl::put_Picture](#put_picture)ile aynı, ancak bir referans sayısı ile.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[IDispatchImpl Sınıfı](../../atl/reference/idispatchimpl-class.md)
