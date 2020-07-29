---
title: __tanımlayıcı (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- __identifier
- __identifier_cpp
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
ms.openlocfilehash: 5f95e9fc55acd33705b855c7c4f0ef268d4776a0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219696"
---
# <a name="__identifier-ccli"></a>__tanımlayıcı (C++/CLI)

C++ anahtar sözcüklerinin tanımlayıcı olarak kullanılmasına izin vermez.

## <a name="all-platforms"></a>Tüm Platformlar

### <a name="syntax"></a>Sözdizimi

```cpp
__identifier(C++_keyword)
```

### <a name="remarks"></a>Açıklamalar

Anahtar sözcük olmayan tanımlayıcılara izin verilen **__identifier** anahtar sözcüğünün kullanımı, ancak stil açısından kesinlikle önerilmez.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/ZW`

### <a name="examples"></a>Örnekler

**Örnek**

Aşağıdaki örnekte, adlı bir sınıf `template` C# dilinde oluşturulur ve DLL olarak dağıtılır. Sınıfını kullanan C++/CLı programında `template` , **`__identifier`** anahtar sözcüğü `template` Standart C++ anahtar sözcüğü olan olguyu gizleme.

```csharp
// identifier_template.cs
// compile with: /target:library
public class template {
   public void Run() { }
}
```

```cpp
// keyword__identifier.cpp
// compile with: /ZW
#using <identifier_template.dll>
int main() {
   __identifier(template)^ pTemplate = ref new __identifier(template)();
   pTemplate->Run();
}
```

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

**__İdentifier** anahtar sözcüğü, `/clr` derleyici seçeneği ile geçerlidir.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnekte, adlı bir sınıf `template` C# dilinde oluşturulur ve DLL olarak dağıtılır. Sınıfını kullanan C++/CLı programında `template` , **`__identifier`** anahtar sözcüğü `template` Standart C++ anahtar sözcüğü olan olguyu gizleme.

```csharp
// identifier_template.cs
// compile with: /target:library
public class template {
   public void Run() { }
}
```

```cpp
// keyword__identifier.cpp
// compile with: /clr
#using <identifier_template.dll>

int main() {
   __identifier(template) ^pTemplate = gcnew __identifier(template)();
   pTemplate->Run();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)<br/>
[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
