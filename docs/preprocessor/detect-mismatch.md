---
title: detect_mismatch pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
ms.openlocfilehash: 6e247b3f251bce47710a3380fb295597314a3bd8
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222386"
---
# <a name="detect_mismatch-pragma"></a>detect_mismatch pragması

Bir nesneye kayıt koyar. Bağlayıcı, bu kayıtları olası uyuşmazlıklar için denetler.

## <a name="syntax"></a>Sözdizimi

> **#pragma detect_mismatch (** "*ad*" **,** "*değer*" **)**

## <a name="remarks"></a>Açıklamalar

Projeyi bağladığınızda, proje aynı *ada* sahip ancak her biri farklı bir *değere*sahip iki nesne içeriyorsa bağlayıcı bir [LNK2038](../error-messages/tool-errors/linker-tools-error-lnk2038.md) hatası oluşturur. Tutarsız nesne dosyalarının bağlanmasını engellemek için bu pragmayı kullanın.

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

Bu dosyaların her ikisini de komut satırını `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp`kullanarak derlerseniz, hatayı `LNK2038`alırsınız.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
