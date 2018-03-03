---
title: "Derleyici Hatası C2097 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2097
dev_langs:
- C++
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e50154d88a5019cdc181c4921c09cbd222d8b530
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2097"></a>Derleyici Hatası C2097
Geçersiz başlatma  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Nonconstant değerini kullanarak bir değişken başlatma.  
  
2.  Uzun bir adresi kısa bir adresle başlatma.  
  
3.  Yerel yapısı, UNION ya da dizi ile derleme yapılırken nonconstant bir ifade ile başlatma **/Za**.  
  
4.  Virgül işleci içeren bir ifade ile başlatma.  
  
5.  Sabit ne sembolik bir ifade ile başlatma.