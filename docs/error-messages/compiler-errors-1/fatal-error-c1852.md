---
title: "Önemli hata C1852 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1852
dev_langs: C++
helpviewer_keywords: C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cd7168c6ffa653af54404bf81cdc4d308a76783a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1852"></a>Önemli hata C1852
'filename' geçerli önceden derlenmiş üst bilgi dosyası değil  
  
 Dosya önceden derlenmiş üstbilgi değil.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Geçersiz dosya ile belirtilen **/Yu** veya **#pragma hdrstop**.  
  
2.  Aksi takdirde belirtmezseniz, derleyici .pch dosya uzantısı varsayar.