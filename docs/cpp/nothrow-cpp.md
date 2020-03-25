---
title: nothrow (C++)
ms.date: 01/03/2018
f1_keywords:
- nothrow_cpp
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
ms.openlocfilehash: 8164f47190267627bdaf7c7ee2f03f22f65c8f50
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161067"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Microsoft 'a özgü**

İşlevlerin bildiriminde kullanılabilen bir genişletilmiş **__declspec** özniteliği.

## <a name="syntax"></a>Sözdizimi

> *dönüş türü* __declspec (nothrow) [*Call-Convention*] *işlev-adı* ([*Argument-List*])

## <a name="remarks"></a>Açıklamalar

Tüm yeni kodların `__declspec(nothrow)`yerine [noexcept](noexcept-cpp.md) işlecini kullanmasını öneririz.

Bu öznitelik, derleyiciye bildirilen işlevlerin ve çağırdığı işlevlerin hiçbir zaman özel durum oluşturmayacağını bildirir. Ancak, yönergesini zorlamaz. Diğer bir deyişle, `noexcept`veya **std: c++ 17** modunda (Visual Studio 2017 sürüm 15,5 ve üzeri), `throw()`farklı olarak [std:: Terminate](../standard-library/exception-functions.md#terminate) çağrılmasına neden olmaz.

Artık varsayılan olarak zaman uyumlu özel durum işleme modeliyle, derleyici böyle bir işlevde geriye doğru izlenemeyen nesnelerin kullanım süresini izleme mekaniklerini ortadan kaldırabilir ve kod boyutunu önemli ölçüde azaltabilir. Aşağıdaki Önişlemci yönergesi verildiğinde, **/std: c++ 14** modunda aşağıdaki üç işlev bildirimi eşdeğerdir:

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

**/Std: c++ 17** modunda `throw()`, işlevden bir özel durum oluşturulursa `std::terminate` çağırmasına neden olduğu için `__declspec(nothrow)` kullanan diğer kişilerle eşdeğer değildir.

`void __stdcall f3() throw();` bildirimi, C++ standart tarafından tanımlanan sözdizimini kullanır. C++ 17 ' de `throw()` anahtar sözcüğü kullanım dışıdır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[noexcept](noexcept-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
