---
title: nothrow (C++)
ms.date: 01/03/2018
f1_keywords:
- nothrow_cpp
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
ms.openlocfilehash: 8ce0e9ea6a39ef7760c7a6d0802913326433cf68
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227276"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Microsoft'a Özgü**

**`__declspec`** İşlevlerin bildiriminde kullanılabilen genişletilmiş bir öznitelik.

## <a name="syntax"></a>Sözdizimi

> *dönüş türü* __declspec (nothrow) [*Call-Convention*] *işlev-adı* ([*Argument-List*])

## <a name="remarks"></a>Açıklamalar

Tüm yeni kodların yerine [noexcept](noexcept-cpp.md) işlecini kullanmasını öneririz `__declspec(nothrow)` .

Bu öznitelik, derleyiciye bildirilen işlevlerin ve çağırdığı işlevlerin hiçbir zaman özel durum oluşturmayacağını bildirir. Ancak, yönergesini zorlamaz. Diğer bir deyişle, bu, std: [: Terminate](../standard-library/exception-functions.md#terminate) 'nin aksine, **`noexcept`** std: **C++ 17** modunun (Visual Studio 2017 sürüm 15,5 ve üzeri), ya da içinde çağrılmasına neden olmaz `throw()` .

Artık varsayılan olarak zaman uyumlu özel durum işleme modeliyle, derleyici böyle bir işlevde geriye doğru izlenemeyen nesnelerin kullanım süresini izleme mekaniklerini ortadan kaldırabilir ve kod boyutunu önemli ölçüde azaltabilir. Aşağıdaki Önişlemci yönergesi verildiğinde, **/std: c++ 14** modunda aşağıdaki üç işlev bildirimi eşdeğerdir:

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

**/Std: c++ 17** modunda, `throw()` `__declspec(nothrow)` `std::terminate` işlevinden bir özel durum oluşturulursa, çağrılmasına neden olduğu için, kullanan diğerlerine eşdeğer değildir.

`void __stdcall f3() throw();`Bildirim, C++ standardı tarafından tanımlanan sözdizimini kullanır. C++ 17 ' de `throw()` anahtar sözcük kullanım dışı bırakılmıştır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[noexcept](noexcept-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
