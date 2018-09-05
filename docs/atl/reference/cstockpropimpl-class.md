---
title: Cstockpropımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CStockPropImpl class
- controls [ATL], stock properties
- stock properties, ATL controls
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2021f98389177e7c3172fd142172c6bc85f6724
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767744"
---
# <a name="cstockpropimpl-class"></a>Cstockpropımpl sınıfı

Bu sınıf, stok özellik değerleri desteklemek için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class InterfaceName,
    const IID* piid = &_ATL_IIDOF(InterfaceName),
    const GUID* plibid = &CComModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CcomTypeInfoHolder>  
class ATL_NO_VTABLE CStockPropImpl : public IDispatchImpl<InterfaceName, piid,
plibid,
    wMajor,
wMinor,
    tihclass>
```

#### <a name="parameters"></a>Parametreler

*T*  
Denetimi uygulamak ve türetilen sınıf `CStockPropImpl`.

*InterfaceName*  
Stok özellikleri kullanıma sunan bir çift arabirim.

*piid*  
Laboratuvardaki işaretçisi `InterfaceName`.

*plibid*  
Tanımını içeren tür kitaplığının Kitaplık kimliği için bir işaretçi `InterfaceName`.

*wMajor*  
Tür kitaplığının ana sürümü. Varsayılan değer 1’dir.

*wMinor*  
Tür kitaplığının bir alt sürümü. Varsayılan değer 0’dır.

*tihclass*  
İçin tür bilgilerini yönetmek için kullanılan sınıf *T*. Varsayılan değer `CComTypeInfoHolder` şeklindedir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|[get_Appearance](#get_appearance)|Boya stil denetimi tarafından kullanılan Örneğin, düz veya 3B almak için bu yöntemi çağırın.|
|[get_AutoSize](#get_autosize)|Denetim bir başka bir boyutu olamaz gösteren bayrak durumunu almak için bu yöntemi çağırın.|
|[get_BackColor](#get_backcolor)|Denetimin arka plan rengini almak için bu yöntemi çağırın.|
|[get_BackStyle](#get_backstyle)|Denetimin arka plan stil, saydam veya donuk almak için bu yöntemi çağırın.|
|[get_BorderColor](#get_bordercolor)|Denetimin kenarlık rengi almak için bu yöntemi çağırın.|
|[get_BorderStyle](#get_borderstyle)|Denetimin kenarlık stili almak için bu yöntemi çağırın.|
|[get_BorderVisible](#get_bordervisible)|Denetimin kenarlığının görünür olup olmadığını gösteren bayrak durumunu almak için bu yöntemi çağırın.|
|[get_BorderWidth](#get_borderwidth)|Denetimin kenarlığının genişliğini (piksel cinsinden) almak için bu yöntemi çağırın.|
|[get_Caption](#get_caption)|Belirtilen bir nesnenin başlığı metin almak için bu yöntemi çağırın.|
|[get_DrawMode](#get_drawmode)|Denetimin çizim modu, örneğin, renkleri veya XOR kalem almak için bu yöntemi çağırın.|
|[get_DrawStyle](#get_drawstyle)|Denetimin çizim stili almak için bu yöntemi, örneğin, düz, kesik çizgili veya noktalı çağırın.|
|[get_DrawWidth](#get_drawwidth)|Denetimin çizim yöntemler tarafından kullanılan çizim genişliğini (piksel cinsinden) almak için bu yöntemi çağırın.|
|[get_Enabled](#get_enabled)|Denetimin etkin olup olmadığını gösteren bayrak durumunu almak için bu yöntemi çağırın.|
|[get_FillColor](#get_fillcolor)|Denetimin dolgu rengini almak için bu yöntemi çağırın.|
|[get_FillStyle](#get_fillstyle)|Denetimin dolgu stili almak için bu yöntemi, örneğin, kesintisiz, saydam veya çapraz çizgili çağırın.|
|[get_Font](#get_font)|Denetim yazı tipi özellikleri için bir işaretçi almak için bu yöntemi çağırın.|
|[get_ForeColor](#get_forecolor)|Denetimin ön plan rengini almak için bu yöntemi çağırın.|
|[get_HWND](#get_hwnd)|Denetimle ilişkili pencere tanıtıcısı almak için bu yöntemi çağırın.|
|[get_MouseIcon](#get_mouseicon)|Grafiğin (simge, bit eşlem veya meta dosyası) fareyi denetimin üzerine getirildiğinde gösterilecek resmi özelliklerini almak için bu yöntemi çağırın.|
|[get_MousePointer](#get_mousepointer)|Fare işaretçisi Fare denetimin üzerine örneğin olduğunda görüntülenir, oku, geçici ya da kum saati türünü almak için bu yöntemi çağırın.|
|[get_Picture](#get_picture)|Bir işaretçi (simge, bit eşlem veya meta dosyası) görüntülenecek grafik resim özelliklerini almak için bu yöntemi çağırın.|
|[get_ReadyState](#get_readystate)|Denetimin hazır durumunu almak için bu yöntemi, örneğin, yükleme veya yüklü çağırın.|
|[get_TabStop](#get_tabstop)|Denetimin sekme durağı olup olmadığını gösteren bayrak almak için bu yöntemi çağırın.|
|[get_Text](#get_text)|Denetim ile görüntülenen metni almak için bu yöntemi çağırın.|
|[getvalid](#get_valid)|Denetim geçerli olup olmadığını gösteren bayrak durumunu almak için bu yöntemi çağırın.|
|[get_Window](#get_window)|Denetimle ilişkili pencere tanıtıcısı almak için bu yöntemi çağırın. Aynı [CStockPropImpl::get_HWND](#get_hwnd).|
|[put_Appearance](#put_appearance)|Boya stil denetimi tarafından kullanılan Örneğin, düz veya 3B ayarlamak için bu yöntemi çağırın.|
|[put_AutoSize](#put_autosize)|Denetim bir başka bir boyutu olamaz gösteren bayrak değerini ayarlamak için bu yöntemi çağırın.|
|[put_BackColor](#put_backcolor)|Denetimin arka plan rengini ayarlamak için bu yöntemi çağırın.|
|[put_BackStyle](#put_backstyle)|Denetimin arka plan stil ayarlamak için bu yöntemi çağırın.|
|[put_BorderColor](#put_bordercolor)|Denetimin kenarlık rengi ayarlamak için bu yöntemi çağırın.|
|[put_BorderStyle](#put_borderstyle)|Denetimin kenarlık stili ayarlamak için bu yöntemi çağırın.|
|[put_BorderVisible](#put_bordervisible)|Denetimin kenarlığının görünür olup olmadığını gösteren bayrak değerini ayarlamak için bu yöntemi çağırın.|
|[put_BorderWidth](#put_borderwidth)|Denetimin kenarlığının genişliğini ayarlamak için bu yöntemi çağırın.|
|[put_Caption](#put_caption)|Denetimle görüntülenecek metni ayarlamak için bu yöntemi çağırın.|
|[put_DrawMode](#put_drawmode)|Denetimin çizim modu, örneğin, renkleri veya XOR kalem ayarlamak için bu yöntemi çağırın.|
|[put_DrawStyle](#put_drawstyle)|Bu yöntem denetimin çizim stilini ayarlayın, örneğin, düz, kesik çizgili veya noktalı çağırın.|
|[put_DrawWidth](#put_drawwidth)|Denetimin çizim yöntemler tarafından kullanılan genişliğini (piksel cinsinden) ayarlamak için bu yöntemi çağırın.|
|[put_Enabled](#put_enabled)|Denetimin etkin olup olmadığını gösteren bayrak ayarlamak için bu yöntemi çağırın.|
|[put_FillColor](#put_fillcolor)|Denetimin dolgu rengini ayarlamak için bu yöntemi çağırın.|
|[put_FillStyle](#put_fillstyle)|Denetimin dolgu stili ayarlamak için bu yöntem, örneğin, düz, saydam veya çapraz çizgili çağırın.|
|[put_Font](#put_font)|Denetim yazı tipi özelliklerini ayarlamak için bu yöntemi çağırın.|
|[put_ForeColor](#put_forecolor)|Denetimin ön plan rengini ayarlamak için bu yöntemi çağırın.|
|[put_HWND](#put_hwnd)|Bu yöntem E_FAIL döndürür.|
|[put_MouseIcon](#put_mouseicon)|Grafiğin (simge, bit eşlem veya meta dosyası) fareyi denetimin üzerine getirildiğinde gösterilecek resmi özelliklerini ayarlamak için bu yöntemi çağırın.|
|[put_MousePointer](#put_mousepointer)|Fare işaretçisi Fare denetimin üzerine örneğin olduğunda görüntülenir, oku, geçici ya da kum saati türünü ayarlamak için bu yöntemi çağırın.|
|[put_Picture](#put_picture)|Bir grafiği (simge, bit eşlem veya meta dosyası) görüntülenecek resim özelliklerini ayarlamak için bu yöntemi çağırın.|
|[put_ReadyState](#put_readystate)|Denetimin hazır duruma ayarlamak için bu yöntem, örneğin, yükleme veya yüklü çağırın.|
|[put_TabStop](#put_tabstop)|Denetimin sekme durağı olup olmadığını gösteren bayrak değerini ayarlamak için bu yöntemi çağırın.|
|[put_Text](#put_text)|Denetim ile görüntülenen metni ayarlama için bu yöntemi çağırın.|
|[putvalid](#put_valid)|Denetim geçerli olup olmadığını gösteren bayrak ayarlamak için bu yöntemi çağırın.|
|[put_Window](#put_window)|Bu yöntemin çağırdığı [CStockPropImpl::put_HWND](#put_hwnd), E_FAIL döndürür.|
|[putref_Font](#putref_font)|Başvuru sayısı ile denetim yazı tipi özelliklerini ayarlamak için bu yöntemi çağırın.|
|[putref_MouseIcon](#putref_mouseicon)|Bir başvuru sayısı ile grafik (simge, bit eşlem ya da meta dosyası) Fare denetimin üzerine geldiğinde görüntülenen resmi özelliklerini ayarlamak için bu yöntemi çağırın.|
|[putref_Picture](#putref_picture)|Bir başvuru sayısı ile grafik (simge, bit eşlem veya meta dosyası) görüntülenecek resim özelliklerini ayarlamak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CStockPropImpl` sağlar **put** ve **alma** stok her özellik için yöntemleri. Bu yöntemler veya her bir özellik ile ilişkili veri üyesi alma ve bildirim ve herhangi bir özellik değiştiğinde, kapsayıcı ile eşitlemek için gerekli kodu sağlayın.

