---
description: pragmaMicrosoft C/C++ ' da alloc_text yönergesi hakkında daha fazla bilgi edinin
title: alloc_text pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
helpviewer_keywords:
- alloc_text pragma
- pragma, alloc_text
no-loc:
- pragma
ms.openlocfilehash: f20cbf90952c6ac5793c5bdf4d2ef1c533be2126
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713135"
---
# <a name="alloc_text-no-locpragma"></a>`alloc_text` pragma

Belirtilen işlev tanımlarının yerleştirildiği kod bölümünü adlandırır. , pragma Bir işlev bildirimci ve adlandırılmış işlevler için işlev tanımı arasında gerçekleşmelidir.

## <a name="syntax"></a>Syntax

> **`#pragma alloc_text(`** "*metin-bölümü*" **`,`** *function_1* [ **`,`** *function_2* ...] **`)`**

## <a name="remarks"></a>Açıklamalar

**`alloc_text`** pragma C++ üye işlevlerini veya aşırı yüklenmiş işlevleri işlemez. Yalnızca C bağlantısıyla belirtilen işlevler, diğer bir deyişle, bağlantı belirtimi ile belirtilen işlevler için geçerlidir **`extern "C"`** . Bunu pragma C++ bağlantısıyla bir işlevde kullanmaya çalışırsanız bir derleyici hatası oluşturulur.

Kullanılarak işlev adresleme **`__based`** desteklenmediğinden, Bölüm konumlarının belirtilmesi öğesinin kullanımını gerektirir **`alloc_text`** pragma . *Metin bölümü* tarafından belirtilen ad, çift tırnak işareti içine alınmalıdır.

**`alloc_text`** pragma Belirtilen işlevlerin ve bu işlevlerin tanımlarından önce bildirimlerinden sonra gelmelidir.

İçinde başvurulan işlevler **`alloc_text`** pragma , ile aynı modülde tanımlanmalıdır pragma . Aksi takdirde, tanımsız bir işlev daha sonra farklı bir metin bölümüne derlenirse, hata yakalanmayabilir veya yakalanmayabilir. Program genellikle doğru şekilde çalışacak olsa da, işlev amaçlanan bölümlerde ayrılmayacaktır.

Diğer sınırlamalar **`alloc_text`** aşağıdaki gibidir:

- Bir işlev içinde kullanılamaz.

- İşlev bildirildikten sonra, ancak işlev tanımlanmadan önce kullanılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
