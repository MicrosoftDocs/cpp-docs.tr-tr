---
title: Derleyici Hatası C2097 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2097
dev_langs:
- C++
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa4b867c7f043d796f208fdc7100509893147daf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2097"></a>Derleyici Hatası C2097
Geçersiz başlatma  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Nonconstant değerini kullanarak bir değişken başlatma.  
  
2.  Uzun bir adresi kısa bir adresle başlatma.  
  
3.  Yerel yapısı, UNION ya da dizi ile derleme yapılırken nonconstant bir ifade ile başlatma **/Za**.  
  
4.  Virgül işleci içeren bir ifade ile başlatma.  
  
5.  Sabit ne sembolik bir ifade ile başlatma.