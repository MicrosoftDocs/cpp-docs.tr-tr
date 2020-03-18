---
title: __alignof İşleci
ms.date: 12/17/2018
f1_keywords:
- __alignof_cpp
- alignof_cpp
- __alignof
- _alignof
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
ms.openlocfilehash: b3764e95846d48d293991d69d04bc71c6b3aed90
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443610"
---
# <a name="__alignof-operator"></a>__alignof İşleci

C++ 11, belirtilen türün bayt cinsinden hizalamasını döndüren **bir işlecin hizalamasını** tanıtır. En fazla taşınabilirlik için, Microsoft 'a özgü __alignof işleci yerine hizalama işlecini kullanmanız gerekir.

**Microsoft 'a özgü**

Türün hizalama gereksinimi olan `size_t` türünde bir değer döndürür.

## <a name="syntax"></a>Sözdizimi

```cpp
  __alignof( type )
```

## <a name="remarks"></a>Açıklamalar

Örnek:

|İfadeler|Değer|
|----------------|-----------|
|**__alignof (Char)**|1|
|**__alignof (kısa)**|2|
|**__alignof (int)**|4|
|**__alignof (\__int64)**|8|
|**__alignof (float)**|4|
|**__alignof (çift)**|8|
|**__alignof (Char\*)**|4|

**__Alignof** değeri, temel türler için `sizeof` değeri ile aynıdır. Ancak şu örneği göz önünde bulundurun:

```cpp
typedef struct { int a; double b; } S;
// __alignof(S) == 8
```

Bu durumda **__alignof** değeri, yapıdaki en büyük öğenin hizalama gereksinimidir.

Benzer şekilde, için

```cpp
typedef __declspec(align(32)) struct { int a; } S;
```

`__alignof(S)`, `32`eşittir.

**__Alignof** için bir kullanım, kendi bellek ayırma yordamlarınızın bir parametresi olarak olacaktır. Örneğin, aşağıdaki tanımlı yapı `S`verildiğinde, belirli bir hizalama sınırında bellek ayırmak için `aligned_malloc` adlı bir bellek ayırma yordamını çağırabilirsiniz.

```cpp
typedef __declspec(align(32)) struct { int a; double b; } S;
int n = 50; // array size
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));
```

Önceki sürümlerle uyumluluk için, [/za \(dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde, **_alignof** **__alignof** için bir eş anlamlı.

Hizalamayı değiştirme hakkında daha fazla bilgi için bkz.:

- [pack](../preprocessor/pack.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [/Zp (Yapı Üyesi Hizalama)](../build/reference/zp-struct-member-alignment.md)

- [Yapı hizalaması örnekleri](../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 'e özgü)

X86 ve x64 için kod hizalama farkları hakkında daha fazla bilgi için bkz.:

- [x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)