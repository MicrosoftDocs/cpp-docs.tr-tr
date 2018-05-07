---
title: İfade değerlendirici hatası CXX0033 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0033
dev_langs:
- C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 720b1aec6c9be16879119bc0e8148a301507577a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0033"></a>İfade Değerlendirici Hatası CXX0033
OMF tür bilgisinde hata  
  
 Çalıştırılabilir dosya bir geçerli nesne modülü biçimi'hata ayıklama için (OMF) sahip değil.  
  
 Bu hata için CAN0033 aynıdır.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Yürütülebilir dosyanın bu sürümü Visual C++ ile yayımlanan bağlayıcı ile oluşturulmadı. LINK.exe geçerli sürümü kullanılarak nesne kodu yeniden bağlayın.  
  
2.  .Exe dosyası bozulmuş olabilir. Derlenir ve programı yeniden bağlayın.