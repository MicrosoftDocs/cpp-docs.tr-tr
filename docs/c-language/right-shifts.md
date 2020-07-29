---
title: Sağa Kaydırmalar
ms.date: 11/04/2016
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
ms.openlocfilehash: 4b83aa231e6e7904fe5682b32a861ffe301b9747
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87199418"
---
# <a name="right-shifts"></a>Sağa Kaydırmalar

Negatif değer işaretli integral türünün sağ kaydırmasının sonucu

Negatif bir değerin sağına doğru bir şekilde kaydırtılmak mutlak değerin yarısını altına yuvarlanır. Örneğin, **`signed short`** -253 değeri (onaltılı 0xFF03, ikili 11111111 00000011) sağa bir bit üretir-127 (onaltılı 0xFF81, ikili 11111111 10000001). Pozitif bir 253 kaydırılan sağ + 126 üretir.

Sağ vardiyalar işaretli integral türlerinin işaret bitini korur. İşaretli bir tamsayı sağa kaydırdığınızda, en önemli bit ayarlanmış olarak kalır. Örneğin, 0xF0000000 imzalanmış ise **`int`** , sağ SHIFT, 0xF8000000 üretir. Negatif bir 32 kez doğru bir şekilde kaydırma, **`int`** 0xFFFFFFFF üretir.

İşaretsiz bir tamsayı sağa kaydırdığınızda en önemli bit temizlenir. Örneğin, 0xF000 imzasız ise, sonuç 0x7800 olur. Bir **`unsigned`** veya pozitif 32 kez doğru bir şekilde kaydırma, **`int`** 0x00000000 üretir.

## <a name="see-also"></a>Ayrıca bkz.

[Kesirli](../c-language/integers.md)
