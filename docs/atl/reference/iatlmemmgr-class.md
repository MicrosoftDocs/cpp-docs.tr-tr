---
title: Iatlmemmgr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAtlMemMgr
- ATLMEM/ATL::IAtlMemMgr
- ATLMEM/ATL::Allocate
- ATLMEM/ATL::Free
- ATLMEM/ATL::GetSize
- ATLMEM/ATL::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- IAtlMemMgr class
- memory, managing
- memory, memory manager
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c1e04bd31ca1942e5e5fa054cb4991233e2f61c
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762193"
---
# <a name="iatlmemmgr-class"></a>Iatlmemmgr sınıfı

Bu sınıf, bir bellek yöneticisi için bir arabirimi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[ayırma](#allocate)|Bir bellek bloğu ayırmak için bu yöntemi çağırın.|
|[Ücretsiz](#free)|Bir bellek bloğunu serbest bırakmak için bu yöntemi çağırın.|
|[GetSize](#getsize)|Ayrılan bellek blok boyutu almak için bu yöntemi çağırın.|
|[Yeniden ayırma](#reallocate)|Bir bellek bloğu yeniden ayırmak üzere bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim tarafından uygulanan [CComHeap](../../atl/reference/ccomheap-class.md), [CCRTHeap](../../atl/reference/ccrtheap-class.md), [CLocalHeap](../../atl/reference/clocalheap-class.md), [CGlobalHeap](../../atl/reference/cglobalheap-class.md), veya [CWin32Heap](../../atl/reference/cwin32heap-class.md).

> [!NOTE]
>  Yerel ve genel yığın işlevlerin diğer bellek yönetimi işlevleri yavaştır ve gibi birçok özelliği sağlamaz. Bu nedenle, yeni uygulamalar kullanmalıdır [yığın işlevleri](/windows/desktop/Memory/heap-functions). Bunlar, kullanılabilir [CWin32Heap](../../atl/reference/cwin32heap-class.md) sınıfı.

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlmem.h

##  <a name="allocate"></a>  IAtlMemMgr::Allocate

Bir bellek bloğu ayırmak için bu yöntemi çağırın.

```
void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*  
İstenen bayt yeni bellek bloğu sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğu başlangıcı için bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrı [IAtlMemMgr::Free](#free) veya [IAtlMemMgr::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.

### <a name="example"></a>Örnek

Bir örnek için bkz. [Iatlmemmgr genel bakış](../../atl/reference/iatlmemmgr-class.md).

##  <a name="free"></a>  IAtlMemMgr::Free

Bir bellek bloğunu serbest bırakmak için bu yöntemi çağırın.

```
void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*  
Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi.

### <a name="remarks"></a>Açıklamalar

Tarafından alınan belleği boşaltmak için bu yöntemi kullanın [IAtlMemMgr::Allocate](#allocate) veya [IAtlMemMgr::Reallocate](#reallocate).

### <a name="example"></a>Örnek

Bir örnek için bkz. [Iatlmemmgr genel bakış](../../atl/reference/iatlmemmgr-class.md).

##  <a name="getsize"></a>  IAtlMemMgr::GetSize

Ayrılan bellek blok boyutu almak için bu yöntemi çağırın.

```
size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*  
Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Bellek Blok boyutu bayt cinsinden döndürür.

### <a name="example"></a>Örnek

Bir örnek için bkz. [Iatlmemmgr genel bakış](../../atl/reference/iatlmemmgr-class.md).

##  <a name="reallocate"></a>  IAtlMemMgr::Reallocate

Bu bellek yöneticisi tarafından ayrılan bellek yeniden ayırmak üzere bu yöntemi çağırın.

```
void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*p*  
Bu bellek yöneticisi tarafından önceden ayrılan bellek işaretçisi.

*nBytes*  
İstenen bayt yeni bellek bloğu sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğu başlangıcı için bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrı [IAtlMemMgr::Free](#free) veya [IAtlMemMgr::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.

Kavramsal olarak bu yöntem, var olan belleği serbest bırakır ve yeni bir bellek bloğu ayırır. Gerçekte, mevcut bellek genişletilmiş veya olabilir yeniden Aksi takdirde.

### <a name="example"></a>Örnek

Bir örnek için bkz. [Iatlmemmgr genel bakış](../../atl/reference/iatlmemmgr-class.md).

##  <a name="get_allowcontextmenu"></a>  IAxWinAmbientDispatch::get_AllowContextMenu

`AllowContextMenu` Özelliği, bağlam menüsünü görüntülemek için denetimden izin verilip verilmeyeceğini belirtir.

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>Parametreler

*pbAllowContextMenu*  
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

*pbAllowShowUI*  
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

*pbAllowWindowless*  
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

*pclrBackground*  
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

*pbDisplayAsDefault*  
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

*pdwDocHostDoubleClickFlags*  
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

*pdwDocHostFlags*  
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

*pFont*  
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

*pclrForeground*  
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

*plcidLocaleID*  
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

*pbMessageReflect*  
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

*pbstrOptionKeyPath*  
[out] Bu özelliğin geçerli değerini almak için bir değişkenin adresidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="get_showgrabhandles"></a>  IAxWinAmbientDispatch::get_ShowGrabHandles

`ShowGrabHandles` Ortam özelliği, kendisini tutamaçların ile çizip varsa öğrenmek denetim sağlar.

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>Parametreler

*pbShowGrabHandles*  
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

*pbShowHatching*  
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

*pbUserMode*  
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

*bAllowContextMenu*  
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

*bAllowShowUI*  
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

*bAllowWindowless*  
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

*clrBackground*  
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

*bDisplayAsDefault*  
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

*dwDocHostDoubleClickFlags*  
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

*dwDocHostFlags*  
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

*pFont*  
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

*clrForeground*  
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

*lcidLocaleID*  
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

*bMessageReflect*  
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

*bstrOptionKeyPath*  
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="put_usermode"></a>  IAxWinAmbientDispatch::put_UserMode

`UserMode` Özelliği, kapsayıcının ortam kullanıcı modunu belirtir.

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>Parametreler

*bUserMode*  
[in] Bu özelliğin yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

ATL konak nesnesi uygulama VARIANT_TRUE bu özelliğin varsayılan değeri kullanır.

##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch

Bu yöntem, kullanıcı tanımlı bir arabirimi varsayılan ortam özelliği arabirimiyle desteklemek üzere çağrılır.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Parametreler

*pDispatch*  
Yeni arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Zaman `SetAmbientDispatch` çağrılır yeni bir arabirim işaretçisi ile tüm özellikler veya yöntemler için barındırılan denetim tarafından sorulan çağırmak için bu yeni arabirim kullanılacak — bu özellikler zaten tarafından sağlanmazsa [Iaxwinambientdispatch](../../atl/reference/iaxwinambientdispatch-interface.md).

##  <a name="attachcontrol"></a>  IAxWinHostWindow::AttachControl

Var olan (ve daha önce başlatılmış) bir denetim tarafından tanımlanan penceresini kullanarak konak nesnesi ekler *hWnd*.

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*pUnkControl*  
[in] Bir işaretçi `IUnknown` konak nesnesine eklenecek denetimin arabirimi.

*hWnd*  
[in] Tanıtıcı penceresine barındırmak için kullanılacak.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="createcontrol"></a>  IAxWinHostWindow::CreateControl

Bir denetimi oluşturur, onu başlatır ve tarafından tanımlanan penceresinde barındıran *hWnd*.

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*lpTricsData*  
[in] Denetimi oluşturmak için tanımlayan bir dize. (Küme ayraçları içermelidir) CLSID, program kimliği, URL veya ham HTML olabilir (önek **MSHTML:**).

*hWnd*  
[in] Tanıtıcı penceresine barındırmak için kullanılacak.

*pStream*  
[in] Denetim için başlatma verilerini içeren bir akış için bir arabirim işaretçisi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bu pencere, bu arabirim iletilerin denetimine yansıtılır ve diğer kapsayıcı özellikleri çalışır böylece gösterme konak nesnesi tarafından sınıflandırma.

Bu yöntemin çağrılması için arama eşdeğer [IAxWinHostWindow::CreateControlEx](#createcontrolex).

Lisanslı bir ActiveX denetimi oluşturmak için bkz [IAxWinHostWindowLic::CreateControlLic](#createcontrollicex).

##  <a name="createcontrolex"></a>  IAxWinHostWindow::CreateControlEx

Bir ActiveX denetimi oluşturur, onu başlatır ve benzer şekilde belirtilen pencerede barındırır [IAxWinHostWindow::CreateControl](#createcontrol).

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

*lpTricsData*  
[in] Denetimi oluşturmak için tanımlayan bir dize. (Küme ayraçları içermelidir) CLSID, program kimliği, URL veya ham HTML olabilir (ön eki **MSHTML:**).

*hWnd*  
[in] Tanıtıcı penceresine barındırmak için kullanılacak.

*pStream*  
[in] Denetim için başlatma verilerini içeren bir akış için bir arabirim işaretçisi. NULL olabilir.

*ppUnk*  
[out] Adresi alacak bir işaretçi `IUnknown` arabirimi oluşturulan denetimi. NULL olabilir.

*riidAdvise*  
[in] Kapsanan nesne üzerinde giden bir arabirim arabirimi tanımlayıcısı. IID_NULL olabilir.

*punkAdvise*  
[in] Bir işaretçi `IUnknown` arabirimi tarafından belirtilen kapsanan nesne üzerindeki bağlantı noktasına bağlı havuz nesnenin `iidSink`.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Farklı `CreateControl` yöntemi `CreateControlEx` de yeni oluşturulan denetime bir arabirim işaretçisi alır ve denetimi tarafından tetiklenen olayları almak için bir olay havuzu ayarlamanıza olanak sağlar.

Lisanslı bir ActiveX denetimi oluşturmak için bkz [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex).

##  <a name="querycontrol"></a>  IAxWinHostWindow::QueryControl

Barındırılan denetim tarafından sağlanan belirtilen arabirim işaretçisini döndürür.

```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*riid*  
[in] İstenen denetimin bir arabirim kimliği.

*ppvObject*  
[out] Oluşturulan denetimi belirtilen arabirim alacak bir işaretçi adresi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="setexternaldispatch"></a>  IAxWinHostWindow::SetExternalDispatch

Kapsanan denetimlere kullanılabilir olan dış dispinterface ayarlar [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) yöntemi.

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*  
[in] Bir işaretçi bir `IDispatch` arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="setexternaluihandler"></a>  IAxWinHostWindow::SetExternalUIHandler

Dış ayarlamak için bu işlevi çağırın [Idochostuıhandlerdispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) için arabirim `CAxWindow` nesne.

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*  
[in] Bir işaretçi bir `IDocHostUIHandlerDispatch` arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bu işlev ana bilgisayarın site için sorgu denetimler (örneğin, Web tarayıcı denetimi) tarafından kullanılan `IDocHostUIHandlerDispatch` arabirimi.

##  <a name="createcontrollic"></a>  IAxWinHostWindowLic::CreateControlLic

Lisanslı bir denetim oluşturur, onu başlatır ve tarafından tanımlanan penceresinde barındıran `hWnd`.

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>Parametreler

*bstrLic*  
[in] Denetim için lisans anahtarı içeren BSTR.

### <a name="remarks"></a>Açıklamalar

Bkz: [IAxWinHostWindow::CreateControl](#createcontrol) kalan parametreler ve dönüş değeri bir açıklaması.

Bu yöntemin çağrılması için arama eşdeğer [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)

### <a name="example"></a>Örnek

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `IAxWinHostWindowLic::CreateControlLic`.

##  <a name="createcontrollicex"></a>  IAxWinHostWindowLic::CreateControlLicEx

Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve benzer şekilde belirtilen pencerede barındırır [IAxWinHostWindow::CreateControl](#createcontrol).

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

*bstrLic*  
[in] Denetim için lisans anahtarı içeren BSTR.

### <a name="remarks"></a>Açıklamalar

Bkz: [IAxWinHostWindow::CreateControlEx](#createcontrolex) kalan parametreler ve dönüş değeri bir açıklaması.

### <a name="example"></a>Örnek

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `IAxWinHostWindowLic::CreateControlLicEx`.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
