---
title: C Çalışma Zamanı Hatası R6008
ms.date: 11/04/2016
f1_keywords:
- R6008
helpviewer_keywords:
- R6008
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
ms.openlocfilehash: 214b6548cc7a3b880223503c2f3e9222d64212ca
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197399"
---
# <a name="c-runtime-error-r6008"></a>C Çalışma Zamanı Hatası R6008

bağımsız değişkenler için yeterli alan yok

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç bellek sorunu olduğundan uygulama kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle son derece düşük bellek koşulu, ortam değişkenleri tarafından çok fazla bellek alınması veya programdaki bir hata nedeniyle oluşur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Uygulama için komut satırı bağımsız değişkenlerinin sayısını ve boyutunu küçültün.
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

Programı yüklemek için yeterli bellek yoktu, ancak **argv** dizisini oluşturmak için yeterli bellek yok. Bunun nedeni son derece düşük bellek koşulları veya alışılmadık büyük komut satırları veya ortam değişkeni kullanımı olabilir. Aşağıdaki çözümlerden birini göz önünde bulundurun:

- Programın kullanabileceği bellek miktarını artırın.

- Komut satırı bağımsız değişkenlerinin sayısını ve boyutunu küçültün.

- Gereksiz değişkenleri kaldırarak ortam boyutunu küçültün.
