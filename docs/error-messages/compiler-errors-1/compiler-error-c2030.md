---
title: Derleyici Hatası C2030
ms.date: 11/04/2016
f1_keywords:
- C2030
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
ms.openlocfilehash: 217f97d205e1da075277b8b0bc22ff3baab13482
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602182"
---
# <a name="compiler-error-c2030"></a>Derleyici Hatası C2030

erişebilirliği 'protected private' olan bir yok edici 'sealed' olarak bildirilmiş bir sınıfın üyesi olamaz

Bir Windows çalışma zamanı sınıf olarak bildirilen `sealed` özel korumalı bir yok Edicisi olamaz. Yalnızca genel sanal ve özel sanal olmayan yok ediciler sealed türlerde izin verilir. Daha fazla bilgi için [başvuru sınıfları ve yapıları](../../cppcx/ref-classes-and-structs-c-cx.md).

Bu hatayı düzeltmek için yok edici erişilebilirliğini değiştirin.