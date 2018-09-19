---
title: İfade değerlendirici hatası CXX0024 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0024
dev_langs:
- C++
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2816be7bb1d33757d9722d605d461ac6fb34fadd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118203"
---
# <a name="expression-evaluator-error-cxx0024"></a>İfade Değerlendirici Hatası CXX0024

işlemin lvalue gerekiyor

Bir l değeri gerektiren bir işlem için bir l değeri olarak değerlendirilmiyor bir ifade belirtildi.

(Bu nedenle atama deyiminin sol tarafında görünür olduğundan adlı) bir l-değeri, bir bellek konumuna başvurduğu bir ifadedir.

Örneğin, `buffer[count]` bir belirli bir bellek konumuna işaret geçerli bir l-değeri olmasıdır. Mantıksal karşılaştırma `zed != 0` bir bellek adresi değil, TRUE veya FALSE değerlendiren olduğundan geçerli bir l-değeri değil.

Bu hata için CAN0024 aynıdır.