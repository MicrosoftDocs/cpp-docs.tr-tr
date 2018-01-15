---
title: "İşleç&lt;= (&lt;örnek kapsayıcı&gt;) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<=
- std.operator<=
- operator<=
- std.<=
- std::operator<=
- <=
dev_langs: C++
helpviewer_keywords:
- operator<=
- operator <=
- <= operator, with specific objects
- <= operator
ms.assetid: 338577dd-dc88-4a2b-9e12-0379c54fc8a2
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f98cbc2cf8431262b1ba50885a7f25e87cde24df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="operatorlt-ltsample-containergt"></a>İşleç&lt;= (&lt;örnek kapsayıcı&gt;)
> [!NOTE]
>  Bu konu, Visual C++ belge C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsel bir örnek olarak kullanılıyor. Daha fazla bilgi için bkz: [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).  
  
 Overloads **operator < =** iki nesne şablonu sınıfının Karşılaştırılacak [kapsayıcı](../standard-library/sample-container-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Ty>  
bool operator<=(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür `!(right < left)`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Örnek kapsayıcı >](../standard-library/sample-container.md)

