---
title: "Runtimeclassbaset::asııd yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
dev_langs: C++
helpviewer_keywords: AsIID method
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 796718c4533bf8730ca7a4c733e5809fb0fde880
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="runtimeclassbasetasiid-method"></a>RuntimeClassBaseT::AsIID Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT AsIID(  
   _In_ T* implements,  
   REFIID riid,  
   _Deref_out_ void **ppvObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Parametresi tarafından belirtilen arabirim kimliği uygulayan bir tür `riid`.  
  
 `implements`  
 Şablon parametresi tarafından belirtilen türde bir değişken `T`.  
  
 `riid`  
 Alınacak arabirimi kimliği.  
  
 `ppvObject`  
 Bu işlem başarılı olursa, parametresi tarafından belirtilen bir işaretçi bir-işaretçiye arabirimine `riid`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen arabirim kimliği için bir işaretçi alır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [RuntimeClassBaseT yapısı](../windows/runtimeclassbaset-structure.md)   
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)