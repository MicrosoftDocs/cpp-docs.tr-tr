---
title: Yığın kullanımı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 827a129c0b7a444cc5b48ba68a3e360712e1c08e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721545"
---
# <a name="stack-usage"></a>Yığın Kullanımı

Tüm geçerli adresi RSP bellekten geçici olarak kabul edilir: işletim sistemi veya bir hata ayıklayıcı, bir kullanıcı hata ayıklama oturumu veya kesinti işleyicisinin sırasında bu bellek yazabilir. Bu nedenle, RSP her zaman bir yığın çerçevesine değerleri okunamıyor veya yazılamıyor denemeden önce ayarlanmalıdır.

Bu bölümde, yerel değişkenler için yığın alanı ayırma anlatılmaktadır ve **alloca** iç.

- [Yığın Ayırma](../build/stack-allocation.md)

- [Dinamik Parametre Yığın Alanı Yapımı](../build/dynamic-parameter-stack-area-construction.md)

- [İşlev Türleri](../build/function-types.md)

- [malloc Hizalaması](../build/malloc-alignment.md)

- [alloca](../build/alloca.md)

## <a name="see-also"></a>Ayrıca Bkz.

[x64 Yazılım Kuralları](../build/x64-software-conventions.md)