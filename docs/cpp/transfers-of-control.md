---
title: Denetim Taşıma
ms.date: 11/04/2016
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
ms.openlocfilehash: c9a46ccb1cf519080c5105855e41ecd3ebc23f77
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188057"
---
# <a name="transfers-of-control"></a>Denetim Taşıma

Bir başlatıcı geçmiş bir program belirtmek için bir **Switch** deyimindeki **goto** ifadesini veya **Case** etiketini kullanabilirsiniz. Bu kod, başlatıcıyı içeren bildirim, sıçrama ifadesinin gerçekleştiği bloğa ait bir blokta değilse geçersizdir.

Aşağıdaki örnek, `total`, `ch`ve `i`nesneleri bildiren ve Başlatan bir döngüyü gösterir. Ayrıca, denetimi bir başlatıcıyı geçen hatalı bir **goto** bildirisi de vardır.

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

Önceki örnekte, **goto** ifadesinin `i`başlatmayı geçmiş denetimi aktarmaya çalışır. Ancak, `i` bildirilirse ancak başlatılmamışsa, aktarım yasal olur.

**While** ifadesinin bir *ifadesidir* olarak işlev gören blokta belirtilen `total` ve `ch`nesneleri, bu blok **Break** ifadesini kullanarak çıkıldığında yok edilir.
