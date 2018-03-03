---
title: "Derleyici Uyarısı (düzey 1) C4656 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4656
dev_langs:
- C++
helpviewer_keywords:
- C4656
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f342887bc91a48e9446f1403f1722c40b989546d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4656"></a>Derleyici Uyarısı (düzey 1) C4656
'simgesi': veri türü yeni veya son derlemeden bu yana değişti ya da farklı başka bir yere tanımlanır  
  
 Eklenen veya son başarılı yapıdan beri kolaylaştırarak kaynak kodunuz için yeni bir veri türü değiştirildi. Düzenle ve devam et, var olan veri türleri değişiklikleri desteklemez.  
  
 Bu uyarı tarafından her zaman izleyecektir [önemli hata C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Daha fazla bilgi için bkz: [desteklenen kod değişiklikleri](/visualstudio/debugger/supported-code-changes-cpp).  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Geçerli hata ayıklama oturumu sona erdirmeden bu uyarıyı kaldırmak için  
  
1.  Geri durumuna hata önce veri türünü değiştirin.  
  
2.  Gelen **hata ayıklama** menüsünde seçin **kod değişikliklerini uygulama**.  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>Bu hata, kaynak kodunuzu değiştirmeden kaldırmak için  
  
1.  Gelen **hata ayıklama** menüsünde seçin **durdurma hata ayıklama**.  
  
2.  Gelen **yapı** menüsünde seçin **yapı**.