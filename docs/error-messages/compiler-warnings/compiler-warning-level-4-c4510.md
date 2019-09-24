---
title: Derleyici Uyarısı (düzey 4) C4510
description: Derleyici Uyarısı C4510 açıklaması ve çözümü.
ms.date: 09/22/2019
f1_keywords:
- C4510
helpviewer_keywords:
- C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
ms.openlocfilehash: 05a6d0fe42d8247d3328506d8772b2fa77b5703c
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71230384"
---
# <a name="compiler-warning-level-4-c4510"></a>Derleyici Uyarısı (düzey 4) C4510

> '*Class*': Varsayılan Oluşturucu üretilemedi

Derleyici, Kullanıcı tanımlı oluşturuculara sahip olmayan belirtilen sınıf için varsayılan bir Oluşturucu oluşturamıyor. Bu türden nesneler oluşturulamıyor.

Derleyicinin varsayılan bir Oluşturucu oluşturmasını önleyen birkaç durum vardır; örneğin:

- Bir **const** veri üyesi.

- Başvuru olan bir veri üyesi.

Bu sorunu onarmak için, bu üyeleri başlatan sınıf için Kullanıcı tanımlı bir varsayılan Oluşturucu oluşturun.
