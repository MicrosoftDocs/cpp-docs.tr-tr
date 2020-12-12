---
description: 'Daha fazla bilgi edinin: kaynak derleyicisi önemli Hatası RW1025'
title: Kaynak Derleyicisi Önemli Hatası RW1025
ms.date: 11/04/2016
f1_keywords:
- RW1025
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
ms.openlocfilehash: 40404f8d6dc16b73f93255a18ce8c632cc1e014a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237198"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Kaynak Derleyicisi Önemli Hatası RW1025

En fazla yığın belleği

Çok fazla alan içerebilecek bellekte yerleşik yazılımlar olup olmadığını denetleyin. Ne kadar bellek olduğunu öğrenmek için CHKDSK programını kullanın.

Büyük bir kaynak dosyası oluşturuyorsanız, kaynak betiği iki dosyaya ayırın. İki. res dosyası oluşturduktan sonra, bunları birbirine katmak için MS-DOS komut satırını kullanın:

```
copy first.res /b + second.res /b full.res
```
