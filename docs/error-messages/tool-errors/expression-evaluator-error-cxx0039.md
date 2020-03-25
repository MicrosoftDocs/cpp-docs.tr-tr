---
title: İfade Değerlendirici Hatası CXX0039
ms.date: 11/04/2016
f1_keywords:
- CXX0039
helpviewer_keywords:
- CXX0039
- CAN0039
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
ms.openlocfilehash: 5706d002eb3d566d05b059cb04b6b1626fdb3d33
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185132"
---
# <a name="expression-evaluator-error-cxx0039"></a>İfade Değerlendirici Hatası CXX0039

sembol belirsiz

C ifadesi değerlendirici, bir simgenin bir ifadede hangi örneğinin kullanılacağını belirleyemez. Sembol, devralma ağacında birden çok kez geçiyor.

İfadede kullanılacak örneği açıkça belirtmek için kapsam çözümleme işlecini (`::`) kullanmanız gerekir.

Bu hata CAN0039 ile aynıdır.
