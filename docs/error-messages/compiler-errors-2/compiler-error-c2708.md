---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2708'
title: Derleyici hatası C2708
ms.date: 11/04/2016
f1_keywords:
- C2708
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
ms.openlocfilehash: c965375c92c98a58a0fb6d0d51b3358e6b5798b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320876"
---
# <a name="compiler-error-c2708"></a>Derleyici hatası C2708

' tanımlayıcı ': gerçek parametrenin bayt uzunluğu önceki çağrıdan veya başvurudan farklı

[__Stdcall](../../cpp/stdcall.md) işlevin önünde bir prototip gelmelidir. Aksi takdirde, derleyici işleve ilk çağrıyı bir prototip olarak yorumlar ve bu hata derleyici eşleşmeyen bir çağrıyla karşılaştığında oluşur.

Bu hatayı onarmak için bir işlev prototipi ekleyin.