Visual C++, kendi sihirbazları üzerinden stok özellikleri için destek sağlar. Bir denetime stok Özellikler ekleme hakkında daha fazla bilgi için bkz. [ATL öğretici](../../atl/active-template-library-atl-tutorial.md).

Geriye dönük uyumluluk için `CStockPropImpl` de sunan `get_Window` ve `put_Window` yalnızca çağıran yöntemleri `get_HWND` ve `put_HWND`sırasıyla. Varsayılan uygulaması `put_HWND` HWND salt okunur bir özellik olması gerektiğinden E_FAIL döndürür.

Ayrıca aşağıdaki özelliklere sahip bir **putref** uygulama:

- Yazı tipi

- MouseIcon

- Resim

Türünde olması, karşılık gelen veri üyesi aynı üç stok özellikleri gerektiren `CComPtr` veya doğru arabirimi başvuruyu sağlayan başka bir sınıfın sayımı yoluyla atama işleci.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

[Idispatchımpl](../../atl/reference/idispatchimpl-class.md)

`CStockPropImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

##  <a name="get_appearance"></a>  CStockPropImpl::get_Appearance

Boya stil denetimi tarafından kullanılan Örneğin, düz veya 3B almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```

### <a name="parameters"></a>Parametreler

*pnAppearance*  
Değişken, denetimin Boya stilini alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_autosize"></a>  CStockPropImpl::get_AutoSize

