---
title: İfade Değerlendirici Hatası CXX0039
ms.date: 11/04/2016
f1_keywords:
- CXX0039
helpviewer_keywords:
- CXX0039
- CAN0039
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
ms.openlocfilehash: 053e57a21f0cb75cbd96732edb6812b3557bcd50
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396983"
---
# <a name="expression-evaluator-error-cxx0039"></a>İfade Değerlendirici Hatası CXX0039

Sembol belirsiz

C ifade değerlendiricisi, hangi örneğinin bir ifadede kullanılacak bir simge olup olmadığını belirleyemez. Sembol birden çok devralma ağacında bir kez gerçekleşir.

Kapsam çözümleme işleci kullanmanız gerekir (`::`) ifadede kullanılacak örneğini açıkça belirtmek için.

Bu hata için CAN0039 aynıdır.