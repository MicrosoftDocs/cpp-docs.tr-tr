---
title: İşlev şablonu örneklemesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- templates, instantiation
- function templates, instantiation
- instantiation, function templates
ms.assetid: f22a07c7-3ad1-465a-84f5-8737e274bd47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6374dcd9dad263afd0961be91971d3283ba863ab
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412130"
---
# <a name="function-template-instantiation"></a>İşlev Şablonu Örneklemesi
İşlev şablonu ilk her tür için çağrıldığında derleyici örnekleme oluşturur. Her bir sürümü şablonlu oluşturulmadan işlevi türü için özelleştirilmiş. İşlev türü için kullanılan her zaman bu örneklemesi çağrılır. Birkaç aynı örneklemesi, hatta farklı modüllerde varsa, örneklemesi yalnızca bir kopyasını yürütülebilir dosyayı son bulur.  
  
 İşlev bağımsız değişkenleri dönüştürülmesi işlevi şablonlarında burada parametresi bir şablon bağımsız değişkenine bağlı değildir bağımsız değişkeni ve parametre çifti için izin verilir.  
  
 İşlev şablonları açıkça bağımsız değişken olarak belirli bir tür ile şablonu bildirerek oluşturulabilir. Örneğin, aşağıdaki kodu izin verilir:  
  
```cpp
// function_template_instantiation.cpp  
template<class T> void f(T) { }  
  
// Instantiate f with the explicitly specified template.  
// argument 'int'  
//  
template void f<int> (int);  
  
// Instantiate f with the deduced template argument 'char'.  
template void f(char);  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlev Şablonları](../cpp/function-templates.md)
