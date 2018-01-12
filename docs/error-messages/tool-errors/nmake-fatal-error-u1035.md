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
ms.workload: cplusplus
ms.openlocfilehash: 0d7730f882b40c24822cb4b8e2c6a12147cacf2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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