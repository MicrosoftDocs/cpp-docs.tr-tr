---
title: "extern depolama sınıfı tanımlayıcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- extern keyword [C]
- storage class specifiers, extern
- extern keyword [C], storage class specifier
- external linkage, storage-class specifiers
- external linkage, extern modifier
ms.assetid: 6e16d927-291f-49e4-986c-9d91a482a441
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0f11789f985c67b59b076bed7ec849a864688743
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="extern-storage-class-specifier"></a>extern Depolama Sınıfı Tanımlayıcısı
`extern` depolama sınıfı belirticisiyle bildirilen bir değişken, programın kaynak dosyalarından birinde dış düzeyde tanımlanmış aynı ada sahip bir değişkene yönelik başvurudur. İç `extern` bildirimi, dış düzey değişken tanımını blok içinde görünür hale getirmek için kullanılır. Dış düzeyinde aksi bildirilmediği sürece, `extern` anahtar sözcüğü ile bildirilen bir değişken yalnızca bildirildiği blok içinde görülebilir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, iç ve dış düzeyi bildirimler gösterilmektedir:  
  
```  
// extern_StorageClassSpecified.c  
#include <stdio.h>  
  
void other( void );  
  
int main()  
{  
    // Reference to i, defined below:   
    extern int i;  
  
    // Initial value is zero; a is visible only within main:   
    static int a;  
  
    // b is stored in a register, if possible:   
    register int b = 0;  
  
    // Default storage class is auto:   
    int c = 0;  
  
    // Values printed are 1, 0, 0, 0:   
    printf_s( "%d\n%d\n%d\n%d\n", i, a, b, c );  
    other();  
    return;  
}  
  
int i = 1;  
  
void other( void )  
{  
    // Address of global i assigned to pointer variable:  
    static int *external_i = &i;  
  
    // i is redefined; global i no longer visible:   
    int i = 16;  
  
    // This a is visible only within the other function:   
    static int a = 2;  
  
    a += 2;  
    // Values printed are 16, 4, and 1:  
    printf_s( "%d\n%d\n%d\n", i, a, *external_i );  
}  
```  
  
 Bu örnekte, `i` değişkeni, dış düzeyde başlangıç değeri 1 ile tanımlanmıştır. `extern` işlevindeki bir `main` bildirimi, dış düzeyi `i` için bir başvuru bildirmek üzere kullanılmıştır. **Statik** değişkeni `a` Başlatıcı atlanmış beri 0 olarak varsayılan olarak başlatılır. `printf` çağrısı 1, 0, 0 ve 0 değerlerini yazdırır.  
  
 İçinde `other` işlevi, genel değişkeni adresi `i` başlatmak için kullanılan **statik** işaretçi değişkeninin `external_i`. Genel değişkeni olduğundan bu çalışır **statik** yaşam süresi, adresini, program yürütme sırasında değişmez anlamına gelir. Ardından, `i` değişkeni, başlangıç değeri 16 ile yerel bir değişken olarak tekrar tanımlanır. Bu tekrar tanımlama işlemi, yerel değişken için adı kullanılarak gizlenen dış düzey `i` değerini etkilemez. Genel `i` değerine şimdi `external_i` işaretçisi aracılığıyla bu blok içinde yalnızca dolaylı olarak erişilebilir. Adresini atanırken **otomatik** değişkeni `i` blok girilir her zaman farklı olabilir bu yana bir işaretçi, çalışmaz. Değişkeni `a` olarak bildirilen bir **statik** değişken ve 2 başlatılmış. Bu `a` ile çakışmayan `a` içinde `main`, bu yana **statik** iç düzeyinde değişkenleri yalnızca blokta görünür, bunlar bildirilir içinde.  
  
 `a` değişkeni 2 arttırılarak 4 sonucunu verir. `other` işlevi aynı programda yeniden çağırılırsa, `a` öğesinin başlangıç değeri 4 olur. İç **statik** değişkenleri tutmak değerlerine program çıkar ve blok reenters zaman içinde bunlar bildirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İç düzey bildirimleri depolama sınıfı tanımlayıcıları](../c-language/storage-class-specifiers-for-internal-level-declarations.md)