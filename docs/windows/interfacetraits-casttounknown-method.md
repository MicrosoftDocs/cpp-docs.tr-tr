---
title: Interfacetraits::casttounknown yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a2fdc46f57f834c3e8217049574ea504aae16f03
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="interfacetraitscasttounknown-method"></a>InterfaceTraits::CastToUnknown Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T>  
static __forceinline IUnknown* CastToUnknown(  
   _In_ T* ptr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Parametrenin türü `ptr`.  
  
 `ptr`  
 İşaretçi türü `T`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 IUnknown işaretçisi içinden `Base` türetilir.  
  
## <a name="remarks"></a>Açıklamalar  
 IUnknown işaretçisi belirtilen işaretçisine çevirir.  
  
 Hakkında daha fazla bilgi için `Base`, genel tür tanımları bölümüne bakın [Interfacetraits yapısı](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Interfacetraits yapısı](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)