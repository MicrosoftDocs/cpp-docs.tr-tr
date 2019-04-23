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
ms.openlocfilehash: 80aade53bf1d1c9aa30c4b8c8fe59c2247fe3cfb
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034517"
---
# <a name="identifier-ccli"></a>__tanımlayıcı (C++/CLI)

Tanımlayıcı olarak C++ anahtar sözcükleri kullanımını etkinleştirir.

## <a name="all-platforms"></a>Tüm Platformlar

### <a name="syntax"></a>Sözdizimi

```cpp
__identifier(C++_keyword)
```

### <a name="remarks"></a>Açıklamalar

Kullanım **__tanımlayıcı** anahtar sözcüğü olmayan anahtar sözcükler tanımlayıcılar için izin verilen ancak stil sağlasa da kesinlikle önerilmez.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

### <a name="examples"></a>Örnekler

**Örnek**

Aşağıdaki örnekte, bir sınıf adlı **şablon** C# içinde oluşturulan ve bir DLL olarak dağıtılmış. İçinde C++kullanan /CLI programı **şablon** sınıfı **__tanımlayıcı** anahtar sözcüğü gizlendiğinden olgu, **şablon** standardıdır C++ anahtar sözcüğü.

```cs
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

**__Tanımlayıcı** anahtar sözcüğü ile geçerli `/clr` derleyici seçeneği.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnekte, bir sınıf adlı **şablon** C# içinde oluşturulan ve bir DLL olarak dağıtılmış. İçinde C++kullanan /CLI programı **şablon** sınıfı **__tanımlayıcı** anahtar sözcüğü gizlendiğinden olgu, **şablon** standardıdır C++ anahtar sözcüğü.

```cs
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