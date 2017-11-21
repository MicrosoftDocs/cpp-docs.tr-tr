---
title: "İşlev çağrıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls, about function calls
- function calls
ms.assetid: 2cfa897d-3874-4820-933c-e624f75d1712
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3f04acfe9458b8a10142ef7bc12155bc8e2a9a52
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="function-calls"></a>işlev Çağrıları
A *işlev çağrısı* denetim ve bağımsız değişkenler (varsa) bir işleve aktardığı ifade olan ve biçime sahiptir:  
  
 *ifade* (*ifade listesinde*opt)  
  
 Burada *ifade* işlev adı veya bir işlev adresi değerlendirir ve *ifade listesi* (virgülle ayrılmış) ifade listesini içerir. Bu ikinci ifadelerin değerleri, işleve geçirilen bağımsız değişkenlerdir. İşlev bir değer döndürmüyor sonra döndüren bir işlev olmasını bildirme `void`.  
  
 Bir bildirim önce işlev çağrısı var, ancak parametreler hiçbir bilgi verilir, bildirilmemiş herhangi bir bağımsız değişken yalnızca olağan aritmetik dönüştürmeler geçer.  
  
> [!NOTE]
>  Başka bir bağımsız değişkende değerleri yan etkileri tarafından değiştirilemez bağımsız değişken değerleri tanımsız şekilde işlevi bağımsız değişken listesi ifadelerinde herhangi bir sırada değerlendirilebilir. İşlev çağırma işleci tarafından tanımlanan bir dizi noktası, yalnızca denetim çağrılan işlev geçirmeden önce tüm yan etkileri bağımsız değişken listesinde değerlendirilir güvence altına alır. (Bağımsız değişkenler bir yığında gönderilen sipariş ayrı sağlasa da olduğunu unutmayın.) Bkz: [sıralama noktaları](../c-language/c-sequence-points.md) daha fazla bilgi için.  
  
 Yalnızca hiçbir işlev çağrısında ifadesi parantez önce bir işlev adresi değerlendirilmelidir gereksinimdir. Başka bir deyişle, bir işlev herhangi bir işlev işaretçisi ifade çağrılabilir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte çağrılır işlev çağrılarını gösterilmektedir bir `switch` deyimi:  
  
```  
int main()  
{  
    /* Function prototypes */  
  
    long lift( int ), step( int ), drop( int );  
    void work( int number, long (*function)(int i) );  
  
    int select, count;  
    .  
    .  
    .  
    select = 1;  
    switch( select )   
    {  
        case 1: work( count, lift );  
                break;  
  
        case 2: work( count, step );  
                break;  
  
        case 3: work( count, drop );  
                /* Fall through to next case */  
        default:  
                break;  
    }  
}  
  
/* Function definition */  
  
void work( int number, long (*function)(int i) )  
{  
    int i;  
    long j;  
  
    for ( i = j = 0; i < number; i++ )  
            j += ( *function )( i );  
}  
```  
  
 Bu örnekte, bir işlevi çağırmak `main`,  
  
```  
work( count, lift );  
```  
  
 bir tamsayı değişken geçirir `count`, işlev adresi `lift` işlevine `work`. İşlev adresi işlevi tanımlayıcı bir işaretçi ifadesi değerlendirildiğinden yalnızca işlevi tanımlayıcı vererek geçirilir unutmayın. Bu şekilde işlevi tanımlayıcı kullanmak için işlevi bildirilen veya gerekir tanımlayıcı kullanılmadan önce tanımlanan; Aksi takdirde kimliği tanınmıyor. Bu durumda prototipini içinde `work` başında verilen `main` işlevi.  
  
 Parametre `function` içinde `work` bir alan bir işlev işaretçisi olarak bildirilen `int` bağımsız değişkeni ve döndüren bir **uzun** değeri. Parametre adı parantezler gereklidir; bunları bir işaretçi döndüren bir işlev bildirimi belirtirsiniz bir **uzun** değeri.  
  
 İşlev `work` içinde seçilen işlevinden çağırır **için** aşağıdaki işlev çağrısı kullanarak döngü:  
  
```  
( *function )( i );  
```  
  
 Tek bir bağımsız değişken `i`, çağrılan işlev geçirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../c-language/functions-c.md)