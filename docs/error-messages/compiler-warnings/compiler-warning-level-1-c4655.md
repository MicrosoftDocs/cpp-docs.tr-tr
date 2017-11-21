---
title: "Derleyici Uyarısı (düzey 1) C4655 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4655
dev_langs: C++
helpviewer_keywords: C4655
ms.assetid: 540f2c7a-e4a1-49af-84b4-03eeea1bbf41
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 891fe3c68e93defba011d4ad4c90daf25fe3a799
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4655"></a>Derleyici Uyarısı (düzey 1) C4655
**'**   
 ***Sembol* ': değişken türü son yapıdan beri yeni olan ya da farklı başka bir yere tanımlanır**  
  
 Değiştirilmiş veya yeni bir veri türü son başarılı yapıdan beri eklenmiş. Düzenle ve devam et, var olan veri türleri değişiklikleri desteklemez.  
  
 Bu uyarı tarafından izlenen bir [önemli hata C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Daha fazla bilgi için bkz: [desteklenen kod değişiklikleri](/visualstudio/debugger/supported-code-changes-cpp).  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Geçerli hata ayıklama oturumu sona erdirmeden bu uyarıyı kaldırmak için  
  
1.  Geri durumuna hata önce veri türünü değiştirin.  
  
2.  Gelen **hata ayıklama** menüsünde seçin **kod değişikliklerini uygulama**.  
  
### <a name="to-remove-this-warning-without-changing-your-source-code"></a>Bu uyarı, kaynak kodunuzu değiştirmeden kaldırmak için  
  
1.  Gelen **hata ayıklama** menüsünde seçin **durdurma hata ayıklama**.  
  
2.  Gelen **yapı** menüsünde seçin **yapı**.