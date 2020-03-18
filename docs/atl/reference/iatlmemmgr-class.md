---
title: IAtlMemMgr sınıfı
ms.date: 11/04/2016
f1_keywords:
- IAtlMemMgr
- ATLMEM/ATL::IAtlMemMgr
- ATLMEM/ATL::Allocate
- ATLMEM/ATL::Free
- ATLMEM/ATL::GetSize
- ATLMEM/ATL::Reallocate
helpviewer_keywords:
- IAtlMemMgr class
- memory, managing
- memory, memory manager
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
ms.openlocfilehash: a0d79ae95a0604ca75f03673873e99394a1bc295
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417658"
---
# <a name="iatlmemmgr-class"></a>IAtlMemMgr sınıfı

Bu sınıf, bir bellek yöneticisinin arabirimini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Allocate](#allocate)|Bellek bloğunu ayırmak için bu yöntemi çağırın.|
|[Ücretsiz](#free)|Bellek bloğunu boşaltmak için bu yöntemi çağırın.|
|[GetSize](#getsize)|Ayrılmış bir bellek bloğunun boyutunu almak için bu yöntemi çağırın.|
|[Maddelerini](#reallocate)|Bir bellek bloğunu yeniden ayırmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, [CComHeap](../../atl/reference/ccomheap-class.md), [CCRTHeap](../../atl/reference/ccrtheap-class.md), [CLocalHeap](../../atl/reference/clocalheap-class.md), [CGlobalHeap](../../atl/reference/cglobalheap-class.md)veya [CWin32Heap](../../atl/reference/cwin32heap-class.md)tarafından uygulanır.

> [!NOTE]
>  Yerel ve genel yığın işlevleri diğer bellek yönetimi işlevlerinden daha yavaştır ve birçok özellik sağlamaz. Bu nedenle, yeni uygulamalar [yığın işlevlerini](/windows/win32/Memory/heap-functions)kullanmalıdır. Bunlar [CWin32Heap](../../atl/reference/cwin32heap-class.md) sınıfında mevcuttur.

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlmem. h

##  <a name="allocate"></a>IAtlMemMgr:: allocate

Bellek bloğunu ayırmak için bu yöntemi çağırın.

```
void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Yeni bellek bloğunda istenen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğunun başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tarafından ayrılan belleği serbest bırakmak için [IAtlMemMgr:: Free](#free) veya [IAtlMemMgr:: yeniden tahsis](#reallocate) çağrısı yapın.

### <a name="example"></a>Örnek

Bir örnek için bkz. [IAtlMemMgr genel bakış](../../atl/reference/iatlmemmgr-class.md).

##  <a name="free"></a>IAtlMemMgr:: Free

Bellek bloğunu boşaltmak için bu yöntemi çağırın.

```
void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Bu bellek Yöneticisi tarafından daha önce ayrılan bellek işaretçisi.

### <a name="remarks"></a>Açıklamalar

[IAtlMemMgr:: allocate](#allocate) veya [IAtlMemMgr::](#reallocate)ayırmayı elde eden belleği boşaltmak için bu yöntemi kullanın.

### <a name="example"></a>Örnek

Bir örnek için bkz. [IAtlMemMgr genel bakış](../../atl/reference/iatlmemmgr-class.md).

##  <a name="getsize"></a>IAtlMemMgr:: GetSize

Ayrılmış bir bellek bloğunun boyutunu almak için bu yöntemi çağırın.

```
size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Bu bellek Yöneticisi tarafından daha önce ayrılan bellek işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Bayt cinsinden bellek bloğunun boyutunu döndürür.

### <a name="example"></a>Örnek

Bir örnek için bkz. [IAtlMemMgr genel bakış](../../atl/reference/iatlmemmgr-class.md).

##  <a name="reallocate"></a>IAtlMemMgr:: yeniden tahsis

Bu bellek Yöneticisi tarafından ayrılan belleği yeniden ayırmak için bu yöntemi çağırın.

```
void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Bu bellek Yöneticisi tarafından daha önce ayrılan bellek işaretçisi.

*nBytes*<br/>
Yeni bellek bloğunda istenen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğunun başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tarafından ayrılan belleği serbest bırakmak için [IAtlMemMgr:: Free](#free) veya [IAtlMemMgr:: yeniden tahsis](#reallocate) çağrısı yapın.

Kavramsal olarak bu yöntem mevcut belleği serbest bırakır ve yeni bir bellek bloğu ayırır. Gerçekte, mevcut bellek genişletilebilir veya başka bir şekilde yeniden kullanılabilir.

### <a name="example"></a>Örnek

Bir örnek için bkz. [IAtlMemMgr genel bakış](../../atl/reference/iatlmemmgr-class.md).

##  <a name="get_allowcontextmenu"></a>IAxWinAmbientDispatch:: get_AllowContextMenu

`AllowContextMenu` özelliği barındırılan denetimin kendi bağlam menüsünü görüntülemesine izin verilip verilmeyeceğini belirtir.

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

##  <a name="get_allowshowui"></a>IAxWinAmbientDispatch:: get_AllowShowUI

`AllowShowUI` özelliği barındırılan denetimin kendi Kullanıcı arabirimini görüntülemesine izin verilip verilmeyeceğini belirtir.

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

##  <a name="get_allowwindowlessactivation"></a>IAxWinAmbientDispatch:: get_AllowWindowlessActivation

`AllowWindowlessActivation` özelliği, kapsayıcının penceresiz etkinleştirmeye izin verip vermeyeceğini belirtir.

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

##  <a name="get_backcolor"></a>IAxWinAmbientDispatch:: get_BackColor

`BackColor` özelliği, kapsayıcının çevresel arka plan rengini belirtir.

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

##  <a name="get_displayasdefault"></a>IAxWinAmbientDispatch:: get_DisplayAsDefault

`DisplayAsDefault`, denetimin varsayılan denetim olup olmadığını bulmasına izin veren bir çevresel özelliktir.

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

##  <a name="get_dochostdoubleclickflags"></a>IAxWinAmbientDispatch:: get_DocHostDoubleClickFlags

`DocHostDoubleClickFlags` özelliği, Çift tıklamayla yanıt olarak gerçekleşmesi gereken işlemi belirtir.

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

##  <a name="get_dochostflags"></a>IAxWinAmbientDispatch:: get_DocHostFlags

`DocHostFlags` özelliği, ana bilgisayar nesnesinin kullanıcı arabirimi yeteneklerini belirtir.

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

##  <a name="get_font"></a>IAxWinAmbientDispatch:: get_Font

`Font` özelliği, kapsayıcının çevresel yazı tipini belirtir.

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
dışı Bu özelliğin geçerli değerini almak için kullanılan bir `IFontDisp` arabirimi işaretçisinin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

ATL ana bilgisayar nesne uygulamasının varsayılan GUI yazı tipini veya sistem yazı tipini bu özelliğin varsayılan değeri olarak kullanır.

##  <a name="get_forecolor"></a>IAxWinAmbientDispatch:: get_ForeColor

`ForeColor` özelliği, kapsayıcının çevresel ön plan rengini belirtir.

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

##  <a name="get_localeid"></a>IAxWinAmbientDispatch:: get_LocaleID

`LocaleID` özelliği kapsayıcının çevresel yerel KIMLIĞINI belirtir.

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

##  <a name="get_messagereflect"></a>IAxWinAmbientDispatch:: get_MessageReflect

`MessageReflect` Ambient özelliği, kapsayıcının iletileri barındırılan denetime yansıtmayacağını belirtir.

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

##  <a name="get_optionkeypath"></a>IAxWinAmbientDispatch:: get_OptionKeyPath

`OptionKeyPath` özelliği, Kullanıcı ayarlarının kayıt defteri anahtarı yolunu belirtir.

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>Parametreler

*pbstrOptionKeyPath*<br/>
dışı Bu özelliğin geçerli değerini alacak bir değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="get_showgrabhandles"></a>IAxWinAmbientDispatch:: get_ShowGrabHandles

`ShowGrabHandles` Ambient özelliği, denetimin kendisini alma tutamaçlarla çizmesi gerekip gerekmediğini bulmasına olanak tanır.

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

##  <a name="get_showhatching"></a>IAxWinAmbientDispatch:: get_ShowHatching

`ShowHatching` Ambient özelliği, denetimin kendisini taralı olarak çizmesi gerekip gerekmediğini bulmasına olanak tanır.

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

##  <a name="get_usermode"></a>IAxWinAmbientDispatch:: get_UserMode

`UserMode` özelliği, kapsayıcının çevresel Kullanıcı modunu belirtir.

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

##  <a name="put_allowcontextmenu"></a>IAxWinAmbientDispatch::p ut_AllowContextMenu

`AllowContextMenu` özelliği barındırılan denetimin kendi bağlam menüsünü görüntülemesine izin verilip verilmeyeceğini belirtir.

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

##  <a name="put_allowshowui"></a>IAxWinAmbientDispatch::p ut_AllowShowUI

`AllowShowUI` özelliği barındırılan denetimin kendi Kullanıcı arabirimini görüntülemesine izin verilip verilmeyeceğini belirtir.

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

##  <a name="put_allowwindowlessactivation"></a>IAxWinAmbientDispatch::p ut_AllowWindowlessActivation

`AllowWindowlessActivation` özelliği, kapsayıcının penceresiz etkinleştirmeye izin verip vermeyeceğini belirtir.

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

##  <a name="put_backcolor"></a>IAxWinAmbientDispatch::p ut_BackColor

`BackColor` özelliği, kapsayıcının çevresel arka plan rengini belirtir.

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

##  <a name="put_displayasdefault"></a>IAxWinAmbientDispatch::p ut_DisplayAsDefault

`DisplayAsDefault`, denetimin varsayılan denetim olup olmadığını bulmasına izin veren bir çevresel özelliktir.

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

##  <a name="put_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::p ut_DocHostDoubleClickFlags

`DocHostDoubleClickFlags` özelliği, Çift tıklamayla yanıt olarak gerçekleşmesi gereken işlemi belirtir.

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

##  <a name="put_dochostflags"></a>IAxWinAmbientDispatch::p ut_DocHostFlags

`DocHostFlags` özelliği, ana bilgisayar nesnesinin kullanıcı arabirimi yeteneklerini belirtir.

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

##  <a name="put_font"></a>IAxWinAmbientDispatch::p ut_Font

`Font` özelliği, kapsayıcının çevresel yazı tipini belirtir.

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

##  <a name="put_forecolor"></a>IAxWinAmbientDispatch::p ut_ForeColor

`ForeColor` özelliği, kapsayıcının çevresel ön plan rengini belirtir.

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

##  <a name="put_localeid"></a>IAxWinAmbientDispatch::p ut_LocaleID

`LocaleID` özelliği kapsayıcının çevresel yerel KIMLIĞINI belirtir.

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

##  <a name="put_messagereflect"></a>IAxWinAmbientDispatch::p ut_MessageReflect

`MessageReflect` Ambient özelliği, kapsayıcının iletileri barındırılan denetime yansıtmayacağını belirtir.

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

##  <a name="put_optionkeypath"></a>IAxWinAmbientDispatch::p ut_OptionKeyPath

`OptionKeyPath` özelliği, Kullanıcı ayarlarının kayıt defteri anahtarı yolunu belirtir.

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>Parametreler

*bstrOptionKeyPath*<br/>
'ndaki Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="put_usermode"></a>IAxWinAmbientDispatch::p ut_UserMode

`UserMode` özelliği, kapsayıcının çevresel Kullanıcı modunu belirtir.

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

##  <a name="setambientdispatch"></a>IAxWinAmbientDispatchEx:: Setambentdispatch

Bu yöntem, Kullanıcı tanımlı bir arabirimle varsayılan çevresel Özellik arabirimini tamamlamak için çağrılır.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Parametreler

*pDispatch*<br/>
Yeni arabirime yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

`SetAmbientDispatch` yeni bir arabirim işaretçisi ile çağrıldığında bu yeni arabirim, barındırılan denetim tarafından istenen özellikleri veya yöntemleri çağırmak için kullanılır. bu özellikler zaten [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)tarafından sağlanmadıysa.

##  <a name="attachcontrol"></a>IAxWinHostWindow:: AttachControl

*HWND*tarafından tanımlanan pencereyi kullanarak, mevcut (ve daha önce başlatılmış) bir denetimi ana bilgisayar nesnesine iliştirir.

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*pUnkControl*<br/>
'ndaki Ana bilgisayar nesnesine eklenecek denetimin `IUnknown` arabirimine yönelik bir işaretçi.

*lendiği*<br/>
'ndaki Barındırma için kullanılacak pencereye yönelik bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="createcontrol"></a>IAxWinHostWindow:: CreateControl

Bir denetim oluşturur, onu başlatır ve *HWND*tarafından tanımlanan pencerede barındırır.

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*Lplarincesdata*<br/>
'ndaki Oluşturulacak denetimi tanımlayan bir dize. Bir CLSID (küme ayraçları içermesi gerekir), ProgID, URL veya ham HTML (ön ek olarak **MSHTML:** ) olabilir.

*lendiği*<br/>
'ndaki Barındırma için kullanılacak pencereye yönelik bir tanıtıcı.

*pStream*<br/>
'ndaki Denetim için başlatma verilerini içeren bir akış için arabirim işaretçisi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu pencere, iletilerin denetime yansıtılabilmesi ve diğer kapsayıcı özelliklerinin çalışması için bu arabirimi kullanıma sunan konak nesnesi tarafından alt sınıflandırılacak.

Bu yöntemi çağırmak, [IAxWinHostWindow:: CreateControlEx](#createcontrolex)çağırma ile eşdeğerdir.

Lisanslı bir ActiveX denetimi oluşturmak için, bkz. [ıaxwinhostwindowlik:: Createcontrollik](#createcontrollicex).

##  <a name="createcontrolex"></a>IAxWinHostWindow:: CreateControlEx

Bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede, [IAxWinHostWindow:: CreateControl](#createcontrol)öğesine benzer şekilde barındırır.

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

*Lplarincesdata*<br/>
'ndaki Oluşturulacak denetimi tanımlayan bir dize. Bir CLSID (küme ayraçları içermesi gerekir), ProgID, URL veya ham HTML (ön ek olarak **MSHTML:** ) olabilir.

*lendiği*<br/>
'ndaki Barındırma için kullanılacak pencereye yönelik bir tanıtıcı.

*pStream*<br/>
'ndaki Denetim için başlatma verilerini içeren bir akış için arabirim işaretçisi. NULL olabilir.

*ppUnk*<br/>
dışı Oluşturulan denetimin `IUnknown` arabirimini alacak bir işaretçinin adresi. NULL olabilir.

*Riidadmenlik*<br/>
'ndaki Kapsanan nesnedeki bir giden arabirimin arabirim tanımlayıcısı. IID_NULL olabilir.

*punkAdvise*<br/>
'ndaki `iidSink`tarafından belirtilen kapsanan nesnedeki bağlantı noktasına bağlanacak havuz nesnesinin `IUnknown` arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`CreateControl` yönteminden farklı olarak, `CreateControlEx` yeni oluşturulan denetime bir arabirim işaretçisi almanıza ve denetim tarafından tetiklenen olayları almak için bir olay havuzu ayarlamanıza olanak sağlar.

Lisanslı bir ActiveX denetimi oluşturmak için, bkz. [ıaxwinhostwindowlik:: CreateControlLicEx](#createcontrollicex).

##  <a name="querycontrol"></a>IAxWinHostWindow:: QueryControl

Barındırılan denetim tarafından sunulan belirtilen arabirim işaretçisini döndürür.

```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*riıd*<br/>
'ndaki İstenen denetimdeki bir arabirimin KIMLIĞI.

*ppvObject*<br/>
dışı Oluşturulan denetimin belirtilen arabirimini alacak bir işaretçinin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="setexternaldispatch"></a>IAxWinHostWindow:: SetExternalDispatch

[Idochostuihandlerdispatch:: GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) yöntemi aracılığıyla içerilen denetimler için kullanılabilen dış dispınterface 'i ayarlar.

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
'ndaki `IDispatch` arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="setexternaluihandler"></a>IAxWinHostWindow:: Setexternaluıhandler

`CAxWindow` nesnesi için dış [ıdochostuihandlerdispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) arabirimini ayarlamak için bu işlevi çağırın.

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
'ndaki `IDocHostUIHandlerDispatch` arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `IDocHostUIHandlerDispatch` arabirimi için konağın sitesini sorgulayan denetimler (Web tarayıcısı denetimi gibi) tarafından kullanılır.

##  <a name="createcontrollic"></a>Iaxwinhostwindowlik:: Createcontrollik

Lisanslı bir denetim oluşturur, onu başlatır ve `hWnd`tarafından tanımlanan pencerede barındırır.

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>Parametreler

*Bstrlik*<br/>
'ndaki Denetim için lisans anahtarını içeren BSTR.

### <a name="remarks"></a>Açıklamalar

Kalan parametrelerin ve dönüş değerinin açıklaması için bkz. [IAxWinHostWindow:: CreateControl](#createcontrol) .

Bu yöntemi çağırmak [ıaxwinhostwindowlik:: CreateControlLicEx](#createcontrollicex) çağırma ile eşdeğerdir

### <a name="example"></a>Örnek

`IAxWinHostWindowLic::CreateControlLic`kullanan bir örnek için [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bölümüne bakın.

##  <a name="createcontrollicex"></a>Iaxwinhostwindowlik:: CreateControlLicEx

Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede, [IAxWinHostWindow:: CreateControl](#createcontrol)öğesine benzer şekilde barındırır.

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

*Bstrlik*<br/>
'ndaki Denetim için lisans anahtarını içeren BSTR.

### <a name="remarks"></a>Açıklamalar

Kalan parametrelerin ve dönüş değerinin açıklaması için bkz. [IAxWinHostWindow:: CreateControlEx](#createcontrolex) .

### <a name="example"></a>Örnek

`IAxWinHostWindowLic::CreateControlLicEx`kullanan bir örnek için [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
