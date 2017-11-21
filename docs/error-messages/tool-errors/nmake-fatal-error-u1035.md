---
title: "NMAKE önemli hatası U1035 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1035
dev_langs: C++
helpviewer_keywords: U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a4d672618656b72ab7ac4c4ed617c90080b58304
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE Önemli Hatası U1035
sözdizimi hatası: beklenen ':' veya '=' ayırıcısı  
  
 Ya da iki nokta (**:**) veya eşittir işareti (**=**) bekleniyordu.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  İki nokta hedef izleyin değil.  
  
2.  Bir tek harfli hedef ardından iki nokta ve boşluk (örneğin, c:). NMAKE sürücü belirtimi yorumlanır.  
  
3.  İki nokta çıkarım kuralı izleyin değil.  
  
4.  Bir makro tanımı bir eşittir işareti arkasından değil.  
  
5.  Ters eğik çizgi karakteri ardından (**\\**) yeni bir satır için bir komut devam etmek için kullanıldı.  
  
6.  Bir dize, herhangi bir NMAKE sözdizimi kural izlemeyecek görüldü.  
  
7.  Derleme görevleri dosyası bir sözcük işlemci tarafından biçimlendirildi.