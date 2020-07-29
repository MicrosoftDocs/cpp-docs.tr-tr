---
title: __unaligned
ms.date: 12/17/2018
f1_keywords:
- __unaligned_cpp
- __unaligned
- _unaligned
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
ms.openlocfilehash: 2ab94a44d08165ca6e8f394278e24d7c8d201398
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223505"
---
# <a name="__unaligned"></a>__unaligned

**Microsoft 'a özgü**. Değiştiriciyle bir işaretçi bildirdiğinizde **`__unaligned`** , derleyici işaretçinin hizalı olmayan verileri adresleyen olduğunu varsayar. Sonuç olarak, işaretçi üzerinde hizalanmamış okuma ve yazma işlemlerini işlemek için platforma uygun kod oluşturulur.

## <a name="remarks"></a>Açıklamalar

Bu değiştirici, işaretçinin başvurduğu verilerin hizalamasını açıklar; işaretçinin kendisi hizalandığı varsayılır.

Anahtar sözcüğü için zorunludur, **`__unaligned`** platforma ve ortama göre değişir. Verileri uygun bir şekilde işaretlemeniz, performans yaptırımlarından donanım hatalarına kadar sorunlara yol açabilir. **`__unaligned`** Değiştirici x86 platformu için geçerli değil.

Önceki sürümlerle uyumluluk için, **`_unaligned`** **`__unaligned`** derleyici seçeneği [ `/Za` \( dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) ' ın belirtildiği durumlar için bir eş anlamlı olur.

Hizalama hakkında daha fazla bilgi için bkz.

- [`align`](../cpp/align-cpp.md)

- [`alignof`İşlecinde](../cpp/alignof-operator.md)

- [`pack`](../preprocessor/pack.md)

- [`/Zp`(Struct üye hizalaması)](../build/reference/zp-struct-member-alignment.md)

- [Yapı Hizalama Örnekleri](../build/x64-software-conventions.md#examples-of-structure-alignment)

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)
