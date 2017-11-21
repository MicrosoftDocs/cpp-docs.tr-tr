---
title: "Derleyici Hatası C2355 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2355
dev_langs: C++
helpviewer_keywords: C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 76d274ee94c20502a0ca6f167a9fce1f1dbf9465
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2355"></a>Derleyici Hatası C2355
'this': yalnızca statik olmayan üye işlevleri veya statik olmayan veri üyesi başlatıcıları içinde başvurulabilir  
  
 `this` İşaretçidir yalnızca statik olmayan üye işlevleri içinde veya statik olmayan veri üyesi başlatıcıları geçerli. Üye işlev tanımının sınıf bildiriminin dışında sınıf kapsamı değil düzgün yetkili olduğunu olduğunda bu hata neden olabilir. Hata da oluşabilir zaman `this` işaretçi sınıfında bildirilmemiş bir işlevdeki kullanılır.  
  
 Bu sorunu gidermek için üye işlev tanımını üye işlevi bildirimi sınıfında eşleştiğinden ve bunu statik bildirilmedi, emin olun. Veri üye başlatıcıları için veri üyesi statik bildirilmedi emin olun.  
  
 Aşağıdaki örnek C2355 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2355.cpp  
// compile with: /c  
class MyClass {};  
MyClass *p = this;   // C2355  
  
// OK  
class MyClass2 {  
public:  
   void Test() {  
      MyClass2 *p = this;  
   }  
};  
```