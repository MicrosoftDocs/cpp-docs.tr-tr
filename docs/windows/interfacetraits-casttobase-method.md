---
title: "Interfacetraits::casttobase yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
dev_langs:
- C++
helpviewer_keywords:
- CastToBase method
ms.assetid: 0591a017-0adf-4358-b946-eb0a307ce7f2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 06791d940f2d6028326808d2bebb328881e7567a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="interfacetraitscasttobase-method"></a>InterfaceTraits::CastToBase Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename T  
>  
static __forceinline Base* CastToBase(  
   _In_ T* ptr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Parametrenin türü `ptr`.  
  
 `ptr`  
 İşaretçi türü `T`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `Base`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir işaretçi belirtilen işaretçisine bıraktığı `Base`.  
  
 Hakkında daha fazla bilgi için `Base`, genel tür tanımları bölümüne bakın [Interfacetraits yapısı](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Interfacetraits yapısı](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)