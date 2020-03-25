---
title: Kaynak Derleyicisi Önemli Hatası RW1025
ms.date: 11/04/2016
f1_keywords:
- RW1025
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
ms.openlocfilehash: 9b6697dff0a445cc342f30d08bd79822b02df7b8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172734"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Kaynak Derleyicisi Önemli Hatası RW1025

En fazla yığın belleği

Çok fazla alan içerebilecek bellekte yerleşik yazılımlar olup olmadığını denetleyin. Ne kadar bellek olduğunu öğrenmek için CHKDSK programını kullanın.

Büyük bir kaynak dosyası oluşturuyorsanız, kaynak betiği iki dosyaya ayırın. İki. res dosyası oluşturduktan sonra, bunları birbirine katmak için MS-DOS komut satırını kullanın:

```
copy first.res /b + second.res /b full.res
```
