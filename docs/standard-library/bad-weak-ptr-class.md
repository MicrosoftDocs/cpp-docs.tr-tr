---
description: 'Hakkında daha fazla bilgi edinin: bad_weak_ptr sınıfı'
title: bad_weak_ptr Sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::bad_weak_ptr
helpviewer_keywords:
- bad_weak_ptr
- bad_weak_ptr class
ms.assetid: a09336d5-7237-4480-ab6b-3787e0e6025e
ms.openlocfilehash: db74ed31ff92f7665e8ecde5fc4700bcdf1a7fc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312923"
---
# <a name="bad_weak_ptr-class"></a>bad_weak_ptr Sınıfı

Bozuk weak_ptr özel durumunu raporlar.

## <a name="syntax"></a>Syntax

```cpp
class bad_weak_ptr : public std::exception
{
    bad_weak_ptr();
    const char *what() throw();
};
```

## <a name="remarks"></a>Açıklamalar

Sınıfı, [Weak_ptr sınıfının](../standard-library/weak-ptr-class.md)türünde bir bağımsız değişken alan [shared_ptr sınıf](../standard-library/shared-ptr-class.md) oluşturucusundan oluşturulabilecek bir özel durumu açıklar. Üye işlevi `what` döndürür `"bad_weak_ptr"` .

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

## <a name="see-also"></a>Ayrıca bkz.

[weak_ptr sınıfı](../standard-library/weak-ptr-class.md)
