---
title: Makrolardaki özel karakterler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55a94001e2f912049518120911c25ae64afa24da
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721435"
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