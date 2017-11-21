---
title: Algoritmalar (Modern C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 6f758d3c-a7c7-4a50-92bb-97b2f6d4ab27
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 61152e939838833e9296643af1144fe363c7cf52
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="algorithms-modern-c"></a>Algoritmalar (Modern C++)
Algoritmalara kullanmanızı tavsiye ederiz Modern C++ programlama [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md). Önemli bazı örnekler şunlardır:  
  
-   `for_each`, varsayılan geçişi algoritma olduğu. (Ayrıca `transform` yerinde değil-semantiği için.)  
  
-   `find_if`, varsayılan arama algoritması olduğu.  
  
-   `sort`, `lower_bound`ve sıralama ve arama algoritmaları diğer varsayılan.  
  
 Bir karşılaştırıcı yazmak için katı kullanmak `<` ve *Lambda'lar adlı* zaman şunları yapabilirsiniz.  
  
```cpp  
auto comp = [](const widget& w1, const widget& w2)  
      { return w1.weight() < w2.weight(); }  
  
sort( v.begin(), v.end(), comp );  
  
auto i = lower_bound( v.begin(), v.end(), comp );  
```  
  
## <a name="loops"></a>Döngüler  
 Mümkün olduğunda, aralığın tabanlı kullanın `for` döngüler veya algoritması çağrıları ya da her ikisini de yerine elle yazılmış döngüler.`copy`, `transform`, `count_if`, `remove_if`, ve diğerleri gibi onları el yazısı döngüler daha iyi çünkü bunların amacı açıktır ve bunlar hata serbest kod yazmayı kolaylaştırır. Ayrıca, birçok C++ Standart Kitaplığı algoritması daha verimli hale uygulama iyileştirmeler vardır.  
  
 Bu gibi eski C++ yerine:  
  
```cpp  
for ( auto i = strings.begin(); i != strings.end(); ++i ) {  
   /* ... */  
}  
  
auto i = v.begin();  
  
for ( ; i != v.end(); ++i ) {  
  if (*i > x && *i < y) break;  
}  
```  
  
 Bu gibi Modern C++ kullanın:  
  
```cpp  
for_each( begin(strings), end(strings), [](string& s) {  
   // ...  
} );  
  
auto i = find_if( begin(v), end(v),  [=](int i) { return i > x && i < y; } );  
```  
  
### <a name="range-based-for-loops"></a>Döngüler için aralık tabanlı  
 Aralık tabanlı `for` döngü bir özelliktir C ++ 11 dil, C++ Standart Kitaplığı algoritması. Ancak, bu konudaki ilgiyi döngüleri hakkında gerektirir. Aralık tabanlı `for` döngüler uzantısı olan `for` anahtar sözcüğü ve değerleri aralığı yineleme döngüler yazmak için kolay ve verimli bir yolunu sağlar. C++ Standart Kitaplığı kapsayıcıları, dize ve diziler için hazır aralık tabanlı `for` döngüler. Bu yeni kullanıcı tanımlı tür yineleme sözdizimi etkinleştirmek için aşağıdaki Destek ekleyin:  
  
-   A `begin` yineleyici yapısı başına döndürür yöntemi ve bir `end` yapısı sonuna yineleyici döndürür yöntemi.  
  
-   Yineleyici bu yöntemleri için destek: `operator*`, `operator!=`, ve `operator++` (önek sürüm).  
  
 Bu yöntemler üyeleri veya tek başına işlevleri olabilir.  
  
## <a name="random-numbers"></a>Rastgele sayılar  
 Hiçbir gizli olmadığından, eski CRT `rand()` işlevi en length C++ topluluğuna açıklanan birçok açıkları vardır. Modern C++'da, bu eksik ile mücadele etmek zorunda değilsiniz — ya da kendi hep dağıtılmış rastgele sayı üreticisinin stok zorunda — hızlı ve kolay bir şekilde bunları oluşturmak için Araçlar C++ Standart kitaplığında kullanılabilir olmadığından gösterildiğigibi[ \<rastgele >](../standard-library/random.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ için yeniden Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)