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
ms.openlocfilehash: 8eb1b93aa55601125600b6c69d9bff3d9ca43aa3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244122"
---
# <a name="unaligned"></a>__unaligned

**Microsoft'a özgü**. Bir işaretçiyi bildirdiğinizde **__unaligned** değiştiricisi, derleyici varsayar işaretçinin hizalanmamış veri yöneliktir. Sonuç olarak, platform için uygun kodu hizalanmamış okuma işlemek için oluşturuldu ve işaretçiyle yazar.

## <a name="remarks"></a>Açıklamalar

Bu değiştirici, işaretçi tarafından ele alınan verilerin hizalamasını açıklar; İşaretçinin hizalandığı varsayılır.

İçin yeterlilikte **__unaligned** anahtar sözcüğü, platform ve ortam tarafından değişir. Veri uygun şekilde işaretlemek için hata sorunları performans cezaları arasında değişen donanım hatalarına neden olabilir. **__Unaligned** değiştiricisi x86 için geçerli değil platform.

Önceki sürümlerle uyumluluk için **_unaligned** eşanlamlıdır **__unaligned** sürece derleyici seçeneği [/Za \(dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md) belirtilir.

Hizalama hakkında daha fazla bilgi için bkz.

- [align](../cpp/align-cpp.md)

- [__alignof İşleci](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (Yapı Üyesi Hizalama)](../build/reference/zp-struct-member-alignment.md)

- [Yapı Hizalama Örnekleri](../build/x64-software-conventions.md#examples-of-structure-alignment)

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)