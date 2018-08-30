---
title: -DYNAMICBASE | Microsoft Docs
ms.custom: ''
ms.date: 06/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /dynamicbase
dev_langs:
- C++
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 255123157da3f802eafaf26206598d54fea02335
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211691"
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