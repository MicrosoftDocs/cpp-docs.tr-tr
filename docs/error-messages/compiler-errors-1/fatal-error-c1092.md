---
title: "Önemli hata C1092 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1092
dev_langs: C++
helpviewer_keywords: C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fac0a5218e1faf16d3db459567c36775acd9bb12
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1092"></a>Önemli hata C1092
Düzenle ve devam et, veri türleri değişiklikler desteklemiyor; gerekli derleme  
  
 Değiştirdiğiniz ya da bir veri türü son başarılı yapıdan beri eklenmiş.  
  
-   Düzenle ve devam et, sınıf, yapı veya liste tanımları dahil olmak üzere var olan veri türleri değişiklikleri desteklemez. Hata ayıklamayı durdurun ve uygulamayı oluşturun.  
  
-   Düzenle ve devam et yeni veri türleri program veritabanı dosyası varsa, vc gibi ek desteklemiyor*x*0. pdb (burada *x* Visual C++ ana sürüm kullanımda olan) salt okunurdur. Veri türlerini eklemek için derleyici, yazma modunda .pdb dosyasını açmanız gerekir.  
  
### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>Bu hata geçerli hata ayıklama oturumu sona erdirmeden kaldırmak için  
  
1.  Geri durumuna hata önce veri türünü değiştirin.  
  
2.  Gelen **hata ayıklama** menüsünde seçin **kod değişikliklerini uygulama**.  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>Bu hata, kaynak kodunuzu değiştirmeden kaldırmak için  
  
1.  Gelen **hata ayıklama** menüsünde seçin **durdurma hata ayıklama**.  
  
2.  Gelen **yapı** menüsünde seçin **yapı**.  
  
 Daha fazla bilgi için bkz: [desteklenen kod değişiklikleri](/visualstudio/debugger/supported-code-changes-cpp).