---
title: Hedefleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- targets, specifying in NMAKE
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: edb75258c548526c68ed33f7f8037656750f6855
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713812"
---
# <a name="targets"></a>Hedefler

Bir bağımlılık satırında herhangi bir geçerli dosya adı, dizin adı'nı kullanarak, bir veya daha fazla hedeflerini belirtin veya [pseudotarget](../build/pseudotargets.md). Birden çok hedefi, bir veya daha fazla boşluk veya sekme ile ayırın. Hedefleri büyük/küçük harfe duyarlı değildir. Yollar ile dosya adlarını izin verilir. Bir hedef 256 karakterden uzun olamaz. İki nokta üst üste önceki hedef tek bir karakter ise ayıran bir alanı kullanın. Aksi takdirde, NMAKE harf iki nokta üst üste birlikte bir sürücü tanımlayıcı olarak yorumlar.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

[Sözde Hedefler](../build/pseudotargets.md)

[Birden çok hedef](../build/multiple-targets.md)

[Birikmeli bağımlılıklar](../build/cumulative-dependencies.md)

[Birden çok açıklama bloğundaki hedefler](../build/targets-in-multiple-description-blocks.md)

[Bağımlılık yan etkileri](../build/dependency-side-effects.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Açıklama Blokları](../build/description-blocks.md)