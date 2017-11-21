---
title: "Interfacetraits::cancastto yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
dev_langs: C++
helpviewer_keywords: CanCastTo method
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 107c89c7643e137b20492f9ae932a736cc0ba603
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
#### <a name="parameters"></a>Parametreler  
 `ptr`  
 Bir işaretçi bir tür adı.  
  
 `riid`  
 Arabirim Kimliği `Base`.  
  
 `ppv`  
 Bu işlem başarılı olursa `ppv` tarafından belirtilen arabirimi işaret `Base`. Aksi takdirde, `ppv` ayarlanır `nullptr`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`Bu işlem başarılı olursa ve `ptr` gösteren bir işaretçi cast `Base`; Aksi halde, `false` .  
  
## <a name="remarks"></a>Açıklamalar  
 Bir işaretçi için belirtilen işaretçi içerip içermeyeceğini gösterir `Base`.  
  
 Hakkında daha fazla bilgi için `Base`, genel tür tanımları bölümüne bakın [Interfacetraits yapısı](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Interfacetraits yapısı](../windows/interfacetraits-structure.md)   
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)