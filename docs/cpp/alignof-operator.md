---
description: 'Daha fazla bilgi edinin: hizalama Işleci'
title: hizalama Işleci
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
ms.openlocfilehash: b7e053b932ed631d8b03dc1b89f6857905740e5a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288320"
---
# <a name="alignof-operator"></a>hizalama Işleci

**`alignof`** İşleci, belirtilen türün bayt cinsinden hizalamasını tür değeri olarak döndürür **`size_t`** .

## <a name="syntax"></a>Syntax

```cpp
alignof( type )
```

## <a name="remarks"></a>Açıklamalar

Örneğin:

| Expression | Değer |
|--|--|
| **`alignof( char )`** | 1 |
| **`alignof( short )`** | 2 |
| **`alignof( int )`** | 4 |
| **`alignof( long long )`** | 8 |
| **`alignof( float )`** | 4 |
| **`alignof( double )`** | 8 |

**`alignof`** Değer, **`sizeof`** temel türler için değeriyle aynıdır. Ancak şu örneği göz önünde bulundurun:

```cpp
typedef struct { int a; double b; } S;
// alignof(S) == 8
```

Bu durumda, **`alignof`** değer yapıdaki en büyük öğenin hizalama gereksinimidir.

Benzer şekilde, için

```cpp
typedef __declspec(align(32)) struct { int a; } S;
```

`alignof(S)` eşittir `32` .

Bir kullanımı, **`alignof`** kendi bellek ayırma yordamlarınızın bir parametresi olarak olacaktır. Örneğin, aşağıdaki tanımlı yapı verildiğinde `S` , `aligned_malloc` belirli bir hizalama sınırında bellek ayırmak için adlı bir bellek ayırma yordamını çağırabilirsiniz.

```cpp
typedef __declspec(align(32)) struct { int a; double b; } S;
int n = 50; // array size
S* p = (S*)aligned_malloc(n * sizeof(S), alignof(S));
```

Hizalamayı değiştirme hakkında daha fazla bilgi için bkz.:

- [pack](../preprocessor/pack.md)

- [acaktır](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [/Zp (yapı üyesi hizalama)](../build/reference/zp-struct-member-alignment.md)

- [Yapı hizalaması örnekleri](../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 'e özgü)

X86 ve x64 için kod hizalama farkları hakkında daha fazla bilgi için bkz.:

- [x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)

### <a name="microsoft-specific"></a>Microsoft'a özgü

**`alignof`** ve, **`__alignof`** Microsoft derleyicisinde eş anlamlılar. C++ 11 ' de standart bir parçası haline gelmeden önce, Microsoft 'a özgü **`__alignof`** işleç bu işlevselliği sağladı. Maksimum taşınabilirlik için, **`alignof`** Microsoft 'a özgü işleç yerine işlecini kullanmanız gerekir **`__alignof`** .

Önceki sürümlerle uyumluluk için, **`_alignof`** **`__alignof`** derleyici seçeneği [ `/Za` \( dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) ' ın belirtildiği durumlar için bir eş anlamlı olur.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