Denetim bir başka bir boyutu olamaz gösteren bayrak durumunu almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```

### <a name="parameters"></a>Parametreler

*pbAutoSize*  
Değişken, bayrak durumunu alır. TRUE, denetimin herhangi bir boyutta olamaz gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_backcolor"></a>  CStockPropImpl::get_BackColor

Denetimin arka plan rengini almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```

### <a name="parameters"></a>Parametreler

*pclrBackColor*  
Değişken, denetimin arka plan rengini alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_backstyle"></a>  CStockPropImpl::get_BackStyle

Denetimin arka plan stil, saydam veya donuk almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```

### <a name="parameters"></a>Parametreler

*pnBackStyle*  
Değişken, denetimin arka plan stilini alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_bordercolor"></a>  CStockPropImpl::get_BorderColor

Denetimin kenarlık rengi almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```

### <a name="parameters"></a>Parametreler

*pclrBorderColor*  
Değişken, denetimin kenarlık rengini alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_borderstyle"></a>  CStockPropImpl::get_BorderStyle

Denetimin kenarlık stili almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```

### <a name="parameters"></a>Parametreler

*pnBorderStyle*  
Değişken, bir denetimin kenarlık stilini alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_bordervisible"></a>  CStockPropImpl::get_BorderVisible

Denetimin kenarlığının görünür olup olmadığını gösteren bayrak durumunu almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```

