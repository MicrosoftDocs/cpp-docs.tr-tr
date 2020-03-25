---
title: İfade Değerlendirici Hatası CXX0019
ms.date: 11/04/2016
f1_keywords:
- CXX0019
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
ms.openlocfilehash: 61646462eeba4918a4993b23f7f4b394083296ce
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195896"
---
# <a name="expression-evaluator-error-cxx0019"></a>İfade Değerlendirici Hatası CXX0019

Hatalı tür dönüştürme

C ifade değerlendirici tür dönüştürmeyi yazılı olarak gerçekleştiremez.

Bu hata CAN0019 ile aynıdır.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Belirtilen tür bilinmiyor.

1. Çok fazla işaretçi türü düzeyi vardı. Örneğin, tür dönüştürme

    ```
    (char **)h_message
    ```

   C ifade değerlendiricisi tarafından değerlendirilemiyor.
