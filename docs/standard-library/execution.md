---
description: 'Daha fazla bilgi edinin: &lt; yürütme&gt;'
title: '&lt;yürütme&gt;'
ms.date: 01/15/2021
f1_keywords:
- <execution>
- execution/std::execution
- std::execution
helpviewer_keywords:
- execution header
ms.openlocfilehash: 2ffba3ad8620092676588c2a67e36cf8956413ba
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667483"
---
# `<execution>`

Paralel algoritmaların yürütme ilkelerini açıklar.

## <a name="syntax"></a>Syntax

```cpp
namespace std {
    template<class T> inline constexpr bool is_execution_policy_v = is_execution_policy<T>::value;
}
namespace std::execution {
    inline constexpr sequenced_policy seq { unspecified };
    inline constexpr parallel_policy par { unspecified };
    inline constexpr parallel_unsequenced_policy par_unseq { unspecified };
}
```

### <a name="classes-and-structs"></a>Sınıflar ve Yapılar

|Ad|Açıklama|
|-|-|
|[`is_execution_policy` Sýný](is-execution-policy-struct.md)|Bazı işlev imzalarını, aksi takdirde belirsiz aşırı yükleme çözümlemesi katılımından hariç tutmak için yürütme ilkelerini algılar.|
|[`parallel_policy` Sınıfı](parallel-policy-class.md)|Paralel algoritma aşırı yüklemesini belirsizliğini ortadan kaldırmak için benzersiz bir tür olarak kullanılır. Paralel algoritma yürütmenin paralelleştirilmesine işaret olabileceğini belirtir.|
|[`parallel_unsequenced_policy` Sınıfı](parallel-unsequenced-policy-class.md)|Paralel algoritma aşırı yüklemesini belirsizliğini ortadan kaldırmak için benzersiz bir tür olarak kullanılır. Bir paralel algoritma yürütmenin paralelleştirilmesine ve vektörleştirilmesine sahip olabileceğini belirtir.|
|[`sequenced_policy` Sınıfı](sequenced-policy-class.md)|Paralel algoritma aşırı yüklemesini belirsizliğini ortadan kaldırmak için benzersiz bir tür olarak kullanılır. Paralel algoritma yürütmenin paralelleştirilmesine neden olabileceğini belirtir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<execution>

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](cpp-standard-library-reference.md)
