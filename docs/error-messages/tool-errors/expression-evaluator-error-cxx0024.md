---
title: İfade Değerlendirici Hatası CXX0024
ms.date: 11/04/2016
f1_keywords:
- CXX0024
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
ms.openlocfilehash: 525210090b0a4c2966f2e1432f85fd4bb6a8156d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195766"
---
# <a name="expression-evaluator-error-cxx0024"></a>İfade Değerlendirici Hatası CXX0024

işlem için l-değeri gerekiyor

L değeri gerektiren bir işlem için bir l değeri olarak değerlendirilmeyecek bir ifade belirtildi.

Bir l-değeri (atama deyiminin sol tarafında göründüğünden çağrılır), bir bellek konumuna başvuran bir ifadedir.

Örneğin, `buffer[count]`, belirli bir bellek konumunu işaret ettiğinden geçerli bir l değeridir. Bir bellek adresine değil, doğru veya yanlış olarak değerlendirildiğinden, mantıksal karşılaştırma `zed != 0` geçerli bir l değeri değil.

Bu hata CAN0024 ile aynıdır.
