---
description: 'Daha fazla bilgi edinin: Ifade değerlendirici hatası CXX0024'
title: İfade Değerlendirici Hatası CXX0024
ms.date: 11/04/2016
f1_keywords:
- CXX0024
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
ms.openlocfilehash: cb40199c217180b08e62d89dee551130eefefc35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228085"
---
# <a name="expression-evaluator-error-cxx0024"></a>İfade Değerlendirici Hatası CXX0024

işlem için l-değeri gerekiyor

L değeri gerektiren bir işlem için bir l değeri olarak değerlendirilmeyecek bir ifade belirtildi.

Bir l-değeri (atama deyiminin sol tarafında göründüğünden çağrılır), bir bellek konumuna başvuran bir ifadedir.

Örneğin, `buffer[count]` belirli bir bellek konumunu işaret ettiğinden geçerli bir l değeri. `zed != 0`Bir bellek adresine DEĞIL true veya false olarak değerlendirildiğinden, mantıksal karşılaştırma geçerli bir l değeri değil.

Bu hata CAN0024 ile aynıdır.
