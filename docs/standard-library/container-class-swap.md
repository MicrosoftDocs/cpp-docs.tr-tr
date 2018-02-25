---
title: "Kapsayıcı sınıfı::Swap | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 62acdf7bf8278dfba3cf85bc9d5ced26a0f3fcea
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="container-classswap"></a>Kapsayıcı Sınıfı::swap
> [!NOTE]
>  Bu konu, Visual C++ belge C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsel bir örnek olarak kullanılıyor. Daha fazla bilgi için bkz: [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).  
  
Denetimli sıraları arasında değiştirir  **\*bu** ve bağımsız değişkeni.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void swap(Container& right);
```  
  
## <a name="remarks"></a>Açıklamalar  
Varsa  **\*this.get\_ayırıcısı ==** _sağ_**.get_allocator**, bunu bir takas Sabit sürede yapar. Aksi durumda, iki denetimli sıralarında öğesi atamaları ve oluşturucu çağrıları öğe sayısını orantılı çeşitli gerçekleştirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Örnek Kapsayıcı Sınıfı](../standard-library/sample-container-class.md)
