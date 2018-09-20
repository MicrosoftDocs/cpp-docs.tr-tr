---
title: 2.7.2.5 varsayılan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c856df07-705c-4ad3-9105-a268dd33e939
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 047110fe80d15d0ff3d979eeec8abf3e42dc35f1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401569"
---
# <a name="2725-default"></a>2.7.2.5 default

**Varsayılan** yan tümcesi değişkenlerin veri paylaşımı öznitelikleri etkiler kullanıcıya izin verir. Söz dizimi **varsayılan** yan tümcesi şu şekildedir:

```
default(shared | none)
```

Belirtme **default(shared)** açıkça görünür her bir değişken listesi için eşdeğer bir gruba bir **paylaşılan** yan tümcesi olduğu sürece **threadprivate** veya **olumsuz**`t`-tam. Açık bir olmadığında **varsayılan** yan tümcesi, varsayılan davranış, aynı ise **default(shared)** belirtildi.

Belirtme **default(none)** aşağıdakilerden en az birini sözcük ölçüde paralel yapısının bir değişkende yapılan her gönderme true olmasını gerektirir:

- Değişken bir veri paylaşım öznitelik yan tümcesinde başvuru içeren bir yapısı açıkça listelenir.

- Değişkeni içinde paralel yapısı bildirilir.

- Bu değişken **threadprivate**.

- Değişkenin bir **const**-tam türü.

- For döngüsü denetim değişkeniyle değişkendir bir **için** hemen takip eden döngü bir **için** veya **için paralel** yönergesi ve değişken başvurusu, döngünün içinde görünür .

Bir değişken belirterek bir **firstprivate**, **lastprivate**, veya **azaltma** kapalı bir yönerge yan tümcesi kapsayan değişkeni örtük bir başvuru neden olur bağlamı. Örtük tür başvurular da, yukarıda listelenen gereksinimlerin tabidir.

Yalnızca tek bir **varsayılan** yan tümcesi belirtilebilir bir **paralel** yönergesi.

Bir değişkenin varsayılan kullanarak veri paylaşım öznitelik kılınabilir **özel**, **firstprivate**, **lastprivate**, **azaltma**, ve **paylaşılan** yan tümceleri, aşağıdaki örnekte gösterildiği gibi:

```
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\
   private(x)  private(r)  lastprivate(i)
```