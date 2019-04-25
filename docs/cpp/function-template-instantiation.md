---
title: İşlev Şablonu Örneklemesi
ms.date: 11/04/2016
helpviewer_keywords:
- templates, instantiation
- function templates, instantiation
- instantiation, function templates
ms.assetid: f22a07c7-3ad1-465a-84f5-8737e274bd47
ms.openlocfilehash: c4667f5ae625468cdab428706ddaff92a1c1af33
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154184"
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