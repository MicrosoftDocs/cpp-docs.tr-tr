---
title: ComPtr::operator&amp; işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0bfe8cf9091d888c33420f53f584ca5509d80527
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="comptroperatoramp-operator"></a>ComPtr::operator&amp; işleci
Bu ile ilişkili arabiriminin serbest `ComPtr` nesne ve adresini alır `ComPtr` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli zayıf başvuru `ComPtr`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem farklıdır [ComPtr::GetAddressOf](../windows/comptr-getaddressof-method.md) , bu yöntem arabirim işaretçisi başvuru serbest bırakır. Kullanım `ComPtr::GetAddressOf` kullandığınızda arabirim işaretçisi adresini gerektirir ancak bu arabirim serbest bırakmak istiyor musunuz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr Sınıfı](../windows/comptr-class.md)