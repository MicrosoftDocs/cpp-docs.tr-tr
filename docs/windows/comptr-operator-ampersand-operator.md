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
ms.openlocfilehash: 0afff1699a4c7a3a14f07967cfb5ba5727ba0320
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461568"
---
# <a name="comptroperatoramp-operator"></a>ComPtr::operator&amp; işleci
Şununla ilişkili arabirimini yayımlar **ComPtr** nesne ve adresini alır. **ComPtr** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli zayıf bir başvuru **ComPtr**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem farklıdır [ComPtr::GetAddressOf](../windows/comptr-getaddressof-method.md) , bu yöntem bir arabirim işaretçisi başvurusu serbest bırakır. Kullanım `ComPtr::GetAddressOf` kullandığınızda arabirim işaretçisi adresini gerektirir ancak bu arabirimi serbest bırakmak istiyor musunuz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr Sınıfı](../windows/comptr-class.md)