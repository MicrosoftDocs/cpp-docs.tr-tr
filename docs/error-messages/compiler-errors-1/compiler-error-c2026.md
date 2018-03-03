---
title: "Derleyici Hatası C2026 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2026
dev_langs:
- C++
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: acee7db1513dd3e999a90218ea674930c2a13f1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2026"></a>Derleyici Hatası C2026
dize sondaki kesilmiş karakterleri çok büyük  
  
 Dize 16380 tek baytlık karakterler sınırdan daha uzun.  
  
 Birleştirilmiş bitişik dizeleri önce bir dize 16380 tek baytlı karakterden uzun olamaz.  
  
 Bu hata hakkında yarısı bu uzunlukta bir UNICODE dizesi de oluşturur.  
  
 Şu şekilde tanımlanmış bir dize varsa, C2026 oluşturur:  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 Bunu şu şekilde bölmek:  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 Özel bir kaynak veya dış dosyası olağanüstü büyük dize değişmez değerleri (32 K veya daha fazla) depolamak isteyebilirsiniz. Bkz: [yeni özel veya veri kaynağı oluşturma](../../windows/creating-a-new-custom-or-data-resource.md) daha fazla bilgi için.