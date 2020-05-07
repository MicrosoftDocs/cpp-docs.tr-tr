---
title: Sağa Kaydırmalar
ms.date: 11/04/2016
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
ms.openlocfilehash: c34373f69a41ad65031753cd352098dce7e98ef4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158366"
---
# <a name="right-shifts"></a>Sağa Kaydırmalar

Negatif değer işaretli integral türünün sağ kaydırmasının sonucu

Negatif bir değerin sağına doğru bir şekilde kaydırtılmak mutlak değerin yarısını altına yuvarlanır. Örneğin,-253 işaretli `short` bir değer (onaltılı 0xFF03, ikili 11111111 00000011) bir bit üretir-127 (onaltılı 0xFF81, ikili 11111111 10000001). Pozitif bir 253 kaydırılan sağ + 126 üretir.

Sağ vardiyalar işaretli integral türlerinin işaret bitini korur. İşaretli bir tamsayı sağa kaydırdığınızda, en önemli bit ayarlanmış olarak kalır. Örneğin, 0xF0000000 imzalanmış `int`ise, sağ SHIFT, 0xF8000000 üretir. Negatif `int` bir 32 kez doğru bir şekilde kaydırma, 0xFFFFFFFF üretir.

İşaretsiz bir tamsayı sağa kaydırdığınızda en önemli bit temizlenir. Örneğin, 0xF000 imzasız ise, sonuç 0x7800 olur. Bir veya `unsigned` pozitif `int` 32 kez doğru bir şekilde kaydırma, 0x00000000 üretir.

## <a name="see-also"></a>Ayrıca bkz.

[Tam Sayılar](../c-language/integers.md)
