---
title: IDocHostUIHandlerDispatch arabirimi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
dev_langs:
- C++
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fbd91deb1d80c49dd403e8e08cc50f5fd8c8ec3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="idochostuihandlerdispatch-interface"></a>IDocHostUIHandlerDispatch arabirimi
Microsoft HTML Ayrıştırma ve işleme altyapısı için bir arabirim.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
interface IDocHostUIHandlerDispatch : IDispatch
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
> [!NOTE]
>  Aşağıdaki tabloda üyeleri için INet SDK başvuru konularına bağlantılardır [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx) arabirimi. `IDocHostUIHandlerDispatch`aynı işlevselliğe sahip **IDocUIHostHandler**, olması fark `IDocHostUIHandlerDispatch` ancak bir görüntüleme arabirimi olan **IDocUIHostHandler** özel bir arabirimdir.  
  
|||  
|-|-|  
|[EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)|MSHTML uygulamadan diğerine adlı [IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115). MSHTML kalıcı UI görüntülediğinde olarak da bilinir.|  
|[FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)|Konaktaki MSHTML'ın veri nesnesi değiştirmek konak izin vermek için MSHTML tarafından çağrılır.|  
|[GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)|Bırakma hedefi olarak alternatif sağlamak konak izin vermek için kullanılan MSHTML tarafından çağrılır [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)|Ana bilgisayarın IDispatch arabirimi sağlamak için MSHTML tarafından çağrılır.|  
|[GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)|MSHTML konak UI özelliklerini alır.|  
|[GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)|Kullanıcı tercihleri altında MSHTML depolar kayıt defteri anahtarını döndürür.|  
|[HideUI](https://msdn.microsoft.com/library/aa753259.aspx)|Menüleri ve araç çubuklarını MSHTML kaldırır çağrılır.|  
|[OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)|MSHTML uygulamadan diğerine adlı [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281).|  
|[OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)|MSHTML uygulamadan diğerine adlı [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969).|  
|[ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx)|MSHTML uygulamadan diğerine adlı [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053).|  
|[ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)|Bir bağlam menüsü görüntüleme MSHTML çağrılır.|  
|[ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)|Ana bilgisayarın MSHTML menüleri ve araç çubuklarını Değiştir izin verir.|  
|[TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)|Tarafından MSHTML adlı zaman [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) veya [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) olarak adlandırılır.|  
|[TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)|Konak yüklenecek URL'sini değiştirmek bir fırsat izin vermek için MSHTML tarafından çağrılır.|  
|[UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx)|Komut durumu değişti konak bildirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir konak menüleri, araç çubukları ve bu arabirim uygulayarak Microsoft HTML Ayrıştırma ve işleme altyapısı (MSHTML) tarafından kullanılan bağlam menülerini değiştirebilirsiniz.  
  
## <a name="requirements"></a>Gereksinimler  
 Bu arabirim tanımı aşağıda gösterildiği gibi IDL ya da C++, kullanılabilir.  
  
|Tanım türü|Dosya|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h içinde de dahil)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx)









