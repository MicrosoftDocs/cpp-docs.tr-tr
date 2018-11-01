---
title: Makrolardaki Özel Karakterler
ms.date: 11/04/2016
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
ms.openlocfilehash: bc40a4d2c3197f0cc85099d0a89ab511f3acf81c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555096"
---
# <a name="special-characters-in-macros"></a>Makrolardaki Özel Karakterler

Bir sayı (#) oturum sonra bir tanımı bir açıklama belirtir. Değişmez değer sayı işareti bir makroda belirtmek için gibi bir şapka (^) kullanın ^ #.

Bir dolar işareti ($), bir makro çağrısını belirtir. Belirtmek için bir sabit değer $ $$ kullanın.

Yeni bir satır için bir tanımı genişletmek için bir ters eğik çizgiyle bitmelidir (\\). Makro çağrıldığında, ters eğik çizgi yanı sıra yeni satır karakteri boşluk ile değiştirilir. Satırın sonunda değişmez bir ters eğik çizgi belirtmek için bir şapka (^) önünde veya yorum tanımlayıcısı ile izleyin (#).

Bir değişmez değer yeni satır karakteri, son bir şapka (^) içeren satırı olarak belirtmek için:

```
CMDS = cls^
dir
```

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Makrosu Tanımlama](../build/defining-an-nmake-macro.md)