---
title: Bağlayıcı araçları uyarısı LNK4227 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4227
dev_langs:
- C++
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28bcf242e48046278030ec4259b7ae3edd1c4a61
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088871"
---
# <a name="linker-tools-warning-lnk4227"></a>Bağlayıcı Araçları Uyarısı LNK4227

> meta veri işlemi Uyarısı (*HRESULT*): *warning_message*

Bağlayıcı birleştirilirken meta verileri farklılıklar algılandı:

- Bir veya daha fazla başvurulan derlemeleri şu anda yerleşik derlemeyi ile.

- Bir veya daha fazla kaynak kodu dosyalarını bir derleme.

İki genel işlevleri ile aynı ada ancak farklı bildirilen parametre bilgileri varsa, örneğin, LNK4227 neden olabilir (diğer bir deyişle, bildirimleri tüm derleme içinde tutarlı değil). İldasm.exe/Text kullanın metadata *object_file* türleri farkı görmek için her .obj dosyası üzerinde.

LNK4227 de başka bir araçla kaynaklanan sorunları bildirmek için kullanılır. Daha fazla bilgi için uyarı iletisi arayın.

Uyarıyı çözmek için meta verileri sorunların düzeltilmesi gerekir.

## <a name="example"></a>Örnek

Başvurulan derlemeyi başvuran derlemenin farklı imzalandığında LNK4227 oluşturulur.

Aşağıdaki örnek, LNK4227 oluşturur:

```cpp
// LNK4227.cpp
// compile with: /clr
using namespace System::Reflection;

[assembly:AssemblyDelaySignAttribute(false)];

int main() {}
```

Ardından,

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

## <a name="example"></a>Örnek

Yanlış biçimde sürüm numaraları için derleme özniteliklerini geçirildiğinde LNK4227 de meydana gelebilir.  ' *' Gösterimi için belirli `AssemblyVersionAttribute`.  Bu uyarıyı çözmek için kullanım yalnızca sürüm öznitelikleri dışında sayı `AssemblyVersionAttribute`.

Aşağıdaki örnek, LNK4227 oluşturur:

```cpp
// LNK4227e.cpp
// compile with: /clr /LD /W1
using namespace System::Reflection;
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227
// try the following line instead
// [assembly:AssemblyFileVersionAttribute("2.3")];
```