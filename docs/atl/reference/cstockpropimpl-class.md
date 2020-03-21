---
title: CStockPropImpl sınıfı
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
ms.openlocfilehash: bc349137661d7026e48688f8ef510958de270280
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075213"
---
# <a name="cstockpropimpl-class"></a>CStockPropImpl sınıfı

Bu sınıf, hisse senedi özellik değerlerini desteklemek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

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

*Şı*<br/>
Denetimi uygulayan ve `CStockPropImpl`türetmede olan sınıf.

*'Nün*<br/>
Hisse senedi özelliklerini açığa çıkaran çift arabirim.

*piıd*<br/>
`InterfaceName`IID 'sine yönelik bir işaretçi.

*plibıd*<br/>
`InterfaceName`tanımını içeren tür kitaplığının LIBıD işaretçisi.

*Wana*<br/>
Tür kitaplığının ana sürümü. Varsayılan değer 1’dir.

*wMinor*<br/>
Tür kitaplığının ikincil sürümü. Varsayılan değer 0’dır.

*tihclass*<br/>
*T*için tür bilgilerini yönetmek için kullanılan sınıf. Varsayılan değer `CComTypeInfoHolder`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|[get_Appearance](#get_appearance)|Denetim tarafından kullanılan boyama stilini (örneğin, düz veya 3B) almak için bu yöntemi çağırın.|
|[get_AutoSize](#get_autosize)|Denetimin diğer bir boyut olup olmayacağını gösteren bayrağın durumunu almak için bu yöntemi çağırın.|
|[get_BackColor](#get_backcolor)|Denetimin arka plan rengini almak için bu yöntemi çağırın.|
|[get_BackStyle](#get_backstyle)|Denetimin arka plan stilini saydam ya da donuk almak için bu yöntemi çağırın.|
|[get_BorderColor](#get_bordercolor)|Denetimin kenarlık rengini almak için bu yöntemi çağırın.|
|[get_BorderStyle](#get_borderstyle)|Denetimin kenarlık stilini almak için bu yöntemi çağırın.|
|[get_BorderVisible](#get_bordervisible)|Denetimin kenarlığının görünür olup olmadığını gösteren bayrağın durumunu almak için bu yöntemi çağırın.|
|[get_BorderWidth](#get_borderwidth)|Denetimin kenarlığının genişliğini (piksel cinsinden) almak için bu yöntemi çağırın.|
|[get_Caption](#get_caption)|Nesnenin Başlık metninde belirtilen metni almak için bu yöntemi çağırın.|
|[get_DrawMode](#get_drawmode)|Denetimin çizim modunu almak için bu yöntemi çağırın, örneğin XOR Pen veya ters çevir renkleri.|
|[get_DrawStyle](#get_drawstyle)|Denetimin çizim stilini (örneğin, düz, kesikli veya noktalı) almak için bu yöntemi çağırın.|
|[get_DrawWidth](#get_drawwidth)|Denetimin çizim yöntemleri tarafından kullanılan çizim genişliğini (piksel cinsinden) almak için bu yöntemi çağırın.|
|[get_Enabled](#get_enabled)|Denetimin etkin olup olmadığını gösteren bayrağın durumunu almak için bu yöntemi çağırın.|
|[get_FillColor](#get_fillcolor)|Denetimin Fill rengini almak için bu yöntemi çağırın.|
|[get_FillStyle](#get_fillstyle)|Denetimin dolgusu stilini almak için bu yöntemi çağırın, örneğin, düz, saydam veya çapraz taranmış.|
|[get_Font](#get_font)|Denetimin yazı tipi özelliklerine bir işaretçi almak için bu yöntemi çağırın.|
|[get_ForeColor](#get_forecolor)|Denetimin ön plan rengini almak için bu yöntemi çağırın.|
|[get_HWND](#get_hwnd)|Denetimle ilişkili pencere tanıtıcısını almak için bu yöntemi çağırın.|
|[get_MouseIcon](#get_mouseicon)|Fare denetimin üzerindeyken görüntülenecek grafiğin (simge, bit eşlem veya meta dosyası) resim özelliklerini almak için bu yöntemi çağırın.|
|[get_MousePointer](#get_mousepointer)|Fare denetimin üzerindeyken (örneğin, ok, çapraz veya kum saati) fare işaretçisinin türünü almak için bu yöntemi çağırın.|
|[get_Picture](#get_picture)|Görüntülenecek grafiğin (simge, bit eşlem veya meta dosyası) resim özelliklerine yönelik bir işaretçi almak için bu yöntemi çağırın.|
|[get_ReadyState](#get_readystate)|Denetimin Ready durumunu (örneğin, yükleme veya yükleme) almak için bu yöntemi çağırın.|
|[get_TabStop](#get_tabstop)|Denetimin bir sekme durağı olup olmadığını gösteren bayrağı almak için bu yöntemi çağırın.|
|[get_Text](#get_text)|Denetimle birlikte görüntülenecek metni almak için bu yöntemi çağırın.|
|[getvalid](#get_valid)|Denetimin geçerli olup olmadığını gösteren bayrağın durumunu almak için bu yöntemi çağırın.|
|[get_Window](#get_window)|Denetimle ilişkili pencere tanıtıcısını almak için bu yöntemi çağırın. [CStockPropImpl:: get_HWND](#get_hwnd)ile özdeş.|
|[put_Appearance](#put_appearance)|Denetim tarafından kullanılan boyama stilini (örneğin, düz veya 3B) ayarlamak için bu yöntemi çağırın.|
|[put_AutoSize](#put_autosize)|Denetimin başka bir boyut olup olmayacağını gösteren bayrağın değerini ayarlamak için bu yöntemi çağırın.|
|[put_BackColor](#put_backcolor)|Denetimin arka plan rengini ayarlamak için bu yöntemi çağırın.|
|[put_BackStyle](#put_backstyle)|Denetimin arka plan stilini ayarlamak için bu yöntemi çağırın.|
|[put_BorderColor](#put_bordercolor)|Denetimin kenarlık rengini ayarlamak için bu yöntemi çağırın.|
|[put_BorderStyle](#put_borderstyle)|Denetimin kenarlık stilini ayarlamak için bu yöntemi çağırın.|
|[put_BorderVisible](#put_bordervisible)|Denetimin kenarlığının görünür olup olmadığını gösteren bayrağın değerini ayarlamak için bu yöntemi çağırın.|
|[put_BorderWidth](#put_borderwidth)|Denetimin kenarlığının genişliğini ayarlamak için bu yöntemi çağırın.|
|[put_Caption](#put_caption)|Denetimiyle görüntülenecek metni ayarlamak için bu yöntemi çağırın.|
|[put_DrawMode](#put_drawmode)|Denetimin çizim modunu ayarlamak için bu yöntemi çağırın, örneğin XOR Pen veya ters çevir renkleri.|
|[put_DrawStyle](#put_drawstyle)|Denetimin çizim stilini (örneğin, düz, kesikli veya noktalı) ayarlamak için bu yöntemi çağırın.|
|[put_DrawWidth](#put_drawwidth)|Denetimin çizim yöntemleri tarafından kullanılan genişliği (piksel cinsinden) ayarlamak için bu yöntemi çağırın.|
|[put_Enabled](#put_enabled)|Denetimin etkin olup olmadığını gösteren bayrağı ayarlamak için bu yöntemi çağırın.|
|[put_FillColor](#put_fillcolor)|Denetimin Fill rengini ayarlamak için bu yöntemi çağırın.|
|[put_FillStyle](#put_fillstyle)|Denetimin Fill stilini ayarlamak için bu yöntemi çağırın, örneğin, düz, saydam veya çapraz taranmış.|
|[put_Font](#put_font)|Denetimin yazı tipi özelliklerini ayarlamak için bu yöntemi çağırın.|
|[put_ForeColor](#put_forecolor)|Denetimin ön plan rengini ayarlamak için bu yöntemi çağırın.|
|[put_HWND](#put_hwnd)|Bu yöntem E_FAIL döndürür.|
|[put_MouseIcon](#put_mouseicon)|Fare denetimin üzerindeyken görüntülenecek grafiğin resim özelliklerini (simge, bit eşlem veya meta dosyası) ayarlamak için bu yöntemi çağırın.|
|[put_MousePointer](#put_mousepointer)|Fare denetimin üzerindeyken (örneğin, ok, çapraz veya kum saati) fare işaretçisinin türünü ayarlamak için bu yöntemi çağırın.|
|[put_Picture](#put_picture)|Görüntülenecek grafiğin resim özelliklerini (simge, bit eşlem veya meta dosyası) ayarlamak için bu yöntemi çağırın.|
|[put_ReadyState](#put_readystate)|Denetimin Ready durumunu ayarlamak için bu yöntemi çağırın, örneğin, yükleme veya yükleme.|
|[put_TabStop](#put_tabstop)|Denetimin bir sekme durağı olup olmadığını gösteren bayrağın değerini ayarlamak için bu yöntemi çağırın.|
|[put_Text](#put_text)|Denetimiyle görüntülenen metni ayarlamak için bu yöntemi çağırın.|
|[putvalid](#put_valid)|Denetimin geçerli olup olmadığını gösteren bayrağı ayarlamak için bu yöntemi çağırın.|
|[put_Window](#put_window)|Bu yöntem, E_FAIL döndüren [CStockPropImpl::p ut_HWND](#put_hwnd)çağırır.|
|[putref_Font](#putref_font)|Denetimin yazı tipi özelliklerini bir başvuru sayısıyla ayarlamak için bu yöntemi çağırın.|
|[putref_MouseIcon](#putref_mouseicon)|Fare denetimin üzerindeyken, bir başvuru sayısıyla görüntülenecek grafiğin resim özelliklerini (simge, bit eşlem veya meta dosyası) ayarlamak için bu yöntemi çağırın.|
|[putref_Picture](#putref_picture)|Görüntülenecek bir grafiğin resim özelliklerini (simge, bit eşlem veya meta dosyası), başvuru sayısı ile ayarlamak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CStockPropImpl` her hisse senedi özelliği için **PUT** ve **Get** yöntemleri sağlar. Bu yöntemler, her bir özellik ile ilişkili veri üyesini ayarlamak ya da almak için gereken kodu ve herhangi bir özellik değiştiğinde kapsayıcıya bildirme ve eşitlemenizi sağlar.

Visual Studio, sihirbazları aracılığıyla hisse senedi özellikleri için destek sağlar. Bir denetime hisse senedi özellikleri ekleme hakkında daha fazla bilgi için bkz. [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md).

Geriye dönük uyumluluk için `CStockPropImpl` Ayrıca, sırasıyla `get_HWND` ve `put_HWND`çağıran `get_Window` ve `put_Window` yöntemler de sunar. `put_HWND` varsayılan uygulanması, HWND salt okunurdur özelliği olması gerektiğinden E_FAIL döndürür.

Aşağıdaki özellikler ayrıca bir **PutRef** uygulamasına sahiptir:

- Yazý

- MouseIcon

- Resim

Aynı üç hisse senedi özelliği, karşılık gelen veri üyelerinin `CComPtr` türünde olmasını veya atama operatörü aracılığıyla doğru arabirim başvurusu sağlayan başka bir sınıfı gerektirir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)

`CStockPropImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

##  <a name="cstockpropimplget_appearance"></a><a name="get_appearance"></a>CStockPropImpl:: get_Appearance

Denetim tarafından kullanılan boyama stilini (örneğin, düz veya 3B) almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```

### <a name="parameters"></a>Parametreler

*pnAppearance*<br/>
Denetimin boyama stilini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_autosize"></a><a name="get_autosize"></a>CStockPropImpl:: get_AutoSize

Denetimin diğer bir boyut olup olmayacağını gösteren bayrağın durumunu almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```

### <a name="parameters"></a>Parametreler

*pbAutoSize*<br/>
Bayrak durumunu alan değişken. DOĞRU, denetimin başka bir boyut olmadığını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_backcolor"></a><a name="get_backcolor"></a>CStockPropImpl:: get_BackColor

Denetimin arka plan rengini almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```

### <a name="parameters"></a>Parametreler

*pclrBackColor*<br/>
Denetimin arka plan rengini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_backstyle"></a><a name="get_backstyle"></a>CStockPropImpl:: get_BackStyle

Denetimin arka plan stilini saydam ya da donuk almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```

### <a name="parameters"></a>Parametreler

*pnBackStyle*<br/>
Denetimin arka plan stilini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_bordercolor"></a><a name="get_bordercolor"></a>CStockPropImpl:: get_BorderColor

Denetimin kenarlık rengini almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```

### <a name="parameters"></a>Parametreler

*pclrBorderColor*<br/>
Denetimin kenarlık rengini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_borderstyle"></a><a name="get_borderstyle"></a>CStockPropImpl:: get_BorderStyle

Denetimin kenarlık stilini almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```

### <a name="parameters"></a>Parametreler

*pnBorderStyle*<br/>
Denetimin kenarlık stilini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_bordervisible"></a><a name="get_bordervisible"></a>CStockPropImpl:: get_BorderVisible

Denetimin kenarlığının görünür olup olmadığını gösteren bayrağın durumunu almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```

### <a name="parameters"></a>Parametreler

*pbBorderVisible*<br/>
Bayrak durumunu alan değişken. DOĞRU, denetimin kenarlığının görünür olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_borderwidth"></a><a name="get_borderwidth"></a>CStockPropImpl:: get_BorderWidth

Denetimin kenarlığının genişliğini almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```

### <a name="parameters"></a>Parametreler

*pnBorderWidth*<br/>
Denetimin kenarlık genişliğini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_caption"></a><a name="get_caption"></a>CStockPropImpl:: get_Caption

Nesnenin Başlık metninde belirtilen metni almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```

### <a name="parameters"></a>Parametreler

*pbstrCaption*<br/>
Denetimle birlikte görüntülenecek metin.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_drawmode"></a><a name="get_drawmode"></a>CStockPropImpl:: get_DrawMode

Denetimin çizim modunu almak için bu yöntemi çağırın, örneğin XOR Pen veya ters çevir renkleri.

```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```

### <a name="parameters"></a>Parametreler

*pnDrawMode*<br/>
Denetimin çizim modunu alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_drawstyle"></a><a name="get_drawstyle"></a>CStockPropImpl:: get_DrawStyle

Denetimin çizim stilini (örneğin, düz, kesikli veya noktalı) almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```

### <a name="parameters"></a>Parametreler

*pnDrawStyle*<br/>
Denetimin çizim stilini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_drawwidth"></a><a name="get_drawwidth"></a>CStockPropImpl:: get_DrawWidth

Denetimin çizim yöntemleri tarafından kullanılan çizim genişliğini (piksel cinsinden) almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```

### <a name="parameters"></a>Parametreler

*pnDrawWidth*<br/>
Denetimin genişlik değeri piksel cinsinden alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_enabled"></a><a name="get_enabled"></a>CStockPropImpl:: get_Enabled

Denetimin etkin olup olmadığını gösteren bayrağın durumunu almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```

### <a name="parameters"></a>Parametreler

*pbEnabled*<br/>
Bayrak durumunu alan değişken. TRUE, denetimin etkinleştirildiğini gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_fillcolor"></a><a name="get_fillcolor"></a>CStockPropImpl:: get_FillColor

Denetimin Fill rengini almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```

### <a name="parameters"></a>Parametreler

*pclrFillColor*<br/>
Denetimin dolgusu rengini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_fillstyle"></a><a name="get_fillstyle"></a>CStockPropImpl:: get_FillStyle

Denetimin Fill stilini (örneğin, düz, saydam veya çapraz tarama) almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```

### <a name="parameters"></a>Parametreler

*pnFillStyle*<br/>
Denetimin Fill stilini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_font"></a><a name="get_font"></a>CStockPropImpl:: get_Font

Denetimin yazı tipi özelliklerine bir işaretçi almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```

### <a name="parameters"></a>Parametreler

*ppFont*<br/>
Denetimin yazı tipi özelliklerine bir işaretçi alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_forecolor"></a><a name="get_forecolor"></a>CStockPropImpl:: get_ForeColor

Denetimin ön plan rengini almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```

### <a name="parameters"></a>Parametreler

*pclrForeColor*<br/>
Denetimlerin ön plan rengini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_hwnd"></a><a name="get_hwnd"></a>CStockPropImpl:: get_HWND

Denetimle ilişkili pencere tanıtıcısını almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Parametreler

*phWnd*<br/>
Denetimle ilişkili pencere tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_mouseicon"></a><a name="get_mouseicon"></a>CStockPropImpl:: get_MouseIcon

Fare denetimin üzerindeyken görüntülenecek grafiğin (simge, bit eşlem veya meta dosyası) resim özelliklerini almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Parametreler

*ppPicture*<br/>
Grafiğin resim özelliklerine bir işaretçi alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_mousepointer"></a><a name="get_mousepointer"></a>CStockPropImpl:: get_MousePointer

Fare denetimin üzerindeyken (örneğin, ok, çapraz veya kum saati) fare işaretçisinin türünü almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```

### <a name="parameters"></a>Parametreler

*pnMousePointer*<br/>
Fare işaretçisinin türünü alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_picture"></a><a name="get_picture"></a>CStockPropImpl:: get_Picture

Görüntülenecek grafiğin (simge, bit eşlem veya meta dosyası) resim özelliklerine yönelik bir işaretçi almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Parametreler

*ppPicture*<br/>
Resmin özelliklerine bir işaretçi alan değişken. Daha fazla ayrıntı için bkz. [IPictureDisp](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) .

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_readystate"></a><a name="get_readystate"></a>CStockPropImpl:: get_ReadyState

Denetimin Ready durumunu (örneğin, yükleme veya yükleme) almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```

### <a name="parameters"></a>Parametreler

*pnReadyState*<br/>
Denetimin Ready durumunu alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_tabstop"></a><a name="get_tabstop"></a>CStockPropImpl:: get_TabStop

Denetimin bir sekme durağı olup olmadığını gösteren bayrağın durumunu almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```

### <a name="parameters"></a>Parametreler

*pbTabStop*<br/>
Bayrak durumunu alan değişken. DOĞRU, denetimin bir sekme durağı olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_text"></a><a name="get_text"></a>CStockPropImpl:: get_Text

Denetimle birlikte görüntülenecek metni almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```

### <a name="parameters"></a>Parametreler

*pbstrText*<br/>
Denetimle birlikte görüntülenen metin.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplgetvalid"></a><a name="get_valid"></a>CStockPropImpl:: getvalid

Denetimin geçerli olup olmadığını gösteren bayrağın durumunu almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```

### <a name="parameters"></a>Parametreler

*pbValid*<br/>
Bayrak durumunu alan değişken. TRUE, denetimin geçerli olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplget_window"></a><a name="get_window"></a>CStockPropImpl:: get_Window

Denetimle ilişkili pencere tanıtıcısını almak için bu yöntemi çağırın. [CStockPropImpl:: get_HWND](#get_hwnd)ile özdeş.

```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Parametreler

*phWnd*<br/>
Denetimle ilişkili pencere tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_appearance"></a><a name="put_appearance"></a>CStockPropImpl::p ut_Appearance

Denetim tarafından kullanılan boyama stilini (örneğin, düz veya 3B) ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```

### <a name="parameters"></a>Parametreler

*nAppearance*<br/>
Denetim tarafından kullanılacak yeni boyama stili.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_autosize"></a><a name="put_autosize"></a>CStockPropImpl::p ut_AutoSize

Denetimin başka bir boyut olup olmayacağını gösteren bayrak değerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```

### <a name="parameters"></a>Parametreler

*bAutoSize*<br/>
Denetim başka bir boyut değilse TRUE.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_backcolor"></a><a name="put_backcolor"></a>CStockPropImpl::p ut_BackColor

Denetimin arka plan rengini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```

### <a name="parameters"></a>Parametreler

*clrBackColor*<br/>
Yeni denetim arka plan rengi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_backstyle"></a><a name="put_backstyle"></a>CStockPropImpl::p ut_BackStyle

Denetimin arka plan stilini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```

### <a name="parameters"></a>Parametreler

*nBackStyle*<br/>
Yeni denetim arka plan stili.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_bordercolor"></a><a name="put_bordercolor"></a>CStockPropImpl::p ut_BorderColor

Denetimin kenarlık rengini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```

### <a name="parameters"></a>Parametreler

*clrBorderColor*<br/>
Yeni kenarlık rengi. OLE_COLOR veri türü dahili olarak 32 bitlik uzun tamsayı olarak temsil edilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_borderstyle"></a><a name="put_borderstyle"></a>CStockPropImpl::p ut_BorderStyle

Denetimin kenarlık stilini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```

### <a name="parameters"></a>Parametreler

*nBorderStyle*<br/>
Yeni kenarlık stili.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_bordervisible"></a><a name="put_bordervisible"></a>CStockPropImpl::p ut_BorderVisible

Denetimin kenarlığının görünür olup olmadığını gösteren bayrağın değerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```

### <a name="parameters"></a>Parametreler

*bBorderVisible*<br/>
Kenarlığın görünür olması durumunda TRUE.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_borderwidth"></a><a name="put_borderwidth"></a>CStockPropImpl::p ut_BorderWidth

Denetimin kenarlığının genişliğini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```

### <a name="parameters"></a>Parametreler

*nBorderWidth*<br/>
Denetimin kenarlığının yeni genişliği.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_caption"></a><a name="put_caption"></a>CStockPropImpl::p ut_Caption

Denetimiyle görüntülenecek metni ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```

### <a name="parameters"></a>Parametreler

*bstrCaption*<br/>
Denetimle birlikte görüntülenecek metin.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_drawmode"></a><a name="put_drawmode"></a>CStockPropImpl::p ut_DrawMode

Denetimin çizim modunu ayarlamak için bu yöntemi çağırın, örneğin XOR Pen veya ters çevir renkleri.

```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```

### <a name="parameters"></a>Parametreler

*nDrawMode*<br/>
Denetim için yeni çizim modu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_drawstyle"></a><a name="put_drawstyle"></a>CStockPropImpl::p ut_DrawStyle

Denetimin çizim stilini (örneğin, düz, kesikli veya noktalı) ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```

### <a name="parameters"></a>Parametreler

*nDrawStyle*<br/>
Denetim için yeni çizim stili.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_drawwidth"></a><a name="put_drawwidth"></a>CStockPropImpl::p ut_DrawWidth

Denetimin çizim yöntemleri tarafından kullanılan genişliği (piksel cinsinden) ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```

### <a name="parameters"></a>Parametreler

*nDrawWidth*<br/>
Denetimin çizim yöntemleri tarafından kullanılacak yeni Genişlik.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_enabled"></a><a name="put_enabled"></a>CStockPropImpl::p ut_Enabled

Denetimin etkin olup olmadığını gösteren bayrağın değerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```

### <a name="parameters"></a>Parametreler

*bEnabled*<br/>
Denetim etkinse TRUE.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_fillcolor"></a><a name="put_fillcolor"></a>CStockPropImpl::p ut_FillColor

Denetimin Fill rengini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```

### <a name="parameters"></a>Parametreler

*clrFillColor*<br/>
Denetimin yeni dolgusu rengi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_fillstyle"></a><a name="put_fillstyle"></a>CStockPropImpl::p ut_FillStyle

Denetimin Fill stilini ayarlamak için bu yöntemi çağırın, örneğin, düz, saydam veya çapraz taranmış.

```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```

### <a name="parameters"></a>Parametreler

*nFillStyle*<br/>
Denetimin yeni Fill stili.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_font"></a><a name="put_font"></a>CStockPropImpl::p ut_Font

Denetimin yazı tipi özelliklerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
Denetimin yazı tipi özelliklerine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_forecolor"></a><a name="put_forecolor"></a>CStockPropImpl::p ut_ForeColor

Denetimin ön plan rengini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```

### <a name="parameters"></a>Parametreler

*clrForeColor*<br/>
Denetimin yeni ön plan rengi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_hwnd"></a><a name="put_hwnd"></a>CStockPropImpl::p ut_HWND

Bu yöntem E_FAIL döndürür.

```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
Ayrılamadı.

### <a name="return-value"></a>Dönüş Değeri

E_FAIL döndürür.

### <a name="remarks"></a>Açıklamalar

Pencere tutamacı salt okunurdur.

##  <a name="cstockpropimplput_mouseicon"></a><a name="put_mouseicon"></a>CStockPropImpl::p ut_MouseIcon

Fare denetimin üzerindeyken görüntülenecek grafiğin resim özelliklerini (simge, bit eşlem veya meta dosyası) ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parametreler

*Ppıcture*<br/>
Grafiğin resim özelliklerine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_mousepointer"></a><a name="put_mousepointer"></a>CStockPropImpl::p ut_MousePointer

Fare denetimin üzerindeyken (örneğin, ok, çapraz veya kum saati) fare işaretçisinin türünü ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```

### <a name="parameters"></a>Parametreler

*nMousePointer*<br/>
Fare işaretçisinin türü.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_picture"></a><a name="put_picture"></a>CStockPropImpl::p ut_Picture

Görüntülenecek grafiğin resim özelliklerini (simge, bit eşlem veya meta dosyası) ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parametreler

*Ppıcture*<br/>
Resmin özelliklerine yönelik bir işaretçi. Daha fazla ayrıntı için bkz. [IPictureDisp](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) .

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_readystate"></a><a name="put_readystate"></a>CStockPropImpl::p ut_ReadyState

Denetimin Ready durumunu ayarlamak için bu yöntemi çağırın, örneğin, yükleme veya yükleme.

```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```

### <a name="parameters"></a>Parametreler

*nReadyState*<br/>
Denetimin Ready durumu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_tabstop"></a><a name="put_tabstop"></a>CStockPropImpl::p ut_TabStop

Denetimin bir sekme durağı olup olmadığını gösteren bayrağı ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```

### <a name="parameters"></a>Parametreler

*bTabStop*<br/>
Denetim bir sekme durağı ise TRUE.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_text"></a><a name="put_text"></a>CStockPropImpl::p ut_Text

Denetimiyle görüntülenen metni ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```

### <a name="parameters"></a>Parametreler

*bstrText*<br/>
Denetimle birlikte görüntülenen metin.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplputvalid"></a><a name="put_valid"></a>CStockPropImpl::p utvalid

Denetimin geçerli olup olmadığını gösteren bayrağı ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```

### <a name="parameters"></a>Parametreler

*bValid*<br/>
Denetim geçerliyse TRUE.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="cstockpropimplput_window"></a><a name="put_window"></a>CStockPropImpl::p ut_Window

Bu yöntem, E_FAIL döndüren [CStockPropImpl::p ut_HWND](#put_hwnd)çağırır.

```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
Pencere tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

E_FAIL döndürür.

### <a name="remarks"></a>Açıklamalar

Pencere tutamacı salt okunurdur.

##  <a name="cstockpropimplputref_font"></a><a name="putref_font"></a>CStockPropImpl::p utref_Font

Denetimin yazı tipi özelliklerini bir başvuru sayısıyla ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
Denetimin yazı tipi özelliklerine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[CStockPropImpl::p ut_Font](#put_font), ancak başvuru sayısı ile aynı.

##  <a name="cstockpropimplputref_mouseicon"></a><a name="putref_mouseicon"></a>CStockPropImpl::p utref_MouseIcon

Fare denetimin üzerindeyken, bir başvuru sayısıyla görüntülenecek grafiğin resim özelliklerini (simge, bit eşlem veya meta dosyası) ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parametreler

*Ppıcture*<br/>
Grafiğin resim özelliklerine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[CStockPropImpl::p ut_MouseIcon](#put_mouseicon), ancak başvuru sayısı ile aynı.

##  <a name="cstockpropimplputref_picture"></a><a name="putref_picture"></a>CStockPropImpl::p utref_Picture

Görüntülenecek bir grafiğin resim özelliklerini (simge, bit eşlem veya meta dosyası), başvuru sayısı ile ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parametreler

*Ppıcture*<br/>
Resmin özelliklerine yönelik bir işaretçi. Daha fazla ayrıntı için bkz. [IPictureDisp](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) .

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[CStockPropImpl::p ut_Picture](#put_picture), ancak başvuru sayısı ile aynı.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[IDispatchImpl Sınıfı](../../atl/reference/idispatchimpl-class.md)
