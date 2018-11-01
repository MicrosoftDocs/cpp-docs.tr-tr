---
title: C çalışma zamanı hatası R6008
ms.date: 11/04/2016
f1_keywords:
- R6008
helpviewer_keywords:
- R6008
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
ms.openlocfilehash: 60e6475a84d2662ad3718e04dba879dc06afeee7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441905"
---
# <a name="c-runtime-error-r6008"></a>C çalışma zamanı hatası R6008

bağımsız değişkenler için yeterli alan yok

> [!NOTE]
> Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bellek sorunu olduğundan uygulaması kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle bir son derece düşük bellek durumu, ortam değişkenleri ya da hata programı tarafından gerçekleştirilecek çok fazla bellek tarafından kaynaklanır.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Uygulamaya sayısını ve komut satırı bağımsız değişkenlerinin boyutunu azaltın.
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> - Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Programı yüklemek için yeterli bellek ancak oluşturmak için yeterli bellek yoktu **argv** dizisi. Bu, olağan dışı derecede büyük komut satırları veya ortam değişken kullanımı veya son derece düşük bellek koşullarını kaynaklanabilir. Aşağıdaki çözümlerden birini göz önünde bulundurun:

- Program için kullanılabilir bellek miktarını artırın.

- Sayı ve komut satırı bağımsız değişkenleri boyutunu azaltın.

- Gereksiz değişkenleri kaldırarak ortam boyutunu azaltın.