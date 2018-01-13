---
title: "İşleç&gt; (&lt;örnek kapsayıcı&gt;) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::operator>
- operator>
- std::>
- '>'
dev_langs: C++
helpviewer_keywords:
- '> operator, comparing specific objects'
- operator >
ms.assetid: 49bd417a-3305-4ffa-9884-39d3904ed87d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 047132a1281a33f3f93b5dc3afe5b0807a63b6bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="operatorgt-ltsample-containergt"></a>İşleç&gt; (&lt;örnek kapsayıcı&gt;)
> [!NOTE]
>  Bu konu, Visual C++ belge C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsel bir örnek olarak kullanılıyor. Daha fazla bilgi için bkz: [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).  
  
 Overloads **işleci >** iki nesne şablonu sınıfının Karşılaştırılacak [kapsayıcı](../standard-library/sample-container-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Ty>  
bool operator*gt;(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür `right < left`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Örnek kapsayıcı >](../standard-library/sample-container.md)

