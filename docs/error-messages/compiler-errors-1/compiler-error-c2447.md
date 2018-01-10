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
ms.workload: cplusplus
ms.openlocfilehash: 30c8195467b9cf287ba9f7220555d903ba51c164
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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