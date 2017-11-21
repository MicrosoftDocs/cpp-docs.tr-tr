---
title: "Derleyici Hatası C2558 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2558
dev_langs: C++
helpviewer_keywords: C2558
ms.assetid: 822b701e-dcae-423a-b21f-47f36aff9c90
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b11827ed70609a83be9e63de2af3d3b8f12d2310
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2558"></a>Derleyici Hatası C2558
'tanımlayıcı' : kullanılabilir kopya oluşturucu yok ya da kopya oluşturucu 'açık' olarak belirtildi  
  
 Kopya oluşturucusu, bir nesneyi aynı türde başka bir nesneden başlatır. (Nesnenin bir kopyasını alır.) Derleyici, herhangi bir oluşturucu tanımlamazsanız, varsayılan bir kopya oluşturucu yaratır.  
  
### <a name="to-fix-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Bir sınıf, kopya Oluşturucu olduğu kopyalamak için bir girişimde sorun ortaya çıkabilir `private`. Çoğu durumda, bir sınıf olan bir `private` kopya Oluşturucu değil kopyalanması. Ortak bir programlama teknik bildiren bir `private` bir sınıf doğrudan kullanılmasını önlemek için kopya Oluşturucu. Sınıf kendisi tarafından kullanılamayabilir ya da düzgün şekilde çalışması için başka bir sınıf gerektirebilir.  
  
     Olan bir sınıfı güvenli olduğunu belirlerseniz bir `private` kopyalama oluşturucusu, sahip sınıfından yeni bir sınıf türetin `private` oluşturucusu ve marka bir `public` veya `protected` kopya Oluşturucu Yeni sınıfta kullanılabilir. Türetilen sınıfı orijinalinin yerine kullanın.  
  
2.  Bir sınıf, kopya Oluşturucu açık kopyalamak için bir girişimde sorun ortaya çıkabilir. Kopya Oluşturucu olarak bildirme  `explicit` /işlevleri, bir sınıfın nesnelerini geçirme ve döndürme engeller. Açıkça oluşturucular hakkında daha fazla bilgi için bkz: [kullanıcı tanımlı tür dönüşümleri](../../cpp/user-defined-type-conversions-cpp.md).  
  
3.  Bildirilen bir sınıf örneği kopyalamak için bir girişimde sorun ortaya çıkabilir `const` değil sürer kopya Oluşturucu kullanarak bir `const` parametresi başvuru. Kopya Oluşturucu ile bildirme bir `const` başvuru const olmayan tür başvurusu yerine yazın.