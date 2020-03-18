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
ms.openlocfilehash: aca3970d13db53ffa04fe9582bbe9b8db78e820d
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417644"
---
# <a name="iaxwinhostwindowlic-interface"></a>Iaxwinhostwindowlik arabirimi

Bu arabirim, lisanslı bir denetimi ve onun konak nesnesini yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
interface IAxWinHostWindowLic : IAxWinHostWindow
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Createcontrollik](#createcontrollic)|Lisanslı bir denetim oluşturur ve onu ana bilgisayar nesnesine ekler.|
|[CreateControlLicEx](#createcontrollicex)|Lisanslı bir denetim oluşturur, onu ana bilgisayar nesnesine ekler ve isteğe bağlı olarak bir olay işleyicisi ayarlar.|

## <a name="remarks"></a>Açıklamalar

`IAxWinHostWindowLic` [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) 'dan devralınır ve lisanslı denetimlerin oluşturulmasını destekleyen yöntemler ekler.

Bu arabirimin üyelerini kullanan bir örnek için bkz. [atl AXHost kullanılarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) .

## <a name="requirements"></a>Gereksinimler

Bu arabirimin tanımı, aşağıda gösterildiği gibi IDL veya C++olarak kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|IDL|Atlıyüz. IDL|
|C++|Atlıyüz. h (ATLBase. h 'ye de dahildir)|

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

Kalan parametrelerin ve dönüş değerinin açıklaması için bkz. [IAxWinHostWindow:: CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) .

Bu yöntemi çağırmak [ıaxwinhostwindowlik:: CreateControlLicEx](#createcontrollicex) çağırma ile eşdeğerdir

### <a name="example"></a>Örnek

`IAxWinHostWindowLic::CreateControlLic`kullanan bir örnek için [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bölümüne bakın.

##  <a name="createcontrollicex"></a>Iaxwinhostwindowlik:: CreateControlLicEx

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

`IAxWinHostWindowLic::CreateControlLicEx`kullanan bir örnek için [atl AXHost kullanarak ActiveX denetimlerini barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bölümüne bakın.
