---
title: C Çalışma Zamanı Hatası R6009
ms.date: 11/04/2016
f1_keywords:
- R6009
helpviewer_keywords:
- R6009
ms.assetid: edfb1f8b-3807-48f4-a994-318923b747ae
ms.openlocfilehash: 64391f8ec05a99bb85a9d6cd00d6488a945fdb62
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197359"
---
# <a name="c-runtime-error-r6009"></a>C Çalışma Zamanı Hatası R6009

ortam için yeterli alan yok

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç bellek sorunu olduğundan uygulama kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle son derece düşük bellek koşulu, ortam değişkenleri tarafından çok fazla bellek alınması veya programdaki bir hata nedeniyle oluşur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

Programı yüklemek için yeterli bellek yoktu, ancak **envp** dizisinin oluşturulması için yeterli bellek yok.  Bunun nedeni son derece düşük bellek koşullarından veya alışılmadık büyük ortam değişkeni kullanımıyla kaynaklanıyor olabilir. Aşağıdaki çözümlerden birini göz önünde bulundurun:

- Programın kullanabileceği bellek miktarını artırın.

- Komut satırı bağımsız değişkenlerinin sayısını ve boyutunu küçültün.

- Gereksiz değişkenleri kaldırarak ortam boyutunu küçültün.
