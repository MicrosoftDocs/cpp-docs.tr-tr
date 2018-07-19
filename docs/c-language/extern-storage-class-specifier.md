---
title: extern depolama sınıfı tanımlayıcısı | Microsoft Docs
ms.custom: ''
ms.date: 07/10/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- extern keyword [C]
- storage class specifiers, extern
- extern keyword [C], storage class specifier
- external linkage, storage-class specifiers
- external linkage, extern modifier
ms.assetid: 6e16d927-291f-49e4-986c-9d91a482a441
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 365f4cf424ee51c493859e1d79f733b2cfcf331c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964190"
---
# <a name="extern-storage-class-specifier"></a>extern Depolama Sınıfı Tanımlayıcısı

Bildirilen bir değişken **extern** depolama sınıfı tanımlayıcısı başka bir kaynak dosyasında tanımlanmış aynı ada sahip bir değişken için bir başvurudur. Dış düzey değişken tanımını görünür yapmak için kullanılır. Olarak bildirilen bir değişken **extern** hiçbir kendisi için ayrılan depolama; yalnızca bir ad değildir. 
  
## <a name="example"></a>Örnek  
 Bu örnekte, iç ve dış düzeyi bildirimler gösterilmektedir:  
  
```c  

// Source1.c  

int i = 1;


// Source2. c

#include <stdio.h>  

// Refers to the i that is defined in Source1.c:   
extern int i;

void func(void);

int main()
{
    // Prints 1:   
    printf_s("%d\n", i);
    func();
    return;
}

void func(void)
{
    // Address of global i assigned to pointer variable:  
    static int *external_i = &i;

    // This definition of i hides the global i in Source.c:   
    int i = 16;

    // Prints 16, 1:  
    printf_s("%d\n%d\n", i, *external_i);
}
```  
  
 Bu örnekte, değişken `i` Source1.c içinde bir başlangıç değeri 1 ile tanımlanır. Bir **extern** Source2.c bildiriminde olan 'i' görünür bu dosyada yapar. 

 İçinde `func` işlevi, genel değişkenin adresi `i` başlatmak için kullanılan **statik** işaretçi değişkeninin `external_i`. Genel değişken olduğu için bu çalışır **statik** ömrü, yani program yürütme sırasında adresi değişmez. Ardından, bir değişken `i` kapsamında tanımlanan `func` başlangıç değeri 16 ile yerel bir değişken olarak. Bu tanım dış düzeyi değerini etkilemez `i`, yerel değişken için adı kullanılarak gizli. Genel değerini `i` artık yalnızca işaretçi erişilebilir `external_i`.   
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İç Düzey Bildirimleri Depolama Sınıfı Tanımlayıcıları](../c-language/storage-class-specifiers-for-internal-level-declarations.md)