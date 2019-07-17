---
title: '&lt;Yürütme&gt;'
ms.date: 04/18/2019
f1_keywords:
- <execution>
- std::<execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: 3bce34019f9ed4880d72a9d16c3c8b78dde0e0e3
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68267882"
---
# <a name="ltexecutiongt"></a>&lt;Yürütme&gt;

Paralel algoritmalar için yürütme ilkelerini açıklar.

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
|[is_execution_policy yapısı](is-execution-policy-struct.md)|Aksi takdirde belirsiz aşırı yükleme çözünürlüğü katılım işlev imzası hariç amacıyla yürütme ilkelerini algılar.|
|[parallel_policy sınıfı](parallel-policy-class.md)|Paralel algoritma aşırı yükleme belirsizliği ortadan kaldırmak ve bir paralel algoritma 's yürütme paralel belirtmek için benzersiz bir türü olarak kullanılır.|
|[parallel_unsequenced_policy sınıfı](parallel-unsequenced-policy-class.md)|Benzersiz bir türü paralel algoritma aşırı yükleme belirsizliği ortadan kaldırmak ve bir paralel algoritma 's yürütme paralel ve vektörleştirildi olduğunu belirtmek için kullanılır.|
|[sequenced_policy sınıfı](sequenced-policy-class.md)|Gerektiren paralel algoritma 's yürütme paralel ve paralel algoritma aşırı yükleme belirsizliği ortadan kaldırmak için benzersiz bir türü olarak kullanılır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yürütme >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](cpp-standard-library-reference.md)
