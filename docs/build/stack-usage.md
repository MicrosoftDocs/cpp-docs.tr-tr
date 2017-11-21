---
title: "Yığın kullanımı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c7a74abff7a2971fe66fa2df878078ac95f58fe8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="stack-usage"></a>Yığın Kullanımı
Geçerli RSP adresinin ötesindeki tüm bellek geçici olarak kabul edilir: işletim sistemi veya bir hata ayıklayıcısı bu bellek bir kullanıcı hata ayıklama oturumu veya kesinti işleyicisinin sırasında üzerine yazabilir. Bu nedenle, RSP her zaman bir yığın çerçevesine değerleri okunamıyor veya yazılamıyor denemeden önce ayarlanmalıdır.  
  
 Bu bölümde, yerel değişkenleri yığın alanı ayırma anlatılmaktadır ve **alloca** iç.  
  
-   [Yığın ayırma](../build/stack-allocation.md)  
  
-   [Dinamik parametre yığın alanı yapımı](../build/dynamic-parameter-stack-area-construction.md)  
  
-   [İşlev türleri](../build/function-types.md)  
  
-   [malloc hizalaması](../build/malloc-alignment.md)  
  
-   [alloca](../build/alloca.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [x64 yazılım kuralları](../build/x64-software-conventions.md)