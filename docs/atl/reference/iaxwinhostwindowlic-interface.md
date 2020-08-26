---
title: Iaxwinhostwindowlik arabirimi
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
ms.openlocfilehash: 55a96e27e58d844ec6fabec689dc2aedf536a9a7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835460"
---
# <a name="iaxwinhostwindowlic-interface"></a>Iaxwinhostwindowlik arabirimi

Bu arabirim, lisanslı bir denetimi ve onun konak nesnesini yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Syntax

```
interface IAxWinHostWindowLic : IAxWinHostWindow
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|-|-|
|[Createcontrollik](#createcontrollic)|Lisanslı bir denetim oluşturur ve onu ana bilgisayar nesnesine ekler.|
|[CreateControlLicEx](#createcontrollicex)|Lisanslı bir denetim oluşturur, onu ana bilgisayar nesnesine ekler ve isteğe bağlı olarak bir olay işleyicisi ayarlar.|

## <a name="remarks"></a>Açıklamalar

`IAxWinHostWindowLic`[IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) 'dan devralır ve lisanslı denetimlerin oluşturulmasını destekleyen yöntemler ekler.

Bu arabirimin üyelerini kullanan bir örnek için bkz. [atl AXHost kullanılarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) .

## <a name="requirements"></a>Gereksinimler

Bu arabirimin tanımı aşağıda gösterildiği gibi IDL veya C++ olarak kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|IDL|Atlıyüz. IDL|
|C++|Atlıyüz. h (ATLBase. h 'ye de dahildir)|

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a> Iaxwinhostwindowlik:: Createcontrollik

Lisanslı bir denetim oluşturur, onu başlatır ve tarafından tanımlanan pencerede barındırır `hWnd` .

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

Kalan parametrelerin ve dönüş değerinin açıklaması için bkz. [IAxWinHostWindow:: CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) .

Bu yöntemi çağırmak [ıaxwinhostwindowlik:: CreateControlLicEx](#createcontrollicex) çağırma ile eşdeğerdir

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) `IAxWinHostWindowLic::CreateControlLic` .

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a> Iaxwinhostwindowlik:: CreateControlLicEx

Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede, [IAxWinHostWindow:: CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol)öğesine benzer şekilde barındırır.

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

Kalan parametrelerin ve dönüş değerinin açıklaması için bkz. [IAxWinHostWindow:: CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) .

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) `IAxWinHostWindowLic::CreateControlLicEx` .
