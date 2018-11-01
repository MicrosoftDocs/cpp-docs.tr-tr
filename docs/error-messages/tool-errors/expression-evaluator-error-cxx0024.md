---
title: İfade Değerlendirici Hatası CXX0024
ms.date: 11/04/2016
f1_keywords:
- CXX0024
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
ms.openlocfilehash: 93f8389ed3959d5747e46c1234fd8d2eae0f1ae5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659699"
---
# <a name="expression-evaluator-error-cxx0024"></a>İfade Değerlendirici Hatası CXX0024

işlemin lvalue gerekiyor

Bir l değeri gerektiren bir işlem için bir l değeri olarak değerlendirilmiyor bir ifade belirtildi.

(Bu nedenle atama deyiminin sol tarafında görünür olduğundan adlı) bir l-değeri, bir bellek konumuna başvurduğu bir ifadedir.

Örneğin, `buffer[count]` bir belirli bir bellek konumuna işaret geçerli bir l-değeri olmasıdır. Mantıksal karşılaştırma `zed != 0` bir bellek adresi değil, TRUE veya FALSE değerlendiren olduğundan geçerli bir l-değeri değil.

Bu hata için CAN0024 aynıdır.