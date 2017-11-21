---
title: "ComPtr::operator! = işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::operator!=
dev_langs: C++
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ce13c5dabf267be5d7c8a77a51d1450f182d226d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptroperator-operator"></a>ComPtr::operator!= İşleci
İki ComPtr nesnenin eşit olup olmadığını gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `a`  
 ComPtr bir nesneye başvuru.  
  
 `b`  
 Başka bir ComPtr nesneye başvuru.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İlk işleci veriyor `true` , nesne `a` nesnesine eşit değil `b`; Aksi halde, `false`.  
  
 İkinci ve üçüncü işleçleri verim `true` , nesne `a` eşit değil `nullptr`; Aksi halde, `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)   
 [ComPtr sınıfı](../windows/comptr-class.md)