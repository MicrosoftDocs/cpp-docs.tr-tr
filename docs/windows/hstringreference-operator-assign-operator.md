---
title: "HStringReference::Operator = işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs:
- C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 097e89ab4ae2d3b6ddaacb2fa52b811c1577ef72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator= İşleci
Başka bir HStringReference nesnenin değerini geçerli HStringReference nesneye taşır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
#### <a name="parameters"></a>Parametreler  
 `other`  
 Varolan bir HStringReference nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Var olan değerin `other` nesne geçerli HStringReference nesnesine kopyalanır ve ardından `other` nesne yok.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HStringReference Sınıfı](../windows/hstringreference-class.md)