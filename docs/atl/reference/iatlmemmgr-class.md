---
title: IAtlMemMgr Sınıfı
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
ms.openlocfilehash: fcecf716e9d865b1b8590a733216576e0da4c2fb
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746007"
---
# <a name="iatlmemmgr-class"></a>IAtlMemMgr Sınıfı

Bu sınıf, bir bellek yöneticisiiçin arabirimi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Ayırmak](#allocate)|Bellek bloğunu ayırmak için bu yöntemi çağırın.|
|[Ücretsiz](#free)|Bellek bloğunu serbest kaldırmak için bu yöntemi arayın.|
|[GetSize](#getsize)|Ayrılmış bellek bloğu boyutunu almak için bu yöntemi arayın.|
|[Yeniden tahsis](#reallocate)|Bellek bloğunu yeniden tahsis etmek için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

Bu arayüz [CComHeap,](../../atl/reference/ccomheap-class.md) [CCRTHeap,](../../atl/reference/ccrtheap-class.md) [CLocalHeap](../../atl/reference/clocalheap-class.md), [CGlobalHeap](../../atl/reference/cglobalheap-class.md), veya [CWin32Heap](../../atl/reference/cwin32heap-class.md)tarafından uygulanmaktadır.

> [!NOTE]
> Yerel ve genel yığın işlevleri diğer bellek yönetimi işlevlerinden daha yavaşve çok fazla özellik sağlamaz. Bu nedenle, yeni uygulamalar [yığın işlevleri](/windows/win32/Memory/heap-functions)ni kullanmalıdır. Bunlar [CWin32Heap](../../atl/reference/cwin32heap-class.md) sınıfında mevcuttur.

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlmem.h

## <a name="iatlmemmgrallocate"></a><a name="allocate"></a>IAtlMemMgr::Ayırma

Bellek bloğunu ayırmak için bu yöntemi çağırın.

```cpp
void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBayt*<br/>
Yeni bellek bloğunda istenen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğunun başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrı [IAtlMemMgr::Ücretsiz](#free) veya [IAtlMemMgr::Bu](#reallocate) yöntem tarafından ayrılan belleği serbest serbest etmek için yeniden bulunun.

### <a name="example"></a>Örnek

Örneğin, [IAtlMemmgr Genel Bakış'a](../../atl/reference/iatlmemmgr-class.md)bakın.

## <a name="iatlmemmgrfree"></a><a name="free"></a>IAtlMemMgr::Ücretsiz

Bellek bloğunu serbest kaldırmak için bu yöntemi arayın.

```cpp
void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Bu bellek yöneticisi tarafından daha önce tahsis edilen belleğe işaretçi.

### <a name="remarks"></a>Açıklamalar

[IAtlMemMgr](#allocate) tarafından elde edilen belleği serbest leştirmek için bu yöntemi kullanın::Ayırma veya [IAtlMemMgr::Yer tahsis .](#reallocate)

### <a name="example"></a>Örnek

Örneğin, [IAtlMemmgr Genel Bakış'a](../../atl/reference/iatlmemmgr-class.md)bakın.

## <a name="iatlmemmgrgetsize"></a><a name="getsize"></a>IAtlMemMgr::GetSize

Ayrılmış bellek bloğu boyutunu almak için bu yöntemi arayın.

```
size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Bu bellek yöneticisi tarafından daha önce tahsis edilen belleğe işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Baytlarda bellek bloğunun boyutunu döndürür.

### <a name="example"></a>Örnek

Örneğin, [IAtlMemmgr Genel Bakış'a](../../atl/reference/iatlmemmgr-class.md)bakın.

## <a name="iatlmemmgrreallocate"></a><a name="reallocate"></a>IAtlMemMgr::Yeniden tahsis

Bu bellek yöneticisi tarafından ayrılan belleği yeniden tahsis etmek için bu yöntemi arayın.

```cpp
void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Bu bellek yöneticisi tarafından daha önce tahsis edilen belleğe işaretçi.

*nBayt*<br/>
Yeni bellek bloğunda istenen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğunun başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrı [IAtlMemMgr::Ücretsiz](#free) veya [IAtlMemMgr::Bu](#reallocate) yöntem tarafından ayrılan belleği serbest serbest etmek için yeniden bulunun.

Kavramsal olarak bu yöntem varolan belleği boşaltır ve yeni bir bellek bloğu ayırır. Gerçekte, varolan bellek uzatılabilir veya başka bir şekilde yeniden kullanılabilir.

### <a name="example"></a>Örnek

Örneğin, [IAtlMemmgr Genel Bakış'a](../../atl/reference/iatlmemmgr-class.md)bakın.

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

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a>IAxWinAmbientDispatchEx::SetAmbientDispatch

Bu yöntem, varsayılan ortam özelliği arabirimini kullanıcı tanımlı bir arabirimle tamamlamak için çağrılır.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Parametreler

*pDispatch*<br/>
Yeni arabirimi işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Yeni `SetAmbientDispatch` bir arabirim için bir işaretçi ile çağrıldığında, bu yeni arabirim barındırılan denetim tarafından istenen herhangi bir özellik veya yöntemleri çağırmak için kullanılacaktır - bu özellikleri zaten [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)tarafından sağlanmadı.

## <a name="iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a>IAxWinHostWindow::AttachControl

*hWnd*tarafından tanımlanan pencereyi kullanarak ana bilgisayar nesnesine varolan (ve daha önce başlatma) bir denetim bağlar.

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*pUnkKontrol*<br/>
[içinde] Ana bilgisayar `IUnknown` nesnesine eklenecek denetimin arabirimine işaretçi.

*Hwnd*<br/>
[içinde] Barındırma için kullanılacak pencerenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a>IAxWinHostWindow::CreateControl

Bir denetim oluşturur, başharflerini ilke landırır ve *hWnd*tarafından tanımlanan pencerede barındırışlar.

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*lpTricsData*<br/>
[içinde] Oluşturmak için denetimi tanımlayan bir dize. CLSID (ayraçları içermelidir), ProgID, URL veya ham HTML **(MSHTML**tarafından önceden belirlenmiş: ) olabilir.

*Hwnd*<br/>
[içinde] Barındırma için kullanılacak pencerenin tutamacı.

*pStream*<br/>
[içinde] Denetim için başlatma verilerini içeren bir akış için arabirim işaretçisi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu pencere, iletilerin denetime yansıtılabilmesi ve diğer kapsayıcı özelliklerinin çalışabilmesi için bu arabirimi açığa çıkaran ana bilgisayar nesnesi tarafından alt sınıflanır.

Bu yöntemi arama [iAxWinHostWindow arama eşdeğerdir::CreateControlEx](#createcontrolex).

Lisanslı activex denetimi oluşturmak için Bkz. [IAxWinHostWindowLic::CreateControlLic](#createcontrollicex).

## <a name="iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a>IAxWinHostWindow:CreateControlEx

ActiveX denetimi oluşturur, başlatılmasını sağlar ve [iAxWinHostWindow](#createcontrol)benzer belirtilen pencerede barındırır::CreateControl .

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

*lpTricsData*<br/>
[içinde] Oluşturmak için denetimi tanımlayan bir dize. CLSID (ayraçlar dahil olmalıdır), ProgID, URL veya ham HTML **(MSHTML**ile önceden belirlenmiş: ) olabilir.

*Hwnd*<br/>
[içinde] Barındırma için kullanılacak pencerenin tutamacı.

*pStream*<br/>
[içinde] Denetim için başlatma verilerini içeren bir akış için arabirim işaretçisi. NULL olabilir.

*ppUnk*<br/>
[çıkış] Oluşturulan denetimin arabirimini `IUnknown` alacak bir işaretçinin adresi. NULL olabilir.

*riidAdvise*<br/>
[içinde] İçe çıkan nesne üzerinde giden bir arabirimin arabirim tanımlayıcısı. IID_NULL olabilir.

*punkAdvise*<br/>
[içinde] Tarafından belirtilen `iidSink` `IUnknown` yer alan nesnenin bağlantı noktasına bağlanacak lavabo nesnesinin arabirimine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Yöntemin `CreateControl` aksine, `CreateControlEx` aynı zamanda yeni oluşturulan denetim için bir arabirim işaretçisi almak ve denetim tarafından ateşlenen olayları almak için bir olay lavabo kurmak sağlar.

Lisanslı activex denetimi oluşturmak için Bkz. [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex).

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a>IAxWinHostWindow::QueryControl

Barındırılan denetim tarafından sağlanan belirtilen arabirim işaretçisini döndürür.

```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
[içinde] İstenmekte olan denetimdeki arabirimin kimliği.

*ppvNesne*<br/>
[çıkış] Oluşturulan denetimin belirtilen arabirimini alacak bir işaretçinin adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>IAxWinHostWindow::SetExternalDispatch

[IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) yöntemi ile denetimleri içerebilecek harici dispinterface'i ayarlar.

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
[içinde] `IDispatch` Arabirime işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>IAxWinHostWindow::SetExternalUIHandler

Nesne için harici [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) arabirimini `CAxWindow` ayarlamak için bu işlevi arayın.

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
[içinde] `IDocHostUIHandlerDispatch` Arabirime işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `IDocHostUIHandlerDispatch` arabirim için ana bilgisayar sitesini sorgulayan denetimler (Web tarayıcıdenetimi gibi) tarafından kullanılır.

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a>IAxWinHostWindowLic::CreateControlLic

Lisanslı bir denetim oluşturur, başlatılmasını sağlar ve `hWnd`tanımlanan pencerede barındırılan.

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>Parametreler

*bstrLic*<br/>
[içinde] Denetim için lisans anahtarını içeren BSTR.

### <a name="remarks"></a>Açıklamalar

Bkz. [IAxWinHostWindow::Kalan](#createcontrol) parametrelerin ve iade değerinin açıklaması için Denetim Oluştur.

Bu yöntemi arama [iAxWinHostWindowLic arama eşdeğerdir::CreateControlLicEx](#createcontrollicex)

### <a name="example"></a>Örnek

Kullanan `IAxWinHostWindowLic::CreateControlLic`bir örnek için [ATL AXHost kullanarak ActiveX Denetimleri Barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bakın.

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a>IAxWinHostWindowLic:CreateControlLicEx

Lisanslı activex denetimi oluşturur, başlatılmasını sağlar ve [iAxWinHostWindow](#createcontrol)benzer belirtilen pencerede barındırır::CreateControl .

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

*bstrLic*<br/>
[içinde] Denetim için lisans anahtarını içeren BSTR.

### <a name="remarks"></a>Açıklamalar

Bkz. [IAxWinHostWindow::Kalan](#createcontrolex) parametrelerin ve iade değerinin açıklaması için CreateControlEx.

### <a name="example"></a>Örnek

Kullanan `IAxWinHostWindowLic::CreateControlLicEx`bir örnek için [ATL AXHost kullanarak ActiveX Denetimleri Barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
