---
title: "_U_MENUorID sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
dev_langs:
- C++
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7ddde6ff5d45c90e675bd2e44ac421e840d1357b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="umenuorid-class"></a>_U_MENUorID sınıfı
Bu sınıf için sarmalayıcıları sağlar **CreateWindow'u** ve **CreateWindowEx**.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class _U_MENUorID
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[_U_MENUorID::_U_MENUorID](#_u_menuorid___u_menuorid)|Oluşturucu.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|Bir menüye işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bağımsız değişken bağdaştırıcı sınıfı ya da kimlikleri verir ( **UINT**s) veya menü tanıtıcıları ( `HMENU`s) arayan bir kısmını açık bir atama gerek kalmadan bir işleve geçirilecek.  
  
 Bu sınıf Windows API sarmalayıcıları uygulamak için tasarlanmıştır özellikle [CreateWindow'u](http://msdn.microsoft.com/library/windows/desktop/ms632679) ve [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) İşlevler, her ikisi de kabul bir `HMENU` alt olabilir bağımsız değişken Pencere tanımlayıcısı ( **UINT**) yerine bir menü işleci. Örneğin, bir parametre olarak bu sınıfın kullanımda görebilirsiniz [CWindowImpl::Create](cwindowimpl-class.md#create).  

  
 Sınıfın iki Oluşturucusu aşırı tanımlar: bir kabul bir **UINT** bağımsız değişkeni ve diğer kabul eden bir `HMENU` bağımsız değişkeni. **UINT** bağımsız değişkeni yalnızca atandığında bir `HMENU` oluşturucusu ve sınıfın tek veri üyesi depolanmış sonucu [m_hMenu](#_u_menuorid__m_hmenu). Bağımsız değişkeni `HMENU` Oluşturucusu doğrudan dönüştürme olmadan depolanır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="_u_menuorid__m_hmenu"></a>_U_MENUorID::m_hMenu  
 Sınıf ya da oluşturucular genel olarak geçirilen değeri tutan `HMENU` veri üyesi.  
  
```
HMENU m_hMenu;
```  
  
##  <a name="_u_menuorid___u_menuorid"></a>_U_MENUorID::_U_MENUorID  
 **UINT** bağımsız değişkeni yalnızca atandığında bir `HMENU` oluşturucusu ve sınıfın tek veri üyesi depolanmış sonucu [m_hMenu](#_u_menuorid__m_hmenu).  
  
```
_U_MENUorID(UINT nID);  
_U_MENUorID(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Alt pencere tanımlayıcısı.  
  
 `hMenu`  
 Menü işleci.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağımsız değişkeni `HMENU` Oluşturucusu doğrudan dönüştürme olmadan depolanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
