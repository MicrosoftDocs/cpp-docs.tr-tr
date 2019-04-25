---
title: IAxWinHostWindowLic Interface
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
ms.openlocfilehash: aca3970d13db53ffa04fe9582bbe9b8db78e820d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275996"
---
# <a name="iaxwinhostwindowlic-interface"></a>IAxWinHostWindowLic Interface

Bu arabirim, lisanslı bir denetim ve onun ana nesneyi işlemek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
interface IAxWinHostWindowLic : IAxWinHostWindow
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CreateControlLic](#createcontrollic)|Lisanslı bir denetim oluşturur ve ana bilgisayar nesnesine iliştirir.|
|[CreateControlLicEx](#createcontrollicex)|Lisanslı bir denetim oluşturur, ana bilgisayar nesnesine iliştirir ve isteğe bağlı olarak bir olay işleyicisini ayarlar.|

## <a name="remarks"></a>Açıklamalar

`IAxWinHostWindowLic` devralınan [Iaxwinhostwindow](../../atl/reference/iaxwinhostwindow-interface.md) ve lisanslı denetimler oluşturulmasını destekleyen yöntemler ekler.

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bu arabirim üyeleri kullanan bir örnek.

## <a name="requirements"></a>Gereksinimler

Bu arabirim tanımı aşağıda gösterildiği gibi IDL veya C++ olarak kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|IDL|ATLIFace.idl|
|C++|ATLIFace.h (ATLBase.h içinde de dahil)|

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

*bstrLic*<br/>
[in] Denetim için lisans anahtarı içeren BSTR.

### <a name="remarks"></a>Açıklamalar

Bkz: [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) kalan parametreler ve dönüş değeri bir açıklaması.

Bu yöntemin çağrılması için arama eşdeğer [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)

### <a name="example"></a>Örnek

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `IAxWinHostWindowLic::CreateControlLic`.

##  <a name="createcontrollicex"></a>  IAxWinHostWindowLic::CreateControlLicEx

Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve benzer şekilde belirtilen pencerede barındırır [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol).

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
[in] Denetim için lisans anahtarı içeren BSTR.

### <a name="remarks"></a>Açıklamalar

Bkz: [IAxWinHostWindow::CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) kalan parametreler ve dönüş değeri bir açıklaması.

### <a name="example"></a>Örnek

Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `IAxWinHostWindowLic::CreateControlLicEx`.
