---
description: 'Daha fazla bilgi edinin: denetim aktarımları'
title: Denetim Taşıma
ms.date: 11/04/2016
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
ms.openlocfilehash: 263c30877100ec37768313fa64e7562a06096396
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161617"
---
# <a name="transfers-of-control"></a>Denetim Taşıma

Bir **`goto`** **`case`** **`switch`** başlatıcıyı geçen bir programı belirtmek için, ifadesini veya bir deyimindeki bir etiketi kullanabilirsiniz. Bu kod, başlatıcıyı içeren bildirim, sıçrama ifadesinin gerçekleştiği bloğa ait bir blokta değilse geçersizdir.

Aşağıdaki örnek, ve nesnelerini bildiren ve Başlatan bir döngüyü gösterir `total` `ch` `i` . Ayrıca, **`goto`** denetimi bir başlatıcıyı geçen bir hatalı ifade da vardır.

```cpp
// transfers_of_control.cpp
// compile with: /W1
// Read input until a nonnumeric character is entered.
int main()
{
   char MyArray[5] = {'2','2','a','c'};
   int i = 0;
   while( 1 )
   {
      int total = 0;

      char ch = MyArray[i++];

      if ( ch >= '0' && ch <= '9' )
      {
         goto Label1;

         int i = ch - '0';
      Label1:
         total += i;   // C4700: transfers past initialization of i.
      } // i would be destroyed here if  goto error were not present
   else
      // Break statement transfers control out of loop,
      //  destroying total and ch.
      break;
   }
}
```

Önceki örnekte,, ' **`goto`** nin başlatılmasından sonra Denetim aktarmaya çalışır `i` . Ancak, `i` bildirilirse, ancak başlatılmamışsa, aktarım geçerli olur.

`total` `ch`  **`while`** Bir blok deyimleri kullanılarak çıkış yapıldığında, ve deyimin açıklaması olarak işlev gören blok içinde belirtilen nesneler yok edilir **`break`** .
