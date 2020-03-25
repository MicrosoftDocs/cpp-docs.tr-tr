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
ms.openlocfilehash: 5f93aaa79fd7c3664ecf80d5007d5954002bce4a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160651"
---
# <a name="__unaligned"></a>__unaligned

**Microsoft 'a özgü**. **__Unaligned** değiştiricisiyle bir işaretçi bildirdiğinizde, derleyici işaretçinin hizalı olmayan verileri adresleyen olduğunu varsayar. Sonuç olarak, işaretçi üzerinde hizalanmamış okuma ve yazma işlemlerini işlemek için platforma uygun kod oluşturulur.

## <a name="remarks"></a>Açıklamalar

Bu değiştirici, işaretçinin başvurduğu verilerin hizalamasını açıklar; işaretçinin kendisi hizalandığı varsayılır.

**__Unaligned** anahtar sözcüğü için zorunludur, platforma ve ortama göre değişir. Verileri uygun bir şekilde işaretlemeniz, performans yaptırımlarından donanım hatalarına kadar sorunlara yol açabilir. **__Unaligned** değiştiricisi x86 platformu için geçerli değil.

Önceki sürümlerle uyumluluk için, [/za \(dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde, **_unaligned** **__unaligned** için bir eş anlamlı.

Hizalama hakkında daha fazla bilgi için bkz.

- [align](../cpp/align-cpp.md)

- [__alignof İşleci](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (Yapı Üyesi Hizalama)](../build/reference/zp-struct-member-alignment.md)

- [Yapı Hizalama Örnekleri](../build/x64-software-conventions.md#examples-of-structure-alignment)

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)