### <a name="parameters"></a>Parametreler

*pbBorderVisible*  
Değişken, bayrak durumunu alır. TRUE, denetimin kenarlığının görünür olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_borderwidth"></a>  CStockPropImpl::get_BorderWidth

Denetimin kenarlığının genişliğini almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```

### <a name="parameters"></a>Parametreler

*pnBorderWidth*  
Değişken, denetimin kenarlık genişliğini alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_caption"></a>  CStockPropImpl::get_Caption

Belirtilen bir nesnenin başlığı metin almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```

### <a name="parameters"></a>Parametreler

*pbstrCaption*  
Denetimle görüntülenecek metin.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_drawmode"></a>  CStockPropImpl::get_DrawMode

Denetimin çizim modu, örneğin, renkleri veya XOR kalem almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```

### <a name="parameters"></a>Parametreler

*pnDrawMode*  
Değişken, denetimin çizim modunu alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_drawstyle"></a>  CStockPropImpl::get_DrawStyle

Denetimin çizim stili almak için bu yöntemi, örneğin, düz, kesik çizgili veya noktalı çağırın.

```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```

### <a name="parameters"></a>Parametreler

*pnDrawStyle*  
Değişken, denetimin çizim stilini alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_drawwidth"></a>  CStockPropImpl::get_DrawWidth

Denetimin çizim yöntemler tarafından kullanılan çizim genişliğini (piksel cinsinden) almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```

### <a name="parameters"></a>Parametreler

*pnDrawWidth*  
Değişken, denetimin genişlik değeri piksel cinsinden alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_enabled"></a>  CStockPropImpl::get_Enabled

Denetimin etkin olup olmadığını gösteren bayrak durumunu almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```

### <a name="parameters"></a>Parametreler

*pbEnabled*  
Değişken, bayrak durumunu alır. TRUE, denetimin etkinleştirildiğini gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_fillcolor"></a>  CStockPropImpl::get_FillColor

Denetimin dolgu rengini almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```

### <a name="parameters"></a>Parametreler

*pclrFillColor*  
Değişken, denetimin dolgu rengini alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_fillstyle"></a>  CStockPropImpl::get_FillStyle

Denetimin dolgu stili almak için bu yöntemi, örneğin, kesintisiz, saydam veya crosshatched çağırın.

