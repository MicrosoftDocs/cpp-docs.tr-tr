---
title: _U_RECT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_U_RECT
- _U_RECT
- ATL._U_RECT
dev_langs:
- C++
helpviewer_keywords:
- U_RECT class
- _U_RECT class
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93d067daf34538e3745e9a4efdd91fda65ef4de9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="urect-class"></a>_U_RECT sınıfı
Bu bağımsız değişken bağdaştırıcı sınıfı ya da verir `RECT` işaretçileri veya bakımından işaretçileri uygulanan bir işlev geçirilmesi başvuruları.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class _U_RECT```  
  
## Members  
  
### Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[_U_RECT::_U_RECT](#_u_rect___u_rect)|The constructor.|  
  
### Public Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[_U_RECT::m_lpRect](#_u_rect__m_lprect)|Pointer to a `RECT`.|  
  
## Remarks  
 The class defines two constructor overloads: one accepts a **RECT&** argument and the other accepts an `LPRECT` argument. The first constructor stores the address of the reference argument in the class's single data member, [m_lpRect](#_u_rect__m_lprect). The argument to the pointer constructor is stored directly without conversion.  
  
## Requirements  
 **Header:** atlwin.h  
  
##  <a name="_u_rect__m_lprect"></a>  _U_RECT::m_lpRect  
 The class holds the value passed to either of its constructors as a public `LPRECT` data member.  
  
```
LPRECT m_lpRect;
```  
  
##  <a name="_u_rect___u_rect"></a>  _U_RECT::_U_RECT  
 The address of the reference argument is stored in the class's single data member, [m_lpRect](#_u_rect__m_lprect).  
  
```
_U_RECT (RECT & rc);  
_U_RECT (LPRECT lpRect);
```  
  
### Parameters  
 `rc`  
 A `RECT` reference.  
  
 `lpRect`  
 A `RECT` pointer.  
  
### Remarks  
 The argument to the pointer constructor is stored directly without conversion.  
  
## See Also  
 [Class Overview](../../atl/atl-class-overview.md)
