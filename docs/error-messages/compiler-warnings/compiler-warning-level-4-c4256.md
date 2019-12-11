---
title: Derleyici Uyarısı (düzey 4) C4256
ms.date: 11/04/2016
f1_keywords:
- C4256
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
ms.openlocfilehash: 1ec3e64548cead53cea906cdf2abd3dd25ee06d4
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991390"
---
# <a name="compiler-warning-level-4-c4256"></a>Derleyici Uyarısı (düzey 4) C4256

' function ': sanal tabanlara sahip sınıf için Oluşturucu '... ' içeriyor. çağrılar, Visual 'ın eski sürümleriyle uyumlu olmayabilirC++

Olası uyumsuzluk.

Aşağıdaki kod örneğini inceleyin. S2:: S2 (int i,...) oluşturucusunun tanımı, Microsoft C++ derleyicisinin sürümü 7 ' den önceki bir sürümü kullanılarak derlenmişse, ancak aşağıdaki örnek geçerli sürüm kullanılarak derlenmişse, özel durum çağırma kuralı değişikliği nedeniyle S3 için oluşturucuya yapılan çağrı düzgün çalışmaz. Her ikisi de Visual C++ 6,0 kullanılarak derlenmişse, üç nokta için hiçbir parametre geçirilmediği müddetçe çağrı tam olarak doğru çalışmaz.

Bu uyarıyı onarmak için

1. Bir oluşturucuda üç nokta kullanmayın.

1. Projesindeki tüm bileşenlerin geçerli sürümle oluşturulduğundan emin olun (Bu sınıfa tanımlayabiliriz veya başvuruda bulunan kitaplıklar dahil) ve [Uyarı](../../preprocessor/warning.md) pragmasını kullanarak uyarıyı devre dışı bırakın.

Aşağıdaki örnek C4256 oluşturur:

```cpp
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
