---
title: "is_lvalue_reference sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_lvalue_reference
dev_langs: C++
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c150a38604ad2c0f6b00b000c7897ed700c940c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="islvaluereference-class"></a>is_lvalue_reference Sınıfı
Testleri lvalue başvuru türüdür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Ty>
struct is_lvalue_reference;
```  
  
#### <a name="parameters"></a>Parametreler  
 `Ty`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu türü koşulu örneği doğru tutan türü `Ty` başvurudur bir nesne ya da false tuttuğu işlevi, aksi takdirde. Unutmayın `Ty` rvalue başvuru olmayabilir. Rvalues hakkında daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)   
 [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)



