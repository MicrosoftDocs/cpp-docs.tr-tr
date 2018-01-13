---
title: "CWinTraits sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
dev_langs: C++
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5c5e71f969f86aee419a0ff9d3701f4d43be5c32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cwintraits-class"></a>CWinTraits sınıfı
Bu sınıf bir pencere nesnesi oluşturulurken kullanılan stiller Standartlaştırma için bir yöntem sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```  
  
#### <a name="parameters"></a>Parametreler  
 `t_dwStyle`  
 Varsayılan standart pencere stilleri.  
  
 `t_dwExStyle`  
 Genişletilmiş pencere stilleri varsayılan.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(Statik) Genişletilmiş stillerini alır `CWinTraits` nesnesi.|  
|[CWinTraits::GetWndStyle](#getwndstyle)|(Statik) Standart stillerini alır `CWinTraits` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu [penceresi nitelikler](../../atl/understanding-window-traits.md) sınıfı, bir ATL pencere nesnesi oluşturmak için kullanılan stiller Standartlaştırma için basit bir yöntem sağlar. Bir şablon parametresi olarak bu sınıfın bir uzmanlık kullanmak [CWindowImpl](../../atl/reference/cwindowimpl-class.md) veya başka bir ATL'ın pencere sınıfları için kullanılan varsayılan standart ve genişletilmiş stilleri belirtmek için bu pencere sınıfı örneği.  
  
 Diğer bir stilleri çağrısında belirtildiğinde, kullanılacak pencere stilleri varsayılan sağlamak istediğinizde bu şablonu kullanmak [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create).  
  
 ATL pencere stilleri yaygın olarak kullanılan bir kombinasyonu için bu şablonun üç önceden tanımlanmış özelleştirmeleri sağlar:  
  
 `CControlWinTraits`  
 Standart denetimi penceresi için tasarlanmıştır. Aşağıdaki standart stilleri kullanılır: **WS_CHILD**, **ws_vısıble**, **ws_clıpchıldren**, ve **ws_clıpsıblıngs**. Hiçbir genişletilmiş stili vardır.  
  
 `CFrameWinTraits`  
 Bir standart çerçeve penceresi için tasarlanmıştır. Kullanılan standart stilleri içerir: **ws_overlappedwındow**, **ws_clıpchıldren**, ve **ws_clıpsıblıngs**. Kullanılan genişletilmiş stilleri içerir: **ws_ex_appwındow** ve **ws_ex_wındowedge**.  
  
 `CMDIChildWinTraits`  
 Standart MDI alt pencere için tasarlanmıştır. Kullanılan standart stilleri içerir: **ws_overlappedwındow**, **WS_CHILD**, **ws_vısıble**, **ws_clıpchıldren**ve **Ws_clıpsıblıngs**. Kullanılan genişletilmiş stilleri içerir: **ws_ex_mdıchıld**.  
  
 Bir örnek başına temelinde ayarlamak için diğer stilleri sorgulamasına sırasında penceresi sınıfın tüm örnekleri kullanmak için belirli stilleri ayarlandığından emin olmak istiyorsanız [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) yerine.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="getwndstyle"></a>CWinTraits::GetWndStyle  
 Standart stillerini almak için bu işlevi çağırmak `CWinTraits` nesnesi.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Bir pencere oluşturma için kullanılan standart stilleri. Varsa `dwStyle` şablonu stili değerlerini 0'dır ( `t_dwStyle`) döndürülür. Varsa `dwStyle` sıfır olmayan, olan `dwStyle` döndürülür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesnenin standart pencere stilleri.  
  
##  <a name="getwndexstyle"></a>CWinTraits::GetWndExStyle  
 Genişletilmiş stillerini almak için bu işlevi çağırmak `CWinTraits` nesnesi.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwExStyle`  
 Bir pencere oluşturma için kullanılan genişletilmiş stilleri. Varsa `dwExStyle` şablonu stili değerlerini 0'dır ( `t_dwExStyle`) döndürülür. Varsa `dwExStyle` sıfır olmayan, olan `dwExStyle` döndürülür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Genişletilmiş pencere stilleri nesnesinin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıf üyeleri](http://msdn.microsoft.com/en-us/dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Pencere Özelliklerini Anlama](../../atl/understanding-window-traits.md)
