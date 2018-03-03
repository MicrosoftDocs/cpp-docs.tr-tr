---
title: "Derleyici Hatası C2558 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2558
dev_langs:
- C++
helpviewer_keywords:
- C2558
ms.assetid: 822b701e-dcae-423a-b21f-47f36aff9c90
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3224a612a41a87c76cd774f50e49d523bd24d06c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2558"></a>Derleyici Hatası C2558
'tanımlayıcı' : kullanılabilir kopya oluşturucu yok ya da kopya oluşturucu 'açık' olarak belirtildi  
  
 Kopya oluşturucusu, bir nesneyi aynı türde başka bir nesneden başlatır. (Nesnenin bir kopyasını alır.) Derleyici, herhangi bir oluşturucu tanımlamazsanız, varsayılan bir kopya oluşturucu yaratır.  
  
### <a name="to-fix-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Bir sınıf, kopya Oluşturucu olduğu kopyalamak için bir girişimde sorun ortaya çıkabilir `private`. Çoğu durumda, bir sınıf olan bir `private` kopya Oluşturucu değil kopyalanması. Ortak bir programlama teknik bildiren bir `private` bir sınıf doğrudan kullanılmasını önlemek için kopya Oluşturucu. Sınıf kendisi tarafından kullanılamayabilir ya da düzgün şekilde çalışması için başka bir sınıf gerektirebilir.  
  
     Olan bir sınıfı güvenli olduğunu belirlerseniz bir `private` kopyalama oluşturucusu, sahip sınıfından yeni bir sınıf türetin `private` oluşturucusu ve marka bir `public` veya `protected` kopya Oluşturucu Yeni sınıfta kullanılabilir. Türetilen sınıfı orijinalinin yerine kullanın.  
  
2.  Bir sınıf, kopya Oluşturucu açık kopyalamak için bir girişimde sorun ortaya çıkabilir. Kopya Oluşturucu olarak bildirme  `explicit` /işlevleri, bir sınıfın nesnelerini geçirme ve döndürme engeller. Açıkça oluşturucular hakkında daha fazla bilgi için bkz: [kullanıcı tanımlı tür dönüşümleri](../../cpp/user-defined-type-conversions-cpp.md).  
  
3.  Bildirilen bir sınıf örneği kopyalamak için bir girişimde sorun ortaya çıkabilir `const` değil sürer kopya Oluşturucu kullanarak bir `const` parametresi başvuru. Kopya Oluşturucu ile bildirme bir `const` başvuru const olmayan tür başvurusu yerine yazın.