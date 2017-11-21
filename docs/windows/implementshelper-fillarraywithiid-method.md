---
title: "Implementshelper::fillarraywithıid yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
dev_langs: C++
helpviewer_keywords: FillArrayWithIid method
ms.assetid: f60035ee-b7d6-4a08-966d-f88c646944c3
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6ced3719644678305b9958cd5c118ada632457d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="implementshelperfillarraywithiid-method"></a>ImplementsHelper::FillArrayWithIid Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void FillArrayWithIid(  
   _Inout_ unsigned long *index,   
   _Inout_ IID* iids) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `index`  
 Bu işlem için başlangıç dizi öğesi gösteren sıfır tabanlı dizini. Bu işlem tamamlandığında `index` 1 artırılır.  
  
 `iids`  
 IID'leri türünde bir dizi.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen dizi öğesi içinde geçerli sıfırıncı şablon parametresi tarafından belirtilen arabirim kimliği ekler.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Implementshelper yapısı](../windows/implementshelper-structure.md)   
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)