```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```

### <a name="parameters"></a>Parametreler

*pnFillStyle*  
Değişken, denetimin dolgu stili alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_font"></a>  CStockPropImpl::get_Font

Denetim yazı tipi özellikleri için bir işaretçi almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```

### <a name="parameters"></a>Parametreler

*ppFont*  
Değişken, denetimin yazı tipi özellikleri için bir işaretçi alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_forecolor"></a>  CStockPropImpl::get_ForeColor

Denetimin ön plan rengini almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```

### <a name="parameters"></a>Parametreler

*pclrForeColor*  
Değişken, denetimleri ön plan rengini alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_hwnd"></a>  CStockPropImpl::get_HWND

Denetimle ilişkili pencere tanıtıcısı almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Parametreler

*phWnd*  
Denetimle ilişkili pencere tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_mouseicon"></a>  CStockPropImpl::get_MouseIcon

Grafiğin (simge, bit eşlem veya meta dosyası) fareyi denetimin üzerine getirildiğinde gösterilecek resmi özelliklerini almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Parametreler

*ppPicture*  
Değişken, grafik resim özellikleri için bir işaretçi alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_mousepointer"></a>  CStockPropImpl::get_MousePointer

Fare işaretçisi Fare denetimin üzerine örneğin olduğunda görüntülenir, oku, geçici ya da kum saati türünü almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```

### <a name="parameters"></a>Parametreler

*pnMousePointer*  
Değişken, fare işaretçisini türünü alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_picture"></a>  CStockPropImpl::get_Picture

Bir işaretçi (simge, bit eşlem veya meta dosyası) görüntülenecek grafik resim özelliklerini almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Parametreler

*ppPicture*  
Değişken, resmin özellikleri için bir işaretçi alır. Bkz: [IPictureDisp](https://msdn.microsoft.com/library/windows/desktop/ms680762) daha fazla ayrıntı için.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_readystate"></a>  CStockPropImpl::get_ReadyState

Denetimin hazır durumunu almak için bu yöntemi, örneğin, yükleme veya yüklü çağırın.

```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```

### <a name="parameters"></a>Parametreler

*pnReadyState*  
Değişken, denetimin hazır durumunu alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_tabstop"></a>  CStockPropImpl::get_TabStop

Denetimin sekme durağı olup olmadığını gösteren bayrak durumunu almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```

### <a name="parameters"></a>Parametreler

*pbTabStop*  
Değişken, bayrak durumunu alır. TRUE, denetimin sekme durağı olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_text"></a>  CStockPropImpl::get_Text

Denetim ile görüntülenen metni almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```

### <a name="parameters"></a>Parametreler

*pbstrText*  
Denetim ile görüntülenen metin.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_valid"></a>  CStockPropImpl::getvalid

Denetim geçerli olup olmadığını gösteren bayrak durumunu almak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```

### <a name="parameters"></a>Parametreler

*pbValid*  
Değişken, bayrak durumunu alır. TRUE, denetimin geçerli olduğunu gösterir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="get_window"></a>  CStockPropImpl::get_Window

