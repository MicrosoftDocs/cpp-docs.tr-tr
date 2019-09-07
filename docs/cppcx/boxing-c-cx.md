---
title: Kutulama (C++/CX)
ms.date: 12/30/2016
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
ms.openlocfilehash: 90c5af31efc6523683227dbf54c85390bc98510a
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740674"
---
# <a name="boxing-ccx"></a>Kutulama (C++/CX)

*Kutulama* , değişken türü olarak [Platform:: Object ^](../cppcx/platform-object-class.md) ' i alan bir yönteme geçirildiğinde, [Windows:: Foundation::D atetime](/uwp/api/windows.foundation.datetime)gibi bir değer türü değişkeni veya bir temel skaler `int`tür (bir başvuru sınıfında) sarmalandır .

## <a name="passing-a-value-type-to-an-object-parameter"></a>Bir nesne ^ parametresine değer türü geçirme

[Platform:: Object ^](../cppcx/platform-object-class.md)türünde bir yöntem parametresine iletmek için bir değişkeni açıkça kutulanabilir olsanız da, daha önce paketlenmiş değerleri alırken özgün türe açıkça geri dönüştürme yapmanız gerekir.

[!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]

### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Nullable değer türlerini desteklemek için Platform\<:: ibox T > kullanma

C#ve Visual Basic Nullable değer türleri kavramını destekler. /CX C++içinde, null yapılabilir değer türü `Platform::IBox<T>` parametrelerini destekleyen ortak yöntemleri açığa çıkarmak için türünü kullanabilirsiniz. Aşağıdaki örnek, bir C++ C# çağıran bağımsız değişkenlerden biri için null geçirdiğinde null döndüren bir/CX ortak yöntemi gösterir.

[!code-cpp[cx_boxing#02](../cppcx/codesnippet/CPP/cx_boxing/class1.h#02)]

C# Xaml istemcisinde şu şekilde kullanabilirsiniz:

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
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
