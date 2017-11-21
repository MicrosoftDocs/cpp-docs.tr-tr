---
title: "HStringReference::Operator = işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs: C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2b6a9938308f0cbd8339c24d1876c09ae49df349
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [HStringReference sınıfı](../windows/hstringreference-class.md)