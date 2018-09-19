---
title: Iaxwinhostwindowlic arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c6b2537f4a4c7ba92a87bfeff2765c3c5e1b274
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088715"
---
# <a name="iaxwinhostwindowlic-interface"></a>Iaxwinhostwindowlic arabirimi

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

