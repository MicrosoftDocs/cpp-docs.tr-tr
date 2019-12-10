---
title: Derleyici Uyarısı (düzey 4) C4706
ms.date: 11/04/2016
f1_keywords:
- C4706
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
ms.openlocfilehash: 2ff8794dcf29539b492f53bfdf6f0810988c0f72
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74989911"
---
# <a name="compiler-warning-level-4-c4706"></a>Derleyici Uyarısı (düzey 4) C4706

Koşullu ifade içinde atama

Koşullu ifadedeki test değeri bir atamanın sonucudur.

Atama, bir test ifadesi dahil olmak üzere başka bir ifadede uygulanabilir bir değere (atamanın sol tarafındaki değer) sahiptir.

Aşağıdaki örnek C4706 oluşturur:

```cpp
// C4706a.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( a  = b ) // C4706
   {
   }
}
```

Bu uyarı, test koşulunun etrafındaki ayraçları çift kullansanız bile oluşur:

```cpp
// C4706b.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( ( a  =  b ) ) // C4706
   {
   }
}
```

Amaç bir ilişkiyi test etmek ve bir atamayı yapmak için `==` işlecini kullanın. Örneğin, aşağıdaki satır a ve b 'nin eşit olup olmadığını sınar:

```cpp
// C4706c.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( a == b )
   {
   }
}
```

Test değerinizi bir atamanın sonucu yapmak istiyorsanız, atamanın sıfır dışında veya null olmadığından emin olun. Örneğin, aşağıdaki kod bu uyarıyı oluşturmaz:

```cpp
// C4706d.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( ( a = b ) != 0 )
   {
   }
}
```
