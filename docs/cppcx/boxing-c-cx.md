---
title: Kutulama (C + +/ CX)
ms.date: 12/30/2016
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
ms.openlocfilehash: 3c281229b509ef72d37400b2088a6663be1afe42
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750760"
---
# <a name="boxing-ccx"></a>Kutulama (C + +/ CX)

*Kutulama* bir değer türü değişkeni gibi sarmalama [Windows::Foundation::DateTime](/uwp/api/windows.foundation.datetime)— ya da temel bir skalar türü gibi `int`— değişken alan bir yönteme geçildiğinde bir başvuru sınıfındaki [ Platform::Object ^](../cppcx/platform-object-class.md) giriş türü olarak.

## <a name="passing-a-value-type-to-an-object-parameter"></a>Bir değer türü bir nesneye geçirme ^ parametre

Bir değişken türü için bir yöntem parametresi geçirmek için açıkça kutusunda zorunda değilsiniz [Platform::Object ^](../cppcx/platform-object-class.md), daha önce Kutulu değerleri aldığınızda açıkça yeniden orijinal türüne sahip.

[!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]

### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Platform::ıbox kullanarak\<T > boş değer atanabilen değer türleri desteklemek için

C# ve Visual Basic'te boş değer atanabilen değer türleri kavramını destekler. C + +/ CX, kullanabileceğiniz `Platform::IBox<T>` null yapılabilir değer türü parametrelerini destekleyen genel yöntemleri açığa türü. Aşağıdaki örnekte gösterilmektedir C + +/ C# çağıran bağımsız değişkenlerden biri null başarılı olduğunda, null döndüren CX genel yöntem.

[!code-cpp[cx_boxing#02](../cppcx/codesnippet/CPP/cx_boxing/class1.h#02)]

C# XAML istemcisinde, onu şöyle raporlarını kullanabilirsiniz:

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
[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)
