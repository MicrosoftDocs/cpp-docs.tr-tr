---
title: Derleyici hatası C2567
ms.date: 11/04/2016
f1_keywords:
- C2567
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
ms.openlocfilehash: 921992c678c1de0b74f99f544173478ebe809b2c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177462"
---
# <a name="compiler-error-c2567"></a>Derleyici hatası C2567

' dosya ' içinde meta veriler açılamıyor, dosya silinmiş veya taşınmış olabilir

Kaynak (`#using`ile) içinde başvurulan bir meta veri dosyası, derleyicinin ön uç sürecinde olduğu gibi derleyici arka ucu işlemiyle aynı dizinde bulunamadı. Daha fazla bilgi için bkz. [#using yönergesi](../../preprocessor/hash-using-directive-cpp.md) .

C2567, bir makinede **/c** ile derleme yapmanız ve sonra başka bir makinede bir bağlantı zamanı kodu oluşturulmasını denerseniz meydana gelebilir. Daha fazla bilgi için bkz. [/LTCG (bağlantı-zaman kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)).

Bilgisayarınızda daha fazla bellek olmadığını da belirtebilir.

Bu hatayı düzeltmek için, meta veri dosyasının yapı sürecinin tüm aşamaları için aynı dizin konumunda olduğundan emin olun.
