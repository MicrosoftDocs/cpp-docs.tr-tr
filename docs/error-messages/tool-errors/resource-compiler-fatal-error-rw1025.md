---
title: Kaynak Derleyicisi önemli hatası RW1025 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW1025
dev_langs:
- C++
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2bf7bdeed320c004ffb75fa1d25d9b89147b0c13
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117406"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Kaynak Derleyicisi Önemli Hatası RW1025

Şimdiye kadar yığın bellek yetersiz

Çok fazla yer gerçekleşebilecek bellekte yazılım olup olmadığını denetleyin. CHKDSK program, sahip olduğunuz ne kadar bellek bulmak için kullanın.

Büyük bir kaynak dosyasını oluşturuyorsanız, kaynak betiği iki dosyalara bölün. İki .res dosyası oluşturduktan sonra bunları birbirine birleştirmek için MS-DOS komut satırını kullanın:

```
copy first.res /b + second.res /b full.res
```