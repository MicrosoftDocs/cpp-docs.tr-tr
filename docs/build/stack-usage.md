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
ms.openlocfilehash: b6f711636089a6f2966002002220aac88cebe17a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379864"
---
# <a name="stack-usage"></a>Yığın Kullanımı
Geçerli RSP adresinin ötesindeki tüm bellek geçici olarak kabul edilir: işletim sistemi veya bir hata ayıklayıcısı bu bellek bir kullanıcı hata ayıklama oturumu veya kesinti işleyicisinin sırasında üzerine yazabilir. Bu nedenle, RSP her zaman bir yığın çerçevesine değerleri okunamıyor veya yazılamıyor denemeden önce ayarlanmalıdır.  
  
 Bu bölümde, yerel değişkenleri yığın alanı ayırma anlatılmaktadır ve **alloca** iç.  
  
-   [Yığın Ayırma](../build/stack-allocation.md)  
  
-   [Dinamik Parametre Yığın Alanı Yapımı](../build/dynamic-parameter-stack-area-construction.md)  
  
-   [İşlev Türleri](../build/function-types.md)  
  
-   [malloc Hizalaması](../build/malloc-alignment.md)  
  
-   [alloca](../build/alloca.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [x64 Yazılım Kuralları](../build/x64-software-conventions.md)