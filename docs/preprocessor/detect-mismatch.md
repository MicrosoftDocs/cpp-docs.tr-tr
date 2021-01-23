---
description: pragmaMicrosoft C/C++ ' da detect_mismatch yönergesi hakkında daha fazla bilgi edinin
title: detect_mismatch pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
helpviewer_keywords:
- pragma, detect_mismatch
- detect_mismatch pragma
no-loc:
- pragma
ms.openlocfilehash: 33bc899eaaed73329e24e7f210fa91adc8addaa9
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713681"
---
# <a name="detect_mismatch-no-locpragma"></a>`detect_mismatch` pragma

Bir nesneye kayıt koyar. Bağlayıcı, bu kayıtları olası uyuşmazlıklar için denetler.

## <a name="syntax"></a>Syntax

> **`#pragma detect_mismatch(`** "*ad*" **`,`** "*değeri*" **`)`**

## <a name="remarks"></a>Açıklamalar

Projeyi bağladığınızda, proje aynı *ada* sahip ancak her biri farklı bir *değere* sahip iki nesne içeriyorsa bağlayıcı bir [LNK2038](../error-messages/tool-errors/linker-tools-error-lnk2038.md) hatası oluşturur. pragmaTutarsız nesne dosyalarının bağlanmasını engellemek için bunu kullanın.

Hem *ad* hem de *değer* dize sabit değerleri olduğundan, kaçış karakterlerine ve birleştirme karakterlerine göre dize sabit değerleri için kurallara uyar. Bunlar büyük/küçük harfe duyarlıdır ve virgül, eşittir işareti, tırnak işaretleri veya **null** karakter içeremez.

## <a name="example"></a>Örnek

Bu örnek, aynı sürüm etiketi için farklı sürüm numaralarına sahip iki dosya oluşturur.

```cpp
// pragma_directive_detect_mismatch_a.cpp
#pragma detect_mismatch("myLib_version", "9")
int main ()
{
   return 0;
}

// pragma_directive_detect_mismatch_b.cpp
#pragma detect_mismatch("myLib_version", "1")
```

Komut satırını kullanarak bu dosyaların her ikisini de derlerseniz `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` , LNK2038 hatasını alırsınız.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
