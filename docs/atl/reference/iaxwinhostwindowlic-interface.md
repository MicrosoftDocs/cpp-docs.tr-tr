---
title: IAxWinHostWindowLic arabirimi | Microsoft Docs
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
ms.openlocfilehash: 41b4d7891d1bb00f4ee689477d1056dbf2bf28cf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362846"
---
# <a name="iaxwinhostwindowlic-interface"></a>IAxWinHostWindowLic arabirimi
Bu arabirim lisanslı denetim ve konak nesnesi düzenleme için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
interface IAxWinHostWindowLic : IAxWinHostWindow
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CreateControlLic](#createcontrollic)|Lisanslı bir denetimi oluşturur ve ana bilgisayar nesnesine ekler.|  
|[CreateControlLicEx](#createcontrollicex)|Lisanslı denetim oluşturur, ana bilgisayar nesnesine ekler ve isteğe bağlı olarak bir olay işleyicisini ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IAxWinHostWindowLic` öğesinden devralınan [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) ve lisanslı denetimler oluşturmayı destekleyen yöntemler ekler.  
  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bu arabirim üyelerini kullanan bir örnek için.  
  
## <a name="requirements"></a>Gereksinimler  
 Bu arabirim tanımı aşağıda gösterildiği gibi IDL ya da C++, kullanılabilir.  
  
|Tanım türü|Dosya|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h içinde de dahil)|  
  
##  <a name="createcontrollic"></a>  IAxWinHostWindowLic::CreateControlLic  
 Lisanslı denetim oluşturur, bunu başlatır ve tarafından tanımlanan penceresinde barındıran `hWnd`.  
  
```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>Parametreler  
 `bstrLic`  
 [in] Denetim için lisans anahtarı içeren BSTR.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) kalan parametreler ve dönüş değeri açıklaması.  
  
 Bu yöntemin çağrılması için arama eşdeğer [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)  
  
### <a name="example"></a>Örnek  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `IAxWinHostWindowLic::CreateControlLic`.  
  
##  <a name="createcontrollicex"></a>  IAxWinHostWindowLic::CreateControlLicEx  
 Lisanslı bir ActiveX denetimi oluşturur, bunu başlatır ve benzer belirtilen penceresinde barındıran [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol).  
  
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
 `bstrLic`  
 [in] Denetim için lisans anahtarı içeren BSTR.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IAxWinHostWindow::CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) kalan parametreler ve dönüş değeri açıklaması.  
  
### <a name="example"></a>Örnek  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `IAxWinHostWindowLic::CreateControlLicEx`.









