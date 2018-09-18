---
title: İfade değerlendirici hatası CXX0039 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0039
dev_langs:
- C++
helpviewer_keywords:
- CXX0039
- CAN0039
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5397426618c5dfcbaa6307105781ff2e6f2eb97
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048337"
---
# <a name="expression-evaluator-error-cxx0039"></a>İfade Değerlendirici Hatası CXX0039

Sembol belirsiz

C ifade değerlendiricisi, hangi örneğinin bir ifadede kullanılacak bir simge olup olmadığını belirleyemez. Sembol birden çok devralma ağacında bir kez gerçekleşir.

Kapsam çözümleme işleci kullanmanız gerekir (`::`) ifadede kullanılacak örneğini açıkça belirtmek için.

Bu hata için CAN0039 aynıdır.