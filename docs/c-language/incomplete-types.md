---
description: 'Hakkında daha fazla bilgi edinin: tamamlanmamış türler'
title: Eksik Türler
ms.date: 11/04/2016
helpviewer_keywords:
- void keyword [C], incomplete
- types [C], incomplete
- incomplete types
- unions, incomplete
- arrays [C], incomplete types
- void keyword [C]
- structures, incomplete
ms.assetid: 01bc0cf6-9fa7-458c-9371-ecbe54ea6aee
ms.openlocfilehash: b85d7a703d6687ad7ec1b0476b8b8a43930330dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243581"
---
# <a name="incomplete-types"></a>Eksik Türler

*Tamamlanmamış tür* , tanımlayıcıyı tanımlayan, ancak tanımlayıcının boyutunu belirlemekte gerekli bilgiler bulunmayan bir türdür. Tamamlanmamış bir tür şu olabilir:

- Üyelerini belirtmediğiniz bir yapı türü.

- Üyelerini belirtmediğiniz bir birleşim türü.

- Boyutlarını belirtmediğiniz bir dizi türü.

**`void`** Tür, tamamlanamayacak tamamlanmamış bir tür. Eksik bir türü tamamlamak için eksik bilgileri belirtin. Aşağıdaki örnekler, eksik türlerin nasıl oluşturulduğunu ve tamamlandığını gösterir.

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

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve türler](../c-language/declarations-and-types.md)
