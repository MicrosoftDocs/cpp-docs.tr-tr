---
description: 'Daha fazla bilgi edinin: Ifade değerlendirici hatası CXX0065'
title: İfade Değerlendirici Hatası CXX0065
ms.date: 11/04/2016
f1_keywords:
- CXX0065
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
ms.openlocfilehash: 8013bdc2541e2ab3719ef700413a87df49731983
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173174"
---
# <a name="expression-evaluator-error-cxx0065"></a>İfade Değerlendirici Hatası CXX0065

değişken, yığın çerçevesine ihtiyaç duyuyor

Bir ifade, geçerli kapsam içinde bulunan ancak henüz oluşturulmamış bir değişken içeriyordu.

Bu hata, bir işlevin giriş sayfasına bir sözcük eklediğinizde ancak işlev için yığın çerçevesini ayarlamanıza veya işlev için çıkış koduna busaydıysanız oluşabilir.

İfadeyi değerlendirmeden önce yığın çerçevesi ayarlanana kadar giriş kodunu adım adım yapın.

Bu hata CAN0065 ile aynıdır.
