---
description: 'Daha fazla bilgi edinin: TypeName'
title: typename
ms.date: 11/04/2016
f1_keywords:
- typename_cpp
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
ms.openlocfilehash: 3bc1385412d23d947c75967c2dc79bee78bbcd28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145801"
---
# <a name="typename"></a>typename

Şablon tanımlarında, derleyiciye bilinmeyen bir tanımlayıcının bir tür olduğunu belirten bir ipucu sağlar. Şablon parametresi listelerinde, bir tür parametresi belirtmek için kullanılır.

## <a name="syntax"></a>Syntax

```
typename identifier;
```

## <a name="remarks"></a>Açıklamalar

Şablon tanımındaki bir ad, şablon bağımsız değişkenine bağımlı nitelikli bir ad ise bu anahtar sözcük kullanılmalıdır; nitelikli ad bağımlı değilse, bu isteğe bağlıdır. Daha fazla bilgi için bkz. [Şablonlar ve ad çözümlemesi](../cpp/templates-and-name-resolution.md).

**`typename`** herhangi bir tür tarafından, bir şablon bildiriminde veya tanımında herhangi bir yerde kullanılabilir. Şablon temel sınıfın şablon bağımsız değişkeni olarak kullanılmadığı sürece temel sınıf listesinde izin verilmez.

```cpp
template <class T>
class C1 : typename T::InnerType // Error - typename not allowed.
{};
template <class T>
class C2 : A<typename T::InnerType>  // typename OK.
{};
```

**`typename`** Anahtar sözcüğü, şablon parametresi listelerinde yerine de kullanılabilir **`class`** . Örneğin, aşağıdaki deyimler anlamsal olarak eşdeğerdir:

```cpp
template<class T1, class T2>...
template<typename T1, typename T2>...
```

## <a name="example"></a>Örnek

```cpp
// typename.cpp
template<class T> class X
{
   typename T::Y m_y;   // treat Y as a type
};

int main()
{
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Şablonlar](../cpp/templates-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
