---
description: 'Daha fazla bilgi edinin: Ifade değerlendirici hatası CXX0019'
title: İfade Değerlendirici Hatası CXX0019
ms.date: 11/04/2016
f1_keywords:
- CXX0019
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
ms.openlocfilehash: 1caf4714c1fc719883ee889c14225e4f69e961a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228241"
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
