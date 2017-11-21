---
title: "is_final sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_final
dev_langs: C++
helpviewer_keywords: is_final
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9f1ab7e0eb9a49e1ed73c2bc33d78b480f8ef907
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="isfinal-class"></a>is_final sınıfı
Türü işaretli bir sınıf türü olup olmadığını sınar `final`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>
struct is_final;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `T` bir sınıf türü olarak işaretlenmiş `final`, aksi takdirde false tutar. Varsa `T` bir sınıf türü tam bir tür olması gerekir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)   
 [final tanımlayıcısı](../cpp/final-specifier.md)



