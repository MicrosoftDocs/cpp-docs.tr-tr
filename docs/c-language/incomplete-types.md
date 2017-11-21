---
title: "Eksik türler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- void keyword [C], incomplete
- types [C], incomplete
- incomplete types
- unions, incomplete
- arrays [C], incomplete types
- void keyword [C]
- structures, incomplete
ms.assetid: 01bc0cf6-9fa7-458c-9371-ecbe54ea6aee
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2dd7ab170717cb0e20d71ad4e62e2cbc03483fbf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="incomplete-types"></a>Eksik Türler
Eksik bir tür, bir tanımlayıcıyı açıklayan, ancak tanımlayıcının boyutunu belirlemek için gereken bilgileri eksik olan bir türdür. Bir "eksik tür" aşağıdakilerden biri olabilir:  
  
-   Üyelerini belirtmediğiniz bir yapı türü.  
  
-   Üyelerini belirtmediğiniz bir birleşim türü.  
  
-   Boyutlarını belirtmediğiniz bir dizi türü.  
  
 Void türü, tamamlanamayan bir eksik türdür. Eksik bir türü tamamlamak için eksik bilgileri belirtin. Aşağıdaki örnekler, eksik türlerin nasıl oluşturulduğunu ve tamamlandığını gösterir.  
  
-   Eksik bir yapı türü oluşturmak için üyelerini belirtmeden bir yapı türü bildirin. Bu örnekte, `ps` işaretçisi `student` adlı eksik bir yapı türüne işaret eder.  
  
    ```  
    struct student *ps;  
    ```  
  
-   Eksik bir yapı türünü tamamlamak için aşağıdaki gibi aynı yapı türünü daha sonra aynı kapsamda üyeleri tanımlanmış olarak bildirin  
  
    ```  
    struct student  
    {  
        int num;  
    }                   /* student structure now completed */  
    ```  
  
-   Eksik bir dizi türü oluşturmak için yinelenme sayısını belirtmeden bir dizi türü bildirin. Örneğin:  
  
    ```  
    char a[];  /* a has incomplete type */  
    ```  
  
-   Eksik bir dizi türünü tamamlamak için aşağıdaki gibi aynı adı daha sonra aynı kapsamda yinelenme sayısı ile birlikte bildirin  
  
    ```  
    char a[25]; /* a now has complete type */  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve türler](../c-language/declarations-and-types.md)