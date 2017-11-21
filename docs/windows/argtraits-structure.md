---
title: "ArgTraits yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::ArgTraits
dev_langs: C++
helpviewer_keywords: ArgTraits structure
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d95fc547d9c755adad58c1ddcd8de5a8e40a863c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="argtraits-structure"></a>ArgTraits Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename TMemberFunction  
>  
struct ArgTraits;  
template<  
   typename TDelegateInterface  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8,  
   typename TArg9  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TMemberFunction`  
 Invoke yöntemi imza eşleşemez ArgTraits yapısı için TypeName parametre.  
  
 `TDelegateInterface`  
 Bir temsilci arabirimi.  
  
 `TArg1`  
 Invoke yöntemi ilk bağımsız değişkeni türü.  
  
 `TArg2`  
 Invoke yöntemi ikinci bağımsız değişkeni türü.  
  
 `TArg3`  
 Invoke yöntemi işlevinin üçüncü bağımsız değişkeninin türü.  
  
 `TArg4`  
 Invoke yöntemi Dördüncü bağımsız değişkeni türü.  
  
 `TArg5`  
 Invoke yöntemi Beşinci bağımsız değişkeni türü.  
  
 `TArg6`  
 Invoke yöntemi altıncı bağımsız değişkeni türü.  
  
 `TArg7`  
 Invoke yöntemi yedinci bağımsız değişkeni türü.  
  
 `TArg8`  
 Invoke yöntemi alt bağımsız değişkeni türü.  
  
 `TArg9`  
 Invoke yöntemi dokuzuncu bağımsız değişkeni türü.  
  
## <a name="remarks"></a>Açıklamalar  
 `ArgTraits` Yapı arabirimi ve belirtilen bir parametre sayısı bir anonim üye işlevi belirtilen temsilci bildirir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`Arg1Type`|Typedef TArg1 için.|  
|`Arg2Type`|Typedef TArg2 için.|  
|`Arg3Type`|Typedef TArg3 için.|  
|`Arg4Type`|Typedef TArg4 için.|  
|`Arg5Type`|Typedef TArg5 için.|  
|`Arg6Type`|Typedef TArg6 için.|  
|`Arg7Type`|Typedef TArg7 için.|  
|`Arg8Type`|Typedef TArg8 için.|  
|`Arg9Type`|Typedef TArg9 için.|  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ArgTraits::args sabiti](../windows/argtraits-args-constant.md)|Invoke yöntemi bir temsilci arabirimin parametrelerin sayısı sayısı tutar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ArgTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)