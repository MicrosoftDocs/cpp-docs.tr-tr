---
title: "Derleyici Hatası C2447 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2447
dev_langs: C++
helpviewer_keywords: C2447
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20f9e3259b355a40875bd9fc06f04fe2bb3147d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2447"></a>Derleyici Hatası C2447
' {': işlev üstbilgisi eksik (eski stil resmi liste?)  
  
 Derleyici, genel kapsamda beklenmedik bir açık ayraç ile karşılaştı. Çoğu durumda, bunun nedeni hatalı biçimlendirilmiş işlev üstbilgisi, yanlış yerleştirilmiş bir bildirim ya da boştaki bir noktalı virgüldür. Bu sorunu gidermek için, açık ayracın düzgün biçimlendirilmiş bir işlev üstbilgisini izlediğini ve kendinden önce bir bildirim veya boşta noktalı virgül gelmediğini doğrulayın.  
  
 Bu hata ayrıca eski stil C dili biçimsel bağımsız değişken listesi nedeniyle de meydana gelebilir. Bu sorunu gidermek için, bağımsız değişken listesini modern stili (parantez içine alınmış biçimi) kullanacak şekilde yeniden düzenleyin.  
  
 Aşağıdaki örnek C2447 oluşturur:  
  
```  
// C2447.cpp  
int c;  
{}       // C2447  
```