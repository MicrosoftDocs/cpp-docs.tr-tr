---
title: "CWinTraitsOR sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
dev_langs: C++
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 14796948369b92c9137dc7e02a8399910d46997c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cwintraitsor-class"></a>CWinTraitsOR sınıfı
Bu sınıf bir pencere nesnesi oluşturulurken kullanılan stiller Standartlaştırma için bir yöntem sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0, 
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```  
  
#### <a name="parameters"></a>Parametreler  
 `t_dwStyle`  
 Varsayılan pencere stilleri.  
  
 `t_dwExStyle`  
 Genişletilmiş pencere stilleri varsayılan.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|Genişletilmiş stillerini alır `CWinTraitsOR` nesnesi.|  
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|Standart stillerini alır `CWinTraitsOR` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu [penceresi nitelikler](../../atl/understanding-window-traits.md) sınıfı, bir ATL pencere nesnesi oluşturmak için kullanılan stiller Standartlaştırma için basit bir yöntem sağlar. Bir şablon parametresi olarak bu sınıfın bir uzmanlık kullanmak [CWindowImpl](../../atl/reference/cwindowimpl-class.md) veya başka bir ATL'ın pencere sınıfları için kullanılacak standart ve genişletilmiş stilleri düşük kümesini belirtmek için bu pencereyi sınıfının örnekleri.  
  
 Bu şablon uzmanlaşması belirli stilleri penceresi sınıfın tüm örnekleri için diğer stilleri izin veren çağrısında örneği başına temelinde ayarlamak için ayarlandığından emin olun istiyorsanız kullanın [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create).  
  
 Diğer bir stilleri çağrısında belirtildiğinde, kullanılacak pencere stilleri varsayılan sağlamak istiyorsanız `CWindowImpl::Create`, kullanın [CWinTraits](../../atl/reference/cwintraits-class.md) yerine.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="getwndstyle"></a>CWinTraitsOR::GetWndStyle  
 Standart stillerini birleşimi (mantıksal veya işlecini kullanarak) almak için bu işlevi çağırmak `CWinTraits` nesne ve tarafından belirtilen varsayılan stillerini `t_dwStyle`.  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Bir pencere oluşturma için kullanılan stiller.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletilen stilleri bileşimini `dwStyle` ve tarafından belirtilen olanları varsayılan `t_dwStyle`, mantıksal veya işlecini kullanarak.  
  
##  <a name="getwndexstyle"></a>CWinTraitsOR::GetWndExStyle  
 Genişletilmiş stillerini birleşimi (mantıksal veya işlecini kullanarak) almak için bu işlevi çağırmak `CWinTraits` nesne ve tarafından belirtilen varsayılan stillerini `t_dwStyle`.  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwExStyle`  
 Bir pencere oluşturma için kullanılan genişletilmiş stilleri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletilen genişletilmiş stilleri bileşimini `dwExStyle` ve tarafından belirtilen varsayılan `t_dwExStyle`, mantıksal veya işlecini kullanarak  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Pencere özellikleri anlama](../../atl/understanding-window-traits.md)

