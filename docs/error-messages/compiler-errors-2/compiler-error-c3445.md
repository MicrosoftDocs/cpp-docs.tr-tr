---
title: "Derleyici Hatası C3445 | Microsoft Docs"
ms.custom: 
ms.date: 04/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3445
dev_langs: C++
helpviewer_keywords: C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e880eca87816973d531a2662486dde0ae7c77987
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3445"></a>Derleyici Hatası C3445
Copy-listesi-başlatılması '*türü*' açık Oluşturucu kullanamazsınız  
  
ISO C ++ 17 standart göre derleyici kopyalama listesi başlatma aşırı yük çözüm için açık bir oluşturucu göz önünde bulundurmanız gereken ancak bu aşırı gerçekte seçilirse hatayla yükseltmeniz gerekir.  
  
Visual Studio 2017 içinde başlayarak, derleyici tarafından Visual Studio 2015 bulunamadı başlatıcı listesi kullanılarak nesne oluşturma ilgili hatalar bulur. Bu hatalar kilitlenmelerine veya çalışma zamanında tanımsız davranış neden olabilir.

## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3445 oluşturur.  
  
```cpp  
// C3445.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1 = { 1 };     // error C3445: copy-list-initialization of 
                      //     'A' cannot use an explicit constructor
}
```  
  
Hatayı düzeltmek için bunun yerine doğrudan başlatma kullanın:  
  
```cpp  
// C3445b.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1{ 1 };
}  
```  
  