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
ms.openlocfilehash: d73b082b9f41d03eb0b1a8c9fe772351ff4da91f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="unaligned"></a>__unaligned

**Microsoft özel**. `__unaligned` değiştiricisiyle bir işaretçiyi bildirdiğinizde, derleyici işaretçinin hizalanmamış verilere yönelik olduğunu varsayar. Sonuç olarak, platform uygun kodu hizalanmamış okuma işlemek için oluşturulan ve işaretçiyi yazar.

## <a name="remarks"></a>Açıklamalar

Bu değiştirici işaretçi ele veri hizalamasını açıklar; İşaretçi hizalanacak varsayılır.

Sürümüne geçirilmesi için zorunludur `__unaligned` anahtar sözcüğü platform ve ortam göre değişir. Veri uygun şekilde işaretlemek için hata performans cezaları donanım hataları arasında değişen sorunları neden olabilir. `__unaligned` Değiştiricisi x86 için geçerli değil platform.

Hizalama hakkında daha fazla bilgi için bkz.

- [align](../cpp/align-cpp.md)

- [__alignof İşleci](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp (Yapı Üyesi Hizalama)](../build/reference/zp-struct-member-alignment.md)

- [Yapı Hizalama Örnekleri](../build/examples-of-structure-alignment.md)

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)
