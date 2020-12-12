---
description: 'Daha fazla bilgi edinin: detect_mismatch pragma'
title: detect_mismatch pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
ms.openlocfilehash: e57ffac731409fb14b61d35f780ee19094108655
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300742"
---
# <a name="detect_mismatch-pragma"></a>detect_mismatch pragması

Bir nesneye kayıt koyar. Bağlayıcı, bu kayıtları olası uyuşmazlıklar için denetler.

## <a name="syntax"></a>Syntax

> **#pragma detect_mismatch (** "*ad*" **,** "*değer*" **)**

## <a name="remarks"></a>Açıklamalar

Projeyi bağladığınızda, proje aynı *ada* sahip ancak her biri farklı bir *değere* sahip iki nesne içeriyorsa bağlayıcı bir [LNK2038](../error-messages/tool-errors/linker-tools-error-lnk2038.md) hatası oluşturur. Tutarsız nesne dosyalarının bağlanmasını engellemek için bu pragmayı kullanın.

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

Bu dosyaların her ikisini de komut satırını kullanarak derlerseniz `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` , hatayı alırsınız `LNK2038` .

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
