---
title: "İfade değerlendirici hatası CXX0033 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0033
dev_langs: C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 618dbe464adc64f36e35b9c329eb476166b8b5e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0033"></a>İfade Değerlendirici Hatası CXX0033
OMF tür bilgisinde hata  
  
 Çalıştırılabilir dosya bir geçerli nesne modülü biçimi'hata ayıklama için (OMF) sahip değil.  
  
 Bu hata için CAN0033 aynıdır.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Yürütülebilir dosyanın bu sürümü Visual C++ ile yayımlanan bağlayıcı ile oluşturulmadı. LINK.exe geçerli sürümü kullanılarak nesne kodu yeniden bağlayın.  
  
2.  .Exe dosyası bozulmuş olabilir. Derlenir ve programı yeniden bağlayın.