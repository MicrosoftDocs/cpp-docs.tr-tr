---
title: NumaralandırmalarC++(/CX)
ms.date: 12/30/2016
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
ms.openlocfilehash: 3bdcff03872dcfe83f0be5752cec4f567fbc6b72
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740220"
---
# <a name="enums-ccx"></a>NumaralandırmalarC++(/CX)

C++/CX, bir `public enum class` standart C++ `scoped  enum`için anaangou olan anahtar sözcüğünü destekler. `public enum class` Anahtar sözcüğü kullanılarak tanımlanmış bir Numaralandırıcı kullandığınızda, her bir Numaralandırıcı değerini atamak için numaralandırma tanımlayıcıyı kullanmanız gerekir.

### <a name="remarks"></a>Açıklamalar

Gibi `public enum class` bir erişim belirticisi `public`olmayan bir standart C++ [kapsamlı numaralandırma](../cpp/enumerations-cpp.md)olarak kabul edilir.

`public enum class` Ya`public enum struct` da bildiriminde, türün kendisi tür Int32 veya bir bayrak numaralandırması için uint32 olması gerektiğinden, herhangi bir integral Windows çalışma zamanı türünde temel alınan bir tür olabilir. Aşağıdaki sözdizimi bir `public enum class` veya `public enum struct`parçalarını açıklar.

Bu örnek, genel bir numaralandırma sınıfının nasıl tanımlanacağını göstermektedir:

[!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]

Bu sonraki örnek, nasıl kullanacağınızı gösterir:

[!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]

### <a name="examples"></a>Örnekler

Sonraki örneklerde, bir numaralandırmanın nasıl bildirildiği gösterilmektedir.

[!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]

Sonraki örnek, sayısal eşdeğerlerine nasıl tür bir dönüştürme yapılacağını gösterir ve karşılaştırmaları gerçekleştirir. Numaralandırıcı `One` kullanımı, `Enum1` numaralandırma tanımlayıcısı tarafından kapsamlandırıldığına ve Numaralandırıcının `First` kapsamına göre `Enum2`belirlenir.

[!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
