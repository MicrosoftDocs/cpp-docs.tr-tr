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
ms.workload: cplusplus
ms.openlocfilehash: d6e3aa8d01dcc85b6c37684ccccaf82c84d8dfb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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