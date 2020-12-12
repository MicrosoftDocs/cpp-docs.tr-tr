---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4462'
title: Derleyici Uyarısı (düzey 1) C4462
ms.date: 10/25/2017
f1_keywords:
- C4462
helpviewer_keywords:
- C4462
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
ms.openlocfilehash: 81696df228b2cbe6278521f602d2a6f986cacb13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212538"
---
# <a name="compiler-warning-level-1-c4462"></a>Derleyici Uyarısı (düzey 1) C4462

> Türün GUID'i belirlenemiyor. Program çalışma zamanında başarısız olabilir.

Uyarı C4462, bir ortak `TypedEventHandler` , tür parametrelerinden biri kapsayan sınıfa bir başvuru olarak olduğunda Windows çalışma zamanı bir uygulamada veya bileşende oluşur.

Bu uyarı otomatik olarak bir hataya yükseltilir. Bu davranışı değiştirmek isterseniz [#pragma uyarı](../../preprocessor/warning.md)kullanın. Örneğin, C4462 4. düzey bir uyarı sorununa dönüştürmek için, bu satırı kaynak kodu dosyanıza ekleyin:

```cpp
#pragma warning(4:4462)
```

## <a name="example"></a>Örnek

Bu örnek, uyarı C4462 oluşturur:

```cpp
namespace N
{
    public ref struct EventArgs sealed {};
    public ref struct R sealed
    {
        R() {}
        event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
    };
}

[Platform::MTAThread]
int main()
{
    auto x = ref new N::R();
}
```

Hataya geçici bir çözüm bulmanın iki yolu vardır. Bunlardan birinde, bir sonraki örnekte gösterildiği gibi, olaya dahili erişilebilirlik vererek onun aynı yürütülebilir dosya üzerinde kodun kullanımına açık olması, aynı zamanda diğer Windows Çalışma Zamanı bileşenlerinde kodun kullanımına açık olmaması sağlanabilir.

```cpp
internal:
    event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
```

Olayın genel olması gerekiyorsa, ikinci yöntem kullanılabilir, yani olay varsayılan arabirim yoluyla genele açılabilir:

```cpp
ref struct R;
public interface struct IR{ event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;};

public ref struct R sealed : [Windows::Foundation::Metadata::Default] IR
{
    R() {}
    virtual event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
};
```

Türün GUID 'ı `Windows::Foundation::TypedEventHandler<R^, EventArgs^>^` yalnızca türe başka bir bileşenden erişildiğinde kullanılır. İlk geçici çözüm, çözüm uygulandıktan sonra yalnızca kendi bileşeni içinden erişilebilir olduğu için işe yarayacaktır. Aksi durumda, derleyici en kötü durumu varsayarak uyarıyı yaymak zorunda kalır.
