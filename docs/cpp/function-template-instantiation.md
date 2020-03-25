---
title: İşlev Şablonu Örneklemesi
ms.date: 11/04/2016
helpviewer_keywords:
- templates, instantiation
- function templates, instantiation
- instantiation, function templates
ms.assetid: f22a07c7-3ad1-465a-84f5-8737e274bd47
ms.openlocfilehash: 6917448af067542fffb13aa043720bf8a26f7ba3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179763"
---
# <a name="function-template-instantiation"></a>İşlev Şablonu Örneklemesi

Her tür için bir işlev şablonu ilk kez çağrıldığında, derleyici bir örnek oluşturur. Her örnekleme, türü için özelleştirilmiş şablonlu işlevin bir sürümüdür. Bu örnek oluşturma, her bir işlev türü için kullanıldığında çağrılacaktır. Farklı modüllerde bile birden fazla özdeş örneklemeiniz varsa, örnek olarak yalnızca bir kopyasının tek bir kopyası çalıştırılabilir dosyada sona alınacaktır.

İşlev bağımsız değişkenlerinin dönüştürülmesine, parametrenin bir şablon bağımsız değişkenine bağlı olmadığı bağımsız değişkenler ve parametre çifti için işlev şablonlarında izin verilir.

İşlev şablonları, bir bağımsız değişken olarak belirli bir türe sahip şablon bildirerek açıkça oluşturulabilir. Örneğin, aşağıdaki koda izin verilir:

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

## <a name="see-also"></a>Ayrıca bkz.

[İşlev Şablonları](../cpp/function-templates.md)
