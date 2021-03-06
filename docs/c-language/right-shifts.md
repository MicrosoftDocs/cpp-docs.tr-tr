---
description: 'Daha fazla bilgi edinin: sağ vardiyalar'
title: Sağa Kaydırmalar
ms.date: 11/04/2016
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
ms.openlocfilehash: 5bc359357e8a3a2e00d0c75012e0e6044d8055f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292929"
---
# <a name="right-shifts"></a>Sağa Kaydırmalar

Negatif değer işaretli integral türünün sağ kaydırmasının sonucu

Negatif bir değerin sağına doğru bir şekilde kaydırtılmak mutlak değerin yarısını altına yuvarlanır. Örneğin, **`signed short`** -253 değeri (onaltılı 0xFF03, ikili 11111111 00000011) sağa bir bit üretir-127 (onaltılı 0xFF81, ikili 11111111 10000001). Pozitif bir 253 kaydırılan sağ + 126 üretir.

Sağ vardiyalar işaretli integral türlerinin işaret bitini korur. İşaretli bir tamsayı sağa kaydırdığınızda, en önemli bit ayarlanmış olarak kalır. Örneğin, 0xF0000000 imzalanmış ise **`int`** , sağ SHIFT, 0xF8000000 üretir. Negatif bir 32 kez doğru bir şekilde kaydırma, **`int`** 0xFFFFFFFF üretir.

İşaretsiz bir tamsayı sağa kaydırdığınızda en önemli bit temizlenir. Örneğin, 0xF000 imzasız ise, sonuç 0x7800 olur. Bir **`unsigned`** veya pozitif 32 kez doğru bir şekilde kaydırma, **`int`** 0x00000000 üretir.

## <a name="see-also"></a>Ayrıca bkz.

[Tam Sayılar](../c-language/integers.md)
