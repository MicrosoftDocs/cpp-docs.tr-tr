---
description: 'Daha fazla bilgi edinin: &lt; yürütme&gt;'
title: '&lt;yürütme&gt;'
ms.date: 04/18/2019
f1_keywords:
- <execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: 7603bc6a78671482f691f15f83f51439a5002870
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126578"
---
# <a name="ltexecutiongt"></a>&lt;yürütme&gt;

Paralel algoritmaların yürütme ilkelerini açıklar.

## <a name="syntax"></a>Syntax

```
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
|[is_execution_policy yapısı](is-execution-policy-struct.md)|Aksi takdirde belirsiz aşırı yükleme çözümlemesi katılımında işlev imzalarını dışlamamak amacıyla yürütme ilkelerini algılar.|
|[parallel_policy sınıfı](parallel-policy-class.md)|Paralel algoritma aşırı yüklemesini belirsizliği ortadan kaldırmak için benzersiz bir tür olarak kullanılır ve paralel algoritma yürütmenin paralelleştirilmesine işaret edilebilir.|
|[parallel_unsequenced_policy sınıfı](parallel-unsequenced-policy-class.md)|Paralel algoritma aşırı yüklemesini netleştirmek için benzersiz bir tür olarak kullanılır ve bir paralel algoritma yürütmenin paralelleştirilmiş ve vektörleştirilmemiş olabileceğini belirtir.|
|[sequenced_policy sınıfı](sequenced-policy-class.md)|Paralel algoritma aşırı yüklemesini ayırt etmek için benzersiz bir tür olarak kullanılır ve paralel algoritma yürütmenin paralelleştirilmesine gerek yoktur.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<execution>

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](cpp-standard-library-reference.md)
