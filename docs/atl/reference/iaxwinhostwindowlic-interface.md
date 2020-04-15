---
title: IAxWinHostWindowLic Arabirimi
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
ms.openlocfilehash: 561a65702f1d4f57b4db1afc75769ce4cc523c1c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329919"
---
# <a name="iaxwinhostwindowlic-interface"></a>IAxWinHostWindowLic Arabirimi

Bu arabirim, lisanslı denetimi ve ana bilgisayar nesnesini işlemek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
interface IAxWinHostWindowLic : IAxWinHostWindow
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CreateControllic](#createcontrollic)|Lisanslı bir denetim oluşturur ve ana bilgisayar nesnesine bağlar.|
|[CreateControllicex](#createcontrollicex)|Lisanslı bir denetim oluşturur, ana bilgisayar nesnesine bağlar ve isteğe bağlı olarak bir olay işleyicisi oluşturur.|

## <a name="remarks"></a>Açıklamalar

`IAxWinHostWindowLic`[IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) devralır ve lisanslı denetimlerin oluşturulmasını destekleyen yöntemler ekler.

Bu arabirimin üyelerini kullanan bir örnek için [ATL AXHost kullanarak ActiveX Denetimleri Barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bölümüne bakın.

## <a name="requirements"></a>Gereksinimler

Bu arabirimin tanımı aşağıda gösterildiği gibi IDL veya C++ olarak kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|ıdl|ATLIFace.idl|
|C++|ATLIFace.h (Ayrıca ATLBase.h dahil)|

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

Bkz. [IAxWinHostWindow::Kalan](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) parametrelerin ve iade değerinin açıklaması için Denetim Oluştur.

Bu yöntemi arama [iAxWinHostWindowLic arama eşdeğerdir::CreateControlLicEx](#createcontrollicex)

### <a name="example"></a>Örnek

Kullanan `IAxWinHostWindowLic::CreateControlLic`bir örnek için [ATL AXHost kullanarak ActiveX Denetimleri Barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bakın.

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a>IAxWinHostWindowLic:CreateControlLicEx

Lisanslı activex denetimi oluşturur, başlatılmasını sağlar ve [iAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol)benzer belirtilen pencerede barındırır::CreateControl .

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

Bkz. [IAxWinHostWindow::Kalan](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) parametrelerin ve iade değerinin açıklaması için CreateControlEx.

### <a name="example"></a>Örnek

Kullanan `IAxWinHostWindowLic::CreateControlLicEx`bir örnek için [ATL AXHost kullanarak ActiveX Denetimleri Barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bakın.
