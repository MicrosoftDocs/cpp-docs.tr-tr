---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2567'
title: Derleyici hatası C2567
ms.date: 11/04/2016
f1_keywords:
- C2567
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
ms.openlocfilehash: 113dfebc1ac6bde6857ea55fd6249fff12c9faae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209119"
---
# <a name="compiler-error-c2567"></a>Derleyici hatası C2567

' dosya ' içinde meta veriler açılamıyor, dosya silinmiş veya taşınmış olabilir

Kaynak (ile) içinde başvurulan bir meta veri dosyası, derleyicinin `#using` ön uç sürecinde olduğu gibi derleyici arka ucu işlemiyle aynı dizinde bulunamadı. Daha fazla bilgi için bkz. [#using yönergesi](../../preprocessor/hash-using-directive-cpp.md) .

C2567, bir makinede **/c** ile derleme yapmanız ve sonra başka bir makinede bir bağlantı zamanı kodu oluşturulmasını denerseniz meydana gelebilir. Daha fazla bilgi için bkz. [/LTCG (bağlantı-zaman kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)).

Bilgisayarınızda daha fazla bellek olmadığını da belirtebilir.

Bu hatayı düzeltmek için, meta veri dosyasının yapı sürecinin tüm aşamaları için aynı dizin konumunda olduğundan emin olun.
