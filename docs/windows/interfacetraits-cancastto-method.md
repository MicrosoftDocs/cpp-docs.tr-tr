---
title: Interfacetraits::cancastto yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: df603fe8d4c063c014118caf89a74a40e73cbe5b
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607835"
---
# <a name="interfacetraitscancastto-method"></a>InterfaceTraits::CanCastTo Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T>  
static __forceinline bool CanCastTo(  
   _In_ T* ptr,  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *ptr*  
 Bir tür için bir işaretçi adı.  
  
 *riid*  
 Arabirim Kimliği `Base`.  
  
 *ppv*  
 Bu işlem başarılı olursa *ppv* tarafından belirtilen arabirim işaret `Base`. Aksi takdirde, *ppv* ayarlanır **nullptr**.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** bu işlem başarılı olursa ve *ptr* işaretçisine dönüştürme `Base`; Aksi takdirde **false** .  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen işaretçi işaretçisi içerip içermeyeceğini belirten `Base`.  
  
 Hakkında daha fazla bilgi için `Base`, bkz: **genel Typedefler** konusundaki [Interfacetraits yapısı](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Interfacetraits yapısı](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)