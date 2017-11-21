---
title: "operator == (&lt;örnek kapsayıcı&gt;) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.==
- std::==
- operator==
- std.operator==
- std::operator==
- ==
dev_langs: C++
helpviewer_keywords:
- operator ==, containers
- operator==, containers
- == operator, with specific standard C++ objects
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c42f6328ce7867c49e240bbcd5946e551b2a5ac6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="operator-ltsample-containergt"></a>operator == (&lt;örnek kapsayıcı&gt;)
> [!NOTE]
>  Bu konu, Visual C++ belge C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsel bir örnek olarak kullanılıyor. Daha fazla bilgi için bkz: [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).  
  
 Overloads `operator==` iki nesne şablonu sınıfının Karşılaştırılacak [kapsayıcı](../standard-library/sample-container-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Ty>  
bool operator==(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür `left.` [boyutu](../standard-library/container-class-size.md) ` == right.size && equal(left.` [başlamak](../standard-library/container-class-begin.md)`, left.`[son](../standard-library/container-class-end.md)`, right.begin)`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Örnek kapsayıcı >](../standard-library/sample-container.md)

