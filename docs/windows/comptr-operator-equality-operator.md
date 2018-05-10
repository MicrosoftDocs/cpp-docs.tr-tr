---
title: ComPtr::operator == işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator==
dev_langs:
- C++
ms.assetid: 6a26e936-29d4-4b7d-b44a-7c575ad07509
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 703204541a05c260e77562729703677b98fb8e9d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="comptroperator-operator"></a>ComPtr::operator== İşleci
İki ComPtr nesnenin eşit olup olmadığını gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
bool operator==(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator==(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator==(  
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
 İlk işleci veriyor `true` , nesne `a` nesnesine eşit olan `b`; Aksi halde, `false`.  
  
 İkinci ve üçüncü işleçleri verim `true` , nesne `a` eşittir `nullptr`; Aksi halde, `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)   
 [ComPtr Sınıfı](../windows/comptr-class.md)