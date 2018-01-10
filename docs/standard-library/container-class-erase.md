---
title: "Kapsayıcı sınıfı::ERASE | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ef45ec608736640f8f17a375838d3778d3ecc9b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="container-classerase"></a>Kapsayıcı Sınıfı::erase
> [!NOTE]
>  Bu konu, Visual C++ belge C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsel bir örnek olarak kullanılıyor. Daha fazla bilgi için bkz: [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).  
  
 Bir öğeyi siler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
 
    iterator erase(
    iterator _Where);

iterator erase(
    iterator first,  
    iterator last);
```  
  
## <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi gösterdiği denetimli sırasının öğeyi kaldırır *_Where*. İkinci üye işlevi denetlenen sıradaki aralığında kaldırır [`first`, `last`). Her ikisi de kaldırıldı, herhangi bir öğenin dışında kalan ilk öğe atayan bir yineleyici dönün veya [son](../standard-library/container-class-end.md) böyle bir öğe varsa.  
  
 Yalnızca bir kopyalama işlemi bir özel durum oluşturursa üye işlevleri bir özel durum.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Örnek Kapsayıcı Sınıfı](../standard-library/sample-container-class.md)
