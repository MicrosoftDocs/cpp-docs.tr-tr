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
ms.openlocfilehash: 69a706577cf112c3d8a3b7748f72679f7213936d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="nothrow-c"></a>nothrow (C++)

**Microsoft özel**

İşlevlerin bildiriminde kullanılabilen `__declspec` genişletilmiş özniteliği.

## <a name="syntax"></a>Sözdizimi  
  
> *dönüş türü* __declspec(nothrow) [*arama kuralı*] *işlev adı* ([*bağımsız değişken listesi*])

## <a name="remarks"></a>Açıklamalar

Tüm yeni kod kullanmanızı öneririz [noexcept](noexcept-cpp.md) işleci yerine `__declspec(nothrow)`.

Bu öznitelik, derleyiciye bildirilen işlevlerin ve çağırdığı işlevlerin hiçbir zaman özel durum oluşturmayacağını bildirir. Ancak, yönergesi uygulamaz. Diğer bir deyişle, hiçbir zaman neden [std::terminate](../standard-library/exception-functions.md#terminate) çağrılacak, aksine `noexcept`, veya **std:c ++ 17** mod (Visual Studio 2017 15,5 ve sonraki sürümleri), `throw()`.

Artık varsayılan olarak zaman uyumlu özel durum işleme modeliyle, derleyici böyle bir işlevde geriye doğru izlenemeyen nesnelerin kullanım süresini izleme mekaniklerini ortadan kaldırabilir ve kod boyutunu önemli ölçüde azaltabilir. Aşağıdaki önişlemci yönergesi verildiğinde, aşağıdaki üç işlev bildirimleri de eşdeğer **/Std: c ++ 14** modu:

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

İçinde **/Std: c ++ 17** modu, `throw()` başkalarına kullanan eşdeğer olmayan `__declspec(nothrow)` neden olduğundan `std::terminate` işlevinden bir özel durum olursa çağrılacak.

`void __stdcall f3() throw();` Bildirimi C++ Standart tarafından tanımlanan sözdizimini kullanır. C ++ 17 içinde `throw()` anahtar sözcük kullanım dışı.

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)  
[noexcept](noexcept-cpp.md)  
[Anahtar Sözcükler](../cpp/keywords-cpp.md)  
