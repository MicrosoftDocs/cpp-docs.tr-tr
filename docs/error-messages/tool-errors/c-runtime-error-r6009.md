---
title: C çalışma zamanı hatası R6009 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6009
dev_langs:
- C++
helpviewer_keywords:
- R6009
ms.assetid: edfb1f8b-3807-48f4-a994-318923b747ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 42a5aed9f823b5d2c5425c4d7baae129c08e76e7
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860933"
---
# <a name="c-runtime-error-r6009"></a>C çalışma zamanı hatası R6009

ortam için yeterli alan yok

> [!NOTE]
> Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bellek sorunu olduğundan uygulaması kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle bir son derece düşük bellek durumu, ortam değişkenleri ya da hata programı tarafından gerçekleştirilecek çok fazla bellek tarafından kaynaklanır.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> - Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Programı yüklemek için yeterli bellek, ancak oluşturmak için yeterli bellek yoktu **envp** dizisi.  Bu, olağan dışı derecede büyük bir ortam değişken kullanımı veya son derece düşük bellek koşullarını neden olabilir. Aşağıdaki çözümlerden birini göz önünde bulundurun:

- Program için kullanılabilir bellek miktarını artırın.

- Sayı ve komut satırı bağımsız değişkenleri boyutunu azaltın.

- Gereksiz değişkenleri kaldırarak ortam boyutunu azaltın.