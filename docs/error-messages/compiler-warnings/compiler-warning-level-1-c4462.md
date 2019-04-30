---
title: Derleyici Uyarısı (düzey 1) C4462
ms.date: 10/25/2017
f1_keywords:
- C4462
helpviewer_keywords:
- C4462
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
ms.openlocfilehash: bd4d5c1fd7dd8d7419fc901149ceab7e769e7076
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404058"
---
# <a name="compiler-warning-level-1-c4462"></a>Derleyici Uyarısı (düzey 1) C4462

> Türün GUID'i belirlenemiyor. Program çalışma zamanında başarısız olabilir.

Bir Windows çalışma zamanı uygulama veya bileşen genel olduğunda c4462 uyarısı meydana gelir `TypedEventHandler` tür parametrelerinden biri olarak kapsayan sınıfa bir başvuru içeriyor.

Bu uyarı, bir hata için otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, [#pragma Uyarısı](../../preprocessor/warning.md). Örneğin, bir düzey 4 uyarısı sorunu C4462 yapmak için kaynak kodu dosyanızda bu satırı ekleyin:

```cpp
#pragma warning(4:4462)
```

## <a name="example"></a>Örnek

Bu örnek C4462 uyarısı oluşturur:

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

Türün GUID'i `Windows::Foundation::TypedEventHandler<R^, EventArgs^>^` yalnızca türü başka bir bileşenden erişim sağlandığında kullanılır. İlk geçici çözüm, çözüm uygulandıktan sonra yalnızca kendi bileşeni içinden erişilebilir olduğu için işe yarayacaktır. Aksi durumda, derleyici en kötü durumu varsayarak uyarıyı yaymak zorunda kalır.
