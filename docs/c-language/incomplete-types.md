---
title: Eksik türleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- void keyword [C], incomplete
- types [C], incomplete
- incomplete types
- unions, incomplete
- arrays [C], incomplete types
- void keyword [C]
- structures, incomplete
ms.assetid: 01bc0cf6-9fa7-458c-9371-ecbe54ea6aee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae26bf4f3e036e6e71acc090c174638133d2e881
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43759612"
---
# <a name="incomplete-types"></a>Eksik Türler

Bir *eksik tür* , bir tanımlayıcıyı açıklayan, ancak tanımlayıcının boyutunu belirlemek için gereken bilgileri eksik bir türdür. Tamamlanmamış bir türü olabilir:

- Üyelerini belirtmediğiniz bir yapı türü.

- Üyelerini belirtmediğiniz bir birleşim türü.

- Boyutlarını belirtmediğiniz bir dizi türü.

**Void** türü, tamamlanamayan bir eksik tür. Eksik bir türü tamamlamak için eksik bilgileri belirtin. Aşağıdaki örnekler, eksik türlerin nasıl oluşturulduğunu ve tamamlandığını gösterir.

- Eksik bir yapı türü oluşturmak için üyelerini belirtmeden bir yapı türü bildirin. Bu örnekte, `ps` işaretçisi `student` adlı eksik bir yapı türüne işaret eder.

    ```C
    struct student *ps;
    ```

- Eksik bir yapı türünü tamamlamak için aşağıdaki gibi aynı yapı türünü daha sonra aynı kapsamda üyeleri tanımlanmış olarak bildirin

    ```C
    struct student
    {
        int num;
    }                   /* student structure now completed */
    ```

- Eksik bir dizi türü oluşturmak için yinelenme sayısını belirtmeden bir dizi türü bildirin. Örneğin:

    ```C
    char a[];  /* a has incomplete type */
    ```

- Eksik bir dizi türünü tamamlamak için aşağıdaki gibi aynı adı daha sonra aynı kapsamda yinelenme sayısı ile birlikte bildirin

    ```C
    char a[25]; /* a now has complete type */
    ```

## <a name="see-also"></a>Ayrıca Bkz.

[Bildirimler ve Türler](../c-language/declarations-and-types.md)