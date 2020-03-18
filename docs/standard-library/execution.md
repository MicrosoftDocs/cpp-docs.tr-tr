---
title: '&lt;yürütme&gt;'
ms.date: 04/18/2019
f1_keywords:
- <execution>
- std::<execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: 81e9aa63265c367412fda709aacd5ca3953e9fdf
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445034"
---
# <a name="ltexecutiongt"></a>&lt;yürütme&gt;

Paralel algoritmaların yürütme ilkelerini açıklar.

## <a name="syntax"></a>Sözdizimi

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

|||
|-|-|
|[is_execution_policy yapısı](is-execution-policy-struct.md)|Aksi takdirde belirsiz aşırı yükleme çözümlemesi katılımında işlev imzalarını dışlamamak amacıyla yürütme ilkelerini algılar.|
|[parallel_policy sınıfı](parallel-policy-class.md)|Paralel algoritma aşırı yüklemesini belirsizliği ortadan kaldırmak için benzersiz bir tür olarak kullanılır ve paralel algoritma yürütmenin paralelleştirilmesine işaret edilebilir.|
|[parallel_unsequenced_policy sınıfı](parallel-unsequenced-policy-class.md)|Paralel algoritma aşırı yüklemesini netleştirmek için benzersiz bir tür olarak kullanılır ve bir paralel algoritma yürütmenin paralelleştirilmiş ve vektörleştirilmemiş olabileceğini belirtir.|
|[sequenced_policy sınıfı](sequenced-policy-class.md)|Paralel algoritma aşırı yüklemesini ayırt etmek için benzersiz bir tür olarak kullanılır ve paralel algoritma yürütmenin paralelleştirilmesine gerek yoktur.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yürütme >

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)\
[Standart kitaplıkta Iş parçacığı güvenliği\ C++ ](thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](cpp-standard-library-reference.md)
