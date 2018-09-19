---
title: C çalışma zamanı hatası R6008 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6008
dev_langs:
- C++
helpviewer_keywords:
- R6008
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39b06566f84003b08f5fe3869a021c4bf86dcf5f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105167"
---
# <a name="c-runtime-error-r6008"></a>C çalışma zamanı hatası R6008

bağımsız değişkenler için yeterli alan yok

> [!NOTE]
>  Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bellek sorunu olduğundan uygulaması kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle bir son derece düşük bellek durumu, ortam değişkenleri ya da hata programı tarafından gerçekleştirilecek çok fazla bellek tarafından kaynaklanır.
>
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
>  -   Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> -   Uygulamaya sayısını ve komut satırı bağımsız değişkenlerinin boyutunu azaltın.
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Programı yüklemek için yeterli bellek ancak oluşturmak için yeterli bellek yoktu **argv** dizisi. Bu, olağan dışı derecede büyük komut satırları veya ortam değişken kullanımı veya son derece düşük bellek koşullarını kaynaklanabilir. Aşağıdaki çözümlerden birini göz önünde bulundurun:

- Program için kullanılabilir bellek miktarını artırın.

- Sayı ve komut satırı bağımsız değişkenleri boyutunu azaltın.

- Gereksiz değişkenleri kaldırarak ortam boyutunu azaltın.