---
title: nothrow (C++) | Microsoft Docs
ms.custom: ''
ms.date: 01/03/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- nothrow_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 65b8a0420bc996812eed5996757e05d50aafc030
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023533"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Microsoft'a özgü**

A **__declspec** işlevlerin bildiriminde kullanılabilen genişletilmiş öznitelik.

## <a name="syntax"></a>Sözdizimi

> *dönüş türü* __declspec(nothrow) [*çağrı kuralı*] *işlevi adı* ([*bağımsız değişken listesi*])

## <a name="remarks"></a>Açıklamalar

Tüm yeni kod kullanmanızı öneririz [noexcept](noexcept-cpp.md) işleci yerine `__declspec(nothrow)`.

Bu öznitelik, derleyiciye bildirilen işlevlerin ve çağırdığı işlevlerin hiçbir zaman özel durum oluşturmayacağını bildirir. Ancak, yönergesi uygulamaz. Diğer bir deyişle, hiçbir zaman neden [std::terminate](../standard-library/exception-functions.md#terminate) çağrılacak, aksine `noexcept`, veya **Std: c ++ 17** modu (Visual Studio 2017 sürüm 15.5 ve üzeri), `throw()`.

Artık varsayılan olarak zaman uyumlu özel durum işleme modeliyle, derleyici böyle bir işlevde geriye doğru izlenemeyen nesnelerin kullanım süresini izleme mekaniklerini ortadan kaldırabilir ve kod boyutunu önemli ölçüde azaltabilir. Aşağıdaki önişlemci yönergesi dikkate alındığında, aşağıdaki üç işlev bildirimi denk **/Std: c ++ 14** modu:

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

İçinde **/Std: c ++ 17** modu `throw()` başkalarına kullanan eşdeğer değildir `__declspec(nothrow)` olur çünkü `std::terminate` işlevden bir özel durum oluşturulursa çağrılacak.

`void __stdcall f3() throw();` Bildirimi C++ standardı tarafından tanımlanan sözdizimini kullanır. C ++ 17'de `throw()` anahtar sözcüğü kullanım dışı.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[noexcept](noexcept-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)