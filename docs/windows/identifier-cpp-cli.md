---
title: __tanımlayıcı (c + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- __identifier
- __identifier_cpp
dev_langs:
- C++
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d578c820660d99e6fa217a14181330d258ab081b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613328"
---
# <a name="identifier-ccli"></a>__tanımlayıcı (C++/CLI)

Tanımlayıcı olarak Visual C++ anahtar sözcükleri kullanımını etkinleştirir.

## <a name="all-platforms"></a>Tüm Platformlar

### <a name="syntax"></a>Sözdizimi

```cpp
__identifier(
Visual_C++_keyword
)  
```

### <a name="remarks"></a>Açıklamalar

Kullanım **__tanımlayıcı** anahtar sözcüğü olmayan anahtar sözcükler tanımlayıcılar için izin verilen ancak stil sağlasa da kesinlikle önerilmez.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

### <a name="examples"></a>Örnekler

**Örnek**

Aşağıdaki örnekte, bir sınıf adlı **şablon** C# içinde oluşturulan ve bir DLL olarak dağıtılmış. Kullanan Visual C++ programında **şablon** sınıfı **__tanımlayıcı** anahtar sözcüğü gizlendiğinden olgu, **şablon** standart bir C++ anahtar sözcüğüdür.

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

Aşağıdaki örnekte, bir sınıf adlı **şablon** C# içinde oluşturulan ve bir DLL olarak dağıtılmış. Kullanan Visual C++ programında **şablon** sınıfı **__tanımlayıcı** anahtar sözcüğü gizlendiğinden olgu, **şablon** standart bir C++ anahtar sözcüğüdür.

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

## <a name="see-also"></a>Ayrıca Bkz.

[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)  
[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)