---
title: Derleyici Uyarısı (düzey 1) C4462 | Microsoft Docs
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4462
dev_langs:
- C++
helpviewer_keywords:
- C4462
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 105a78fe9f8a8d2b6442c9b403af0266de53d3b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281407"
---
# <a name="compiler-warning-level-1-c4462"></a>Derleyici Uyarısı (düzey 1) C4462

> Türün GUID'i belirlenemiyor. Program çalışma zamanında başarısız olabilir.

Bir Windows çalışma zamanı uygulama veya bileşenin genel olduğunda uyarı C4462 oluşur `TypedEventHandler` türü parametrelerinden biri olarak kapsayan sınıfı bir başvuru içeriyor.

Bu uyarı için bir hata otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, kullanmak [#pragma Uyarısı](../../preprocessor/warning.md). Örneğin, bir düzey 4 uyarı sorunu yaşayıp C4462 yapmak için kaynak kodu dosyasına bu satırı ekleyin:

```cpp
#pragma warning(4:4462)
```

## <a name="example"></a>Örnek

Bu örnek uyarı C4462 oluşturur:

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

Türünde bir GUID `Windows::Foundation::TypedEventHandler<R^, EventArgs^>^` türü başka bir bileşenden erişildiğinde yalnızca kullanılır. İlk geçici çözüm, çözüm uygulandıktan sonra yalnızca kendi bileşeni içinden erişilebilir olduğu için işe yarayacaktır. Aksi durumda, derleyici en kötü durumu varsayarak uyarıyı yaymak zorunda kalır.
