---
title: Derleyici Hatası C3803 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3803
dev_langs:
- C++
helpviewer_keywords:
- C3803
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a841dbaae4142e92d8e0987b0618285e4f71f60
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075873"
---
# <a name="compiler-error-c3803"></a>Derleyici Hatası C3803

'property': özelliği, 'erişimcisinin' erişimcilerini biri ile uyumlu bir türe sahip

İle tanımlanmış bir özelliğin türünü [özelliği](../../cpp/property-cpp.md) bir erişimci işlevleri için dönüş türü ile eşleşmiyor.

Aşağıdaki örnek, C3803 oluşturur:

```
// C3803.cpp
struct A
{
   __declspec(property(get=GetIt)) int i;
   char GetIt()
   {
      return 0;
   }

   /*
   // try the following definition instead
   int GetIt()
   {
      return 0;
   }
   */
}; // C3803

int main()
{
}
```