---
title: Numaralandırmalar (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fff0ffb62182e078149d1403c495c69ae918c36
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105730"
---
# <a name="enums-ccx"></a>Numaralandırmalar (C + +/ CX)

C + +/ CX destekler `public enum class` işlevdedir standart bir C++ anahtar sözcüğünü `scoped  enum`. Kullanılarak bildirilen bir numaralandırıcı kullandığınızda `public enum class` anahtar sözcüğü her Numaralandırıcı değeri kapsam için numaralandırma tanımlayıcı kullanmalısınız.

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

## <a name="see-also"></a>Ayrıca Bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)