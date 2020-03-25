---
title: __interface
ms.date: 05/07/2019
f1_keywords:
- __interface_cpp
helpviewer_keywords:
- __interface keyword [C++]
ms.assetid: ca5d400b-d6d8-4ba2-89af-73f67e5ec056
ms.openlocfilehash: 9b265dcbaca9f8fa836795cca990804371813647
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178217"
---
# <a name="__interface"></a>__interface

**Microsoft 'a özgü**

Bir Microsoft C++ arabirimi aşağıdaki gibi tanımlanabilir:

- , Sıfır veya daha fazla taban arabiriminden devralınabilir.

- Temel sınıftan devralma yapılamaz.

- Yalnızca genel, saf sanal yöntemlere sahip olabilir.

- Oluşturucular, Yıkıcılar veya işleçler içeremez.

- Statik yöntemler içeremez.

- Veri üyeleri içeremez; özelliklere izin verilir.

## <a name="syntax"></a>Sözdizimi

```
modifier __interface interface-name {interface-definition};
```

## <a name="remarks"></a>Açıklamalar

Bu C++ kurallarla bir [sınıf](../cpp/class-cpp.md) veya [Yapı](../cpp/struct-cpp.md) uygulanabilir, ancak **__interface** uygular.

Örneğin, aşağıdaki örnek bir arabirim tanımıdır:

```cpp
__interface IMyInterface {
   HRESULT CommitX();
   HRESULT get_X(BSTR* pbstrName);
};
```

Yönetilen arabirimler hakkında daha fazla bilgi için bkz. [interface class](../extensions/interface-class-cpp-component-extensions.md).

`CommitX` ve `get_X` işlevlerinin saf sanal olduğunu açıkça belirtmeniz gerekmediğine dikkat edin. İlk işlev için eşdeğer bir bildirim şöyle olacaktır:

```cpp
virtual HRESULT CommitX() = 0;
```

**__interface** [novtable](../cpp/novtable.md) **__declspec** değiştiricisini gerektirir.

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

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Arabirim Öznitelikleri](../windows/attributes/interface-attributes.md)
