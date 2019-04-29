---
title: Kaynak Derleyicisi Önemli Hatası RW1025
ms.date: 11/04/2016
f1_keywords:
- RW1025
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
ms.openlocfilehash: 8ecfc11f5cc991294d966a4b6c75d8da6669d5b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347213"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Kaynak Derleyicisi Önemli Hatası RW1025

Şimdiye kadar yığın bellek yetersiz

Çok fazla yer gerçekleşebilecek bellekte yazılım olup olmadığını denetleyin. CHKDSK program, sahip olduğunuz ne kadar bellek bulmak için kullanın.

Büyük bir kaynak dosyasını oluşturuyorsanız, kaynak betiği iki dosyalara bölün. İki .res dosyası oluşturduktan sonra bunları birbirine birleştirmek için MS-DOS komut satırını kullanın:

```
copy first.res /b + second.res /b full.res
```