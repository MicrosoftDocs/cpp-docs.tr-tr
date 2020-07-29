---
title: Derleyici Uyarısı (düzey 4) C4510
description: Derleyici Uyarısı C4510 açıklaması ve çözümü.
ms.date: 09/22/2019
f1_keywords:
- C4510
helpviewer_keywords:
- C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
ms.openlocfilehash: e4bb688266d9fe638978d2d3fa2666b83b3e6cc9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225260"
---
# <a name="compiler-warning-level-4-c4510"></a>Derleyici Uyarısı (düzey 4) C4510

> '*Class*': Varsayılan Oluşturucu üretilemedi

Derleyici, Kullanıcı tanımlı oluşturuculara sahip olmayan belirtilen sınıf için varsayılan bir Oluşturucu oluşturamıyor. Bu türden nesneler oluşturulamıyor.

Derleyicinin varsayılan bir Oluşturucu oluşturmasını önleyen birkaç durum vardır; örneğin:

- Bir **`const`** veri üyesi.

- Başvuru olan bir veri üyesi.

Bu sorunu onarmak için, bu üyeleri başlatan sınıf için Kullanıcı tanımlı bir varsayılan Oluşturucu oluşturun.
