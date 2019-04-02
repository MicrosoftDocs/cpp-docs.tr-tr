---
title: Derleyici Hatası C2865
ms.date: 11/04/2016
f1_keywords:
- C2865
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
ms.openlocfilehash: 38b7dd86a57c3cd89811c6489e51fb4271fd7b79
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769621"
---
# <a name="compiler-error-c2865"></a>Derleyici Hatası C2865

'function': handle_or_pointer için geçersiz karşılaştırma

Başvurular karşılaştırabilirsiniz [sınıfları ve yapıları](../../extensions/classes-and-structs-cpp-component-extensions.md) veya yönetilen bunlar aynı nesneye (==) veya farklı nesnelere başvuruyorsa, görmek için eşitlik için yalnızca başvuru türleri (! =).

Bunları herhangi bir zamanda .NET çalışma zamanı yönetilen nesneleri taşıma çünkü sıralama için test sonucunu değiştirmek karşılaştırılamıyor.