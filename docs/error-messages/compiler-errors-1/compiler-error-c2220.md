---
title: Derleyici Hatası C2220 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2220
dev_langs:
- C++
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d23476de35e0af45b46a775683ba8673b4959346
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171499"
---
# <a name="compiler-error-c2220"></a>Derleyici Hatası C2220
hata - oluşturulan herhangi bir nesne dosyası olarak kabul uyarı  
  
 [/WX](../../build/reference/compiler-option-warning-level.md) tüm uyarıları hata ele bildirir. Bir hata oluştuğundan hiçbir nesne veya yürütülebilir dosyası oluşturuldu.  
  
 Bu hata görünür **/WX** bayrağı ayarlanmış ve derleme sırasında bir uyarı gerçekleşir. Bu hatayı düzeltmek için her uyarı projenizdeki ortadan kaldırmanız gerekir.  
  
### <a name="to-fix-use-one-of-the-following-techniques"></a>Düzeltmek için aşağıdaki yöntemlerden birini kullanın  
  
-   Uyarı projenizdeki neden sorunları giderin.  
  
-   Daha düşük bir uyarı düzeyde derleme — Örneğin, **/W3** yerine **/W4**.  
  
-   Kullanım bir [uyarı](../../preprocessor/warning.md) devre dışı bırakmak veya belirli bir uyarı bastırma pragması.  
  
-   Kullanmayan **/WX** derlemek için.