---
title: /DYNAMICBASE
ms.date: 06/12/2018
f1_keywords:
- /dynamicbase
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
ms.openlocfilehash: fb8bfd4f4b11d14dbbc605f4366cf1cd5446a319
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430805"
---
# <a name="dynamicbase"></a>/DYNAMICBASE

Rastgele yükleme zamanında adres alanı düzeni rastgele (ASLR) özelliği, öncelikle Windows Vista'da kullanılabilir Windows temellendirilebilen yürütülebilir bir imaj oluşturulup oluşturulmayacağını belirtir.

## <a name="syntax"></a>Sözdizimi

> **/ DYNAMICBASE**[**: NO**]

## <a name="remarks"></a>Açıklamalar

**Dynamıcbase** seçenek değiştirir üst bilgisine bir *yürütülebilir görüntü*, uygulama rastgele yükleme zamanında ReBase işlemi gerçekleştirildi ve sayesinde sanal adresi olup olmadığını belirtmek için .dll veya .exe dosyası Yığınlar sanal bellek konumunu etkileyen, ayırma rastgele yığınları ve diğer işletim sistemi ayırma. **Dynamıcbase** seçenek, hem 32-bit hem de 64-bit görüntüleri için geçerlidir. ASLR, Windows Vista ve sonraki işletim sistemlerinde desteklenir. Seçenek, eski işletim sistemleri tarafından göz ardı edilir.

Varsayılan olarak, **dynamıcbase** etkinleştirilir. Bu seçenek devre dışı bırakmak için **taban**. **Dynamıcbase** için seçeneği gereklidir [/highentropyva](highentropyva-support-64-bit-aslr.md) efekt için seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

- [EDITBIN Seçenekleri](../../build/reference/editbin-options.md)
- [ISV yazılım güvenlik Savunmaları Windows](https://msdn.microsoft.com/library/bb430720.aspx)