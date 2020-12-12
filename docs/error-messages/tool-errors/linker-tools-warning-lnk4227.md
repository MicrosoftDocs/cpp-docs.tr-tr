---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4227'
title: Bağlayıcı Araçları Uyarısı LNK4227
ms.date: 11/04/2016
f1_keywords:
- LNK4227
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
ms.openlocfilehash: d8fd0f6755b675490f35579a4609c5b2742e4e46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180428"
---
# <a name="linker-tools-warning-lnk4227"></a>Bağlayıcı Araçları Uyarısı LNK4227

> meta veri işlemi Uyarısı (*HRESULT*): *warning_message*

Bağlayıcı birleştirilirken meta veri farklılıkları algıladı:

- Şu anda oluşturulmakta olan bütünleştirilmiş koda sahip bir veya daha fazla başvurulan derleme.

- Bir derlemedeki bir veya daha fazla kaynak kodu dosyası.

Örneğin, LNK4227 aynı ada sahip iki genel işlevleriniz varsa, ancak parametre bilgileri farklı şekilde bildirilirse (yani, bildirimler tüm uygulamalarda tutarlı değildir) olabilir. Türlerin nasıl farklı olduğunu görmek için her. obj dosyasında ildasm.exe/TEXT/METADATA *object_file* kullanın.

LNK4227, başka bir araçla kaynaklanan sorunları raporlamak için de kullanılır. Daha fazla bilgi için uyarı iletisini arayın.

Uyarı çözümlemek için meta veri sorunları düzeltilmelidir.

## <a name="examples"></a>Örnekler

Başvurulan bir derleme kendisine başvuran derlemeden farklı şekilde imzalanmışsa, LNK4227 oluşturulur.

Aşağıdaki örnek LNK4227 oluşturur:

```cpp
// LNK4227.cpp
// compile with: /clr
using namespace System::Reflection;

[assembly:AssemblyDelaySignAttribute(false)];

int main() {}
```

ardından,

```cpp
// LNK4227b.cpp
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe
using namespace System::Reflection;
using namespace System::Runtime::CompilerServices;

[assembly:AssemblyDelaySignAttribute(true)];
// Try the following line instead
// [assembly:AssemblyDelaySignAttribute(false)];

ref class MyClass
{
};
```

Ayrıca, yanlış biçimdeki sürüm numaraları derleme özniteliklerine geçirildiğinde de LNK4227 oluşturulabilir.  ' * ' Gösterimi öğesine özeldir `AssemblyVersionAttribute` .  Bu uyarıyı çözmek için yalnızca sürüm özniteliklerinde dışındaki sayıları kullanın `AssemblyVersionAttribute` .

Aşağıdaki örnek LNK4227 oluşturur:

```cpp
// LNK4227e.cpp
// compile with: /clr /LD /W1
using namespace System::Reflection;
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227
// try the following line instead
// [assembly:AssemblyFileVersionAttribute("2.3")];
```
