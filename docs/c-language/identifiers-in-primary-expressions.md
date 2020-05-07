---
title: Birincil İfadelerdeki Tanımlayıcılar
ms.date: 11/04/2016
helpviewer_keywords:
- identifiers, designating objects
ms.assetid: d4602fe6-e7e6-40cc-9823-3b1ebf5d3d38
ms.openlocfilehash: 053720bcdf635a7e09363712259b558d93a2972c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233092"
---
# <a name="identifiers-in-primary-expressions"></a>Birincil İfadelerdeki Tanımlayıcılar

Tanımlayıcılar integral, **float**, `enum`, `struct`, **Union**, dizi, işaretçi veya işlev türüne sahip olabilir. Bir tanımlayıcı, bir nesne (Bu durumda bir l değeri olduğu gibi) veya bir işlev olarak (Bu durumda bir işlev göstergesi olduğu gibi) tanımlayarak bildirildiği belirtilen birincil ifadedir. L-değeri tanımı için bkz. l-Value [ve R-Value ifadeleri](../c-language/l-value-and-r-value-expressions.md) .

Bir dizi tanımlayıcısı tarafından temsil edilen işaretçi değeri bir değişken değildir, bu nedenle bir dizi tanımlayıcısı atama işleminin sol işlenenini oluşturamaz ve bu nedenle değiştirilebilir bir l değeri değildir.

İşlev olarak tanımlanan bir tanımlayıcı, değeri işlevin adresi olan bir işaretçiyi temsil eder. İşaretçi, belirtilen türde bir değer döndüren bir işleve yöneliktir. Bu nedenle, işlev tanımlayıcıları Ayrıca atama işlemlerinde l-Values olamaz. Daha fazla bilgi edinmek için bkz. [Tanımlayıcılar](../c-language/c-identifiers.md).

## <a name="see-also"></a>Ayrıca bkz.

[C birincil Ifadeler](../c-language/c-primary-expressions.md)
