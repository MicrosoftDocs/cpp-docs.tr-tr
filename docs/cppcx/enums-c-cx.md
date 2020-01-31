---
title: NumaralandırmalarC++(/CX)
ms.date: 12/30/2016
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
ms.openlocfilehash: be11d8d8f38a92fbe4be00eed53dd5226bab0b59
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821759"
---
# <a name="enums-ccx"></a>NumaralandırmalarC++(/CX)

C++/CX, standart C++ bir `scoped  enum`benzer `public enum class` anahtar sözcüğünü destekler. `public enum class` anahtar sözcüğü kullanılarak tanımlanmış bir Numaralandırıcı kullandığınızda, her bir Numaralandırıcı değerini atamak için numaralandırma tanımlayıcıyı kullanmanız gerekir.

### <a name="remarks"></a>Açıklamalar

`public`gibi bir erişim belirticisi olmayan `public enum class` standart C++ [kapsamlı bir sabit listesi](../cpp/enumerations-cpp.md)olarak değerlendirilir.

Bir `public enum class` veya `public enum struct` bildirimi herhangi bir integral türünün temel bir türüne sahip olabilir, ancak Windows Çalışma Zamanı kendisi türün Int32 veya bir Flags numaralandırması için uint32 gerektirir. Aşağıdaki sözdizimi bir `public enum class` veya `public enum struct`parçalarını açıklar.

Bu örnek, genel bir numaralandırma sınıfının nasıl tanımlanacağını göstermektedir:

[!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]

Bu sonraki örnek, nasıl kullanacağınızı gösterir:

[!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]

### <a name="examples"></a>Örnekler

Sonraki örneklerde, bir numaralandırmanın nasıl bildirildiği gösterilmektedir.

[!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]

Sonraki örnek, sayısal eşdeğerlerine nasıl tür bir dönüştürme yapılacağını gösterir ve karşılaştırmaları gerçekleştirir. Numaralandırıcı `One` kullanımı, `Enum1` numaralandırma tanımlayıcısının kapsamında olduğunu ve Numaralandırıcı `First` `Enum2`tarafından kapsamlandırıldığına dikkat edin.

[!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
