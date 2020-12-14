---
description: 'Daha fazla bilgi edinin: kutulama (C++/CX)'
title: Kutulama (C++/CX)
ms.date: 12/30/2016
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
ms.openlocfilehash: 50b7f3f071fcd0109a85fb24985024666bd8fad3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302744"
---
# <a name="boxing-ccx"></a>Kutulama (C++/CX)

*Kutulama* , [Windows:: Foundation::D atetime](/uwp/api/windows.foundation.datetime)gibi bir değer türü değişkeni ya da **`int`** değişken, giriş türü olarak [Platform:: Object ^](../cppcx/platform-object-class.md) alan bir yönteme geçirildiğinde bir tür temel skaler türü sarmalama.

## <a name="passing-a-value-type-to-an-object-parameter"></a>Bir nesne ^ parametresine değer türü geçirme

[Platform:: Object ^](../cppcx/platform-object-class.md)türünde bir yöntem parametresine iletmek için bir değişkeni açıkça kutulanabilir olsanız da, daha önce paketlenmiş değerleri alırken özgün türe açıkça geri dönüştürme yapmanız gerekir.

[!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]

### <a name="using-platformiboxt-to-support-nullable-value-types"></a>\<T>Nullable değer türlerini desteklemek Için Platform:: IBox kullanma

C# ve Visual Basic Nullable değer türleri kavramını destekler. C++/CX ' te, `Platform::IBox<T>` null yapılabilir değer türü parametrelerini destekleyen ortak yöntemleri açığa çıkarmak için türünü kullanabilirsiniz. Aşağıdaki örnek, bir C# çağıranı bağımsız değişkenlerden biri için null geçirdiğinde null döndüren bir C++/CX ortak yöntemi gösterir.

[!code-cpp[cx_boxing#02](../cppcx/codesnippet/CPP/cx_boxing/class1.h#02)]

C# XAML istemcisinde bunu şöyle kullanabilirsiniz:

```

// C# client code
    BoxingDemo.Class1 obj = new BoxingDemo.Class1();
    int? a = null;
    int? b = 5;
    var result = obj.Multiply(a,b); //result = null
```

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Atama (C++/CX)](../cppcx/casting-c-cx.md)<br/>
[C++/CX dil başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md)
