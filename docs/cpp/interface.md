---
description: 'Hakkında daha fazla bilgi edinin: __interface'
title: __interface
ms.date: 05/07/2019
f1_keywords:
- __interface_cpp
helpviewer_keywords:
- __interface keyword [C++]
ms.assetid: ca5d400b-d6d8-4ba2-89af-73f67e5ec056
ms.openlocfilehash: 03ce2b6feb276ed90c3b8855b375a9240e061bba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291993"
---
# <a name="__interface"></a>__interface

**Microsoft'a Özgü**

Microsoft C++ arabirimi şu şekilde tanımlanabilir:

- , Sıfır veya daha fazla taban arabiriminden devralınabilir.

- Temel sınıftan devralma yapılamaz.

- Yalnızca genel, saf sanal yöntemlere sahip olabilir.

- Oluşturucular, Yıkıcılar veya işleçler içeremez.

- Statik yöntemler içeremez.

- Veri üyeleri içeremez; özelliklere izin verilir.

## <a name="syntax"></a>Syntax

```
modifier __interface interface-name {interface-definition};
```

## <a name="remarks"></a>Açıklamalar

C++ [sınıfı](../cpp/class-cpp.md) veya [yapısı](../cpp/struct-cpp.md) bu kurallarla uygulanabilir, ancak **`__interface`** bunları uygular.

Örneğin, aşağıdaki örnek bir arabirim tanımıdır:

```cpp
__interface IMyInterface {
   HRESULT CommitX();
   HRESULT get_X(BSTR* pbstrName);
};
```

Yönetilen arabirimler hakkında daha fazla bilgi için bkz. [interface class](../extensions/interface-class-cpp-component-extensions.md).

`CommitX`Ve işlevlerinin saf sanal olduğunu açıkça belirtmeniz gerekmediğine dikkat edin `get_X` . İlk işlev için eşdeğer bir bildirim şöyle olacaktır:

```cpp
virtual HRESULT CommitX() = 0;
```

**`__interface`**[novtable](../cpp/novtable.md) **`__declspec`** değiştiricisini gösterir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir arabirimde tanımlanan özelliklerin nasıl kullanılacağını gösterir.

```cpp
// deriv_interface.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <string.h>
#include <comdef.h>
#include <stdio.h>

[module(name="test")];

[ object, uuid("00000000-0000-0000-0000-000000000001"), library_block ]
__interface IFace {
   [ id(0) ] int int_data;
   [ id(5) ] BSTR bstr_data;
};

[ coclass, uuid("00000000-0000-0000-0000-000000000002") ]
class MyClass : public IFace {
private:
    int m_i;
    BSTR m_bstr;

public:
    MyClass()
    {
        m_i = 0;
        m_bstr = 0;
    }

    ~MyClass()
    {
        if (m_bstr)
            ::SysFreeString(m_bstr);
    }

    int get_int_data()
    {
        return m_i;
    }

    void put_int_data(int _i)
    {
        m_i = _i;
    }

    BSTR get_bstr_data()
    {
        BSTR bstr = ::SysAllocString(m_bstr);
        return bstr;
    }

    void put_bstr_data(BSTR bstr)
    {
        if (m_bstr)
            ::SysFreeString(m_bstr);
        m_bstr = ::SysAllocString(bstr);
    }
};

int main()
{
    _bstr_t bstr("Testing");
    CoInitialize(NULL);
    CComObject<MyClass>* p;
    CComObject<MyClass>::CreateInstance(&p);
    p->int_data = 100;
    printf_s("p->int_data = %d\n", p->int_data);
    p->bstr_data = bstr;
    printf_s("bstr_data = %S\n", p->bstr_data);
}
```

```Output
p->int_data = 100
bstr_data = Testing
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[Arabirim öznitelikleri](../windows/attributes/interface-attributes.md)
