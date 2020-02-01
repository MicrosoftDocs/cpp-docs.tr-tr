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
ms.openlocfilehash: 395f1443f4eef16d9eea44c23a6e3288daf03d14
ms.sourcegitcommit: c4528a7424d35039454f17778baf1b5f98fbbee7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912836"
---
# <a name="__identifier-ccli"></a>__tanımlayıcı (C++/CLI)

C++ Anahtar sözcüklerin tanımlayıcı olarak kullanılmasına izin vermez.

## <a name="all-platforms"></a>Tüm Platformlar

### <a name="syntax"></a>Sözdizimi

```cpp
__identifier(C++_keyword)
```

### <a name="remarks"></a>Açıklamalar

Anahtar sözcük olmayan tanımlayıcılara izin verilen **__identifier** anahtar sözcüğünün kullanımı, ancak stil açısından kesinlikle önerilmez.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

### <a name="examples"></a>Örnekler

**Örnek**

Aşağıdaki örnekte, **şablon** adlı bir sınıf içinde C# oluşturulur ve DLL olarak dağıtılır. **Şablon** sınıfını C++kullanan/CLI programında, **__identifier** anahtar sözcüğü, **şablonun** standart C++ bir anahtar sözcük olduğunu bir şekilde gizleme.

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

**__İdentifier** anahtar sözcüğü `/clr` derleyici seçeneği ile geçerlidir.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnekte, **şablon** adlı bir sınıf içinde C# oluşturulur ve DLL olarak dağıtılır. **Şablon** sınıfını C++kullanan/CLI programında, **__identifier** anahtar sözcüğü, **şablonun** standart C++ bir anahtar sözcük olduğunu bir şekilde gizleme.

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

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)<br/>
[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)