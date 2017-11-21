---
title: "is_trivially_destructible sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::is_trivially_destructible
dev_langs: C++
helpviewer_keywords: is_trivially_destructible
ms.assetid: 3f7a787d-2448-40c5-ac51-a228318e02ce
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f2b9f29915fb2b47f84b3192b9bd90a71c92eae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="istriviallydestructible-class"></a>is_trivially_destructible sınıfı
Türü trivially destructible olup olmadığını sınar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
struct is_trivially_destructible;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `T` destructible türü ve yıkıcı derleyici hiçbir Önemsiz olmayan işlemlerini kullanmak için bilinen bir. Aksi takdirde false tutar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)



