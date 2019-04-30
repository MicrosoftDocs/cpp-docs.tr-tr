---
title: Numaralandırmalar (C++/CX)
ms.date: 12/30/2016
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
ms.openlocfilehash: f16a288a0b928b74ef42de5781fd1b54930927d6
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345812"
---
# <a name="enums-ccx"></a>Numaralandırmalar (C++/CX)

C++/CX destekler `public enum class` işlevdedir için standart bir anahtar sözcüğünü C++ `scoped  enum`. Kullanılarak bildirilen bir numaralandırıcı kullandığınızda `public enum class` anahtar sözcüğü her Numaralandırıcı değeri kapsam için numaralandırma tanımlayıcı kullanmalısınız.

### <a name="remarks"></a>Açıklamalar

A `public enum class` , bir erişim belirticisi gibi yok `public`, standart bir C++ kabul edilir [kapsamlı numaralandırma](../cpp/enumerations-cpp.md).

A `public enum class` veya `public enum struct` Windows Runtime türü Int32 veya bayrak sabit listesi için uint32 olmasını gerektirse de, bildirimi herhangi bir tamsayı türü türünü temel sahip olabilir. Aşağıdaki söz dizimini açıklar bölümlerini bir `public enum class` veya `public enum struct`.

Bu örnek bir genel liste sınıfın nasıl tanımlanacağını gösterir:

[!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]

Bu örnekte, tüketicilerimizin gösterilmektedir:

[!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]

### <a name="examples"></a>Örnekler

Sonraki örneklerde enum bildirmeyi Göster

[!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]

Sonraki örnek, sayısal eşdeğerleri dönüştürün ve karşılaştırmalar yapmak gösterilmektedir. Dikkat Numaralandırıcı kullanımını `One` tarafından kapsamlı `Enum1` numaralandırma tanımlayıcı ve Numaralandırıcı `First` tarafından kapsamlı `Enum2`.

[!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
