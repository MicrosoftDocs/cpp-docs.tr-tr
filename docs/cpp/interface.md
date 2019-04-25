---
title: __interface
ms.date: 11/04/2016
f1_keywords:
- __interface_cpp
helpviewer_keywords:
- __interface keyword [C++]
ms.assetid: ca5d400b-d6d8-4ba2-89af-73f67e5ec056
ms.openlocfilehash: 1ec3a1d2cddbf8dbbb248a7366d5d56dd95ad074
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166301"
---
# <a name="interface"></a>__interface

**Microsoft'a özgü**

Visual C++ arabirimi aşağıdaki gibi tanımlanabilir:

- Sıfır veya daha fazla temel Ara birimden devralınabilir.

- Bir temel sınıfından devralamaz.

- Yalnızca genel, saf sanal yöntemler içerebilir.

- Oluşturucular, Yıkıcılar veya işleçler içeremez.

- Statik yöntemler içeremez.

- Veri üyeleri içeremez; özelliklere izin verilir.

## <a name="syntax"></a>Sözdizimi

```
modifier __interface interface-name {interface-definition};
```

## <a name="remarks"></a>Açıklamalar

A C++ [sınıfı](../cpp/class-cpp.md) veya [yapı](../cpp/struct-cpp.md) bu kurallar ile uygulanabilir ancak **__interface** bunları zorlar.

Örneğin, aşağıdaki örnek bir arabirim tanımı şöyledir:

```cpp
__interface IMyInterface {
   HRESULT CommitX();
   HRESULT get_X(BSTR* pbstrName);
};
```

Yönetilen arabirimleri hakkında daha fazla bilgi için bkz. [arabirim sınıfı](../extensions/interface-class-cpp-component-extensions.md).

Açıkça belirtmek gerekmez bildirimi `CommitX` ve `get_X` işlevleri saf sanal. İlk işlev için eşdeğer bir bildirim olacaktır:

```cpp
virtual HRESULT CommitX() = 0;
```

**__interface** gelir [novtable](../cpp/novtable.md) **__declspec** değiştiricisi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir arabirimde bildirilen özelliklerinin nasıl kullanılacağını gösterir.

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Arabirim Öznitelikleri](../windows/attributes/interface-attributes.md)