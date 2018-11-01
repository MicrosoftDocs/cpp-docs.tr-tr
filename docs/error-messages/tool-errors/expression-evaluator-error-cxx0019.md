---
title: İfade Değerlendirici Hatası CXX0019
ms.date: 11/04/2016
f1_keywords:
- CXX0019
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
ms.openlocfilehash: 266e97f28cf0f27cb87e9743399c66aba87c0e8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658100"
---
# <a name="expression-evaluator-error-cxx0019"></a>İfade Değerlendirici Hatası CXX0019

bozuk tür dönüştürme

C ifade değerlendiricisi yazıldığı gibi cast türü gerçekleştirilemiyor.

Bu hata için CAN0019 aynıdır.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Belirtilen türü bilinmiyor.

1. Çok fazla sayıda iç işaretçi türlerinin vardı. Örneğin, atama türü

    ```
    (char **)h_message
    ```

   C ifade değerlendiricisi tarafından değerlendirilemez.