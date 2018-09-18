---
title: __unaligned | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __unaligned_cpp
dev_langs:
- C++
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9593a0b3c6e6980f5be2ce9dcf13e505e94dcace
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040210"
---
# <a name="unaligned"></a>__unaligned

**Microsoft'a özgü**. Bir işaretçiyi bildirdiğinizde **__unaligned** değiştiricisi, derleyici varsayar işaretçinin hizalanmamış veri yöneliktir. Sonuç olarak, platform için uygun kodu hizalanmamış okuma işlemek için oluşturuldu ve işaretçiyle yazar.

## <a name="remarks"></a>Açıklamalar

Bu değiştirici, işaretçi tarafından ele alınan verilerin hizalamasını açıklar; İşaretçinin hizalandığı varsayılır.

İçin yeterlilikte **__unaligned** anahtar sözcüğü, platform ve ortam tarafından değişir. Veri uygun şekilde işaretlemek için hata sorunları performans cezaları arasında değişen donanım hatalarına neden olabilir. **__Unaligned** değiştiricisi x86 için geçerli değil platform.

Hizalama hakkında daha fazla bilgi için bkz.

- [align](../cpp/align-cpp.md)

- [__alignof İşleci](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (Yapı Üyesi Hizalama)](../build/reference/zp-struct-member-alignment.md)

- [Yapı Hizalama Örnekleri](../build/examples-of-structure-alignment.md)

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)