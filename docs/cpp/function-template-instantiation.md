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
ms.openlocfilehash: fb94a54c4f99b79e3be742c5b1448151cff140c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116795"
---
# <a name="function-template-instantiation"></a>İşlev Şablonu Örneklemesi

Bir işlev şablonu her türü için ilk kez çağrıldığında, derleyici örneklemesi oluşturur. Şablonlu bir sürümünü her örneklemesi olan işlev türü için özelleştirilmiş. Bu örnek oluşturma, işlev türü için kullanılan her zaman çağrılır. Birden fazla özdeş örneklemeleri, hatta farklı modülde varsa, yalnızca bir kopyasını örneklemesinin yürütülebilir dosyada elde edebilirsiniz.

İşlev bağımsız değişkenlerinin dönüştürme işlevi şablonlarında burada parametresi bir şablon bağımsız değişkenine bağımlı değildir bağımsız değişken ve parametre çifti için izin verilir.

İşlev şablonlarının açık şablon bağımsız değişken olarak belirli bir tür ile bildirerek oluşturulabilir. Örneğin, aşağıdaki koda izin verilir:

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