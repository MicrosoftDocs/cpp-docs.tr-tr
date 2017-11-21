---
title: "vektör&lt;bool&gt;:: sınıf başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vector/vector<bool>::reference
dev_langs: C++
helpviewer_keywords: vector<bool> reference class
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1ca67fcf0ea4b74d167ddb6cdeb01de071a24862
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vectorltboolgtreference-class"></a>vektör&lt;bool&gt;:: sınıfı başvurusu
`vector<bool>::reference` Sınıftır tarafından sağlanan bir proxy [vektör\<bool > sınıfı](../standard-library/vector-bool-class.md) benzetimini yapmak için `bool&`.  
  
## <a name="remarks"></a>Açıklamalar  
 C++ yerel olarak doğrudan başvuruların bitlere atanmasına izin vermediğinden, benzetimli bir başvuru gereklidir. `vector<bool>`Bu proxy sınıfını kullanarak başvurulabilir öğesi başına yalnızca bir bit kullanır. Bununla birlikte, belirli atamalar geçersiz olduğundan başvuru benzetimi tam değil. Örneğin, çünkü adresini `vector<bool>::reference` nesne olamaz alınması, kullandığı aşağıdaki kodu [vektör\<bool >:: işleci &#91; &#93;](http://msdn.microsoft.com/Library/97738633-690d-4069-b2d9-8c54104fbfdd) doğru değil:  
  
```cpp  
vector<bool> vb;  
// ...  
bool* pb = &vb[1]; // conversion error - do not use  
bool& refb = vb[1];   // conversion error - do not use  
```  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[ters çevirin](../standard-library/vector-bool-reference-flip.md)|Bir vektör öğesinin Boolean değerini tersine çevirir.|  
|[işleç bool değeri](../standard-library/vector-bool-reference-operator-bool.md)|Örtük bir dönüştürme sağlar `vector<bool>::reference` için `bool`.|  
|[işleç =](../standard-library/vector-bool-reference-operator-assign.md)|Bir bite bir Boolean değeri, veya başvurulan bir öğenin tuttuğu değeri atar.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: \<vektör >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<vektör >](../standard-library/vector.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

