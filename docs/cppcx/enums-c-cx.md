---
description: 'Daha fazla bilgi edinin: Numaralandırmalar (C++/CX)'
title: Numaralandırmalar (C++/CX)
ms.date: 12/30/2016
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
ms.openlocfilehash: cdf058dc1549a8bc483127cffaeb347492d80716
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341964"
---
# <a name="enums-ccx"></a>Numaralandırmalar (C++/CX)

C++/CX, `public enum class` Standart C++ ile benzer olan anahtar sözcüğünü destekler `scoped  enum` . Anahtar sözcüğü kullanılarak tanımlanmış bir Numaralandırıcı kullandığınızda `public enum class` , her bir Numaralandırıcı değerini atamak için numaralandırma tanımlayıcıyı kullanmanız gerekir.

### <a name="remarks"></a>Açıklamalar

Gibi bir erişim belirticisi olmayan bir, `public enum class` **`public`** Standart C++ [kapsamlı numaralandırma](../cpp/enumerations-cpp.md)olarak değerlendirilir.

`public enum class`Ya da `public enum struct` bildiriminde, türün kendisi tür Int32 veya bir bayrak numaralandırması için uint32 olması gerektiğinden, herhangi bir integral Windows çalışma zamanı türünde temel alınan bir tür olabilir. Aşağıdaki sözdizimi bir veya parçalarını açıklar `public enum class` `public enum struct` .

Bu örnek, genel bir numaralandırma sınıfının nasıl tanımlanacağını göstermektedir:

[!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]

Bu sonraki örnek, nasıl kullanacağınızı gösterir:

[!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]

### <a name="examples"></a>Örnekler

Sonraki örneklerde, bir numaralandırmanın nasıl bildirildiği gösterilmektedir.

[!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]

Sonraki örnek, sayısal eşdeğerlerine nasıl tür bir dönüştürme yapılacağını gösterir ve karşılaştırmaları gerçekleştirir. Numaralandırıcı kullanımı, `One` numaralandırma tanımlayıcısı tarafından kapsamlandırıldığına `Enum1` ve Numaralandırıcının `First` kapsamına göre belirlenir `Enum2` .

[!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]

## <a name="see-also"></a>Ayrıca bkz.

[Tür sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX dil başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md)