Denetimle ilişkili pencere tanıtıcısı almak için bu yöntemi çağırın. Aynı [CStockPropImpl::get_HWND](#get_hwnd).

```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Parametreler

*phWnd*  
Denetimle ilişkili pencere tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_appearance"></a>  CStockPropImpl::put_Appearance

Boya stil denetimi tarafından kullanılan Örneğin, düz veya 3B ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```

### <a name="parameters"></a>Parametreler

*nAppearance*  
Denetim tarafından kullanılmak üzere yeni Boya stili.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_autosize"></a>  CStockPropImpl::put_AutoSize

Denetim bir başka bir boyutu olamaz gösteren bayrak değerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```

### <a name="parameters"></a>Parametreler

*bAutoSize*  
Denetim, diğer herhangi bir boyutta olamaz, TRUE.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_backcolor"></a>  CStockPropImpl::put_BackColor

Denetimin arka plan rengini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```

### <a name="parameters"></a>Parametreler

*clrBackColor*  
Yeni denetim arka plan rengi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_backstyle"></a>  CStockPropImpl::put_BackStyle

Denetimin arka plan stil ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```

### <a name="parameters"></a>Parametreler

*nBackStyle*  
Yeni denetim arka plan stili.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_bordercolor"></a>  CStockPropImpl::put_BorderColor

Denetimin kenarlık rengi ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```

### <a name="parameters"></a>Parametreler

*clrBorderColor*  
Yeni kenarlık rengi. OLE_COLOR veri türü, dahili olarak bir 32-bit uzun tamsayı olarak temsil edilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_borderstyle"></a>  CStockPropImpl::put_BorderStyle

Denetimin kenarlık stili ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```

### <a name="parameters"></a>Parametreler

*nBorderStyle*  
Yeni kenarlık stili.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_bordervisible"></a>  CStockPropImpl::put_BorderVisible

Denetimin kenarlığının görünür olup olmadığını gösteren bayrak değerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```

### <a name="parameters"></a>Parametreler

*bBorderVisible*  
Kenarlık görünür olması gerekiyorsa TRUE.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_borderwidth"></a>  CStockPropImpl::put_BorderWidth

Denetimin kenarlığının genişliğini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```

### <a name="parameters"></a>Parametreler

*nBorderWidth*  
Yeni Denetimin kenarlık genişliği.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_caption"></a>  CStockPropImpl::put_Caption

Denetimle görüntülenecek metni ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```

### <a name="parameters"></a>Parametreler

*bstrCaption*  
Denetimle görüntülenecek metin.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_drawmode"></a>  CStockPropImpl::put_DrawMode

Denetimin çizim modu, örneğin, renkleri veya XOR kalem ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```

### <a name="parameters"></a>Parametreler

*nDrawMode*  
Denetim için yeni çizim modu.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_drawstyle"></a>  CStockPropImpl::put_DrawStyle

Bu yöntem denetimin çizim stilini ayarlayın, örneğin, düz, kesik çizgili veya noktalı çağırın.

```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```

### <a name="parameters"></a>Parametreler

*nDrawStyle*  
Denetim için yeni çizim stili.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_drawwidth"></a>  CStockPropImpl::put_DrawWidth

Denetimin çizim yöntemler tarafından kullanılan genişliğini (piksel cinsinden) ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```

### <a name="parameters"></a>Parametreler

*nDrawWidth*  
Yöntemleri çizim denetimi tarafından kullanılmak üzere yeni genişliği.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_enabled"></a>  CStockPropImpl::put_Enabled

Denetimin etkin olup olmadığını gösteren bayrak değerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```

### <a name="parameters"></a>Parametreler

*bEtkin*  
Denetimin etkin olması halinde TRUE.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_fillcolor"></a>  CStockPropImpl::put_FillColor

Denetimin dolgu rengini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```

### <a name="parameters"></a>Parametreler

*clrFillColor*  
Denetim için yeni dolgu rengi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_fillstyle"></a>  CStockPropImpl::put_FillStyle

Denetimin dolgu stili ayarlamak için bu yöntem, örneğin, düz, saydam veya çapraz çizgili çağırın.

```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```

### <a name="parameters"></a>Parametreler

*nFillStyle*  
Denetim için yeni dolgu stili.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_font"></a>  CStockPropImpl::put_Font

Denetim yazı tipi özelliklerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*  
Denetim yazı tipi özellikleri için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_forecolor"></a>  CStockPropImpl::put_ForeColor

Denetimin ön plan rengini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```

### <a name="parameters"></a>Parametreler

*clrForeColor*  
Denetim yeni ön plan rengi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_hwnd"></a>  CStockPropImpl::put_HWND

Bu yöntem E_FAIL döndürür.

```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```

### <a name="parameters"></a>Parametreler

*/\* hWnd \*/*  
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

E_FAIL döndürür.

### <a name="remarks"></a>Açıklamalar

Pencere tanıtıcısı salt okunur bir değerdir.

##  <a name="put_mouseicon"></a>  CStockPropImpl::put_MouseIcon

Grafiğin (simge, bit eşlem veya meta dosyası) fareyi denetimin üzerine getirildiğinde gösterilecek resmi özelliklerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parametreler

*pPicture*  
Grafik resim özellikleri için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_mousepointer"></a>  CStockPropImpl::put_MousePointer

Fare işaretçisi Fare denetimin üzerine örneğin olduğunda görüntülenir, oku, geçici ya da kum saati türünü ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```

### <a name="parameters"></a>Parametreler

*nMousePointer*  
Fare işaretçisi türü.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_picture"></a>  CStockPropImpl::put_Picture

Bir grafiği (simge, bit eşlem veya meta dosyası) görüntülenecek resim özelliklerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parametreler

*pPicture*  
Resmin özellikleri için bir işaretçi. Bkz: [IPictureDisp](https://msdn.microsoft.com/library/windows/desktop/ms680762) daha fazla ayrıntı için.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_readystate"></a>  CStockPropImpl::put_ReadyState

Denetimin hazır duruma ayarlamak için bu yöntem, örneğin, yükleme veya yüklü çağırın.

```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```

### <a name="parameters"></a>Parametreler

*nReadyState*  
Denetimin hazır durumda.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_tabstop"></a>  CStockPropImpl::put_TabStop

Denetimin sekme durağı olup olmadığını gösteren bayrak ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```

### <a name="parameters"></a>Parametreler

*bTabStop*  
Denetimin sekme durağı ise TRUE.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_text"></a>  CStockPropImpl::put_Text

Denetim ile görüntülenen metni ayarlama için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```

### <a name="parameters"></a>Parametreler

*bstrText*  
Denetim ile görüntülenen metin.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_valid"></a>  CStockPropImpl::putvalid

Denetim geçerli olup olmadığını gösteren bayrak ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```

### <a name="parameters"></a>Parametreler

*bValid*  
Denetim geçerli ise TRUE.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="put_window"></a>  CStockPropImpl::put_Window

Bu yöntemin çağırdığı [CStockPropImpl::put_HWND](#put_hwnd), E_FAIL döndürür.

```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```

### <a name="parameters"></a>Parametreler

*hWnd*  
Pencere tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

E_FAIL döndürür.

### <a name="remarks"></a>Açıklamalar

Pencere tanıtıcısı salt okunur bir değerdir.

##  <a name="putref_font"></a>  CStockPropImpl::putref_Font

Başvuru sayısı ile denetim yazı tipi özelliklerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*  
Denetim yazı tipi özellikleri için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Aynı [CStockPropImpl::put_Font](#put_font), ancak bir başvuru sayısı.

##  <a name="putref_mouseicon"></a>  CStockPropImpl::putref_MouseIcon

Bir başvuru sayısı ile grafik (simge, bit eşlem ya da meta dosyası) Fare denetimin üzerine geldiğinde görüntülenen resmi özelliklerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parametreler

*pPicture*  
Grafik resim özellikleri için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Aynı [CStockPropImpl::put_MouseIcon](#put_mouseicon), ancak bir başvuru sayısı.

##  <a name="putref_picture"></a>  CStockPropImpl::putref_Picture

Bir başvuru sayısı ile grafik (simge, bit eşlem veya meta dosyası) görüntülenecek resim özelliklerini ayarlamak için bu yöntemi çağırın.

```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parametreler

*pPicture*  
Resmin özellikleri için bir işaretçi. Bkz: [IPictureDisp](https://msdn.microsoft.com/library/windows/desktop/ms680762) daha fazla ayrıntı için.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Aynı [CStockPropImpl::put_Picture](#put_picture), ancak bir başvuru sayısı.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)   
[IDispatchImpl Sınıfı](../../atl/reference/idispatchimpl-class.md)
