---
title: NMAKE önemli hatası U1035 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1035
dev_langs:
- C++
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bb32f815345b933ad6a65a0c8c1ec8ad59cbe81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322802"
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