---
title: Derleyici Uyarısı (düzey 1) C4715
ms.date: 11/04/2016
f1_keywords:
- C4715
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
ms.openlocfilehash: 268a26f5de1bb7f757a8e7cba6d3f5e6ddff882e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052474"
---
# <a name="compiler-warning-level-1-c4715"></a>Derleyici Uyarısı (düzey 1) C4715

' function ': tüm denetim yolları bir değer döndürmüyor

Belirtilen işlev, büyük olasılıkla bir değer döndüremez.

## <a name="example"></a>Örnek

```cpp
// C4715a.cpp
// compile with: /W1 /LD
int func1( int i )
{
   if( i )
   return 3;  // C4715 warning, nothing returned if i == 0
}
```

Bu uyarıyı engellemek için, tüm yolların işleve bir dönüş değeri atamasını sağlayacak şekilde kodu değiştirin:

```cpp
// C4715b.cpp
// compile with: /LD
int func1( int i )
{
   if( i ) return 3;
   else return 0;     // OK, always returns a value
}
```

Aşağıdaki örnekte olduğu gibi, kodunuzun hiçbir şekilde döndürdüğü bir işleve çağrı içermesi olasıdır:

```cpp
// C4715c.cpp
// compile with: /W1 /LD
void fatal()
{
}
int glue()
{
   if(0)
      return 1;
   else if(0)
      return 0;
   else
      fatal();   // C4715
}
```

Bu kod ayrıca bir uyarı oluşturur, çünkü derleyici `fatal` hiçbir şekilde dönmediğini bilmez. Bu kodun bir hata mesajı oluşturmasını engellemek için [__declspec (noreturn)](../../cpp/noreturn.md)kullanarak `fatal` bildirin.