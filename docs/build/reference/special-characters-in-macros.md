---
title: Makrolardaki Özel Karakterler
ms.date: 11/04/2016
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
ms.openlocfilehash: aac7b07500d2a129194e7234210a590cb5d0f19a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823563"
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

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Makrosu Tanımlama](defining-an-nmake-macro.md)
