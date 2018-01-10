---
title: "İşlev şablonu örneklemesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- templates, instantiation
- function templates, instantiation
- instantiation, function templates
ms.assetid: f22a07c7-3ad1-465a-84f5-8737e274bd47
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 41bf7f6ba3a2a17c6355ee9239cadb6e5014ee96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
