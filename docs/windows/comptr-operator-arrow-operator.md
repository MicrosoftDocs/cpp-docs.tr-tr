---
title: "ComPtr::operator -&gt; işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::operator->
dev_langs: C++
helpviewer_keywords: operator-> operator
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 28ac6f7dfc4e53e6aadc4fd082e10a0325124ee0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptroperator-gt-operator"></a>ComPtr::operator -&gt; işleci
Geçerli şablon parametresi tarafından belirtilen tür için bir işaretçi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli şablon tür adıyla belirtilen türün işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yardımcı işlevi STDMETHOD makrosu kullanımından kaynaklanan gereksiz yükünü kaldırır. Bu işlev IUnknown türleri sanal yerine özel hale getirir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr sınıfı](../windows/comptr-class.md)