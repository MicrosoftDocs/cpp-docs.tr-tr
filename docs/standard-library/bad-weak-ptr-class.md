---
title: bad_weak_ptr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::bad_weak_ptr
dev_langs:
- C++
helpviewer_keywords:
- bad_weak_ptr
- bad_weak_ptr class
ms.assetid: a09336d5-7237-4480-ab6b-3787e0e6025e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7fcd0309321ce841a739d24d037a24f81a9551f1
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725514"
---
# <a name="badweakptr-class"></a>bad_weak_ptr Sınıfı

Bozuk weak_ptr özel durumunu raporlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class bad_weak_ptr : public std::exception
{
public:
    bad_weak_ptr();
    const char *what() throw();
};
```

## <a name="remarks"></a>Açıklamalar

Öğesinden oluşturulan bir özel durum sınıfı tanımlar [shared_ptr sınıfı](../standard-library/shared-ptr-class.md) türünde bir bağımsız değişken alan oluşturucu [weak_ptr sınıfı](../standard-library/weak-ptr-class.md). Üye işlevi `what` döndürür `"bad_weak_ptr"`.

## <a name="example"></a>Örnek

```cpp
// std__memory__bad_weak_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int);
        wp = sp;
    }

    try
    {
        std::shared_ptr<int> sp1(wp); // weak_ptr has expired
    }
    catch (const std::bad_weak_ptr&)
    {
        std::cout << "bad weak pointer" << std::endl;
    }
    catch (...)
    {
        std::cout << "unknown exception" << std::endl;
    }

    return (0);
}
```

```Output
bad weak pointer
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[weak_ptr Sınıfı](../standard-library/weak-ptr-class.md)<br/>
