---
title: "ComPtr::operator&amp; işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::operator&
dev_langs: C++
helpviewer_keywords: operator& operator
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2b464a77fedf0d996210040b744faea0ee7372ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [ComPtr sınıfı](../windows/comptr-class.md)