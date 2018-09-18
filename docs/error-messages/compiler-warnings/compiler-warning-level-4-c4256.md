---
title: Derleyici Uyarısı (düzey 4) C4256 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4256
dev_langs:
- C++
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6112a541f4bc7efc0ab36feb14f285cf132b08e8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075377"
---
# <a name="compiler-warning-level-4-c4256"></a>Derleyici Uyarısı (düzey 4) C4256

'function': sanal tabanları olan sınıfın oluşturucusunda '...'; sahip çağrılar eski Visual C++ sürümleriyle uyumlu olmayabilir

Olası uyumsuzluğu.

Aşağıdaki kod örneği göz önünde bulundurun. Varsa S2::S2 Oluşturucu tanımı (int i,...) Visual C++ derleyicinin sürüm 7, önce bir sürümü kullanılarak derlendi ancak aşağıdaki örnek geçerli sürüm kullanarak derlenmiş, S3 için oluşturucu çağrısı nedeniyle doğru şekilde çalışmaz bir özel durum çağırma kuralı değiştirin. Hem de Visual C++ 6.0 kullanılarak derlendi ise, hiçbir parametre için üç nokta geçirilen sürece çağrı oldukça sağa ya da, çalışmıyordu.

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