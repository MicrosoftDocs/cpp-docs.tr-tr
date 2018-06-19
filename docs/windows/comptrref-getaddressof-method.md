---
title: ComPtrRef::GetAddressOf yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- GetAddressOf method
ms.assetid: 797df323-a2fa-412b-ab60-32cce3721096
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5dc8e80fe97bc0a4ace0cb53e43f306ad2b85309
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883313"
---
# <a name="comptrrefgetaddressof-method"></a>ComPtrRef::GetAddressOf Metodu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
InterfaceType* const * GetAddressOf() const;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli ComPtrRef nesnesinin temsil ettiği arabirimi için bir işaretçi adresi.  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli ComPtrRef nesnesinin temsil ettiği arabirimi için bir işaretçi adresi alır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtrRef sınıfı](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)