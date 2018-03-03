---
title: "Derleyici Hatası C2099 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2099
dev_langs:
- C++
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44e5faccc28877793aa42c5fb765e6d21eb19a1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2099"></a>Derleyici Hatası C2099
Başlatıcı sabit bir değer değil  
  
 Bu hata yalnızca C derleyicisi tarafından verilir ve yalnızca otomatik olmayan değişkenleri oluşur.  Program başlangıcında otomatik olmayan değişkenleri derleyici başlatır ve ile başlatılmış değerlerin sabit olması gerekir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2099 oluşturur.  
  
```  
// C2099.c  
int j;  
int *p;  
j = *p;   // C2099 *p is not a constant  
```  
  
## <a name="example"></a>Örnek  
 C2099 da gerçekleşebilir derleyici sabit bir ifade altında Katlama gerçekleştirmek mümkün olmadığı için **/fp: katı** kayan nokta çünkü duyarlık ortam ayarları (bkz [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md) için Daha fazla bilgi) çalışma zamanı için derleme farklı olabilir.  
  
 Sabit olduğunda başarısız Katlama, c dilinde izin verilmiyor dinamik başlatma derleyici çağırır  
  
 Bu hatayı gidermek için .cpp dosyası olarak modülü derleme veya ifade basitleştirin.  
  
 Daha fazla bilgi için bkz: [/fp (Floating-Point davranış belirtin)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
 Aşağıdaki örnek C2099 oluşturur.  
  
```  
// C2099_2.c  
// compile with: /fp:strict /c  
float X = 2.0 - 1.0;   // C2099  
float X2 = 1.0;   // OK  
```