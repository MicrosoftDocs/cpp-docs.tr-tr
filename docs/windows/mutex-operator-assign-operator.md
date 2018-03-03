---
title: "Mutex::operator = işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 23526911a2d9e723455a7d846bdaafb2dbefd45a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mutexoperator-operator"></a>Mutex::operator= İşleci
Atar (taşır) belirtilen Mutex geçerli Mutex nesnesi nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Mutex& operator=(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `h`  
 Bir rvalue-başvuru Mutex nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli Mutex nesneye başvuru.  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: **taşıma semantiği** bölümünü [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Mutex sınıfı](../windows/mutex-class1.md)