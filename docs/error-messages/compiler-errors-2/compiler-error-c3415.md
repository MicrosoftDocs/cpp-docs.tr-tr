---
title: Derleyici hatası C3415
ms.date: 11/04/2016
f1_keywords:
- C3415
helpviewer_keywords:
- C3415
ms.assetid: fa2db8ab-2820-4ec3-a740-fb5e2adcfb29
ms.openlocfilehash: da7b49d30866b9fa5ab27a93357fd2812aaa2806
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742931"
---
# <a name="compiler-error-c3415"></a>Derleyici hatası C3415

farklı özniteliklere sahip birden çok ' section_name ' bölümü bulundu (' Value ')

[Bölüm](../../preprocessor/section.md) pragmaları içinde çakışan değerler belirtildi.

`value`,, ntımage. h içinde belirtildiği gibi, bölüm için geçerli ayardır. Örneğin:

```
// Section contains extended relocations.
#define IMAGE_SCN_LNK_NRELOC_OVFL            0x01000000
// Section can be discarded.
#define IMAGE_SCN_MEM_DISCARDABLE            0x02000000
// Section is not cachable.
#define IMAGE_SCN_MEM_NOT_CACHED             0x04000000
// Section is not pageable.
#define IMAGE_SCN_MEM_NOT_PAGED              0x08000000
// Section is shareable.
#define IMAGE_SCN_MEM_SHARED                 0x10000000
// Section is executable.
#define IMAGE_SCN_MEM_EXECUTE                0x20000000
// Section is readable.
#define IMAGE_SCN_MEM_READ                   0x40000000
// Section is writeable.
#define IMAGE_SCN_MEM_WRITE                  0x80000000
```

Aşağıdaki örnek C3415 oluşturur:

```cpp
// C3415.cpp
#pragma section("mysec1",write)
#pragma section("mysec1",read)   // C3415
```
