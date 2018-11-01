---
title: Yığın Kullanımı
ms.date: 11/04/2016
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
ms.openlocfilehash: 5ee9da50a03e1137ed6543cd349481148c9127d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452227"
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