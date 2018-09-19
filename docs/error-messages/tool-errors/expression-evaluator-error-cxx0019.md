---
title: İfade değerlendirici hatası CXX0019 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0019
dev_langs:
- C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3fba76b75c640917b3b99cd41500d682cb1b32f0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031814"
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