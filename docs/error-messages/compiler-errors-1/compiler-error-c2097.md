---
title: "Derleyici Hatası C2097 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2097
dev_langs: C++
helpviewer_keywords: C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d6955a610e3109c3b16edf96913be4503ee4c647
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2097"></a>Derleyici Hatası C2097
Geçersiz başlatma  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Nonconstant değerini kullanarak bir değişken başlatma.  
  
2.  Uzun bir adresi kısa bir adresle başlatma.  
  
3.  Yerel yapısı, UNION ya da dizi ile derleme yapılırken nonconstant bir ifade ile başlatma **/Za**.  
  
4.  Virgül işleci içeren bir ifade ile başlatma.  
  
5.  Sabit ne sembolik bir ifade ile başlatma.