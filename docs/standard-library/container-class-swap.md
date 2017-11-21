---
title: "Kapsayıcı sınıfı::Swap | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 13d083c596dcbaa275ed8d0f05ded2c5cb5547eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
[Örnek kapsayıcı sınıfı](../standard-library/sample-container-class.md)
