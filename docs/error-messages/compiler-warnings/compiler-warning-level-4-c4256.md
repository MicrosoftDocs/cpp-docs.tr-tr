---
title: Derleyici Uyarısı (düzey 4) C4256
ms.date: 11/04/2016
f1_keywords:
- C4256
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
ms.openlocfilehash: 3e8a3ab1b11c719730016e6a0cd248770cd89af8
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447779"
---
# <a name="compiler-warning-level-4-c4256"></a>Derleyici Uyarısı (düzey 4) C4256

'function': sanal tabanları olan sınıfın oluşturucusunda '...'; sahip çağrılar eski Visual C++ sürümleriyle uyumlu olmayabilir

Olası uyumsuzluğu.

Aşağıdaki kod örneği göz önünde bulundurun. Varsa S2::S2 Oluşturucu tanımı (int i,...) Microsoft sürümünü kullanarak derlenmiş C++ derleyici önce sürüm 7, ancak aşağıdaki örnek, geçerli sürümü kullanılarak derlendiğinde, S3 için oluşturucu çağrısı düzgün çalışmaz bir özel durum çağırma kuralı değişikliği nedeniyle. Hem de Visual C++ 6.0 kullanılarak derlendi ise, hiçbir parametre için üç nokta geçirilen sürece çağrı oldukça sağa ya da, çalışmıyordu.

Bu uyarıyı düzeltmek için

1. Bir oluşturucuda üç nokta kullanmayın.

1. Kendi projedeki tüm bileşenleri (tanımlayın veya başvuru bu sınıfı kitaplıkları dahil) geçerli sürümüyle oluşturulmuş ve ardından uyarı kullanarak devre dışı olduğundan emin olun [uyarı](../../preprocessor/warning.md) pragması.

Aşağıdaki örnek, C4256 oluşturur:

```
// C4256.cpp
// compile with: /W4
// #pragma warning(disable : 4256)
struct S1
{
};

struct S2: virtual public S1
{
   S2( int i, ... )    // C4256
   {
      i = 0;
   }
   /*
   // try the following line instead
   S2( int i)
   {
      i = 0;
   }
   */
};

void func1()
{
   S2 S3( 2, 1, 2 );   // C4256
   // try the following line instead
   // S2 S3( 2 );
}

int main()
{
}
```